# GIT x GitHub — Parte 5

## Conectando o repositório local ao GitHub

Eu tô aqui no meu **repositório** local, tá? Ele não tá na internet ainda e eu quero levar ele pro **GitHub**. Então eu vou dar aqui um `git remote add origin`. E aí aqui eu vou pôr a URL do meu **repositório**. Posso vir daqui e fazer isso, Mira? Pode. Se você quiser também um `git`, deixa aqui, ó, pra você. Prontinho. Esse cara aqui.

Nossa, eu vou ter que fazer um negócio aqui que eu esqueci, que eu tô num **repositório** novo. Mas é legal, vai ser até da hora, isso vocês vão ver também. Tá vendo aqui que ele já deu uma mensagem? "You don't have public **SSH** keys in your **GitHub** account. You can add a new public key or try cloning this repository via HTTPS." Você pode ou adicionar uma nova chave **SSH** ou tentar clonar esse **repositório** via HTTPS.

O que eu quero, na realidade, eu não quero clonar esse **repositório**, eu quero só trackear esse **repositório** lá. Mas, para fazer isso, eu tenho que comprovar pro **Git** que eu sou eu. E para fazer isso, eu tenho que criar uma configuração aqui.

## Gerando a chave SSH

E aqui eu vou deixar vazar mesmo, porque a conta é for fun. Mas isso aqui vocês vão fazer com muito cuidado e deixar de preferência muito bem guardado, sem fazer pros outros, tá?

Você vai vir aqui em **SSH keys** e clicar em **new**. Você vai colocar um nome aqui, sei lá, "teste 123". E aí aqui você vai gerar uma **SSH**. Mira, como é que gera uma **SSH**? Eu não lembro o comando específico, e aí vamos usar a **IA** para lembrar o comando específico para a gente.

Então abrir o **Claude** aqui. Vamos pedir para ela fazer isso para nós. Claude: "preciso gerar uma **SSH** pro meu **GitHub**. Como faço?". E aí a gente vai dar aqui, ó, copiar esse cara aqui.

Eu vou vir aqui, pesquisar Google no Google, tá? Não me xinguem. Vou dar uma de dev de pesquisar Google no Google. Só porque eu quero facilidade. Vou trocar aqui pra conta random que a gente tá usando pra brincar com o **Git**. E vamos pegar o e-mail dela certinho aqui. Beleza?

Aí a gente vai vir aqui e vai rodar esse comando que ele passou aqui pra gente. Pera aí, vou pegar aqui. Copiar. Abrir no terminal. Antes de fazer isso aqui, a gente vai gerar a chave **SSH**.

Então vamos dar aqui Shift. Em `cm.exemplo.com` a gente vai colar o e-mail da nossa conta que tá lá no **GitHub**, no nosso Gmail mesmo principal. Eu vou vir aqui e vou pegar esse cara que tá aqui. Ctrl+C, Shift+Ctrl+V e vamos dar um Enter. Qualquer arquivo é gerado aí mesmo. Beleza.

Eu vou sobrescrever minha chave do meu **GitHub** aqui quando eu fizer isso. Não tem problema, depois eu volto, crio uma nova chave. Mas no de vocês, provavelmente vai tipo, se for a primeira vez que você tá usando, vai de boa.

Aqui a gente cria uma **passphrase**, é uma palavra-passe pra validar que a gente é a gente. Então vou colocar aqui. O Linux não mostra quando a gente tá digitando absolutamente nada desse tipo de coisa. Beleza, ele criou, tá vendo? The key fingerprint, tá aqui ó. Beleza.

A gente tem que copiar isso, mas vamos ler o passo a passo que ele deu pra gente. Beleza, cria uma nova chave. Aí ele tá dando aqui ó: programa para criar a chave, `ssh-keygen`, tipo de criptografia. Quem assistiu os vídeos do Yuri, se você não sabe o que é criptografia, ele explica lá. Adiciona um comentário tipo o seu e-mail, pressione Enter três vezes, onde salvar, aperte Enter ou crie uma mais segura se você quiser.

E aí depois a gente vai dar um `cat` nesse cara aqui. Como eu tô no Linux, é esse comando aqui. Dá um Shift, dá um Enter. Ele pegou a chave pública. Vou dar um copy nesse cara.

E aí a gente vai lá pro **GitHub**. Eu vou vir aqui. Aí você pega. Pronto. Tem uma chave gerada aqui que fala pro **GitHub** que eu sou eu. Então eu posso modificar meu **repositório** a partir de agora. Beleza.

