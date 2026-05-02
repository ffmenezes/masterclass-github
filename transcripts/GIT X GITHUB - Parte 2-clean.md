# GIT x GitHub — Parte 2

## Instalação

Então vambora. **Instalação**. Eu coloquei aqui os três OS mais comuns, né? Eu acho os únicos, mas vamos lá.

Para quem quiser seguir o manual, passo a passo de instalação certinho, vai na página do **Git** e lê a documentação. É muito importante isso. Eu vou só passar por cima aqui de como faz a instalação.

Mas basicamente, no **Windows**, você vai lá embaixo no site, você usa o **Git Bash** e boa. No **Linux** ele é praticamente nativo, então você dá o `sudo apt install git` e num passe de mágica o **Git** está instalado. E no **Mac** ele também é praticamente, ele já vem pré-instalado. Você dá esse `xcode-select --install`. Beleza?

Linux, instalando o **Git**. Até como é que eu uso essa merda.

## Configuração inicial do Git

Bom, vamos lá. A primeira coisa que você vai fazer é configurar o seu **Git**. Por quê? Você precisa... Lembra que a gente comentou ali pra usar com várias pessoas, você conseguir desenvolver um sistema com várias pessoas juntos. Então, o **Linus**, isso é uma maneira, ele pensou assim: eu preciso identificar quem é quem, quem tá fazendo a mudança, como tá fazendo essa mudança, e afim.

Então, você baixou o seu **Git**, no terminal — o meu já está configurado, mas dá pra gente entrar aqui pra brincar só pra vocês verem. Eu venho aqui e rodo literalmente este comando aqui: `git config` e aqui. E configuro aqui meu **Git** pra falar assim: o meu nome de usuário é esse aqui.

É uma boa prática, se você tá usando, usar o mesmo nome de usuário que você vai usar no **GitHub**, no **Heroku**, ou afins. Então, beleza.com. Vou fazer a mesma coisa para o meu email.

E isso aqui é legal. O **Git**, por padrão, quando a gente cria uma **branch** — e eu vou explicar mais pra frente como faz isso — mas ele cria o nome da sua **branch** como `master`, a `initial branch`. Isso é antigo, né? E por algumas questões raciais e afins, não se usa mais o nome `master` e se modificou para usar o nome `main`. Então você vem aqui e dá esse `global init default branch`.

Se você não adicionar essa configuração, ele não vai funcionar. Não, ele vai funcionar, só que o nome dessa **branch** vai ser `master`. Só isso que muda. E ele vai te dar um aviso falando que isso não é mais usado e que é bom você adicionar essa configuração. Tá bom?

Muda, posso colocar `default branch` batatinha? Cara, pode, mas lembre-se: se você não coda pra você, você escreve para que os outros possam ler. Então, seguir boas práticas é muito importante. Beleza.

## Conceito: pintando um quadro

Vamos entender o conceito disso aqui. Aqui é o seguinte. Imagina que você está trabalhando, ou você está pintando um quadro, tá? E é o seguinte, você vai pegar — e esse quadro você vai fazer, tipo, vai fazer como se fosse uma colagem, vai colocar várias folhas A4.

Então você vai lá e começa a pintar a folha 1. E isso aí vai estar na sua mesa, o que você tá vendo. Beleza? Aí tem a **staging area**. O que é isso? Eu vou guardar esse pedaço do quadro que eu fiz em um lugar pra meio que falar assim: olha, isso aqui tá praticamente pronto. Peguei isso, guardei nesse lugar. Vou lá, faço a próxima parte.

O **Git** não vai salvando automaticamente o que você vai fazendo. Você escolhe o que é importante salvar. Então, pô, quero salvar isso. Acho isso importante. Quero guardar essa versão que eu fiz. Eu vou lá e guardo nessa **staging area**.

Depois que eu guardei tudo, eu quero comitar. Eu quero fazer uma marcação da minha linha do tempo falando assim: pô, essa aqui é a minha versão 1. Aí eu vou pro cofre, pro álbum. Imagina aqui, eu coloquei como cofre, álbum, mas imagina pro quadro mesmo. Eu vou lá e colo isso no quadro e tiro uma foto do quadro do jeito que tá e guardo isso no álbum de fotos, assim. A foto do quadro do jeito que tá.

Basicamente ele vai funcionar nessas três etapas. Então eu vou lá, pego uma — imaginando a folha A4 — faço o meu primeiro desenho, guardo ele, colo ele no meu quadro branco gigante lá, colo esse primeiro desenho, tiro uma foto. Pego essa foto e guardo num álbum de colagem. Beleza?

Por que eu vou fazendo dessa forma? Aquela foto 1, eu fiz ela e na foto 2 ficou mais legal do que na foto 1. Eu consigo, tipo... na foto 1 ficou mais legal do que na foto 2. Então, mano, eu quero voltar pra minha foto anterior. Eu vou lá e volto. Naquele álbum de fotos lá, eu tenho a primeira foto guardada lá. Então eu consigo ir lá e voltar e guardar. Tipo, pegar aquilo que eu já fiz sem modificar, sem, tipo, ter que ficar dando Ctrl+Z, indo procurar o arquivo de versão 1, eu vou lá só olhar no álbum de fotos e dou o playback.

Espera aí que vocês vão entender isso um pouco melhor. Beleza.

## git init e git clone

Então vamos lá. Qual que é o comando para iniciar isso? Eu vou abrir meu terminal, e aí a gente vai fazer junto aqui para vocês entenderem.

