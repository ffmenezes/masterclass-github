# Guia completo de Git e GitHub: programe com IA da forma certa

## Introdução

Sempre que nós trabalhamos com inteligência artificial, nós corremos o risco de que a tarefa não saia exatamente como planejado. Muitas vezes a gente quer voltar para o estado anterior antes das modificações. Também não é novidade para ninguém histórias de terror, quase, onde a **IA** basicamente destrói um projeto que estava funcionando.

Hoje eu quero ensinar para você como você pode se resguardar desse problema, com esse guia completo de **Git**: tudo que você precisa saber sobre **Git** para poder trabalhar com bastante tranquilidade com seus modelos de IA.

Nesse canal aqui eu falo bastante de programação e eu meio que assumo que todo mundo aqui já sabe o que é **Git**. Porém, no vídeo que eu falei sobre o meu setup para rodar agentes de IA em paralelo (vou colocar o link aqui na descrição), muita gente apareceu aqui me pedindo para fazer um vídeo sobre **Git**. E eu também sei que muita gente aqui no canal que me acompanha não é tão programador assim. Temos bastante programador e temos bastante gente que tá iniciando, ou faz aquele vibe coding e tudo mais. Portanto, achei oportuno fazer uma masterclass aqui, uma aula falando sobre tudo que você precisa saber sobre **Git**.

Se você é programador, calma, fica nesse vídeo também, que eu tenho certeza que muito disso pode ser útil para você, porque são conceitos que às vezes passam batidos e, francamente, quem trabalha com software precisa saber **Git**, beleza? Se você trabalha com **IA**, então nem se fala. Você precisa utilizar **Git** em todos os seus projetos e entender muito bem essa ferramenta, porque a **IA** de fato adiciona o risco de estragar o seu projeto. Então você precisa sempre ir avançando as etapas, tendo plena consciência e certeza de que você não está estragando o que funcionava no passado e que, se algum erro acontecer, você sempre pode reverter, como se fosse aquele Ctrl+Z, né? Aquele botão de undo: deu problema, você volta e tá tudo certo, beleza?

## O que é Git

Então tá, pessoal, vamos dar uma olhada aqui primeiro no site do **Git**, enquanto eu vou dizendo para vocês exatamente o que é essa tecnologia. Então, primeiro de tudo, você consegue ver aqui que é um site com a cara até meio antiga, né? Já mostra a idade do **Git**. Realmente tá aqui há bastante tempo.

Então tá, pessoal, basicamente o **Git** é um software de código aberto, e ele é de graça e **open source**. Significa que você pode ver ali o código, né? É aberto o código do **Git** e é de graça, você não precisa pagar nada, beleza? E ele foi projetado para lidar com desde apps bem pequenos, projetos bem pequenos, até projetos bem grandes, sempre com esse olhar de velocidade e eficiência. Então é um dos grandes casos de sucesso de software **open source**.

E até uma curiosidade interessante: o **Git** foi criado pelo mesmo criador do Linux, né, que é o **Linus Torvalds**. Na verdade, claro, foi toda a comunidade ali, mas o Linux também é **open source**. Então, aquela comunidade daquela época ali, no início do século, tava ali bem empolgada com essas ferramentas e tudo mais. E aí precisaram desenvolver o **Git** para fazer o versionamento do Linux, né? Então, assim, realmente uma lenda o **Linus Torvalds** criando o software que eu e você utilizamos basicamente todo dia em todos os nossos projetos. O que seria da engenharia de software, da programação, se nós não tivéssemos o **Git**? Beleza? Então tá, é importante entender isso.

## Versionamento de código

O **Git** é uma tecnologia para versionamento e gerenciamento de código. Sabe quando você vê alguma coisa assim: "ah, versão 1.0, 1.1, 1.1.2"? Isso é o que nós chamamos de versionamento. É um snapshot, é uma foto do seu código naquele momento com todas as mudanças, beleza? Então isso é o que nós chamamos de um versionamento.

Isso fica fácil porque, quando você passa da versão um pra versão dois, por exemplo, você vai ter ali o que muita gente chama de um changelog, né? Uma diferença. O que foi que mudou da um para a dois? Ah, colocamos isso, isso, isso, isso, isso. E tem uma mudança de código associada àquilo, tá? Então, por exemplo, se você fez uma atualização, sei lá, pra versão 1.2 e essa versão quebrou no seu computador por alguma razão, você sempre consegue fazer um downgrade ali pra versão 1.1, por exemplo, onde ela tá funcionando.

Então, você tem essa sequência de fotos, de snapshots do seu código, da sua base de código, né, que você pode navegar entre elas e instalar a versão que é mais adequada para você, beleza? Então é muito importante que nós tenhamos esse versionamento pra gente poder sempre voltar para aquele código que tá funcional e partir daquele código existente para fazer a modificação, pra gente não precisar sempre construir o código do zero.

Então a gente trabalha, trabalha, trabalha, chega num ponto onde "meu software tá legal", eu vou lá e tenho uma versão. E aí eu trabalho, trabalho, trabalho, chego no outro ponto, crio uma nova versão e aí eu tenho essa história, né, do meu software, do meu código mudando. Então essa é meio que a ideia aqui, grosso modo, do que a gente tá falando quando nós estamos dizendo versionamento.

## O que vamos cobrir

Eu vou entrar aqui na prática do **Git** e vou mostrar para você uma ferramenta que eu construí para te ajudar a visualizar. Nós vamos criar um **repositório** na prática também, beleza? Então vou criar aqui um **repositório** com você, vou te mostrar como você pode criar, vou te mostrar alguns problemas que podem acontecer.

Evidentemente, pessoal, já adianto aqui: o **Git** tem muita coisa. Se a gente voltar aqui pra história do **Git**, ele foi desenvolvido ali em 2005, ele nasceu em 2005. Então, assim, ele tem muita coisa para softwares bem mais complexos, para projetos bem mais complexos. Eu vou me limitar aqui a um conjunto pequeno de funcionalidades, que é o indispensável que você precisa para trabalhar.

Vou ser sincero com vocês: eu sou engenheiro de software de formação, trabalho com software há mais de 13 anos. Eu uso basicamente isso. Caríssimas vezes eu vou precisar utilizar algo que eu não vou mencionar aqui hoje. E são coisas simples mesmo. Então, se você que tá vendo esse vídeo não é um programador, calma, não desanima. São realmente o básico do básico que você precisa. Embora no início ali, para você entender um pouco a ideia do **Git**, né, precisa de algum tipo de explicação, que é o que eu vou passar para você agora, beleza?

Depois que a gente falar da explicação da teoria, eu vou mostrar para você uma simulação visual e aí a gente vai pra prática, criar o **repositório**, beleza?

## Dicionário: o que é um repositório

Então, primeira coisa aqui que a gente precisa fazer hoje é ter uma espécie de dicionário, tá? Eu vou falar muitos termos aqui e eu não vou assumir que você aí entende cada um desses termos, beleza? Então eu vou ser bem didático aqui, para que a gente saia desse vídeo aqui sabendo tudo que você precisa sobre **Git**.

