# Masterclass — Git & GitHub (02/05/2026)

## A ideia da masterclass

Eu vou ter um conteúdo estruturadinho aqui que eu gerei no **Claude**, mas queria fazer no estilo do que a gente fez no **Cloudflare**: tenho certeza que nem todos os tópicos estão na cabeça de vocês, vai ter coisa que vocês conhecem e usam, mas mesmo nesses pontos é legal escutar a experiência de quem usa **Git** no dia a dia. Como o Marcelo já comentou aí da **branch**: como vocês estão usando **branch** no dia a dia? Quando chegar, não deixem de compartilhar — nossa famosa inteligência coletiva.

## Por que usar Git (e não usar pasta)

Vamos lá do básico: por que usar **Git** e não usar o versionamento em pasta, aquele famoso versionamento de TCC? Não é aquele nosso `appline_v1`, `V2`, `V_final`, `V_agora_vai`. Mas é bom falar disso, porque quando eu comecei com **IA** eu só programava com **Bubble**: ia fazendo, copiando a pasta, e eu não sabia mexer no **Git**. 5 anos de **Bubble** e não sabia mexer no **Git**. Ficam aí as obviedades que precisam ser ditas.

E hoje, por causa dos riscos da **IA**, isso ficou ainda mais importante. Dependendo do harness — pra pegar o termo da moda — e do jeito que a gente pede, a ferramenta vai alterar mais coisas do que uma **IDE** ou uma **CLI**, porque ela não tem um contexto tão bom. Então o **Git** acaba sendo realmente obrigatório por uma questão de segurança.

## Git vs GitHub

Quando eu falo **Git**, não necessariamente é **GitHub**, embora eles estejam totalmente aninhados na nossa cabeça. Vamos a um exemplo: estou na **branch** `main` e vou criar um arquivo novo. Esse carinha aqui não está no **GitHub**, ele está só no **Git** de fato — que é só a tecnologia que faz a diferenciação de arquivos. Eu salvo o arquivo na **branch** e comito essa diferença.

Agora, se eu trocar de **branch**, esse arquivo não está no **GitHub**, está só local. Vou criar uma nova **branch**, peço pra essa **branch** ficar com a versão nova do arquivo e comito também. Então tenho duas versões: na `main` e na branch `nova`. Se eu volto pra `main`, o arquivo está com o conteúdo da `main`. Volto pra `nova`, está com o conteúdo `nova`.

O que permite fazer isso? Essa tecnologia do **Git**, não do **GitHub**. Vocês viram que eu não fiz nenhum push, nada — está só local. Então mesmo sem criar um repositório online, quando você começa a desenvolver no computador, já ative o **Git**: isso já te dá segurança, já te permite voltar no tempo pro commit inicial, voltar pra branch inicial, sem alterar de fato o arquivo.

Como é que a **IDE** consegue ler que o arquivo na branch nova tem outro conteúdo? Por aquela pastinha oculta que fica ali, a `.git`. Toda vez que a gente inicializa um **Git** numa pasta, vem essa pastinha — ela é a magia.

## Conceitos base: repositório, commit, branch, merge

- **Repositório**: o nosso projeto, via de regra a nossa pasta no computador, que vira um repositório lá no **GitHub**.
- **Commit**: esses checkpoints, esses retratos que a gente faz de cada ponto. Na timeline, cada commit aparece como um checkpoint — clicando num commit, vejo tudo que mudou e os arquivos no estado daquele momento.
- **Branch**: as ramificações que a gente faz do projeto — e, como vimos, só com o **Git** já funciona.
- **Merge**: quando juntamos duas branches de forma segura. O próprio **Git** faz a diferenciação entre branches; se houver conflito, ele acusa e pede pra gente resolver.

## Comandos do dia a dia (add, commit, push, pull)

Quando abro o terminal na `main`, não tem nada pra ser comitado. Altero o arquivo: ele já apresenta uma mudança. Clicando na **IDE**, dá pra ver exatamente o que foi alterado — isso é muito útil no **vibe coding**. Sempre que faço uma alteração mais crítica e não levei muita fé no que a **IA** fez, eu venho aqui e olho. Visualmente é fácil: a linha vermelhinha é o que saiu, a verdinha é o que entrou.

Outro exemplo clássico: você pede pra **IA** alterar algo, ela diz "vou debugar" e faz uma cagada, tipo inserir uma chave de **API** hardcoded. Você vê, vira pra ela e ela volta atrás.

