# GIT x GitHub — Parte 3

## O .gitignore

Bom, aí vamos falar do **.gitignore**. Lembra que eu dei uma adiantada aqui, mas comentei que existem alguns arquivos que eu não quero que o **Git** trackeie. Para isso acontecer, eu tenho que criar um arquivo chamado **.gitignore**, beleza?

A partir desse momento, se eu criar aqui, se eu não me engano, é assim, tá? **.env**. E vir aqui e criar um arquivo chamado **.env**, se vocês prestarem atenção, esse arquivo ficou em cinza aqui. O **Git** não está prestando atenção nesse arquivo, ele ignorou esse arquivo. Ele literalmente fala: "tá bom, eu não quero saber o que tem aí, eu vou completamente ignorar o que tem dentro desse arquivo".

Se eu rodar aqui um `git status`, só para vocês terem certeza, ele só vai apitar para mim o arquivo do **.gitignore**. De resto, o **.env** ele não vai nem ver. E eu dou um `git add .gitignore`, `git status` de novo para ver se ele foi trackeado, `git commit` para guardar essa modificação. Vou salvar como segundo **commit** e rodar um `git status` de novo de novo para ter certeza. Pronto. *On branch master, nothing to commit, working clean*. Beleza?

Beleza. Então só para exemplificar para que serve esse arquivo **.gitignore** que muita gente vê em muito projeto e muita gente não usa. Inclusive, isso é uma falha de segurança, porque se vocês entrarem no **GitHub** agora e pesquisarem por `API_KEY`, por exemplo, lá no negócio do **GitHub**, vocês vão achar um monte de **API key**, que é de um monte de arquivo do tipo **.env** que subiu para o **GitHub** porque os caras simplesmente esqueceram de adicionar esse arquivo aqui.

## Branches: trabalhando com várias linhas do tempo

Bom, vamos lá. Agora a gente vai começar. Agora começa a complicar. Vamos lá, rapaziada.

O que acontece? Quando a gente está falando de sistemas grandes mesmo para valer e afins, a gente tem vários ambientes. Eu não posso simplesmente alterar o código que está funcionando para o meu cliente, para o meu usuário, sem testar antes. Só que vamos lá, uma vez que eu desenvolvi o código, o código já tá funcionando. Já tá lá, funcionando, bonitinho. E eu preciso, com base naquele código que já funciona, fazer um novo código, adicionar uma mudança naquele código, trazer uma feature nova, trazer isso aqui.

Essa é outra parte do **Git** que é sensacional, a maneira de pensar. Então eu tô aqui com o Excalidraw aberto. Não sei se tá dando pra todo mundo enxergar legal. Deixa eu abrir o chat aí. Se tiver pra todo mundo conseguindo ler suave, dá um joinha aí.

Então vamos lá. A **branch**, a gente vai tratar ela como linha do tempo, porque fica mais fácil de explicar. O que acontece? Toda vez que a gente faz um **commit**, a gente gera como se fosse um nó nessa linha do tempo nossa. Então lá eu fiz dois **commits**. Eu fiz o primeiro **commit**, certo? E eu fiz lá também o segundo.

Dá um zoomzinho, só um pequeno zoom. Só mais um. Beleza? Agora dá pra ler. Se quiser dar mais um, só de brincadeira, pode dar também. É porque aqui na apresentação a tela fica pequenininha. Pode continuar, agora tá de boa.

Então, beleza. Lá eu fiz dois **commits**. O primeiro e o segundo **commit**, beleza? Fiz duas marcas nessa minha linha do tempo, beleza.

## Modificando código e dando rollback

Esse código aqui, ó, que a gente viu no `teste.py`, é o código que tá em produção. É o código que o meu usuário tá usando. Que tá funcionando. Que tá, mano, perfeito. Não tem erro. Tá funcionando da hora.

Eu quero agora modificar esse código. Se eu vim aqui modificar esse código, e aqui eu vou causar um erro de propósito, eu vou tirar a opção de dar `break`. Criei um loop infinito. Fui lá, modifiquei o código, criei um loop infinito.