Então eu tô falando aqui de **repositório**, beleza? O que é um **repositório**? Bom, basicamente um **repositório** é um lugar onde vive o seu código, beleza? O seu código vive lá. Então, por exemplo, se eu entrar aqui no **repositório** do Codex, né? Eu tô aqui no **GitHub** e aqui eu consigo ver o **repositório** do Codex. Então, o Codex é o nome do projeto, ele pertence a essa organização aqui chamada OpenAI. E tá aqui todo o código. Eu consigo entrar aqui e ver tudo que o Codex que eu instalo e uso lá para fazer a minha programação, para me ajudar a programar. Tá tudo aqui: a CLI, documentações, scripts, SDK. Posso vir aqui e saber exatamente "olha como que eles fazem isso, cara". Então isso é a grande beleza do **open source**, é um código aberto.

Parênteses aqui, pessoal: eu sei que **open source** não é a mesma coisa que você poder olhar o código, seria **open code**. Tô usando esses termos aqui meio que de forma significando a mesma coisa que o outro, não é? Porque tem licença, etc, etc. Mas para fins aqui da nossa conversa, vamos assumir que, quando eu falo **open source**, você entende **open code**, código aberto. Você pode vir aqui e inspecionar o código, beleza?

Então essa é a primeira definição do dia. Um **repositório** é onde vai viver o seu código. Então você vai criar um projeto, vai criar lá o seu app, o seu software, o seu jogo. E você vai colocar todos os códigos, todos os arquivos do código aqui, tudo que você precisa para rodar aquele projeto vai viver nesse **repositório**, beleza?

## Git vs GitHub

E aqui já é importante a gente fazer uma primeira distinção. Eu falei que aqui a gente tá visualizando o **GitHub**, certo, pessoal? **Git** não é a mesma coisa que **GitHub**.

**Git** é a tecnologia. **Git** é um sistema de versionamento de código distribuído, beleza? **GitHub** é um cliente, é um app que usa **Git** e que te expõe interfaces, ações ali, botões, se você tiver utilizando aqui na UI, para interagir com o **Git** por trás dos panos. Então, seu código vive em um lugar aqui e você consegue interagir com ele via **Git** através desse cliente **GitHub**.

**GitHub** não é o único cliente que existe. Você tem **Bitbucket**, **GitLab**, por exemplo. Embora, claro, o **GitHub** vai ter aí, sei lá, deve ter um market share de 99%, né? Você só deveria não utilizar o **GitHub** se você tiver uma razão muito forte, tá?

Um fun fact aqui: quando eu comecei a programar, o **GitHub** não era de graça se você quisesse ter **repositórios** privados, né? Então, se fosse **repositório** público, beleza, era de graça. Se fosse privado, aí você só podia ter uma quantidade X de **repositório**, né? Tinha algumas limitações e você tinha que pagar lá pro **GitHub**. Hoje em dia você pode ter **repositórios** públicos ou privados, 100% gratuitos, sem pagar nada. E como a maior parte das pessoas usam o **GitHub** e, na minha visão, também é provavelmente o melhor cliente mesmo, não vejo porque você não usaria, tá? Além disso, o **GitHub** hoje é da Microsoft, então tem um player grande interessado em manter esse software, podendo ali tomar algumas pancadinhas financeiras para manter ali a hegemonia desse produto, beleza?

## Repositórios públicos e privados

E aí eu falei aqui, pessoal, de **repositório** público e privado. A diferença deles é basicamente que um **repositório** público é um **repositório** onde você consegue entrar aqui e ver o código, né? Então se eu entrar aqui numa página anônima, eu consigo ver o código do Codex.

E um **repositório** privado seria, por exemplo, o **repositório** do Quant Brasil, que é o meu app de finanças quantitativas. Tá vendo? Se eu tentar entrar nele numa aba anônima aqui, ele vai me dar um 404, né, dizendo "ó, não tem nada aqui para você não, faz o login, né?". Mas não é 404, ele existe. Posso entrar aqui, tá aqui o **repositório** do Quant Brasil, só que ele é privado, tá vendo? Tem um cadeadozinho aqui dizendo que só eu, né, ou quem tá no time ali do Quant Brasil consegue ter acesso a esse código, beleza?

Então, hoje o **GitHub** permite criar tanto **repositórios** abertos, como é o Codex, quanto **repositórios** fechados, como são os seus próprios **repositórios**, beleza? Até o fim desse vídeo, eu vou criar um **repositório**, vou criar ele aberto, vou deixar ele aberto para você depois poder visualizar ele, enfim, e ver mais ou menos a mecânica de como ele funciona. O link pro **repositório** vai estar aqui na descrição depois, beleza?

## Por que Git é indispensável (especialmente com IA)

Maravilha, pessoal. Então, por que o **Git** é tão indispensável a quem programa, e mais ainda a quem programa com inteligência artificial? Toda vez que você tá trabalhando e você finaliza alguma tarefa, você quer salvar aquela tarefa. Então pense nesse ato de salvar, né? Como não meramente salvar o arquivo, mas salvar todo o estado do seu código naquele momento, como se tivesse tirando uma foto, beleza? Você tirou a foto do seu código naquele exato momento para você sempre poder voltar para ele.

Lembra quando eu falei do versionamento, né? Claro, não é um versionamento público necessariamente fazer isso que eu tô falando, mas você poderia tirar uma foto de como tá aquele seu código e aí você vai fazer alguma outra coisa. Se der algum outro problema, você reverte e volta para aquele momento onde você tirou a foto.

Isso é particularmente interessante pra gente programar com **IA**, porque, quando a gente tá programando com **IA**, a gente tá delegando para a inteligência artificial a tarefa de fazer mudanças no código. E como a gente bem sabe, nem sempre ela vai acertar. Às vezes ela pode deletar arquivos, ela pode fazer coisas, né, que você não tá esperando, ela pode quebrar uma funcionalidade que tá funcionando.

E hoje em dia, principalmente com o fato de que as IAs conseguem escrever código muito rápido, eu diria que muitas das tarefas que você passa para **IA** são basicamente descartáveis. Então eu prefiro passar algo para **IA**, ver se ela vai acertar, se ela fizer algo que eu não gosto, eu descarto. Eu não tenho problema nenhum de deletar tudo aquilo. Por quê? Porque eu sei que eu tenho o estado salvo. Meu código está versionado. Eu sempre posso voltar.

Se ela fez algo que eu gostei, aí eu continuo, tiro a foto a partir daquele trabalho da **IA** e passo pra próxima. E aí você vai tendo essa sequência de fotos, gerando esse histórico.

## O que é um commit

Esse ato de tirar uma foto é o que nós chamamos de um **commit**. Você está commitando, você está garantindo ali: "Opa, aqui tá certo, daqui pra trás, beleza? Aqui gostei de tudo que eu vi, beleza." É a ideia do **commit**.

Já vai ver isso aqui na prática. Se você vier aqui num **repositório** qualquer, como esse do Codex aqui, que é público, você consegue ter uma ideia dos **commits**. Olha lá. Aqui, ó. Veja que teve 1701 **commits** nesse **repositório** até o momento que eu gravo esse vídeo. Se eu clicar aqui, eu consigo ver exatamente as fotos que foram tiradas e por quem. Então esse cara aqui acabou de dar esse **commit**, né, com todas as modificações.