Como a **IA** escreve código muito mais rápido do que a gente lê, o mínimo que a gente pode fazer é vir nos arquivos-chave e passar o olho. Quando o projeto está bem estruturado, são ajustes finos: o verdinho aparece destacado na barra de rolagem, você vai lá embaixo, vê o que é. A maioria do código hoje em dia é legível pra humano: você bate o olho, "ah, ele tá declarando uma variável, fazendo uma açãozinha", segue.

> **Manuel:** Tem uma coisa legal nas IDEs que não tem no terminal: aquele `+` e `-` na lateral, mostrando quantas linhas adicionou e quantas tirou. Dá uma ideia do tamanho da alteração.

> **Felipe:** Boa. É no chatzinho do próprio agente. Quando vejo que ficou muito grande, vou lá olhar.

Não tô pedindo muito de vocês — não estou dizendo "aprenda o código do projeto desde o zero". É aquele negócio: a maioria da minha geração aprendeu inglês de tanto jogar **GTA** e ver "game over" na tela. Código é a mesma coisa. De tanto a gente ver código na nossa tela, a gente aprende.

## Stage e adição granular

Voltando ao `git add`: fiz uma alteração visualmente na branchezinha do **Git** ali. O `git add` pega da nossa "área de mudanças" e leva pro stage, que é a área pronta pra comitar. O fluxo do dia a dia é `git add`, `git commit` e `git push` (e o `git pull` que vamos ver depois).

`git add .` significa "adiciona tudo que eu alterei". Mas se alterei muita coisa ao mesmo tempo — abriu três, quatro chats no **Cursor**, quatro sessões do **Claude Code**, quatro do **Gemini** —, é importante saber separar. Se aquilo é uma feature nova e dá pra ver pelos nomes dos arquivos ou pela visualização em árvore, eu pego e adiciono só esses dois. Tanto via terminal (mas não precisa ser psicopata pra escrever cada arquivo) quanto pela visualização da **IDE**, dá pra adicionar/tirar arquivo a arquivo.

Depois eu preciso comitar de fato. Posso escrever a mensagem na mão ou clicar no "**gerar com IA**" — eu uso muito esse aqui. Ou, se eu tentar comitar sem escrever nada, ele abre o editor de texto pra eu escrever a mensagem.

## Push e pull

`push` envia pro repositório na nuvem; `pull` busca alterações de lá. Trabalhando sozinho, na maioria das vezes, não dá problema; em equipe, tem que sempre cuidar e conversar. O hábito é chegar e apertar no botão de refresh quando está sincronizado com o **GitHub**.

No projeto **Sublima** aqui, ó: tem duas alterações pendentes. Aparece um indicador `0 / 2` — o primeiro número são alterações pendentes de puxar do **GitHub**, o segundo são alterações locais pra subir. Em uma branch só, sempre tem que estar sincronizadinho.

## Instalação e configuração

Instalação: baixar o **Git** (`git-scm.com`) e criar uma conta no **GitHub**. São coisas separadas, mas que andam juntas. No Windows, instala o instalador.

Configuração inicial: às vezes a **IDE** se autentica com algum e-mail aleatório. Onde isso esbarra? Quando a gente faz um push e espera um deploy automático na **Vercel**, ela exige que o e-mail bata. Aconteceu de uma **IA** ter configurado um `filipe@email.com` falso e a **Vercel** bloquear o deploy.

Caso real: um parceiro fazendo um push apareceu como um usuário totalmente aleatório — provavelmente a **IA** estava treinada com aquele user e configurou o **Git** local com ele. Não é porque eu coloco o e-mail de outro no `git config` que eu vou ter acesso aos repositórios dele — o acesso vem da autenticação.

## Autenticação: SSH e Access Token

As **IDEs** facilitam muito quando a gente instala o **Git**: fazem um **OAuth2**, levam pro navegador, e dependendo da configuração do **GitHub** você faz duas ou três autenticações. Existem duas formas principais:

### SSH

É uma chave que você cria no computador e cola lá no **GitHub** (Settings → SSH keys → New). Sempre que acessar por essa máquina, não precisa se autenticar de novo — já está autenticado, já tem a chave.

> **Igor:** O SSH seria o mais seguro? Tipo a Vercel teve aquele vazamento — se eu tivesse SSH eu deletava a chave, criava outra, subia e estava seguro de novo?

> **Felipe:** O **SSH** está vinculado à máquina. Quando eu crio um SSH eu colo a chave gerada localmente lá no **GitHub** em "New SSH key". É diferente das chaves de **API**.

