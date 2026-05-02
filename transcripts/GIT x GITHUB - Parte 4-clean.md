# GIT x GitHub — Parte 4

## Recapitulando: Git é local

Beleza, vou que eu te falei o seguinte, **GitHub**, um outro exemplo aqui que ficou maravilhoso, ficou muito bom de entender. Mas vamos para os tópicos técnicos da ideia.

O **Git** é o software, ele é a ferramenta, ele está instalado na sua máquina. Tudo que eu fiz aqui foi **localhost**. Eu não fui pra internet em nenhum momento, foi 100% na minha máquina. Se eu puxar o cabo de rede aqui, o **Git** vai continuar funcionando. É completamente local.

Então, esse **repositório** fica local. Fica tudo na minha máquina. E aqui você tem um problema: pra eu compartilhar isso com outras pessoas, eu vou ter que pegar e mandar o meu arquivo. Eu vou vir aqui, vou abrir meu explorador de arquivos, vou vir em desktop, vou vir aqui no **Git**, vou pegar isso aqui inteiro, essa pasta aqui inteira, e vou mandar pro Yuri. Porque, quando for a pasta `.git`, ele consegue ter.

## A pasta .git

Aqui dentro da pasta `.git` fica toda a história do teu projeto. Então, se a gente vir aqui em `branch`, vai dar pra visualizar algumas coisas. Mas se a gente vir aqui em `branches`, fica as coisas no `logs` aqui, ó. Ele tem algumas. Fica aqui guardado os `logs`. Não dá pra entender nada.

Eu não manjo muito de **Git** nessa parte de como ele funciona por trás e afins. Se alguém conhecer e quiser compartilhar aí com nós, fica à vontade. Mas basicamente, se eu mandar esse cara aqui pro Yuri, com a pasta `.git`, vê todo o histórico do projeto.

Só que eu vou ter que pegar, sair da minha máquina, entrar até no e-mail, no chat do Discord, enviar isso pra ele, pô, meu trabalho, cara.

## O que é GitHub

Foi daí que surgiu o **GitHub**. O **GitHub** nada mais é do que uma maneira de eu pegar esse arquivo que tá local na minha máquina, expor ele na internet, pra alguém do outro lado do mundo conseguir vir e baixar ele direto na internet, sem eu ter que enviar. E eu conseguir fazer isso de uma maneira rápida, pelo terminal. Simples, prática. Beleza?

Beleza, vamos lá. O que é o **GitHub**? É isso. Ele é basicamente a casa dos seus **repositórios** **Git** na nuvem. Fora isso, ele é a rede social dos devs, ele ajuda você a fazer revisão de código, que a gente vai falar um pouquinho mais pra frente. Algumas automações com **GitHub Actions**, que eu não vou entrar em muitos detalhes, mas dá pra, por exemplo, só passando por cima, eu colocar para que, antes de eu fazer aqui esse processo que eu mostrei pra vocês de **merge**, de pegar as atualizações e trazer para a minha base que está tudo funcionando, ele teste todo o meu código sozinho, de maneira automatizada.

E ele facilita a gerência do projeto, o gerenciamento do projeto entre as pessoas. Porque no **GitHub** eu consigo, por exemplo, falar assim, tem tal coisa. Tem várias coisas ali no **GitHub** que você consegue chamar as pessoas para participar e colaborar do seu projeto e falar onde elas vão mexer, o que elas têm que atualizar e afim.

Se vocês não estiverem muito cansados, dá pra gente até brincar com isso hoje. Eu criei uma conta aleatória aqui no **GitHub** e a gente sobe o projeto lá e a gente vai mexendo todo mundo junto no mesmo projeto. Só pra vocês verem como é que é da hora.

## Conectando Git local e GitHub

Beleza. Vamos conectar esses dois. A primeira coisa que a gente vai fazer é entender como é que fica. As coisas vão modificar um pouco.

O que acontece é que nem sempre as **branches** que estão na minha máquina, as linhas do tempo que estão na minha máquina, estão no **GitHub**. E nem sempre também as linhas do tempo que estão no **GitHub** estão na minha máquina. Isso varia do momento que eu trouxe as atualizações do **repositório remoto** para a minha máquina, do momento que eu levei as atualizações da minha máquina para o **repositório remoto**. Então, nem sempre vão ter.

Para a gente identificar quem é que… normalmente as **branches** que estão no **repositório remoto**, elas vêm com um apelido. Esse apelido é que a galera chama ele de **origin**. De **origin**.

## Criando um repositório no GitHub

Beleza, mas eu tô falando demais. Como é que eu criei o **repositório** do **GitHub**? Você botar aqui, pode iniciar o seu **GitHub**. Aqui normalmente fica os **repositórios** que você já tem. Como essa conta é nova, eu venho aqui e dou um **Create Repository**.

Beleza? Coloco o nome do **repositório** que eu quiser. Batatinha. Salvar esse cara como batatinha. Eu posso adicionar uma descrição do meu **repositório**.

Eu posso modificar aqui quem vai ver meu **repositório**. Se eu quero que o mundo inteiro veja, quando eu deixo público, qualquer pessoa do mundo pode ver. Privado, só eu e quem eu permitir acesso consegue ver. Nesse caso, para a gente zoar um pouco aqui, eu vou deixar público para quem quiser mexer aí e ir brincando junto.