E aí o legal do **commit** é justamente isso, porque eu commito, eu salvo apenas a mudança, né, o **diff**, que a gente chama. Então eu entro aqui e consigo ver claramente o que mudou. Então eu tinha um código no estado A, fiz uma mudança, uma alteração, commitei, ou seja, salvei ele, tirei a foto de novo, e aí eu consigo em cada **commit** ver exatamente o que mudou. Por exemplo, esse aqui, o cara trocou, né, esse texto por esse. Eu consigo ver aqui, por exemplo, um outro **commit**, ó, um **commit** com mudanças, tá vendo? Modificou esse arquivo, deletou essa linha, colocou essas linhas, etc, etc.

Então eu consigo ali ter um histórico, tá vendo? É como se tudo isso aqui fossem fotos. E aí eu consigo ver, um a um, o que foi feito. Esse cara aqui, por exemplo, já mudou dois arquivos. Então ele adicionou 96 linhas, deletou 10 linhas, mexeu em dois arquivos, gostou do que viu, commitou, tirou uma foto. Então essa é a ideia: das modificações serem feitas e serem salvas em forma de **commit**, tá?

## O que é uma branch

"Rafael, salvei meu código, mas salvei aonde?" E aqui que a gente vai precisar falar do conceito de **branch**, beleza?

Veja aqui no Codex, a gente tem uma **branch** principal, tá? Essa **branch** principal aqui, no caso, está chamada de **main**. Historicamente ela é chamada de **master**. Eu prefiro sempre chamar de **master**. Primeiro porque eu aprendi assim, então cognitivamente eu sempre uso **master**. Segundo porque a mudança por trás do nome é meio bisonha. Mas seja como for, o importante é que você sempre precisa ter uma **branch** principal, beleza? Então uma **branch** **master**, uma **branch** **main**.

Quando você fizer o seu código, o seu código vai estar vivendo ali naquela **branch**. "Que é **branch**, Rafael?" Bom, **branch** literalmente no inglês significa galho, né? É uma ramificação, tá?

Então você pensa no **branch** do seguinte sentido: então eu tenho aqui o meu código representado aqui por essa bolinha aqui, tá? Então aqui eu tô na minha **branch** **master**, beleza? E ela é hoje a cabeça ali de onde eu tô trabalhando, é minha **branch**, a gente chama isso de **HEAD**. Aqui, muita gente no canal reclama quando eu falo em inglês aqui, mas é que não tem jeito, pessoal. Nomenclatura de **Git** é inglês mesmo. Nem tente abrasileirar isso aqui, que você não vai conseguir.

Então você tem **HEAD**: é onde tá apontando a sua **branch** principal, onde você tá trabalhando no momento, beleza? Então essa ferramentinha aqui, inclusive, eu criei utilizando Codex, né? Eu criei, não, Codex criou para mim aqui. E a gente vai usar ela, né? Vai ser bem meta esse vídeo, que eu tô usando essa ferramenta para mostrar para vocês. E depois nós vamos colocar esse app, esse código, aí lá no **GitHub** e a gente vai ver como fazer isso, de modo que você possa botar os seus próprios projetos lá e você consiga ver também tudo que pode acontecer de errado, beleza?

Então pensa que essa bolinha aqui representa o estado do meu código nesse momento, tá? Ó, esse aqui é o código, tá? Então esse aqui é o **repositório**. Tenho essas pastas aqui com esses arquivos aqui, beleza? Você tá vendo os arquivos que eu tenho? `app`, `index`, `readme`, `styles.css`. Então eu tenho esse conjunto de arquivos dessa forma. Como ele tá aqui agora, ele é representado por essa bolinha aqui.

## Fazendo um commit na prática

Então vamos supor que eu fiz uma mudança. Assim como o cara do Codex veio aqui e trocou uma linha por outra, eu posso vir fazer uma mudança, sei lá, eu posso vir aqui no `styles`. Aqui, essa cor accent, para um roxinho, tá? E salvar aqui de novo. Eu não estou no **Git** aqui ainda, tá? Esse **repositório** não está no **Git**. A gente vai fazer isso junto. Mas imagine que você poderia fazer isso e, pô, fiz isso e gostei. Dá um F5 aqui, testei, pô, ficou roxinho, legal, maneiro. É isso que eu quero.

Aí você vai lá e fala: "Beleza, estou satisfeito, vou commitar". Ou seja, vou tirar uma foto do **repositório** com essa mudança que eu acabei de fazer, né? Trocar o accent, a cor verde para roxo. E aí você dá um **commit**.

E aí, olha só, pessoal, o que essa minha ferramenta aqui fez. A partir do momento que você deu um **commit**, você criou uma cópia daquele seu código com a mudança feita, beleza? Então aqui você tá de novo na mesma **branch**, porque você commitou naquele mesmo código, só que ali você fez uma alteração. E aí, nesse painel lateral aqui, você consegue ver como seria o comando, tá? O comando real ali do **Git**.

Você chama **Git**. Você vai ter que instalar o **Git** na sua máquina, normalmente já vai vir com ela, mas é bem tranquilo de instalar. Você vai passar `git commit` e o nome da mensagem. Normalmente todo **commit** tem uma mensagem para você dizer o que foi feito, beleza?

Então aqui, por exemplo, esse último **commit** aqui do Codex, o cara falou que foi algo relacionado ao MCP, ó, clarificação na documentação, né? Então ele meio que uma documentação que tava meio errada, ele deu uma clarificação ali e escreveu o **commit** pra gente entender exatamente o que foi feito, beleza?

Vamos ver se a gente consegue pegar um que seja mais complexo aqui, ó. Sei lá, "added summary, a risk assessment for sandbox policy violations". Parece algo um pouco mais complexo. É, deu para ver, né? 31 arquivos mudados aqui. Deu para ver simplesmente pelo **commit**, tá? Olha o **commit** bem grande, com bastante descrição do que foi feito, etc, etc, etc. Muitas mudanças. Isso é legal porque você consegue, é como se você desse uma legenda para foto, entende? É uma legenda daquela foto que você tirou.

Então isso foi feito na **branch**, então fiz aqui na minha **branch**, beleza? Certo?

## Por que usar branches separadas

Acontece o seguinte: quando você tá trabalhando num **repositório** e você tá trabalhando, principalmente se você tá num projeto sozinho ali, é bem comum que você faça mudanças e você vai lá e vai commitando ali, ó. Ah, faço mudança um, mudança dois, mudança três, mudança quatro, etc, etc. Tô fazendo várias mudanças aqui, jogando ali pra **master**, ou seja, pra sua **branch** principal. Não tem problema nenhum fazer isso, principalmente se você tiver sozinho.

Acontece que, quando o seu projeto for crescendo, ainda mais se ele estiver em produção, muitas vezes você não quer jogar o seu **commit** diretamente pra **master**. Por quê? Porque basicamente o que acontece é que tudo que tá em **master** é o que os usuários podem utilizar.

No caso do Codex, então, tudo que tá aqui em **master**, em **main**, é a última versão do Codex, como ele deveria estar funcionando, beleza? Evidentemente, aqui no caso deles, eles estão versionados, tá? Então em algum momento você precisa cortar e fazer a versão.