Eu criei aqui uma pasta chamada `aulagit`. Beleza. Então vamos começar. Eu quero, a partir desse momento, eu quero que o **Git** preste atenção nesse **repositório**, nessa pasta, nesse diretório. Então eu vou aqui e vou dar um `git init`.

Ele deu esses hints aqui, que é aquilo que eu estava falando: usou o `master` as the name of the initial branch, ele criou como `master`, mas ele dá um hint falando que dá para você renomear o nome da **branch**, que não se usa mais e afim. Beleza.

Criei aqui, falei para o **Git**: a partir desse momento o **Git** está começando a prestar atenção no que está acontecendo aqui.

E tem outra maneira de você fazer isso. Eu quero dar um `git clone`. Já tem um **repositório** existente na internet, lá no **GitHub**. Eu vou lá e dou um `git clone`, trago aqueles arquivos lá da internet para dentro da minha máquina, para começar a versionar ele dentro da minha máquina. Beleza?

## Criando o primeiro arquivo

Beleza. Então vamos lá. Pô, vou abrir o **VS Code** aqui. Vamos começar a criar nossa calculadora aqui. Vem aqui. `calculator.py`. Vamos fazer aqui.

O que o **Copilot** fez aqui para nós? Beleza, vamos mudar aqui para `soma`. `subtração`. Beleza? Beleza, tá aqui. Eu não vou fazer as funções soma e subtração, não sei o quê, porque o que interessa pra gente é isso aqui.

Se vocês perceberem aqui, onde eu estou com o mouse em cima, tá aqui: `Desktop/aula de git/test.py` e um `package`. O que é um `package`? O **Git** viu que foi criado um novo arquivo. Ele prestou atenção que tem um novo arquivo que foi criado, mas ele não está controlando as versões desse arquivo. Ele sabe que tem um novo arquivo, mas ele não está versionando. Ele não está pegando e colando essas fotos no álbum.

## git status

Então como é que a gente vai fazer isso agora? Eu vou vir aqui no terminal, salvar esse cara aqui, vou vir aqui no terminal e eu vou rodar o comando mais importante que existe do **Git**: `git status`. Beleza.

Quando eu rodo o comando do `git status`, ele traz algumas informações pra gente. Ele traz a **branch** que eu tô, ou seja, a linha do tempo que eu tô. Ou vamos pensar assim, a página do meu álbum de fotos. Quais são os arquivos que ele tá enxergando? E qual que é o status desse arquivo?

Então, assim, ó, ele tá falando assim: eu tô enxergando o arquivo `teste.py`, porém, eu não tô trackeando o histórico desse arquivo ainda. Só tô enxergando ele aqui.

## git add

Pô, beleza. Como é que eu faço para o **Git** trackear esse arquivo? Bom, para o **Git** trackear esse arquivo, a gente tem duas maneiras de fazer.

Primeiro, uma maneira que é a maneira de preguiçoso, e aí é a seguinte: ela dá problema. Por que ela dá problema? Porque a partir do momento que eu rodar este comando aqui, ó, `git add .` (espaço) — se eu tiver mil arquivos aqui untracked, ele vai trackear todos de uma vez. Ele só vai simplesmente trackear todos esses arquivos de uma vez. Beleza.

Por que isso dá problema? Dependendo, tem alguns arquivos que a gente vai falar um pouquinho mais adiante, que a gente não quer que o **Git** versione ou que o **Git** conheça esses arquivos. Que são os arquivos `.env`, são os arquivos `.env`, os arquivos que eu vou guardar senha, os arquivos... esse tipo de arquivo, a gente não quer que o **Git** versione eles. Eles vão guardar informações sensíveis. Então é muito perigoso você só dar um `git add .`.

Então, normalmente o que a gente vai lá e vai fazer é seguir o passo a passo aqui, que é dar o `git add` e o nome do arquivo que eu quero que ele trackeie. `git add test.py`.

Depois que eu fiz isso, eu vou lá e verifico se ele trackeou mesmo. Então rodo de novo o `git status`. Quando eu rodar o `git status`, ele vai lá, ó: `Changes to be committed`. Você tem modificações em um arquivo que podem ser comitadas.

## git commit

O que é comitar? É adicionar a foto no seu álbum de fotos ou adicionar a sua marquinha na linha do tempo. Aqui eu guardei sua foto num canto, ele está trackeado, mas ele não foi comitado. Ainda bem que eu gerei a foto dele.

Então vamos lá. Vamos fazer ele gerar o **commit**. Ele colocar essa foto nesse meu álbum. `git commit -m` abre aspas. Primeiro **commit**.

Vamos entender esse comando. `git`, o sistema que eu estou usando. O que eu quero fazer? A flag. E a mensagem que eu quero colocar. Todo **commit** tem que ter uma mensagem. Se eu tentar dar um **commit** sem mensagem, ele vai me trazer um erro. Beleza?

Então, `git commit -m`. A partir desse momento, se eu rodar um `git status` de novo, ele comitou na **branch** `master`, ele criou um **commit**. Ele criou uma marquinha da linha do tempo. Guardou uma foto e afins. Primeiro, da hora.

## git log

Quero ver os **commits**. Se eu rodar um `git log` aqui, eu vou conseguir enxergar o autor, quem fez, e o **commit** que foi feito. A data, a hora, o ano e qual foi a alteração, qual que é a mensagem de **commit** que ele deixou pra mim.

Beleza? Da hora!