Vim aqui e fazer assim: `git status`. Olha lá. *On branch master*, um arquivo foi modificado. Vou adicionar essa modificação na minha caixa: `git add teste.py`. Adicionei essa modificação. Vou rodar de novo um `git status` pra ter certeza que eu adicionei. Beleza. Vou rodar agora um `git commit -m "commit"`. Opa, isso aqui vai dar erro porque não tá entre aspas. Beleza. Rodei.

Beleza. Cara, lá no meu servidor, não sei o quê. Mano, vai bagunçar tudo. Parou de funcionar. O código que tá funcionando lá parou de funcionar. Puts, e agora? Ferrou.

Graças a Deus, o **Git** nos dá a opção de fazer o famoso **rollback**, voltar pra trás. Como é que eu faço isso? Eu vou adiantar o **rollback**, depois eu vou lá e vou introduzir melhor a explicação. Então eu já fiz o **commit**, eu quero agora voltar pra trás. Eu vou vir aqui e vou rodar...

Deixa eu só pegar o comando aqui que fugiu da cabeça aqui rapidão. Mas eu vou vir aqui e vou rodar esse cara aqui. `git revert`. Shift Ctrl C, ai carai. Terminal do Linux dando problema, como sempre. Beleza?

Só pra ficar fácil, eu tenho que pegar esse cara aqui, ó. Ctrl X, beleza. *Revert terceiro commit*. O que aconteceu? Eu voltei pra trás. Se vocês verem aqui no código, o `break` que eu tinha removido voltou pra trás. Consegui dar **rollback** na minha versão de código, tá?

## Criando uma nova branch

Então, beleza. Pra evitar esse tipo de coisa, a gente vai vir aqui. E a partir desse segundo **commit** aqui, eu vou puxar uma nova linha do tempo. Essa nova linha do tempo, quando eu criar ela, ela tem, ela traz consigo as mesmas coisas que tem na linha do tempo de baixo. Então eu vou ter nela aqui... não é o **commit** em si, tá, rapaziada? É as mesmas informações do que tem na linha de baixo, na minha linha do tempo de baixo. Porém, as coisas que eu modificar aqui não se refletem automaticamente aqui.

Então, aqui, quando eu estiver aqui, existem dois comandos que vocês vão ver para fazer isso, que é o `git switch` e o `git checkout`. O `git checkout` é o jeito antigo de fazer isso, e existe o `git switch`, que é o jeito mais novo. Eu sou da véia guarda e eu sempre fiz assim.

Então, para mudar de **branch**, eu venho aqui. Pra mudar e criar uma nova **branch**, eu venho aqui e digito `git checkout -b` e o nome da **branch** que eu quiser.

Mira, tem um padrão? Cara, por boa prática, a gente trabalha assim: **main**, **debugger**, **developer**. **Developer** são as novas features que eu vou trazer. **Debugger** tem a mesma peculiaridade do ambiente que está em produção, só que ele é para teste, para ver se está tudo funcionando certinho. E tem a **main**, que é a principal onde realmente esse sistema está rodando.

Então eu vou dar um `git checkout -b`, abrir aqui e vou colocar aqui, sei lá, `developer`. Beleza, *switched to branch developer*. Se vocês perceberem aqui, no meu, como eu estou no Linux, ele fica assim, tá? Ele mostra a **branch** que eu tô. Eu tava na **master**, agora eu tô na **developer**.

## Trabalhando na branch developer

Vamos entender como isso funciona. Eu vou aqui de novo adicionar um novo `elif`. `elif option == 4`, `print("you selected option 4")`. Ctrl S. Criei uma alteração, beleza?

Vou dar um `git status` aqui pra vocês verem. *Status*. Ele vai ver que tem o arquivo, tá? Só que ele vai ver que teve uma alteração nesse arquivo, `teste.py`. E aí, o que acontece agora é que eu preciso falar: "beleza, trackeei essa operação". Então, essa modificação que teve, `git add teste.py`, pronto. `git status` para validar. Foi trackeado. Vou dar um `git commit -m`, abri aspas, "quarto commit", fecha aspas. `git status` só pra ver se não tem mais nada pra fazer. Beleza, tranquilo.

Eu tenho a **developer**. Vocês estão vendo aqui ó? No código tem a `option 4`. Beleza.