Mas se a gente der um exemplo aqui, por exemplo, do Quant Brasil, se eu entrar aqui no **repositório** do Quant Brasil, a partir do momento que eu faço o **merge** em **master**, que eu coloco um código em **master**, esse **repositório** vai automaticamente estar disponível para as pessoas, beleza? Porque o Quant Brasil é um app web, então eu já tenho uma automação que, quando joga um código para **master**, ele automaticamente faz um deploy, ou seja, pega aquilo e joga pro servidor para que você possa entrar em quantbrasil.com.br e ver as modificações que eu acabei de fazer. Esse código que tá aqui vivendo em quantbrasil.com.br, ele está na minha **branch**, certo?

Então você consegue entender que, principalmente quando você tem um app em produção, você quer ter um pouquinho mais de zelo e cuidado na hora de fazer um **merge** em **master**, beleza? Então, assim, "ah, mexi aqui, olhei rapidinho, acho que tá bom, **master**" não vai funcionar muito bem quando você tiver um app maior, com cliente pagando, ou mais de uma pessoa trabalhando com você, etc, etc. Por essa razão, muitas vezes a gente trabalha numa **branch** separada.

## Criando uma branch

E aí agora entra a hora da gente entender melhor o que é **branch**. Então vamos voltar aqui pro nosso simulador. Eu tô aqui em **master**, coloquei um **commit** com uma mudança qualquer. OK, aconteceu.

E aí eu quero agora trabalhar numa nova feature. Sei lá, eu vou trabalhar numa feature chamada `change color`. Bom, então eu quero que o usuário seja capaz de trocar a cor, por exemplo, tá? Eu quero ter um color picker aqui, sei lá. É uma feature que chegou, um requisito para mim, veio para eu trabalhar nisso aqui.

Então eu posso criar essa **branch**, e aí você cria essa **branch** com esse comando aqui, ó: `git branch` e aí o nome, né?

Existem algumas convenções de como você pode criar nomes de **branch**. Não se prenda muito a isso, tá? Eu coloquei aqui `feat/` e o nome da feat. É uma forma de você olhar a **branch** e saber exatamente o que ela pretende fazer.

Outra forma bem comum, que eu costumo utilizar bastante, é se você usa um software de gerenciamento, né, como é o caso do Linear ou do Jira. Normalmente, quando você tá trabalhando em algo, ele tá atrelado a um ticket, a um issue, né? Algum código ali. E aí esses softwares, se você criar **branch** com o ID daquele ticket, ele automaticamente já vai sincronizar com o seu software. Então isso é uma boa prática também. Eu já falei sobre isso no vídeo onde eu falo de engenharia de software na prática, vou deixar o link aqui na descrição. É bem legal esse vídeo também, beleza?

Mas enfim, não se importe muito com a convenção. Fato é que agora você criou uma **branch**. Então veja, eu criei a **branch** `feat/change-color`, mas eu ainda estou em **master**, beleza? O que significa "eu criei a **branch**"? É como se eu tivesse duplicado aquele meu código. Ó, eu tinha minha foto aqui. Agora eu peguei aquela foto e agora vamos começar a trabalhar daqui exatamente como ela tava antes. Só que agora eu tô criando um outro caminho. Eu estou me ramificando. Você vai ver essa ideia da ramificação visualmente.

Agora criei a **branch**, beleza? Tirei uma cópia, e agora eu faço **checkout**, né? Eu entro naquela **branch**. Então, entrei. Agora estou trabalhando nesse ambiente dessa **branch**. Eu tinha a **branch** **master** principal, criei uma nova, que é uma cópia com os mesmíssimos arquivos, e agora saí da principal e entrei na minha cópia, beleza?

Você consegue fazer isso com um comando só, tá? Se você mandar `git checkout -b`, é a mesma coisa que você mandar o `git branch` e depois o `git checkout`, tá?

Só um detalhe para você: veja que aqui em cima, ó, o **HEAD** agora tá apontando pra **branch** que eu acabei de criar, beleza?

## Trabalhando na branch e voltando para master

Então, trabalhei agora nessa minha **branch** nova e commitei. E olha aqui, olha essa ideia aqui, pessoal. Olha visualmente como ficou isso aqui. Foi um **commit** em uma outra **branch**. Esse código que eu mudei aqui não está em **master**, ele está somente nesse estado, porque eu mudei, eu mexi no código na **branch** `feat/change-color`, não em **master**, certo?

Então eu posso seguir trabalhando aqui na **branch**, mais um **commit**. Não está em **master**, tá? Não está em **master**.

"Tá, Rafael, mas aí, peraí. Eu precisei, tava trabalhando ali na change color, mas eu precisei voltar porque deu um erro em produção." Vamos voltar pra **master** ali, então. `checkout master`. Opa, meu **HEAD** tá aqui em **master** agora.

Então, erro de produção, qual que é? Ah, vamos corrigir aqui, pá, commitei. Viram o que aconteceu? Olha lá, o **master** agora foi até pra frente, porque ele não contém essas mudanças aqui. Ele não tem essas mudanças. E da mesma forma, `feat/change-color`, essa última bolinha aqui, não tem as mudanças do meu fix, beleza?

Deu para entender, pessoal? Espero que tenha ficado claro, tá? **Git** é um pouco complicado, mas espero que com essa visualização aqui esteja melhor.

Então, eu criei uma **branch** nova, é uma cópia, fiz um **commit** na **branch** nova, fiz um segundo **commit** na **branch** nova, precisei voltar pra **master**, dei um outro **commit**. O código aqui, esse **commit** C5 não está aqui, nem C3, C4 está nessa **branch**, nem esse **commit** C5 está na **branch** color.

Acabei, resolvi o problema de produção. Vamos voltar pra **branch** novamente. Voltei para cá, olha o **HEAD** voltando. Olha o meu comando aqui, `git checkout`. Beleza.

## O que é um merge

Agora o meu código aqui em **master**, esse meu **commit** C5, não está na **branch**. Então preciso pegar essas mudanças que eu fiz ali da **branch** **master** na minha **branch** `feat/change-color`. Como que a gente faz isso? A gente faz isso chamando de um **merge**. Você une, você mescla, você pega aquilo de uma **branch** e une com a outra. Faz o **merge**.

Então eu tô aqui na **branch** color e eu vou clicar aqui para dar um **merge** de **master** na **branch**. E olha isso, o comando é `git merge master`. E aí, a partir do momento que eu fiz isso, o **commit** C5 passa a integrar essa **branch**, beleza?

Veja, eu tenho ela aqui, eu tenho as mudanças de **master** nela, **master** não tem as mudanças da **branch**. Então segui, trabalhei mais, terminei, feature pronta, testei, passei pro meu QA, passei para um outro engenheiro revisar, todo mundo gostou, posso agora jogar pra produção.

Então eu preciso pegar esse código que tá nessa **branch** e agora sim jogar ele pra **master**. Então o que eu preciso fazer? Vou para **master**, tô aqui em **HEAD**, e agora eu vou fazer o **merge**. Eu vou unir o código que estava na minha **branch** color, vou unir na minha **branch** **master**. E eu faço isso com o comando **merge** novamente.