### Access Token

A chave geral do perfil. Cuidados: não saia usando em todo lugar, especialmente em mais de um projeto, porque é a chave do perfil. Na hora de criar, dá pra limitar a repositórios específicos:

- **Owner**: você (ou a organização).
- **Expiration**: a melhor prática é por uma data de expiração (30/90/365 dias). Eu sempre uso `Never`, mas o ideal é rotacionar.
- **Repositories**: `All` ou `Only select` — escolha só os que precisam.

Caso de uso típico: chamar a **API** do **GitHub** num **N8N** pra fazer commit em paralelo, por exemplo. Em geral, no dia a dia o **CLI** ou a integração resolvem.

> **Renato:** A Vercel, quando a gente conecta o GitHub, ela gera um token dela?

> **Felipe:** Por baixo dos panos é isso. Nas configurações de Applications no **GitHub** dá pra ver os apps conectados (Vercel, Cloudflare, etc.) — se vazou, você revoga e conecta de novo.

## Repositórios públicos vs privados

Via de regra, nossos projetos serão privados. Os puristas da segurança dizem "se seu app é seguro, dá pra deixar público", mas eu não recomendo. Pra compartilhar com alguém, ou o repo é público (qualquer um abre, faz pull request, etc.) ou eu adiciono colaborador num repo privado.

Já peguei caso de pessoa expondo banco de dados, chaves, dados de migração num repo público "porque queria que o fulano visse". Não. Coloca como colaborador. Tem robô fazendo crawling no **GitHub** dia e noite, todo minuto. Repositório público com chave vazada? É questão de segundos. O **Claude Code** ficou alguns minutos vulnerável e já vazou.

## Monorepo vs polirrepo

Decisão particular, sem certo ou errado. No meu **Sublima Builder** eu tenho vários sites num único repo — facilitou pro meu sócio, que abre e mexe em qualquer um. Contra: build do projeto inteiro a cada alteração. Se você está na **Vercel** e o build demora 3 minutos, está pagando esses 3 minutos.

Já no **Trincheira Links** e similares, cada mini app é um repo. Pra **SAS** sério, via de regra é repositório isolado, privado, com colaboradores sob demanda.

## Aprendendo de repositórios públicos

Cara, repos públicos open source servem pra: copiar, estudar, se inspirar (cuidando licenças). Vamos pensar em ferramentas:

- **DeepWiki** (`deepwiki.com`): cole um link de repositório público e ele indexa tudo. Pergunta: "Tem integração com WhatsApp?" → "Sim, via WhatsApp Business, Twilio, Cloud API e 360Dialog". Ele traz inclusive os arquivos envolvidos.
- **GitNexus** (`gitnexus.io` ou similar): faz uma árvore visual de dependências, marca o que cada arquivo usa. Tem MCP pra evitar alucinação da **IA** quando ela vai mexer.

Outro padrão útil: forks. Faz dois meses que forquei o **OpenSquad**: `Sync update` e ele atualiza com o original (ele estava 149 commits atrás). Maior utilidade do fork é essa: rastrear o original e atualizar fácil. Limitação: fork não vira privado — se você quer privado, copia e cola num repo novo.

## .gitignore

Tudo que está no `.gitignore` é ignorado pelo **Git**. Vou ignorar uma pasta `.temp/`: crio a pasta, ela já fica sombreada, e arquivos dentro não aparecem no changes. Crio um `secret.txt` na raiz: aparece. Movo pro `.temp/`: some. Simples assim.

Casos típicos:
- Variáveis de ambiente (`.env`).
- Pasta `node_modules/` — gigantesca, gerada pelo `npm install`.
- Wildcards tipo `*.mp4` (mídias pesadas — **GitHub** não é lugar de guardar vídeo/foto).
- Pastas de agentes (`.cursor/`, `.claude/`) — depende: às vezes você quer compartilhar.

E **chaves** — sempre. O **GitHub** tem templates de `.gitignore` por linguagem (Next.js, Node, etc.), bom ponto de partida.

## Branches e flows

Se vocês forem desorganizados como eu nos projetos pessoais, vão trabalhar com **uma branch só**: commit, commit, commit, push, commit, commit, push.

### Fluxo simples (feature branch)

`main` intacta. Pra cada feature: abre uma branch, trabalha nela, faz pull request, mergeia na `main`. Cuidado: não abrir feature em cima de feature na mesma área do código, senão dá conflito no merge.

### Git Flow (mais granular)