## Adicionando o remote e fazendo o primeiro pull

Vamos ir lá pros nossos **repositórios** agora. **Repositórios**. O batatinha. Vamos vir aqui. **SSH**, copia esse cara, e aí a gente vai dar um `add` lá pra ele começar a trackear.

Então, só pegando o comando de novo aqui, a gente vai dar um `git remote add origin` e a URL. Eu não sei se com o **SSH** funciona, mas eu vou testar aqui com vocês. Que dessa maneira eu nunca fiz. Normalmente eu crio no **GitHub** e depois clono no PC. Mas vamos testar se assim funciona.

`git remote add`, Shift+Ctrl+V. Vamos ver se funciona. Funcionou. Ele não reclamou.

Vamos ver se tem alguma **branch** aqui. O comando para você listar as **branches** que você tem é `git branch`. Beleza. Isso aqui lista suas **branches** locais. Tá bom?

Eu quero listar as remotas. Ué, nenhuma? Agora `-r` aqui. Vamos testar. Vamos dar um `git pull` aqui. Opa, agora ele trouxe. Beleza, então é isso.

Tá, eu vou explicar pra vocês o que aconteceu, tá? Seguinte, rapaziada, quando eu rodei... Quando eu só adicionei, eu só falei pro **Git** que, a partir de agora, o **repositório** remoto pra minha pasta `.git` é essa aqui, tá? O meu **repositório** remoto lá na internet. Eu só falei isso, mas eu não trouxe as informações que estavam lá no meu **repositório** remoto.

Agora, quando eu rodei esse comando aqui, ó, `git pull`, eu trouxe as informações, eu puxei lá da internet as informações pra minha máquina. Beleza.

Agora, se eu não me engano, se eu der um `git branch -r`, ele vai aparecer pra mim a **branch** que é a do meu **repositório** remoto. Beleza?

## O conflito entre master e main

Só que, legal, ele trouxe a **branch** main. Eu tô na master. O meu código tá na master. Como é que eu levo esse código que tá na master pra main?

Bom, tem duas maneiras: eu posso fazer isso localmente ou eu posso enviar as informações que tão daqui lá pro remoto e fazer isso lá. Vamos fazer lá no **GitHub** para vocês verem como é que é o **merge**.

Então eu vou vir aqui e vou fazer assim. Ele vai retornar erro, esse comando, e eu vou explicar o porquê. `git push`. Fatal. Ele falou assim: "olha, eu vi que você tentou levar as informações dessa sua **branch** master lá pro seu **repositório** remoto. Só que no meu **repositório** remoto, a única **branch**, a única linha do tempo que existe, chama main. Então eu preciso levar as informações. Eu preciso que você crie essa **branch** master lá no seu **repositório** remoto também".

Ah, beleza. Vamos dar um Ctrl+L aqui e limpar. Opa! Pra fazer isso, ele só dá o comando pra você: `git push --set-upstream origin master`. Leva essa **branch** master pro **repositório** de origem, né? Pro **repositório** remoto lá.

Então, só pra facilitar o tempo e não perder tempo aqui, vamos copiar esse cara aqui e mandar pra lá. Shift+Ctrl+V. Dá um Enter. Foi. Beleza. E ele falou ó: "Enumerating objects 16, done. Counting objects 16, done. Delta compression". Beleza, compactou e enviou. Beleza.

## Tentando abrir o pull request

Vamos voltar pro **GitHub** e ver o que aconteceu. Boom. Ele já deu aqui, ó: "Head recent push three seconds ago". Ele falou: "olha, alguém trouxe um negócio novo aqui pra mim há três segundos atrás. O que você quer que eu faça com isso? Você quer que eu dê um compare e um pull request, abrir uma **pull request**?". Beleza. Vamos fazer isso aqui.

Aqui é o momento que a gente presta um pouco de atenção no que a gente tá fazendo. Que é o quê? Se eu vir aqui e olhar, eu faço isso aqui de trás pra frente. Então eu vou pegar a master e levar pra main. Tá bom? Aqui tem as coisas que eu tô adicionando, um change file adicional. Beleza.

Ele não abriu o **PR** pra mim. Por que será? Ah, por causa do nome de origem. Ele vai dar confusão isso aqui. Porque master e main são duas **branches** principais. Agora, quem que é quem?