E quando eu fiz isso, olha, se uniram de novo nessa linha aqui. E aí o comando foi basicamente `git merge` e o nome da **branch**, beleza? Então, tô na **branch** **master**, quando eu dou **merge** de outra **branch**, eu tô pegando o código que tava naquela outra **branch** e jogando na minha **branch** principal.

Pessoal, isso aqui é o **Git**, isso aqui é versionamento de código. É isso aqui que você precisa saber. Evidentemente pode ir ficando mais complexo do que isso, mas o principal tá aqui: **commit**, criar **branches**, entrar na **branch** e fazer o **merge**, ou seja, pegar o trabalho feito em uma **branch** e jogar de volta para uma **branch** principal.

## Workflow com staging

Como seria isso aqui um pouco mais próximo da realidade, tá? Eu falei: "você tá trabalhando sozinho, você faz tudo lá em **master**". Muitas vezes, no entanto, você quer testar aquela feature completamente antes de jogar ela pra produção.

Então é comum que a gente tenha uma **branch** chamada **staging** ou **develop**, né? São nomes que você vai ver comumente por aí, tá? Então, a **branch** **staging**, ela é uma **branch** colocando modificações aqui nela. Quando você tiver satisfeito, "quero fazer um release, quero fazer aquilo, jogar aquele código novo pra produção", eu vou lá pra **master** e dou um **checkout** para **master**, faço o **merge** de **staging**. Pronto, tá aqui o meu novo **master**, as modificações de **staging**.

Mas daí continuo trabalhando em **staging**, **checkout** para **staging**, mais um **commit**, mais um **commit**. Ah, terminei. Vamos lá para **master**. **Checkout** para **master**. **Merge** **staging**, mais um release feito, beleza?

Então, este seria mais ou menos o workflow ali. Evidentemente, quando você tem um time maior ou você tá trabalhando ali com Linear da vida, o seu workflow vai ser ligeiramente diferente.

## Múltiplas features em paralelo

Então, vamos supor que a gente tem aqui essa **branch** **staging**. Criei a **branch** **staging**, entrei nela aqui, beleza? Então tô aqui em **staging**, fiz um **commit**, **staging** tá diferente do que tá em **master**, beleza?

Normalmente você vai estar trabalhando, vai ter ali 10 desenvolvedores trabalhando ao mesmo tempo, tudo mais. Você vai fazer o seguinte: você quer testar todas aquelas mudanças, assim como o Codex. Veja, se você entrar aqui no release do Codex, olha quantas mudanças eles fizeram nesse release. Foram diversas **branches** aqui que foram feitas o **merge** pra gente poder ter esse novo release com todos esses códigos, beleza? Então eles juntam um monte de coisa e fazem o release. É uma forma de você gerenciar o seu software, beleza?

Então normalmente você vai fazer uma **branch** a partir do seu **staging**, né? Então, de **staging**, eu vou criar aqui uma feature `change-color`. Então criei essa **branch**, vou entrar aqui em `change-color`, vou trabalhar. Então veja, ela é a partir de **staging**.

Então você consegue ver aqui que tá tendo um monte de modificação, né? Tendo vários níveis. Então, o developer um tá trabalhando em `change-color`. Aí veio, por exemplo, o developer 2, ou o mesmo developer trabalhando em mais de uma feature ao mesmo tempo. Se você tá trabalhando em paralelo, como eu falei no meu vídeo lá do YouTube, você pode estar com várias **branches** ao mesmo tempo, né?

Então tô ali, criei uma feature `add-scroll-bar`, sei lá, uma outra feature aqui. Criei a partir de **staging**. Vou dar aqui o **checkout** pra **branch** e trabalhei nela. Pá, mais uma aqui, ó. `feat/scroll-bar`, beleza?

Parece aqui, da forma como foi feita aqui, parece que ele tá passando pro `change-color`, mas não precisa necessariamente. Deixa eu voltar aqui para ficar mais claro. Se eu não fizer isso, eu entrar aqui em `change-color`, entrei na **branch** color, dei um **commit**, beleza? Agora vou entrar na **branch** **staging**, dei um **commit** em **staging**. Agora vou entrar na **branch** `scroll-bar`, dei um **commit** em `add-scroll-bar`.

Como disse, né, parece que necessariamente ele passa por `feat/change-color`. Não é verdade. Eu poderia ter aqui uma outra linha, né, vindo daqui, beleza?

E aí tô trabalhando, então tô trabalhando aqui em `add-scroll-bar`. Ao mesmo tempo, eu ou outra pessoa tá trabalhando ali em `change-color`. O cara do `change-color` foi lá, terminou. Beleza, terminei esse meu trabalho, deixa eu ir lá pra **staging** e deixa eu fazer o **merge** de `change-color`, ou seja, finalizei isso aqui ou uni eles aqui.

E aí a pessoa que tá ali trabalhando em `add-scroll-bar` segue trabalhando, segue trabalhando, finalizou, beleza, vai ali pra **staging**. Tô aqui em **staging**, **merge** de `add-scroll-bar`. Tá, juntei aqui. E agora o meu **staging** tem essas duas features, tanto `change-color` quanto `add-scroll-bar`.

E agora eu quero fazer um release pra produção. Quero jogar essas duas features lá no meu código principal. Vou pra **master**, faço **merge** de **staging** para unir todo mundo aqui. Beleza, pessoal? Deu para entender aqui? Veja como é essa ideia de ramificação. Por isso que a gente chama de **branch**, tá? Ramificando, certo?

Muito bem. Então isso aqui é o principal do que você precisa saber. E aqui eu quis te mostrar visualmente.

## Criando um repositório no GitHub na prática

Agora vamos criar esse **repositório** na prática, tá? Eu tô aqui nessa pasta, beleza? Eu criei uma pasta normal aqui no meu computador, onde eu botei esse código, tá? Criei ele aqui com o Codex. Tô com essa sessão com Codex aqui rodando. Beleza, gostei. Agora eu quero jogar, né, no **GitHub**, para que mais pessoas consigam mexer ou olhar esse código, por exemplo.

Então, eu vou entrar aqui no meu **GitHub**, tá aqui o meu perfil do **GitHub**. Você vai lá, cria uma conta no **GitHub**, é bem fácil, de graça, tudo mais. E aí você vem aqui em "create new" e "new repository". Cria um novo **repositório**.

E aí eu vou chamar isso aqui de `git`, é o nome do meu **repositório**, tá dentro aqui do meu perfil, né? E eu vou falar "a project on git operations", beleza? Descrição. Mind. Visibilidade pública ou privado. Vou deixar aqui público para que vocês possam ver depois. Não preciso de template. Vou deixar tudo sem nenhuma configuração por enquanto. Ó, README, gitignore (é muito importante o gitignore, já vou falar dele), license (não preciso de licença), só vou criar o **repositório**, beleza?

Tá aqui criado o **repositório**, só que ele não tem nada, né? Não tenho nada aqui, não tenho nenhum arquivo, não joguei nada ali para ele, beleza?

## Conectando código local ao GitHub

Então, o que eu vou fazer? O seguinte: eu agora, do meu terminal, vou conectar esse meu código ao **repositório**. Então eu vou rodar, primeiro comando que eu preciso fazer é rodar esse `git init`. Então `git init`, inicializei o **repositório**, beleza, pessoal?