- `main` ou `master` em produção.
- `dev` em homologação.
- Features partem da `dev`.
- `hotfix` parte direto da `main` quando precisa de ajuste rápido.

Bubble usa esse modelo (Live, Test, Development). Mais complexo, mas é o controle de versões mais granular. Cuidado: feature isolada por muito tempo enquanto a `dev` evoluiu vira pesadelo no merge — quase reescrever do zero.

## Status, diff e leitura visual

`git status` confirma a branch atual e o que está alterado. Cuidado clássico: estou comitando na branch errada. Já vi caso de eu querer atualizar uma coisinha na `main`, vir afoito e mandar `git commit -a` num conjunto de alterações que era de outra feature em andamento. **Bagunça pronta**.

Pra **IA**: peça "atualiza essa branch onde estou trabalhando". Normalmente ela levanta a bola de "tem alteração local que não faz parte daqui, o que faz?" e sugere `stash`, `cherry-pick`, etc. A **IA** faz isso muito bem, mas é bom a gente ter noção do que está acontecendo.

## Múltiplas contas Git

> **Igor:** Eu ajudo amigos com projetos deles e fico trocando login no terminal. Tem como deixar mais de uma conta?

> **Felipe:** Tem, mas é chatinho. Eu tenho duas: minha pessoal (`@ffmenezes`) e a **SemCodar** (`@felipesemcodar`). Configurei localmente: quando o projeto for da SemCodar, considera o user da SemCodar. Fiz isso com auxílio da **IA**.

Mas, no teu caso, recomendaria diferente: peça pros amigos te adicionarem como **colaborador** no repo. Daí você usa só sua conta. Inclusive pra fins de auditoria, é melhor: você sempre vê quem comitou cada coisa.

> **Igor:** Tinha esquecido. Vou fazer isso, porque login no terminal com aquele código que demora, mais a verificação da minha conta pessoal — eu rezo toda vez.

Outra opção: ter SSH liberado pras duas contas. Mas no cenário do Igor, colaborador é o caminho.

## Diffs e revisão de código com IA

Já bati nessa tecla várias vezes: a **IA** faz todo o trabalho sujo muito mais rápido e barato. A gente não vai se prestar a passar o olho? Aí dá merda e a gente não entende por quê. Use o **Git** pra isso.

## Ciclo padrão

`git status` → `git add` → `git commit` → `git push` → `git pull`. Eu faço push menos vezes do que commit: comito a cada feature, a cada ajuste, e empurro depois.

## Organizations

Quando estamos em uma **organization** do **GitHub**, conseguimos dar permissões granulares de leitura/escrita/edição em repositórios e até em ações específicas — coisa que num perfil pessoal não dá. Ex.: 10 repos na org, fulano lê todos mas só edita um.

> **Igor:** Tu consegue dar permissão só pra branch?

> **Felipe:** Acho que sim, eu já trabalhei dessa forma — branch por nome, eu comitava só nela, e uma branch envelopadora fazia o merge na main. Funciona no Bubble, então certamente tem no GitHub.

## Submódulos

Submódulo cria um **link pra outro repositório** dentro do seu. Não é cópia, é ponteiro.

Exemplo no **Sublima**: tenho 10 repositórios separados (Marketing, SAS, Site, etc.). Crio um repo `base` com tom de voz, dados da empresa, design system — coisas que todos precisam. O Marketing referencia o `base` como submódulo: vê o conteúdo, mas não edita; quando o `base` atualiza, automaticamente reflete.

> **Igor:** Vários repositórios um dentro do outro? É como atalho do Drive?

> **Felipe:** Basicamente. Eu tentei fazer no Google Drive — funciona ali, mas no **VS Code/Cursor** o atalho não é uma pasta, é um arquivo `.lnk`. Submódulo resolve isso — aparece liso na **IDE**.

Por que isso é interessante em tempos de **IA**? Eu quero criar o "cérebro da empresa": agente do marketing precisa do branding; agente comercial precisa do tom de voz. Submódulo permite que o agente Renata acesse o `base` mas não a pasta `infra` — separação por papel, seja humano ou **IA**. Combinação **organization + submódulos** é poderosa, e sem pagar nada no **GitHub**.

## Issues e Projects

`Issues` virou minha to-do list. WhatsApp como sistema de gestão nunca funcionou pra mim. Crio uma issue por ideia, demanda, mensagem — anexo zip, áudio, texto via voz, qualquer coisa.

