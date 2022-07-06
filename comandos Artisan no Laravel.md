Criar uma nova controladora
Para criar uma nova controladora, utilizamos o comando abaixo. Note que onde está NomeController, deve ser substituído pelo nome da sua controladora. O Sufixo Controller é uma obrigatoriedade.

php artisan make:controller NomeController
Caso deseje criar uma nova controladora com os métodos padrão para um CRUD, adicione o --resource, conforme mostra o exemplo a seguir.

php artisan make:controller AlgumaController --resource
Criando uma modelo
Sabemos que as modelos são responsáveis pela comunicação com uma fonte de dados, no Laravel, normalmente utilizamos as modelos para interagir com o ORM Eloquent.

Para cria rum novo arquivo, basta utilizar o comando abaixo, mas lembre-se sempre de atribuir nomes no singular e no padrão Pascal Case, ou seja, todas as inicias das palavras na maiúscula.

php artisan make:model Alguma
Caso deseje também criar uma nova migration, adicione o comando --migration, assim será criado um novo arquivo nomeado corretamente dentro da pasta /Migrations.

php artisan make:model Alguma --migration

Executar o Laravel
Sabemos que o Laravel possui seu próprio servidor para rodar a nossa aplicação, dispensando configurar o Apache ou Ngnix, por exemplo.
Parar iniciar um servidor no endereço padrão, que é localhost:8000, utilizamos o comando abaixo.

php artisan serve
Acontece que nem sempre vamos conseguir rodar tudo na porta 8000, principalmente quando algum outro processo está usando ela. Também pode acontecer do localhost não estar configurado em alguma parte do sistema e você necessite de um nome customizado.

Para especificar uma nova porta, basta adicionar --port e o nome da porta, ex: --port=2500.

Se precisar informar outro endereço IP, basta adicionar --host passando o novo IP, ex: 127.0.0.10.

Veja como fica os comandos de porta e host.

php artisan serve --port=2500 --host 127.0.0.9
Criando uma nova Migration
Migrations são mecanismos que nos permite criar tabelas nos banco de dados, possibilitando toda a equipe manter o SGBD atualizado e com a última versão. Esse recurso ainda dispensa a necessidade de criar os SQL na mão ou utilizar qualquer outro software para modelagem.

Conseguimos criar uma nova migration usando o comando abaixo.

php artisan make:migration create_algumas_table
É importante se atentar em seguir a convenção do uso das migrations, que consiste em adicionar o create, seguido do nome da migration tudo na minúscula e no plural, por fim, adicionar o table.

Para rodar as migrations, usamos:

php artisan migrate
Já para ver o status, usamos:

php artisan migrate:status
Listando as rotas existentes
Finalizamos esse artigo com comandos para as rotas, que é a parte mais importante da nossa aplicação, afinal, sem elas não seria possível definir o caminho e ação para as nossas URLs.

Podemos listar todas as rotas utilizando:

php artisan route:list
Mas caso esteja com problemas de rotas não funcionando ou com comportamento diferente do esperado, utilize o clear cache para forçar o Laravel a recompilar a estrutura de rotas.

php artisan route:clear