Então, inicializei. Aí aqui eu vou fazer algo que eu, como falei, gosto de trocar o nome de **main** para **master** por diversas razões. Então tô aqui com o meu **repositório** em **master** normalmente.

E aí, vamos seguir aqui o que o próprio **GitHub** instrui a gente a fazer. Primeiro ele fala pra gente dar um `git add`. E aí, o que seria isso, pessoal? Se você rodar um comando chamado `git status`, você vai conseguir ver aqui tudo que você modificou no seu **repositório** que não foi commitado antes, tá? Então, o que foi modificado desde aquela sua foto anterior pra foto atual?

Bom, quando você dá o status aqui, ele te fala: "Eu tô na **branch** **master**, nenhum **commit** ainda e aqui os arquivos que estão untracked", ou seja, ele não viu esse arquivo ainda, ele não tinha visto esses arquivos, beleza?

E aí o **Git** fala "ó, rode o comando `git add` e o nome do arquivo para incluir eles, né, para serem commitados", ou seja, para incluir ele na foto que você vai bater.

Eu vou dar um reload aqui no Cursor ou no VS Code, só para você ver aqui, ó, que se você tiver a extensão do GitLens, você consegue visualizar aqui no próprio VS Code ou no Cursor algumas informações relevantes. Então aqui, por exemplo, tá o source control com todas as mudanças.

Você pode fazer por aqui também, ó, clicar nesse botãozinho de mais aqui ou ver aqui o status. E dá basicamente `git add .`. Ponto significa que dentro desse **repositório**, como eu tô na raiz da pasta, todos os arquivos vão ser commitados. Então, vocês viram, automaticamente aqui ele já foi pro staged, ou seja, o arquivo tá pronto para ser lançado, né? Tá staged, tá ali pronto para você lançar ele pra nuvem, para o **repositório** localmente.

Se eu der agora um `git status` de novo, ele me fala: "ó, as mudanças para serem commitadas", tá? Então, se eu sem querer não queria commitar isso aqui, ó, eu posso dar um `git rm` ou, se eu tiver usando a interface aqui, eu posso vir nesse menuzinho aqui, ó, por exemplo, tá? Não quero jogar o README. Aí, tá vendo, ó? Ele já me fala aqui, ó, "se quiser, adiciona o README". Posso adicionar ele por aqui.

Então, faz o que você preferir utilizar. Se você tiver usando uma IDE, é bem legal fazer por aqui, mas é importante também entender na CLI, porque, se você estiver programando com **IA**, muito comumente você vai estar usando um Claude Code, um Codex, algo do tipo. E aí é interessante ter isso configurado na sua CLI também. O que é CLI? Command line interface, o famoso terminal, beleza?

## Fazendo o primeiro commit e push

Então, ó, demos o `add` e agora falta dar o **commit**. Lembra dos nossos exemplos aqui? Sempre tinha um **commit** quando você fazia modificação. Pense que essas, esses cinco arquivos que eu mexi aqui, é um **commit**. Eu saí de zero, não tinha nada e tirei minha primeira foto. Então, naturalmente, o **commit** vai conter todas as modificações, todas as linhas de código que eu escrevi.

Então, posso simplesmente dar um **commit** aqui, ó, algo do tipo `first commit`. E aí você passa aqui `-m`, **m** de mensagem, e o texto ali entre aspas, né? E ele já falou: beleza, funcionou. Vê que naturalmente já sumiu. Aqui não tem mais nada, né, modificado que não tenha sido entendido pelo **Git**. Acabei de bater a minha foto.

Beleza, bati minha foto. E o que eu preciso agora? Agora eu preciso jogar ele pra nuvem. E aí o comando que você vai rodar só uma vez na vida, assim como `git init`, você vai precisar rodar esse `git remote add origin`. E aí, né, github.com, blá, blá. Isso aqui é para você linkar o seu **repositório** com o **GitHub** necessariamente. Então, linkou, beleza.

E agora é só jogar pra nuvem. Eu ainda não joguei, eu só linkei ele. Eu tirei a foto e linkei. Agora eu quero jogar lá pro **GitHub**, tá? Como que eu faço isso? `git push`, eu tô empurrando, tô jogando esse código lá pra nuvem.

E aí você pode jogar aqui simplesmente `origin head`. O que é isso? Da origem de onde eu tô localmente, pra **HEAD**, a **branch** que eu tava. Lembra do **HEAD** que a gente viu aqui sempre? Ó, o **HEAD** apontando para **master**.

Eu poderia fazer aqui também `origin master`, beleza? Eu gosto de usar **HEAD** porque ele sempre vai na **branch** que eu tô. Então, se eu tiver às vezes numa outra **branch** e der um push numa errada, dá uma confusão danada. Então eu prefiro sempre utilizar **HEAD** que eu sei que ele sempre vai jogar pra **branch** que eu tô, beleza?

Se eu der um `push origin head`, a minha **HEAD** tá apontada pra **master**. Tá aqui, ó, os objetos, o que ele fez? Pá, pá, pá, pá. Criou ali uma nova **branch** **master**, fez o push, beleza?

Se eu vier aqui agora no meu **repositório** e der um F5, agora eu consigo ver tudo. Agora eu consigo ver os meus arquivos, inclusive o **commit**, quando ele foi feito, o meu README fica bonitinho, etc, etc. Então tá aqui como você faz para jogar um código para o **GitHub**, beleza, pessoal? O que eu precisei fazer? `git add`, `git commit`, `git push`. Acabou.

## Trabalhando direto em master

Se eu fizer isso, eu posso ficar fazendo diretamente em **master**, tá? Então, sei lá, vamos supor que agora a gente vai trocar essa cor aqui do roxinho para um rosa, beleza? Salvei aqui, atualizei. Ah, gostei dessa corzinha. Vamos fazer o seguinte, ó.

Olha lá. Viu como eu alterei? Ele automaticamente já me mostrou aqui o arquivo que eu mexi. Se eu clicar aqui, ó, ele já me fala exatamente. Eu tirei essa linha e adicionei essa. É o que ele chama de um **diff**. É um `git diff`. Tô vendo a diferença. A ideia é legal que ela te dá essa visualização. Consigo visualizar a CLI um pouco pior, beleza?

Posso fazer a mesma coisa aqui do **commit**, só que agora vamos utilizar o IDE, Cursor, VS Code, todos eles vão funcionar. Posso dar um `add` por aqui, mesma coisa que dar o `git add` no terminal. E posso escrever um **commit**. Posso escrever aqui o que eu fiz, ou nas IDEs mais modernas, ele tem até esse botãozinho aqui que ele vai gerar a mensagem automaticamente com **IA**. Então, ó, já falou até o que ele fez aqui.

Então acabei de bater uma outra foto com o meu botãozinho rosa e já publiquei, ou seja, já dei o push pra produção, pra minha **branch**. Dei um F5 aqui. Olha lá, dois **commits**. Inclusive, sabendo exatamente qual foi o último **commit**, posso vir aqui agora e ver o histórico de todas as minhas mudanças, exatamente como nós fizemos aqui: o histórico de todas as minhas mudanças, incluindo, né, a linha que foi modificada. Então essa é uma grande vantagem de você ter um cliente **Git**: você poder visualizar ali aquilo que você tá fazendo no terminal ou na sua IDE, beleza?