`Projects` (gratuito): tabela estilo Notion, kanban, gráfico Gantt, gráficos. Puxa direto das issues. Marco issues como `In Progress`, `Done`, atribuo a pessoas. Dá pra automatizar: quando o commit referenciar a issue, marca como resolvida.

> **Renato:** É um ClickUp, só que dentro do Git.

## Bloqueio de deploy automático em conta secundária

> **Marcelo:** Tenho duas contas Git. Quando mando push pela conta errada, na Vercel aparece um "X" e bloqueia, eu tenho que subir outra alteração pra ela "pular".

> **Felipe:** O caso é: a Vercel tem que ter o usuário como colaborador também (e isso exige plano pago). Soluções: centralizar pushes em uma conta, ou na própria Vercel clicar em **Redeploy** num deploy seu, que ele personifica e resolve.

Cuidado também com builds em monorepo: um push pode disparar 5 deploys. Dá pra configurar **build watches** — só fazer o deploy se tiver alteração em pasta tal.

## GitHub Desktop

> **Igor:** Para começar, pode ser bem mais didático usar o **GitHub Desktop**. O botão de Fetch/Pull/Push é bem grande, é só a janela do GitHub.

> **Felipe:** Eu nunca usei, sempre fiz na **IDE** integrado. Mas, pra quem está aprendendo, é uma opção válida.

E nada impede abrir o mesmo projeto em duas **IDEs** (Cursor e Antigravity, por exemplo) — está tudo sincronizado pela `.git`.

## GitHub Pages

Tipo um Cloudflare Pages: cria página estática útil pra compartilhar coisa simples. O comparativo de **LLMs** que eu publiquei está aí. Dá pra colocar domínio customizado. Outro caso de uso: servir um CSV público, arquivos estáticos que você quer expor por link.

## GitHub Actions

"Sempre que acontecer X, faça Y". As mensagenzinhas de novo link no Discord do **Sublima** estão configuradas via Actions. Configura com um arquivo `.yml`:

```
on: push
steps:
  - send webhook
```

O webhook fica numa **variável de ambiente** (Settings → Secrets), não em texto plano.

> **Renato:** Por que nas stacks do N8N self-host a gente coloca direto, não com secret?

> **Felipe:** Lá é facilidade. Deveria usar `secrets` do Docker — cria no nível Docker, ou no Portainer, e referencia na stack. É chato porque você cria um bloco de secrets, faz a referência, aí na stack invoca, mas em ambiente profissional é o correto. Cenário: colaborador entra, sai dois meses depois — sem secrets, você tem que rotacionar tudo.

Outras ferramentas de cofre de chaves: **Doppler**, **HashiCorp Vault**, **Infisical**. Ao invés de string em texto plano, o app chama o cofre pela referência. Adiciona complexidade, mas tranquiliza quando se trabalha em equipe.

### Outros usos de Actions

- **Webhooks** de notificação (deploy falhou → WhatsApp).
- **Testes automatizados** antes do push.
- **Verificar chaves vazadas** com regex (padrões `sk_`, `eyJ`, UUID).
- **Builds remotos**: o **AI Workspace** faz build da imagem e manda pro **GHCR** (tipo Docker Hub) direto na infra do **GitHub**. Tira a carga da minha **VPS**. Dá até pra terceirizar build da Vercel pra cá.

> **Marcelo:** Tem limite gratuito?

> **Felipe:** 2000 minutos por mês. Se um build leva 8 min, dá uns 250 builds — uns 10 por dia. Não bati nesse limite ainda.

## Casos de uso interessantes

### Estudo

`star-history.com` mostra os repos mais quentes. **Build Awesome** lista projetos. Quer criar uma rede social? Tem blueprint. Space Invaders em C? Tem. **Awesome lists** (`awesome-claude-code`, `awesome-opencode`) seguem padrão "Awesome <ferramenta>" e listam casos de uso.

### Backup e versionamento

Para ferramentas sem versionamento próprio. **N8N**: cada fluxo é um JSON. Se eu não usar credentials (secrets), está em texto plano — atenção. Faço backup automático no **Git**.

### Cérebro da empresa

Documentação, design system, tom de voz — tudo no **GitHub** com submódulos. Acessível por humanos e **IAs**, com versionamento. Cuidado: limite de tamanho de arquivo é 50 MB, mídia vai pro storage.

### Portfólio

Repo `README` no perfil com links e referências. Repos públicos servem como currículo — meu perfil tem coisa de 2019, 2021 quando eu mexia com análise de dados em Jupyter Notebooks.

## Vazamento de credencial — e como remover do histórico