## Trocando de branch

Vamos trocar de **branch**? `git checkout`. Pra eu voltar pra **branch** que eu tava, eu não preciso dar o `-b`, tá rapaziada? O `-b` é a flag de criação de nova **branch**. Eu só preciso colocar aqui o nome da **branch** que eu quero voltar. `git checkout master`. Voltei para a **master**.

Aqui não tem nenhuma alteração. Por quê? Eu alterei em outra linha do tempo. Então o que eu fiz aqui, voltando para o Excalidraw para ficar mais fácil de visualizar, eu vim aqui e criei uma nova alteração aqui, certo? Só que essa alteração não está aqui ainda. Eu não trouxe essa alteração para cá.

O que acontece? Isso me facilita desenvolver, testar tudo com as mesmas coisas que eu tenho nesse arquivo aqui, sem modificar o que está funcionando. E aí eu posso fazer teste, fazer não sei o quê. E quando eu implantar, eu já vou implantar com as modificações feitas seguro, testado, aprovado, funcionando, sem erros. Beleza?

## Fazendo o merge

Beleza. Então como é que eu vou fazer isso? Eu quero trazer agora as alterações que eu fiz na **developer** para a minha **branch master**. Para eu fazer isso aqui, a gente vai... eu não coloquei no slide, brisei, mas a gente vai vir aqui e vai fazer o **merge**. É o nome.

A gente brinca aqui: "**mergeia** tudo, fica igualzinho, **merdeia** tudo", porque é nesses momentos que dá problema. Mas a gente vem.

Então percebam que eu estou na **branch master** e eu quero trazer as informações da **developer**. Então eu vou dar um `git`... é sempre assim, eu quero trazer as informações. Eu nunca empurro as informações para outra **branch**. Eu sempre puxo as informações da outra **branch** para mim.

Então eu dou um `git merge developer`. Quando eu der esse comando aqui, ó, ele dá um update desse **commit** pra cá e ele traz as alterações. O que foi alterado? *One file changed, two insertions*.

Se eu vir aqui, agora na **branch master**, o VS Code mostra a **branch** que a gente tá. Agora tem a `option 4` aqui. Funcionando bonitinho.

## Desfazendo alterações antes do commit

Bom, vamos entrar na parte do "eu quero desfazer as coisas". Lembra que a gente tinha ali três camadas? Então, a parte que eu estou desenvolvendo, que é meus arquivos **untracked**.

Então vamos criar um novo arquivo aqui só para ficar fácil. `teste2.py`, beleza. Se eu vim aqui agora no meu terminal e dar um `git status`, eu tenho aqui agora o `teste2.py`.

Beleza, eu vim aqui e escrevi meu código. `print(`, abre aspas, `"hello world"`. Beleza, vim aqui e coloquei meu código. Aí eu vim aqui e dei um `git add` pra ele trackear esse `teste2.py`. Ele começou a trackear, tá vendo? Se eu der um `git status`, ele trackeou.

Cara, eu quero voltar esse arquivo, velho. Não gostei desse add que eu dei. Beleza, eu vou vir aqui dar um `git restore --staged`. Ai, copiar o comando, mas fácil que eu ficar dando auto.

Olha, rapaziada, esse negócio de voltar pra trás é uma coisa que eu não uso muito mais, porque eu já presto mais atenção no que eu tô fazendo. Mas vocês, pra quem tá começando agora ou aprendendo agora, vai ser uma coisa que vocês vão usar bastante.

E o nome do arquivo aqui, não copiou o bagulho? Mosquei. `--staged` e o nome do arquivo que eu dei, então, esse `teste_2.py`. Se eu rodar um `git status` aqui... era na minha... pra ele voltar pra cá, tá vendo? Ele não foi pra aquela. Eu tirei ele daquela minha caixa lá. Falei: "não, cara, não é pra você ir ainda". Tá bom?

É isso. Esse cara aqui, ó, esse antes do add, o **Git** aqui, ó, ele já tá trackeando esse arquivo pra mim. Então, eu vou vir aqui e vou fazer o processo normal de dar um **commit** nele e tal.

## Restaurando arquivos modificados

