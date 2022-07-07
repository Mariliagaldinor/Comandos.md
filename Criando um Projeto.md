
1. Comando para criar o projeto: composer create-project laravel/laravel nome

2. executar servidor: php artisan serve

3. criar o banco de dados

mysql -u root -p # digite a senha do usuário root. Por padrão é simplesmente root
create database nome;
show databases;


4. Criar tabela: php artisan make:migration create_nome_table

5. executar as migrations pendentes: php artisan migrate

6. Vamos visualizar a tabela "migrations"

mysql -u root -p # digite a senha do usuário root. Por padrão é simplesmente root

Usando o banco de dados exemplo

use exemplo;
 
visualizando as tabelas 

show tables;

+------------------------+
| Tables_in_exemplo      |
+------------------------+
| failed_jobs            |
| migrations             |
| products               |
| password_resets        |
| personal_access_tokens |
| users                  |
+------------------------+
6 rows in set (0.00 sec)

Vamos selecionar todos os campos da tabela migrations.

select * from migrations;


+----+-------------------------------------------------------+-------+
| id | migration                                             | batch |
+----+-------------------------------------------------------+-------+
|  1 | 2014_10_12_000000_create_users_table                  |     1 |
|  2 | 2014_10_12_100000_create_password_resets_table        |     1 |
|  3 | 2019_08_19_000000_create_failed_jobs_table            |     1 |
|  4 | 2019_12_14_000001_create_personal_access_tokens_table |     1 |
|  5 | 2022_05_06_024944_create_products_table               |     1 |
+----+-------------------------------------------------------+-------+
5 rows in set (0.02 sec)

7. Descricao da tabela.

mysql > describe nomedatabela;


Criar a model: php artisan make:model nome

Criar a seeder: php artisan make:seeder nome

Executar a seeder pendente: php artisan db:seed

Criar a request: php artisan make:request nome

Criar o controller: php artisan make:controller nome

Autorizar o acesso a pasta public: php artisan storage:link
