# Transcrição local — aprendizados

Notas para reutilização em qualquer projeto onde precise transcrever vídeo/áudio
sem chamar APIs (privacidade, custo, offline).

## Decisão final

**Stack:** `ffmpeg` + NVIDIA NeMo + Parakeet TDT 0.6B v3 + PyTorch CUDA, em
Python 3.11 no Windows.

Porquê esta combinação:

- **Parakeet TDT 0.6B v3** é multilingue (suporta PT-BR/PT-PT), pequeno
  (~600M params, ~2.4 GB) e rápido em GPU consumidora. Para PT especificamente,
  ganha de Whisper-medium em qualidade e é 5–10× mais rápido em GPU.
- **NeMo** é o framework oficial — `from_pretrained("nvidia/parakeet-tdt-0.6b-v3")`
  é uma linha. Faz cache local em `~/.cache/torch/NeMo/`.
- **ffmpeg** para extrair WAV mono 16 kHz pcm_s16le (formato esperado do modelo).
- **GPU NVIDIA com ≥6 GB VRAM** é o ponto-doce. CPU é inviável para vídeos
  longos (hora+).

## Como fazer (recipe)

1. Pré-requisitos:
   - `ffmpeg` no PATH (`winget install Gyan.FFmpeg`).
   - Python 3.10+.
   - Driver NVIDIA recente + CUDA toolkit compatível.
   - PyTorch com a build CUDA correta — instalar **antes** do NeMo:
     `pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu124`
   - Depois: `pip install "nemo_toolkit[asr]>=2.4.0"`.

2. Pipeline mínimo por ficheiro:
   - `ffmpeg -i input.mp4 -vn -ac 1 -ar 16000 -c:a pcm_s16le out.wav`
   - `model = nemo_asr.models.ASRModel.from_pretrained("nvidia/parakeet-tdt-0.6b-v3")`
   - Para áudios longos: `model.change_attention_model("rel_pos_local_attn", att_context_size=[256, 256])`
   - `hyp = model.transcribe([wav_path], timestamps=True)[0]`
   - `text = hyp.text`; timestamps em `hyp.timestamp["word"]` (lista de
     `{word, start, end}`) → agrupar em blocos para gerar `.srt`.

3. Output: `.txt` (corrido) e/ou `.srt` (com timestamps a nível palavra
   agrupados em blocos legíveis: até ~84 chars ou ~5 s por bloco).

## O que funcionou bem

- **Cachear o WAV** numa pasta separada (`transcripts/.wav_cache/`) — permite
  re-transcrever sem reprocessar com ffmpeg.
- **Skip se o `.txt` já existe** (com `--force` para forçar) — torna o script
  reiniciável.
- **Atenção local (`rel_pos_local_attn`, [256, 256])** é a flag mágica para
  caber em GPU pequena com áudio longo. Sem ela, vídeos de >10 min estouram
  qualquer VRAM realista.
- **Carregar o modelo uma vez** e iterar sobre vários ficheiros — o
  warm-up custa caro (~30 s só de carregar pesos).
- **Timestamps a nível palavra são gratuitos** com Parakeet — basta passar
  `timestamps=True`. O modelo ainda devolve com decoder TDT, sem inferência extra.

## O que não funcionou (e como contornar)

### 1. Segfault no `pyarrow` ao importar NeMo no Windows

Sintoma: o processo morre com `Windows fatal exception: access violation`,
exit code 139, com stack trace passando por
`pyarrow/__init__.py` ou `pyarrow/dataset.py`. `python -c "import pyarrow"`
isolado funciona; mas dentro do NeMo (que carrega `transformers` →
`sklearn` → `pandas` → `pyarrow`, ou `datasets` → `pyarrow.dataset`) crasha.

Causa: conflito de DLLs (provavelmente OpenMP/MKL/oneDNN duplicados) — a
ordem de carga de DLLs depende de quem é importado primeiro.

Fix: **pré-importar `pyarrow` no topo do script**, antes de qualquer import
pesado:

```python
import pyarrow  # noqa: F401
import pyarrow.dataset  # noqa: F401
# … resto dos imports só depois
```

Isso força o `pyarrow` a carregar as suas DLLs cedo, antes do torch as substituir.

### 2. CUDA OOM em GPU de 8 GB com áudio longo

Sintoma: `torch.OutOfMemoryError: Tried to allocate 19.55 GiB. GPU 0 has a
total capacity of 8.00 GiB`. Acontece com Parakeet em modo full self-attention
em ficheiros >10 min.

**Recomendação prática:** começar pela opção 1. Se ainda estourar, juntar 1+3
(long-form + FP16). Ir para chunking manual (opção 2) apenas para vídeos de
4h+ ou GPU de 4 GB.

#### Alternativas, por ordem de simplicidade

**1. Atenção local (a opção que usámos aqui)**

```python
model.change_attention_model("rel_pos_local_attn", att_context_size=[256, 256])
```

O modelo faz "chunking" interno via janelas locais. Zero perda de contexto
entre chunks (cada token vê os 256 anteriores e seguintes), sem código de
merge. Pode degradar marginalmente em frases muito longas que cruzam janelas
— na prática quase imperceptível. Combinar com:

```bash
PYTORCH_CUDA_ALLOC_CONF=expandable_segments:True
```

para reduzir fragmentação de VRAM.

**2. Chunking manual com ffmpeg**

Útil quando 1 não chega ou quando se quer paralelizar entre GPUs:

```bash
ffmpeg -i in.wav -f segment -segment_time 300 -c copy chunk_%03d.wav
```

Notas:

- 5 min (300 s) é seguro para 8 GB com Parakeet em full attention.
- **Cortar exato parte palavras a meio.** Soluções:
  - Sobrepor 2–3 s entre chunks (`-segment_time 300 -segment_overlap 3`,
    ou cortar com `-ss`/`-to` manualmente) e dedup das primeiras/últimas
    palavras no merge (compare últimos N tokens do chunk anterior com
    primeiros N do seguinte).
  - **Cortar em silêncios** com `silencedetect` — sem perda de palavras,
    melhor qualidade:
    ```bash
    ffmpeg -i in.wav -af silencedetect=n=-30dB:d=0.5 -f null - 2>&1 \
      | grep silence_end
    ```
    Usar essas timestamps como pontos de corte para os chunks.
- Para `.srt`, **somar offset** (`chunk_index * 300 s`, ou o `start` real do
  chunk) a todos os timestamps de palavra do chunk antes de concatenar.
- Para `.txt`, basta concatenar com espaço/quebra de linha entre chunks.

**3. Reduzir precisão (FP16)**

```python
model = model.half()  # FP32 -> FP16
```

Corta VRAM ~40%. Parakeet TDT é estável em FP16 (treinado em mixed precision).
Combinado com atenção local cabe áudio de horas em 8 GB. Pode usar bfloat16
em GPUs Ampere+ se houver problemas de overflow.

**4. Trocar de modelo para um mais leve**

- **`faster-whisper`** (CTranslate2) com `compute_type="int8_float16"` em
  modelo `medium` ou `large-v3` — usa ~3 GB VRAM, internamente já faz
  chunking de 30 s com VAD (Silero). Para PT fica ligeiramente atrás do
  Parakeet em qualidade, mas resolve tudo numa linha:
  ```python
  from faster_whisper import WhisperModel
  m = WhisperModel("large-v3", device="cuda", compute_type="int8_float16")
  segments, _ = m.transcribe("in.wav", language="pt", vad_filter=True)
  ```
  Sem dependência de NeMo/HuggingFace datasets/pyarrow — instalação muito
  mais simples e robusta no Windows.
- **`whisper.cpp`** com modelo quantizado (Q5_0/Q4_0) — corre em CPU
  decentemente ou em GPU pequena. Sem dependências Python.

**5. CPU offloading**

Mover parte do modelo para CPU com `accelerate`:

```python
from accelerate import dispatch_model, infer_auto_device_map
device_map = infer_auto_device_map(model, max_memory={0: "6GB", "cpu": "32GB"})
model = dispatch_model(model, device_map=device_map)
```

Lento (decoder em CPU é gargalo), mas funciona em qualquer máquina. Último
recurso.

### 3. Aviso `Full CUDA graph compilation failed: cudaErrorInsufficientDriver`

Não-fatal. Driver mais antigo do que o que o NeMo TDT prefere. O modelo
faz fallback para CUDA graphs nativas — funciona, fica ~10–20% mais lento.
Não vale a pena atualizar driver só por isto.

### 4. Output em buffer mascara o ponto do crash

Sintoma: o script crasha cedo mas só vês as primeiras linhas porque
`print()` está em buffer.

Fix: correr com `PYTHONUNBUFFERED=1 python -X faulthandler ...`. O
`-X faulthandler` imprime o stack trace mesmo em segfaults nativos —
indispensável para diagnosticar crashes em código C de bibliotecas (pyarrow,
torch, etc).

### 5. `PermissionError: [WinError 32]` em ficheiros temp

Quando o script crasha a meio, o NeMo deixa lockfiles em
`%LOCALAPPDATA%\Temp\tmp*\manifest.json`. Reinícios subsequentes podem
queixar-se. Limpar manualmente ou ignorar — costuma resolver-se sozinho.

## Quando escolher outra coisa

- **Sem GPU** ou GPU com <4 GB VRAM: `faster-whisper` (CTranslate2) é mais
  leve. Aceita CPU razoavelmente bem com modelo `small` ou `medium`. Não
  precisa de pyarrow/datasets — instala-se com um único `pip install`.
- **Línguas exóticas / muitas línguas**: Whisper large-v3. Pior em PT do
  que Parakeet, melhor em cobertura linguística.
- **Diarização (quem fala quando)**: Parakeet/Whisper sozinhos não fazem.
  Combinar com `pyannote.audio` ou `whisperx`.
- **Tempo real / streaming**: Parakeet RNNT-CTC ou um modelo Conformer-CTC
  com decoder streaming.

## Tempos reais nesta máquina (RTX 4060 8 GB)

5 vídeos PT-BR, ~575 MB total, durações somadas ~2h:
- Carregamento do modelo: ~30 s (primeira vez baixa pesos, depois cache).
- Extração WAV (ffmpeg): ~5 s por vídeo.
- Transcrição com `--long-form`: ~1× tempo real ou um pouco melhor (RTF≈0.8–1.0).
- Total end-to-end: ~10–15 min para 2h de vídeo.

Se o RTF (real-time factor) ficar >2, suspeitar de:
- Atenção local **desligada** (volta a OOM ou swap CPU/GPU).
- CUDA graph fallback (já incluído acima — pequeno).
- Driver/torch sem CUDA — verificar `torch.cuda.is_available()`.

## Estrutura mínima recomendada

```
projeto/
├── videos/                   # input (.mp4, .mkv, .mov, .wav, .mp3 …)
├── transcripts/              # output
│   └── .wav_cache/           # WAV intermédios (cache; gitignore)
├── scripts/
│   └── transcribe_videos_parakeet.py
└── requirements-transcription.txt
```

`requirements-transcription.txt`:

```
nemo_toolkit[asr]>=2.4.0
```

(PyTorch com CUDA instalado **antes**, fora deste requirements, com o
`--index-url` certo.)