Aqui eu tenho uma opção de adicionar um **README**. O que é um **README**? Cara, normalmente os sistemas que você baixa vêm com um **README**, que é tipo assim, "me leia". Aqui vão ficar as instruções de como o seu código funciona, de como o seu sistema funciona, como eu faço para baixar o seu sistema, como eu faço para usar, o que eu preciso fazer para configurar. Fica tudo aqui.

Essa parte do **gitignore**, o **GitHub** já monta, se você quiser, um **gitignore** para você. Então, se eu vir aqui e colocar Python, ele vai criar sozinho para mim um **repositório** Python.

E eu consigo adicionar licença desse meu **repositório**. Já tem várias licenças prontas. A **MIT** você está falando assim: qualquer um pode usar desde que me dê crédito e afim. Beleza? Vou colocar aqui **WTFPL** só para não zoar. E vou criar esse **repositório** aqui. Criei.

Vou mandar o link aí no chat da Cal, para quem quiser mexer. Mexi aí. Quem que tá com a mão levantada aí? Eu vou aceitar ele, porque ele tá se empenhando, mano. Quero ver se ele ia falar uma coisa interessante. Ele fez uma pergunta boa já. Chama aí, picolé. Chama aí você, picolé, vê se apareceu pra ti. Vai, sumiu, acho que ele não vai subir, não. Eu acho que não vai subir, não. Bom, continuar. Aí, subiu. Só desmutar pra você. Salve, picolé. Fala, picolé. "Cadê a aula de criar injetor de DLL?" Picolé assim no picolé. Tá bom.

## Explorando o GitHub: Issues

Beleza. Vamos levar esse cara aqui pro **Git** aqui. Trazer esse cara aqui pro meu terminal. Como é que a gente faz isso?

A gente vai vir aqui. "Devo dar uma coisa no **issue** aí depois, tá? Mostra pro pessoal. Tá bom. Quer explorar o **GitHub** então antes? E aí depois a gente faz essa parte de misturar os dois?" Então vamos ver, vamos explorar o **GitHub** antes e depois a gente mexe.

No **GitHub**, quando a gente cria um **repositório**, a gente tem várias coisas aqui que ficam aparecendo aqui pra gente. Lembra aquela parte que eu falei de organização, de fazer com que a gente consiga marcar pessoas, cada um fazer o quê? A gente tem **issues**, que é exatamente pra fazer isso. Pra fazer a gestão do seu projeto.

Então aqui pro GTA eu vou lá e posto: "Vamos melhorar o **README**?" Beleza. Vamos, cara. Acho que é da hora. **Create sub-issue**. Beleza. Vou aqui. **Link issues**. Eu não lembro, eu não lembro isso aqui. Mas sei lá. **Title**. Melhorar o read. Eu posso colocar, escrever melhor sobre como é que vamos melhorar essa **issue**. E ainda, só de brincadeira, esse cara aqui é um **Markdown**. Então, pra quem conhece **Markdown**, pra deixar bonitinho, você consegue deixar bonitinho aqui. "Vazae, Yuri.dev. Twitch."

Pra **sub-issue**, além da **issue** principal, que é melhorar o **README**. Beleza? Tá.

## Pull Requests, Actions e segurança

No **Pull Requests** a gente vai tratar depois. O **Actions** aqui é aquilo que eu tava falando pra vocês: de criar coisas para automatizar o meu **repositório** e afins. Eu consigo fazer aqui.

Eu vou trabalhar a segurança do meu **repositório**. Na realidade, aqui eu trabalho algumas coisas de segurança do meu **repositório** no meu perfil. Eu tenho mais configurações do meu **repositório** que eu posso fazer.

## Colaboradores

Eu posso chamar colaboradores. Tipo… ser o YuriDev pra cá. Manda teu **GitHub** aí, Yuri Dev. "Ainda bem que eu escutei isso aqui. Eu tava do outro lado da minha casa. Eu tô pegando água, só que eu escutei. Meu **GitHub** é YuriRDev." Yuri é R. Tudo minúsculo assim? Yuri Dev.

Agora o Yuri é um colaborador. Não sei se ele tá podendo compartilhar a tela, mas ele consegue fazer modificações. "Não, eu não consigo, que você tá compartilhando. Eu acho que é só um por vez. Mas depois você mostra aí pra galera se der."

Ele consegue fazer modificações, adicionar novos arquivos ou afins. "Puta, dá pra codar por aqui? Dá pra codar por aqui?" Ele abre o **VS Code** online pra você. Você consegue editar código aqui.

## Editando direto no GitHub e fazendo commit

Então, sei lá, eu vou clicar aqui no **README**. Se eu clicar aqui, eu consigo editar aqui. Teste 1, 2, 3, 4. **Commit**, mesma coisa, ó. **Commit changes**, "update readme". **Commit directly to the branch main**. No caso, como só tem uma **branch**, a gente vai deixar assim e vai colocar aqui "teste". Esse **commit message** é aqui no menos M lá, tá? Tash, **commit**.

E aí ele criou a alteração desse cara. Beleza? Então vamos formar a gente.