Comitei uma chave, fiz push. Apaguei e comitei de novo. Está limpo? **Não**. O commit anterior fica no histórico do **Git**. Mesmo revertendo, fica no log.

> **Renato:** Uma vez pedi pro Claude limpar o GitHub e deixar igual minhas pastas locais. Ele entendeu o contrário e apagou tudo. Minha sorte foi que tinha um deploy no Cloudflare Pages com os arquivos.

Cenários de risco:
1. Repo privado, só eu — risco mínimo (mas o **GitHub** já vazou; **Bitwarden** vazou; nada é 100%).
2. Repo privado com colaborador mal intencionado — ele vê o histórico todo.
3. Repo público mesmo que por 15 minutos — robôs indexam em segundos. Pior cenário, rotaciona tudo.

### Limpando

Pede pra **IA**: "remova esse arquivo de todo o histórico de commits, faça force push e atualize o `.gitignore`". Ela usa `git filter-repo` ou `filter-branch`, faz `force push`, reescreve o histórico. Resultado: o arquivo some das referências antigas.

Depois, pede pra ela vasculhar o repo procurando padrões de chave (`sk_`, `eyJ`, prefixos de Stripe, Supabase, OpenAI, etc.). Já fiz isso e achei chave vazada — não é casualidade. Caso típico: a **IA** cria um teste temporário, mete a chave do `.env` em texto plano no script pra "facilitar", comita e dá push. Pega no `.gitignore` os scripts de teste também.

## Aikido.dev e Dependabot

> **Igor:** Tem um site, **Aikido.dev**, gratuito, conecta no repo e acha falhas, variáveis expostas, dá insights. Bom principalmente quando o projeto começa no Lovable e migra.

> **Felipe:** Boa. Outro que uso muito: **Dependabot** do próprio **GitHub** — Settings → Advanced Security → ativar.

> **Igor:** Falando de segurança que não está nas nossas mãos: usar Next.js, sai uma falha, eles corrigem, mas você não atualizou. Se tiver Dependabot, ele resolve com pull request automático. Eu estava no Next 15 sem saber que existia o 17 — Dependabot mostrou várias falhas.

Use com parcimônia: aceita PR a PR. Nem só o framework principal, dependência de dependência. Ninguém audita o segundo nível — você importa `marked`, que importa `marked-mangle`; se esse for hackeado, ninguém viu. Por isso essas ferramentas com alerta automático são valiosas.

## Alternativas ao GitHub

- **GitLab**: alternativa mais próxima.
- **Google Cloud Source Repositories**: o Google tem o seu.
- **Bitbucket**, e os Git internos enterprise.

Quando vamos olhar pra eles? Quando o **GitHub** falir, ou quando o trabalho corporativo tiver Git próprio. Por baixo, todos rodam **Git**, mesmos comandos do Linus Torvalds.

## NPM/NPX e GitHub

> **Renato:** O squad que eu fiz, ele instala via `npx`. Como NPM se relaciona com Git?

> **Felipe:** Pensa no **N8N**: na stack você referencia `n8nio/n8n:latest` — isso é uma imagem no **Docker Hub**. Quando o N8N faz release no GitHub, uma Action builda a imagem e publica.

NPM é o mesmo conceito pra Node: registro de pacotes. Quando você roda `npx alguma-coisa`, o npm cata a versão do pacote nesse registro. O fluxo CI/CD no GitHub Actions faz `npm publish` e atualiza o registro.

> **Renato:** Mas eu posso fazer um instalador interativo sem publicar no NPM, certo?

> **Felipe:** Certo. O meu **Half-Loops** é assim: comando `half`, ele faz perguntas (qual IDE? prompt direto ou via arquivo?), você responde no terminal, ele cria os arquivos. Não precisa publicar — é só um script local. Pra instalar global pra todo mundo, aí publica no NPM via `npm publish`.

## Encerrando

Roteiro coberto: ciclo diário (`status` / `add` / `commit` / `push` / `pull`), branches e flows, organizations, submódulos, issues e projects, deploy automático e suas armadilhas, GitHub Pages, GitHub Actions, secrets, vazamento e limpeza de histórico, Dependabot e Aikido. Cobrimos também os usos não triviais — cérebro da empresa, backup de N8N, portfólio.

Como começar simples e ir avançando: faça o básico do ciclo diário, ative Dependabot, configure colaboradores em vez de trocar login, use `.gitignore` desde o primeiro commit, e use a **IA** pra limpar histórico se vazar credencial.

Bora vibe codar. Até daqui 15 dias.
