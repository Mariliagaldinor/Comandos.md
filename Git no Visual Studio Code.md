Como usar a integração do Git no Visual Studio Code

Introdução
O Visual Studio Code (VS Code) tornou-se um dos editores mais populares disponíveis para o desenvolvimento Web. Ele ganhou toda essa popularidade graças às suas muitas funcionalidades integradas, incluindo a integração do controle de código-fonte, sendo esta, feita com o Git. Aproveitar o poder do Git dentro do VS Code pode tornar seu fluxo de trabalho mais eficiente e robusto.

Neste tutorial, você irá explorar o uso da Integração de controle de código-fonte no VS Code com o Git.

Pré-requisitos
Para concluir este tutorial, você precisará do seguinte:

O Git instalado em sua máquina. Para mais detalhes sobre como fazer isso, reveja o tutorial Começando com o Git.
A versão mais recente do Visual Studio Code instalada em sua máquina.
Passo 1 — Familiarizando-se com a guia de controle de código-fonte
A primeira coisa que você precisa fazer para aproveitar a integração do controle de código-fonte é inicializar um projeto como um repositório do Git.

Abra o Visual Studio Code e acesse o terminal integrado. Abra ele usando o atalho no teclado CTRL + ` no Linux, macOS ou Windows.

Em seu terminal, crie um diretório para um novo projeto e vá até esse diretório:

mkdir git_test
cd git_test
Em seguida, crie um repositório do Git:

git init
Outra maneira de fazer isso com o Visual Studio Code é abrindo a guia de controle de código-fonte (o ícone se parece com uma divisão na estrada) no painel esquerdo:

Ícone do controle de código-fonte

Em seguida, selecione Open Folder:

Captura de tela mostrando o botão Open Folder

Isso irá abrir seu explorador de arquivos no diretório atual. Selecione o diretório de projeto de sua preferência e clique em Open.

Em seguida, selecione Initialize Repository:

Captura de tela mostrando o botão Initialize Repository

Se você verificar agora seu sistema de arquivos, verá que ele inclui um diretório .git. Para fazer isso, use o terminal para navegar até o diretório do seu projeto e liste todo o seu conteúdo:

ls -la
Você verá o diretório .git que foi criado:

Output
.
..
.git
Agora que o repositório foi inicializado, adicione um arquivo chamado index.html.

Depois de fazer isso, você verá no painel Source Control que seu arquivo novo aparece com a letra U ao seu lado. U representa untracked file (arquivo não rastreado), o que representa um arquivo novo ou alterado, mas que ainda não foi adicionado ao repositório:

Captura de tela de um arquivo não rastreado com o indicador da letra U

Agora, clique no ícone mais (+) ao lado da listagem de arquivos do index.html para rastrear o arquivo pelo repositório.

Depois de adicionado, a letra ao lado do arquivo irá mudar para um A. A letra A representa um novo arquivo que foi adicionado ao repositório.

Para fazer o commit com suas alterações, digite uma mensagem de confirmação na caixa de entrada no topo do painel Source Control. Em seguida, clique no ícone confirma para fazer o commit.

Captura de tela de um arquivo adicionado com o indicador da letra A e mensagem de commit

Depois de fazer isso, ficará evidente que não há alterações pendentes.

Em seguida, adicione um pouco de conteúdo ao seu arquivo index.html.

Use um atalho do Emmet para gerar um esqueleto HTML5 no VS Code pressionando o ! seguido pela tecla Tab. Vá em frente e adicione algo no <body>, como um título <h1>, e salve.

No painel do controle de código-fonte, você verá que seu arquivo foi alterado. Ele irá exibir a letra M ao lado dele, que representa um arquivo ter sido modificado:

Captura de tela do arquivo modificado com o indicador da letra M

Para fins de prática, vá em frente e também confirme essa alteração.

Agora que está familiarizado com o painel do controle de código-fonte, vamos seguir em frente para a interpretação de indicadores de medianiz.

Passo 2 — Intepretando indicadores de medianiz
Neste passo, você irá dar uma olhada naquilo que chamamos de “Medianiz” no VS Code. A medianiz é a área estreita à direita do número da linha.

Se você já usou o dobramento de código antes, os ícones maximize e minimize ficam localizados na medianiz.

Vamos começar fazendo uma pequena alteração no seu arquivo index.html, como uma mudança no conteúdo dentro da etiqueta <h1>. Depois de fazer isso, você irá notar uma marca azul vertical na medianiz da linha que você mudou. A marca azul vertical significa que a linha de código correspondente foi alterada.

Agora, tente excluir uma linha de código. Exclua uma das linhas na seção <body> do seu arquivo index.html. Observe agora na medianiz que há um triângulo vermelho. O triângulo vermelho indica uma linha ou grupo de linhas que foi excluída.

Por fim, no final da sua seção <body>, adicione uma nova linha de código e note a barra verde. A barra vertical verde indica uma linha de código que foi adicionada.

Este exemplo retrata os indicadores de medianiz para uma linha modificada, uma linha removida e uma nova linha:

Captura de tela com exemplos dos três tipos de indicadores de medianiz

Passo 3 — Comparando arquivos
O VS Code também tem a capacidade de executar uma comparação em um arquivo. Normalmente, seria necessário baixar uma ferramenta de comparação separada para fazer isso, de forma que essa funcionalidade integrada pode ajudar a aumentar a eficiência do seu trabalho.

Para visualizar uma comparação, abra o painel do controle de código-fonte e clique duas vezes em um arquivo alterado. Neste caso, clique duas vezes no arquivo index.html. Você será levado para uma visualização de comparação típica, com a versão atual do arquivo à esquerda e a versão previamente confirmada do arquivo à direita.

Este exemplo mostra que uma linha foi adicionada na versão atual:

Captura de tela com um exemplo de uma visualização em tela dividida de uma comparação

Passo 4 — Trabalhando com ramificações
Indo para a barra inferior, você tem a capacidade de criar e trocar ramificações. Observando na região mais baixa e à esquerda do editor, você deve ver o ícone do controle de código-fonte (aquele ícone que se parece com uma divisão na estrada) muito provavelmente seguido por master ou o nome da ramificação de trabalho atual.

Indicador de ramificação na barra inferior do VS Code exibindo: master

Para criar um branch, clique no nome do branch. Um menu deve aparecer dando-lhe a capacidade de criar um novo branch:

Prompt para criar uma nova ramificação

Vá em frente e crie uma nova ramificação chamada test.

Agora, faça uma alteração em seu arquivo index.html que indique que você está no novo branch test.

Confirme essas alterações na ramificação test. Em seguida,clique no nome da ramificação no canto inferior esquerdo novamente e volte para a ramificação master.

Depois de retornar para a ramificação master, você irá notar que o texto this is the new test branch (esta é a nova ramificação de teste) confirmado na ramificação test não está mais presente.

Passo 5 — Trabalhando com repositórios remotos
Esse tutorial não irá abordar este tema em profundidade, mas através do painel do controle de código-fonte, o trabalho com repositórios remotos está disponível. Se você já trabalhou com um repositório remoto, irá notar alguns comandos familiares como pull, sync, publish, stash, etc.

Passo 6 — Instalando extensões úteis
O VS Code vem com muitas funcionalidades integradas para o Git, mas, além delas, também existem diversas outras extensões bastante populares que adicionam funcionalidades extras.

Git Blame
Essa extensão dá a capacidade de visualizar informações do Git Blame na barra de status para a linha atualmente selecionada.

Isso pode parecer intimidante, mas não se preocupe, a extensão do Git Blame tem muito mais a ver com a praticidade do que fazer qualquer pessoa se sentir mal. A ideia de “blaming” (culpar) alguém por uma alteração no código não tem a ver com apontar o erro para a pessoa, mas sim identificar o indivíduo certo a se questionar a respeito de determinadas partes do código.

Como pode ser observado na captura de tela, essa extensão fornece uma mensagem sutil relacionada à linha atual de código em que você está trabalhando na barra de ferramentas inferior, explicando quem fez a alteração e quando ela foi feita.

Git Blame na barra de ferramentas inferior

Git History
Embora seja possível visualizar alterações atuais, executar comparações e gerenciar ramificações com as funcionalidades integradas do VS Code, ele não oferece uma visualização aprofundada em seu histórico do Git. A extensão do Git History resolve esse problema.

Como pode-se ver na imagem abaixo, essa extensão permite explorar meticulosamente o histórico de um arquivo, um determinado autor, uma ramificação, etc. Para ativar a janela do Git History mostrada abaixo, clique com o botão direito em um arquivo e escolha Git: View File History:

Resultados da extensão Git History

Além disso, é possível comparar branches e commits, criar branches de commits e muito mais.

Git Lens
O GitLens incrementa as capacidades do Git integradas no Visual Studio Code. Ele ajuda a visualizar a autoria do código rapidamente através das anotações do Git blame e lentes de código, navegar e explorar repositórios do Git, ganhar informações valiosas via comandos poderosos de comparação, e muito mais.

A extensão Git Lens é uma das mais populares na comunidade e também é a mais poderosa. Na maioria dos casos, ela pode substituir cada uma das duas extensões previamente discutidas com sua funcionalidade.

Para informações de “culpa”, uma mensagem sutil aparece à direita da linha em que você está atualmente trabalhado e informa quem fez a alteração, quando ela foi feita e a mensagem de confirmação associada. Existem algumas informações adicionais que aparecem ao passar o mouse nesta mensagem, como a alteração do código em si, o carimbo de data/hora e mais.

Funcionalidade do Git Blame no Git Lens

Para informações do histórico do Git, essa extensão fornece várias funcionalidades. Você tem acesso fácil a diversas opções, incluindo exibir o histórico de arquivos, realizar comparações com versões anteriores, abrir uma revisão específica, e muito mais. Para abrir essas opções, clique no texto na barra de status inferior que contém o autor que editou a linha de código e há quanto tempo ela foi editada.

Isso irá abrir a seguinte janela:

Funcionalidade do Git History no Git Lens

Essa extensão é lotada de funcionalidades, e pode levar um tempo para aprender sobre tudo o que ela tem a oferecer.

Conclusão
Neste tutorial, você explorou como usar a integração do controle de código-fonte com o VS Code. O VS Code é capaz de lidar com muitas funcionalidades que anteriormente exigiriam baixar uma ferramenta separada.