Vamos ver se pelo PR público consigo fazer aqui. New PR master. Ele não vai dar. Ele não vai deixar eu levar. E ele não trouxe a developer pra cá. Quer ver? Tu vem pra master aqui, ó. Ele traz as coisas, só que eu não consigo. Isso aqui ele tá dando um conflito, que é o seguinte. E aí vai ficar um pouco complicado de resolver. Eu não vou entrar nesses detalhes.

Mas o que ele tá dando um conflito? Master e main são dois nomes de **branches** principais. E aí o que acontece é que ele fica assim, ó: "tá, quem que é quem? Quem que é a principal de verdade?". Fica meio confuso. O **GitHub** fica meio confuso.

Por isso que é importante você padronizar. Se você vai usar master, sempre use master. Se você vai usar main, sempre use main. Ele não vai deixar fazer o **PR**. Não sei porquê. Normalmente aqui ele deixa, mas vamos fazer diferente então.

## Tentando pela branch developer

Só pra modificar, a gente vai dar um `git checkout`. É legal dar esses erros, rapaziada, porque eu aprendo também com vocês. Porque eu não manjo muito de **Git**, eu manjo bem o básico. A intenção aqui era ajudar.

`git checkout developer`. Vamos pra developer. `git status`. Beleza? E vamos dar um `git push` aqui na developer. Vamos ver se a developer ela deixa. Ele vai trazer o mesmo erro, que ela não existe lá. Vamos copiar esse cara aqui.

Depois eu tenho que estudar e entender por que ele deu aquele conflito lá. Aí, talvez amanhã, pra quem quiser, eu volto aí. Ou se alguém souber no chat o porquê que ele deu aquele conflito e quiser compartilhar com nós aí, eu aceito também, tá, rapaziada?

Bom, dá um F5 aqui. Recarregar. Beleza. A developer ele trouxe pra cá. "Choose branches to start a pull request. If you need, can also compare across forks. About diff comparisons". Vamos entender o que tá acontecendo, porque nem a developer tá deixando. "Comparisons shows the difference between the branches, for example. About three-dot comparisons on **GitHub**".

Tá, você tá reclamando demais e tá me ajudando de menos no que eu preciso. Vamos fazer o seguinte. Não façam isso, tá rapaziada? Pelo amor de Deus, porque isso é perfeito pra dar cagada. Mas eu vou vir aqui em **branches**. E eu vou falar assim, ó, eu vou mandar você pro espaço. Vamos ver se ele... "You can't do this, default branch". Tá, eu vou mandar a master pro espaço pra ver se ele consegue melhorar ou não.

Vamos ver aí. F5 aqui. Ele mandou a master pro espaço. Beleza. Será que agora eu consigo levar a developer pra main? Ou não? **PRs**. Compare pull requests. Vamos ver. "There isn't anything to compare. Main and developer are entirely different commit histories". Olha que da hora. Não vai deixar, pode crer.

Deixa eu fazer diferente então. Vamos rodar isso aqui duas vezes. Será que da developer pra master eu consigo, que tem a mesma história? E eles partem do princípio... deveria deixar. Eu vou levar a developer pra master. Esse cara vai estar clear. Beleza.

## Entendendo o porquê do conflito

Eu entendi porquê. Já vou fazer isso aqui só pra gente adiantar a aula. E aí eu explico. `else if option equal a 5`.

O que aconteceu, família? Lembra daquela pasta `.git`? No caso aqui, como eu criei esse **repositório** depois, o que tá acontecendo é o seguinte: é o mesmo **repositório**. Quer dizer, aqui aparece como se fosse o mesmo **repositório**. Só que eles têm duas... Isso é um chutômetro, tá? Pelo que eu entendi.

"Try switch the base". Vamos ver se ele dá. Deixa eu fazer alguma coisa aí. Agora sim, eu consigo trazer coisas da master pra developer.

Só que o que aconteceu? Tipo, são duas histórias diferentes. Duas árvores, dois livros de história diferentes. Um com o livro principal chamando main, e outro com o livro principal chamando master. E aí eu não consigo juntar dois livros de história. Entendeu? Cada linha do tempo tem o seu livro de história, que é a sua pasta `.git`.

Se eu não me engano, é por isso que tá dando erro. Depois, na hora que eu liberar pra pergunta aí, geral quiser falar, a gente discute se é isso e descobre se é isso junto.

## Fazendo o push e visualizando as diferenças

Eu vou dar um `git status`. `git add .`, `git commit -m "test"`, só pra testar se é isso. `git push`. Beleza, subiu, beleza.