## Trabalhando com branch e IA

Então, o que mais que eu quero mostrar para vocês agora na prática? Vamos pensar numa feature aqui, tá? Eu notei que, quando eu adiciono muita coisa aqui, o scroll vai ficando, vai scrollando para cá e aqui fica uma área vazia, tá vendo? Eu quero mudar isso aqui. Então, eu vou criar uma feature e eu quero fazer com que isso aqui seja um scroll panel, né? Que ele não cresça para cá, né? Que ele fique sempre fixo e que só apareça o scroll diretamente nesse painel do lado direito aqui.

Então, beleza, pessoal. Vamos implementar o scroll. Vou inicializar o Claude, OK? E aí eu vou falar para ele o que eu quero fazer. Então, basicamente falei para ele assim: "Use a ferramenta do **GitHub**, que é esse `gh` tool". Pessoal, é muito importante que, se você está trabalhando com **GitHub** e com **IA**, instale localmente a CLI do **GitHub**, tá? Vai permitir que **IA** faça operações diretamente ali no **GitHub**, o que é bem bom.

Então tá, a primeira coisa que ele quis fazer aqui, rodar o comando para criar uma **branch**. Lembra que a gente viu `checkout -b`? `-b` é para criar a **branch** `feature/right-panel-scroll`. Então ele já criou a **branch** e já entrou nela. Naquela minha ferramenta, a gente criava a **branch** e depois entrava nela. Aqui esse comando é o que você precisa saber.

Então ele já trocou de **branch**. Então, se eu vier aqui pro meu VS Code, ó, eu até consigo ver aqui embaixo que ele tá numa **branch** nova, tá? Ele vai trabalhar, já identificou, vai fazer modificação. OK, beleza, ele terminou aqui. E aí ele até já me perguntou se eu quero que ele commite.

Vamos ver primeiro se tá funcionando. Então atualizei aqui. Vamos botar um monte de **commit** aqui. Ah, beleza. OK. Não deveria ter esse scroll aqui, mas ó, agora não foi mais todo mundo. Tá vendo? O scroll apareceu aqui só do lado direito.

Vou falar para ele o seguinte. Então falei para ele: "ó, tá funcionando perfeitamente do lado direito, mas eu não quero o scroll no canvas". É uma modificação simples aqui que ele fez. Beleza, vamos adicionar o **commit** aqui. Perfeito. Exatamente o que eu queria. Tô pronto para tirar a foto. Eu consigo entrar aqui e ver onde foram feitas as modificações.

E aí, beleza? Agora eu posso até pedir para ele aqui, ó. "Alright, commit and push". Então, da própria **IA**, eu consigo interagir, pedir para ele fazer o **commit** e fazer o push para mim. E você vai ver todos os comandos que ele vai rodar. `git status` para ver o que foi modificado. O `git diff` para ver exatamente a modificação. Esse `git log` aqui você pega o que foi feito antigamente, e aqui ele tá dando o `add` dos arquivos que foram modificados e já concatenando com o **commit**, ó, beleza?

OK, funcionou. Vamos deixar ele dar o push. E agora, ó, ele deu `git push -u origin`. E aí ele passou o nome da **branch**. Lembra? Lembra que eu falei que eu prefiro **HEAD** por causa disso? Você não precisa ficar escrevendo o nome da **branch** toda hora. Mas pode ser assim também: `git push -u`, **u** de upstream. E aí ele acabou de fazer esse push.

## Pull Request

Só que agora, pessoal, tem uma coisa interessante. Veja, eu dei o push numa **branch**, só que se eu entrar aqui no meu **repositório**, olha o que vai acontecer. Eu tô na **branch** **master**, não mudou. Se eu entrar aqui na minha modificação, ó, o último **commit** foi de 10 minutos atrás. Só que olha o que tá aparecendo aqui. Aparecendo aqui um banner do **GitHub** falando que uma nova **branch** foi criada. Essa **branch** `feature/right-panel-scroll`, que eu posso até entrar aqui e ver, ó. Aí nela aqui sim eu consigo ver. Olha lá, o **commit** pertence a essa **branch**. Foi aquilo que nós vimos aqui, certo? É um **commit** que pertence a essa **branch** feat. Ela não está aqui em **master**, beleza?

Então eu quero agora pegar o que eu mexi na minha **branch** e jogar lá pra **master**. Você pode fazer isso dando **merge**, como nós vimos ali na simulação, mas, quando você tá trabalhando na vida real, normalmente você vai fazer o que se chama de um **pull request**.

O que é isso, pessoal? Quando eu clicar no botão ali, a própria interface do cliente — é importante dizer que isso aqui não é algo do **Git**, tá? Isso é algo dos clientes que implementam o **Git**, por exemplo, **GitHub** — você vai ver essa tela aqui que tá dizendo basicamente o seguinte, ó. A minha **branch** base é a **master**, ou seja, eu estou querendo jogar lá, beleza? E a **branch** que eu estou comparando, que eu modifiquei e quero jogar pra base, é a **branch** `feature/right-panel-scroll`.

E aqui no próprio cliente você consegue colocar o que é o título, o que eu quis fazer aqui, né? Aqui eu tô juntando um conjunto de modificações, pode ter, sei lá, 15 **commits** aqui. E eu tô falando: ó, tô colocando essa nova funcionalidade. Tá aqui o título e uma descrição do **PR** (pull request). Como foi gerado pela **IA**, fica até bem legal. A gente consegue ter uma descrição bem boa do que foi feito.

Clico para criar o **PR**. Viu que ele rodou alguns checks aqui. Isso é porque eu tô no **GitHub**. Então, se você configura isso e você tá num time maior, você consegue rodar testes, rodar linter, verificar que nada tá quebrando, beleza?

E aí, beleza, você tá com seu **PR** criado. E o que eu preciso fazer aqui agora é fazer esse **merge**, tá? Posso dar o **merge** normal. Se eu tivesse mais de um **commit**, eu gosto de fazer com **squash and merge**, que basicamente o **squash and merge** pega todos os **commits** de uma **branch** e faz squash, né? Comprime eles em um **commitzão**, né, para aquela **branch**. Isso deixa o histórico mais fácil, né? Mas não é obrigado a fazer isso não, tá?

E a outra opção seria fazer com **rebase**. Eu não vou cobrir o **rebase** nesse vídeo. Claramente uso o **rebase** e, se você tá trabalhando com outras pessoas, muito dificilmente você vai utilizar o **rebase** também. Então vamos focar aqui hoje só no **merge**.

Vou fazer o **merge** desse PR. Confirmei o **merge**. Tenho aqui uma interface do PR que eu poderia passar para algum outro reviewer, posso colocar uma pessoa para dar uma olhada, posso colocar uma label, enfim, consigo olhar o que foi proposto de ser feito antes de fazer o **merge**.

## Pull para sincronizar local