Eu vou fazer isso com o `teste` normal. Então eu vou vir aqui e vou alterar esse cara aqui. Vou adicionar uma linha nele aqui, que é o `print` multiplicação. E aí eu vou vir aqui, vou dar um `git status`, beleza?

Se vocês forem ver, esse arquivo agora está marromzinho assim, meio cor de bool quando foge. Ele foi modificado, mas eu não levei ele para a caixa. Mas eu adicionei modificação e back nessa modificação que eu fiz.

Aqui é simples, é uma linha. Eu vou aqui e apago. Mas vamos dizer que é bastante coisa. Eu tenho um comando para facilitar minha vida, que é esse cara aqui, `restore`. Ele vai voltar para o arquivo como ele era antes. Então eu vou dar um `git restore .py`. Se eu vir aqui dar um `git status`, ele não vai aparecer mais ali pra mim como *modified*. Ele voltou as alterações sem o que eu estava antes.

Essas são duas maneiras de vocês darem **rollback** antes de fazer o **commit**. Isso aqui, lembrando, eu não marquei essas alterações na linha do tempo. Beleza.

## Marcando alterações na linha do tempo

Vamos lá. Eu vou marcar essas alterações na minha linha do tempo. O `teste2.py`. Então, `git status`. `git add teste2.py`. `git status` de novo.

Mano, de começo, eu sei que é chato vocês ficarem usando `git status` o tempo inteiro. **Git** é: faz um comando, roda `git status`. Mas pra quem tá começando é muito importante fazer isso. Evita muita cagada isso, tá rapaziada? Então foquem, se forcem, é chato pra caramba. Às vezes você já quer pular etapa. Mano, se força a fazer o negócio.

E dá um `git commit -m "teste"`. Eu vou... `teste 1, 2, 3`. Vou dar o nome desse **commit** de "teste 1 2 3", beleza? Beleza. `git status`. Beleza, não tem nada pra fazer.

Putz, rodei o **commit**. Agora eu fiz uma marcação na minha linha do tempo.

## Revert vs Hard reset

Isso aqui tem bastante... tem duas formas de você fazer também, igual do `git add`. Só que aqui é um pouco mais crítico e tem que prestar muita atenção no que você vai fazer.

Normalmente no **Git**, quando a gente dá `force`, `hard`, não sei o quê, você tem que prestar muita atenção no que você está fazendo. Porque quando a gente faz isso, é como se ele apagasse. Ele vai vir aqui... vamos pegar aqui no Excalidraw. Ele vai vir, quando a gente dá `git hard`, vai deletar esse negócio dentro da linha do tempo.

Então, às vezes tem alteração que você fez que é boa, você quer manter, você só quer dar um **rollback** de algumas coisas que não funcionaram. Se você dá um `git hard` ali, ele vai deletar o **commit**. Então, todas as alterações que tinham sido feitas, tanto as boas quanto as ruins, se perderam. Já era, acabou. Não dá para recuperar. Morreu.

Então prestem muita atenção quando vocês forem dar esse tipo de comando aqui, o `hard commit`.

O **revert** é diferente. O que o **revert** faz? Ele vai vir aqui... deixa eu dar um Ctrl Z aqui. Eu quero voltar para esse novo **commit**, para esse **commit** antigo. Ele não apaga a alteração. O que ele faz? Ele cria um novo **commit** e traz para a gente as informações desse cara aqui. Mas essa marca na linha do tempo, essa página na linha do tempo, fica aqui.

Então, às vezes, eu quero ir aqui e olhar as alterações que eu fiz. Quando a gente for para o **GitHub**, vai ficar um pouco mais fácil de ver: onde ficou, qual linha, onde foi, não sei o quê. Quando a gente for para o **GitHub**, tem interface gráfica, não sei o quê, fica um pouquinho mais fácil de ver. No **Git** mesmo cru, só pelo terminal, é um pouco mais difícil. Mas tem como ver. Eu só não vou entrar nesses detalhes agora, mas depois é a hora que abrir para a pergunta aí. Se alguém quiser mostrar como é que faz, fica à vontade.

Então, basicamente, de **Git**, de **Git** que a gente tinha pra tratar, é isso. Não tem mais muito, não tem muito que descobrir que muda.