Agora no **GitHub**, vamos voltar do começo. Eu consigo vir aqui na master e vir na developer, que tem coisas novas. E aí o que acontece? Aqui eu consigo enxergar aonde foi a modificação.

Lembra aquela história que a gente tava falando lá no começo, que é o seguinte: é bom saber quem modificou, quando modificou e como modificou. Se vocês virem aqui, tá o meu **GitHub**. Por quê? Porque lá eu tô logado, as minhas configurações. Lá, aquelas configurações iniciais, aquele segundo slide que eu falei aqui. Eles tão com as minhas configurações do meu **GitHub**.

Então ele veio aqui e trouxe as informações. Olha, é o Mira que tá trazendo alterações aqui pro código. Beleza. Aonde ele tá trazendo as alterações? Da linha 14 pra linha 15, ele adicionou umas modificações aqui. Ele adicionou um `if` novo.

Então você consegue ver onde modificou. Só em um arquivo, Mira? Não, em todos os arquivos que o **Git** trackeou. Então, todos os arquivos que o **Git** trackeou, você consegue comparar o como ele tá e o que vai ser modificado e aonde vai ser modificado nele.

## Criando o pull request e fazendo o merge

Beleza, vamos criar o **pull request**. Aqui é bom você descrever o que você tá fazendo nesse **pull request**, quais são as alterações, quais são as coisas. Lembra que aquele `-m` de mensagem, ele tá aqui ó. Ele vem, ele é o título desse **commit** que eu vou adicionar nessa história.

E aqui eu vou fazer o **merge**. Eu vou pegar essas informações aqui e vou levar pra master. Então eu vou dar o "Create Pull Request". Ele aqui vai checar se tem conflito. Então, se, por exemplo, esse arquivo foi modificado ao mesmo tempo por duas pessoas, o próprio **GitHub** checa esse tipo de conflito pra vocês.

"Merge pull request", só confirmo aqui. "Confirm merge". Pronto. As alterações que estavam na developer eu levei pra master. Vamos ver se funcionou? Eu vou dar um `git checkout master` aqui. E aí eu vou dar aqui um `git pull`. Ele já trouxe aqui a mensagem pra mim, tá? "Você trocou pra **branch** master e sua **branch** master is up to date with na parte do remoto". Então assim, ó, sua **branch** master tem alterações no remoto. Cara, eu quero trazer essas alterações. Trouxe as alterações.

Se a gente for aqui no VS Code, na **branch** master já trouxe esse `else if` que eu tinha adicionado aqui. Vamos voltar às vacas magras.

## Recapitulando o fluxo: push, pull e PR

Então: conectei. **Push** e **pull**. **Push**, eu envio. **Pull**, eu trago. Recebi o trabalho da minha equipe e enviei o meu trabalho pro **GitHub**.

O fluxo de **PR**. Cara, esse é o fluxo que vocês mais vão ver na vida. Cria uma **branch**, `checkout` na suite. Trabalha, adiciona, comita. Trabalha, adiciona, comita. Beleza, comitou tudo, envia pro remoto. Envia pro remoto. Abra uma **PR**, discute a **PR** com o seu tech lead, não sei o quê. Revisa tudo que você tem que revisar. Faz o **merge** lá no próprio site do **GitHub** e atualiza. Tá bom?

Mais do fluxo: `git pull`, `git switch`, abre **PR**, faz o **merge**, switch também, `git pull`. E vai ficar nessa brincadeira pra sempre.

## Encerramento

Rapaziada, eu não sei se vocês preferem ficar no palco. Vocês preferem ir pro Macau lá. Eu acho que ficar no palco fica mais organizado pra nós debater. E agora é só trocar ideia sobre o assunto, tirar dúvida, falar e tal, pra quem quiser. Demorou?

Então, quem quiser subir aí pra falar, trocar ideia, mano, só levanta a mão aí que nós puxamos vocês pra cima. Ou vocês quiserem ir pro Macau, vocês que sabem.

Demorou, mano. Ninguém quer trocar ideia, ninguém quer falar nada. É isso, família. Se tiver suave pra todo mundo. Zaninho, eu acho que o mais é agradecer mesmo a minha aula. Eu tava bem secão no... ai, muita gente agradecendo aqui. Tava bem secão no **GitHub**. Isso aqui foi bem esclarecedor pra mim. Muito obrigado em nome de todos.