Agora que eu fiz o **merge**, eu tô com código em **master**, olha lá, com um **commit** que foi feito 4 minutos atrás. Só que veja uma coisa interessante, pessoal. Se eu for para **master** aqui, veja, vamos dar uma olhada qual foi a mudança feita aqui. A mudança foi essa aqui, ó. Linha 53, height, tiramos `min-height` e botamos `height`. Foi uma das mudanças, né?

Se eu entrar em **master** aqui, vamos na linha 53. Opa, ainda tô com `min`. Ué, mas eu não acabei de fazer o **merge**? Sim, na nuvem. Mas agora eu quero buscar essas mudanças para mim aqui no meu computador. Então eu preciso dar um **pull**, eu preciso puxar as mudanças que estão lá na nuvem pro meu **repositório** local.

Então eu dou aqui um `pull origin master`, né? Quero puxar o que tá em **master**. E aí agora eu peguei aquela modificação que foi feita por outra pessoa — aqui no caso foi feito pelo Claude Code, mas pensa que você tá trabalhando num time com cinco desenvolvedores, todo mundo tá colocando código lá, você quer pegar aquele código mais atualizado, beleza?

Então fiz um push, criei um **pull request**, aprovei o **pull request**, fiz o **merge**, entro na minha **branch** principal de novo e faço o **pull** para pegar aquele dado mais recente, beleza, pessoal?

## Conflitos

Muito bem, pessoal. A última coisa que eu quero mostrar nesse vídeo, que é algo que acontece com bastante frequência, é o que nós chamamos de **conflito**, tá?

Veja, a gente tá fazendo **merge**, tá juntando códigos que estão vindo de fontes separadas. O que acontece se mais uma pessoa mexer na mesma linha ao mesmo tempo? Aí acontece um **conflito** e você precisa resolver esse **conflito**. Eu vou mostrar para você como isso acontece na prática, beleza?

Então vamos supor o seguinte: vamos supor que eu criei uma **branch** aqui para trocar de cor principal, tá? A accent color. Então, criei uma nova **branch**. OK, não gostei desse rosa. Vou aqui pra um verde. Beleza, troquei, salvei, vejo aqui o que modificou. Posso dar um **commit** aqui, `change accent color`. Vou dar até um push aqui, `origin head`, para que essa minha mudança vá lá, para que alguém possa revisar, dar uma olhada se realmente eu posso fazer o **merge** aqui, beleza?

Daí o push, olha lá, já até apareceu o PR aqui para mim. Posso criar o PR. Tranquilo. Esse PR vai jogar da minha **branch** `change-accent-color`.

Mas agora vamos supor o seguinte, pessoal. Vamos supor que um outro programador estava trabalhando em uma outra **branch**, beleza? E esse cara, né, já fez o **merge**. Enquanto eu tava trabalhando naquela **branch**, esse cara veio e já trocou a cor de novo. Ele trocou por esse amarelo. Só que por algum acaso o **merge** dele saiu mais rápido que o meu. Então eu vou fazer aqui o **merge** diretamente em **master** para vocês verem.

Então, esse cara, por alguma razão, o **merge** dele saiu na frente. Ele fez lá o **commit**, jogou em **master**. E agora, ó, ele vai ter, no **repositório**, eu consigo ver que em styles, beleza, a cor tá para amarelo.

E o que aconteceu com o meu PR? Se você entrar aqui, ó, agora eu não posso mais fazer o **merge**. Por quê? Porque o **GitHub** já identificou um **conflito**, certo?

O que é o **conflito**? Aqui nós dois tentamos mexer na mesma coisa. Fica quem? Quem que fica? Tá aqui, ó. Current change é o que tá lá em **master**. Incoming change é o que eu quero fazer, beleza?

E aqui eu preciso decidir. Você pode resolver esse **conflito** aqui diretamente na interface do **GitHub**. Fica um pouco feio, né, você fazer por aqui. É um pouco ruim. Resolvi, poderia marcar aqui como resolvido e fazer um **commit** diretamente por aqui, tá? É uma forma de fazer.

Ou o que talvez seja mais comum é você tá ali na sua **branch**, né? `chore/change-accent`. Então, tô lá trabalhando na minha **branch** `change-accent`. Um monte de gente saiu mexendo em **master**. Eu quero pegar as atualizações deles. Então eu dou um **merge** de **master**. Eu pego tudo que tá lá em **master** aqui para mim. E quando eu dou o **merge**, olha o que acontece. **Conflito**, beleza?

Então tá aqui, ó, entre o que eu queria fazer, que é a minha mudança atual, e o que tá vindo lá de **master**, né, que é o que o cara fez lá na mudança, trocando a cor para amarelo. Mas não, eu falei com designer e realmente o que eu quero fazer é deixar verdinho. E aqui é a mesma coisa.

Você pode vir aqui deletar na mão a linha ou, se você tiver na IDE, você tem até facilidade de clicar nesses botõezinhos aqui, ó. O current change, essa aqui não tá dando muito bem para ler aqui. Por causa... aí agora dá para ler melhor. Current change foi essa linha aqui, é o que eu quero, é o verdinho. Cliquei aqui, ele já atualizou. Você vê que fica até vermelho aqui na IDE. Essa é uma das vantagens.

E pronto, posso mudar. Resolvi o **conflito**. Cliquei em sync change. É basicamente a mesma coisa que fazer um push. E ó, automaticamente aqui gerou um **commit** novo e agora eu já posso fazer esse **merge**, beleza?

E agora eu vou mostrar para você o que é fazer o **squash and merge**. Se eu fizesse o **merge** normal, eu ia ter dois **commits** aqui, né? Eu faço o **squash and merge**, eu tenho um **commit** só agora.

E aí se a gente entrar aqui agora, tá aqui, ó. Inclusive eu consigo dar uma olhada aqui e ver de onde veio o PR que mudou aquele arquivo. Beleza, pessoal? Maravilha.

## Conclusão

Pessoal, espero que tenham gostado desse guia completo sobre **Git** para você que quer programar com inteligência artificial. Obviamente, não é só para quem quer trabalhar com **IA**, beleza? Todo programador precisa saber **Git**. Mas aqui nesse vídeo eu quis dar um apanhado geral do 95% do que você precisa saber.

Se você sabe isso que eu te ensinei no vídeo de hoje, você já tem basicamente tudo que você precisa para trabalhar com **Git**, ter código versionado, poder ter tranquilidade em trabalhar com a **IA**, sabendo que qualquer coisa você tem ali um snapshot, você consegue voltar para aquele código.

Eu não mostrei aqui no **GitHub** como você faz para fazer isso. Fica para uma outra aula. Se você quiser que eu faça uma continuação mais avançada, me conta aqui nos comentários. Mas basicamente o que você precisa é ter essa paz de espírito. Modifiquei o meu código, bati um **commit**, tirei uma foto, crio **branch**, trabalho isoladamente nas **branches**, tô satisfeito, jogo para **master**, faço **merge** para **master** e assim sucessivamente. É esse o trabalho de um engenheiro de software.

Se você gosta de inteligência artificial e programação, esse canal é para você. Então já te peço por gentileza, se inscreva nesse canal, curta e compartilhe com seu amigo e sua amiga. Se você puder, hype a gente aí, se você achar a opção aí no YouTube, hype, que ajuda bastante a gente com o algoritmo. Agradeço a audiência de sempre e até a próxima.
