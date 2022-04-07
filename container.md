Como Usar o Container

O container também pode ser qualquer uma das tags semânticas do HTML5, como <nav>, <header>, <section>, <aside>, <footer>, etc.

Ele pode ser usado para envolver todo o conteúdo da página e, também, para uma seção, ou parte, da página. É o container que mantém o layout funcionando corretamente.

Você pode ter mais de um container em uma mesma página.

O código abaixo mostra um exemplo de container implementado em uma página com Bootstrap:

<!DOCTYPE html>
<html lang="pt">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap Template</title>

    <link href="css/bootstrap.min.css" rel="stylesheet">
  </head>
  <body>
    <div class="container">
      <h1 class="page-header">Hello, Bootstrap!</h1>
      ...
    </div>

    <script src="js/jquery.min.js"></script>
    <script src="js/bootstrap.min.js"></script>
  </body>
</html>
view raw
bootstrap-exemplo-container.html hosted with ❤ by GitHub

Essa é a marcação que gerou a imagem anterior. Perceba que o container adicionou margens laterais ao conteúdo, e centralizou na tela. Além disso, ele já definiu a largura máxima do conteúdo.

Você pode escolher entre dois tipos de containers para usar em suas páginas: o container simples e o container fluído.

O container simples, que é o padrão, cria uma área responsiva e de largura fixa, que fica centralizada na tela (ou no elemento-pai). No código abaixo, temos um exemplo do container simples:

<div class="container">
  ...
</div>
