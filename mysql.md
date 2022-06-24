Skip to content
Voltar para a página inicial
INÍCIO
SOBRE MIM
Search
MYSQLTERMINAL
Comandos básicos do MySQL no terminal
por Diego Brocanelli|Publicado 21/04/2017|13 Comentários
Olá pessoal, tudo bem?!

Não é nada fora do comum que nós desenvolvedores  tenhamos que manipular/modificar/criar bancos de dados, com certeza isso é o pesadelo de qualquer DBA. Particularmente gosto de trabalhar com front, back e banco de dados pois isso me permite a ter acesso a conteúdos fantásticos aprendendo coisas novas sempre.

Como podemos manipular o banco de dados? Bom, particularmente para atividades corriqueira utilizo o terminal, sim o terminal, é simples e rápido.

Caso você seja usuário Windows recomento que utilize o cmder software portable que emula o terminal como se fosse no Linux, caso você seja usuário Linux ou Mac, bom, sua vida com o terminal já é tranquila 🙂

Conectar no MySQL

Abra o terminal e digite:

mysql -u root -p
Parâmetro: -u
Indica o usuário ao qual desejamos utilizar para conectar ao banco.
Parâmetro: root
Nome do usuário que estamos utilizando para realizar a conexão com o banco de dados. Onde pode ser qualquer usuário cadastrado no MySQL.
Parâmetro: -p
Indica a senha do usuário para conexão com o banco, este parâmetro é opcional, pois caso o usuário desejado não utilize senha para se conectar basta omitir este parâmetro, porem não é nada recomendado utilizar usuários sem senha 🙂
Conectar no MySQL acessando  direto o banco de dados desejado

Abra o terminal e digite:

 mysql -u root -p nome_do_banco_de_dados
Parâmetro: nome_do_banco_de_dados
Como descrito, refere-se ao nome do banco de dados que desejamos acessar.
Após execução do comando é realizado a conexão e acesso ao banco de dados que desejamos utilizar.

Listar os banco de dados

Abra o terminal acesso o MySQL e digite:

show databases;
Abaixo segue um exemplo de retorno do comando, podemos observar que é listado todos os bancos de dados até mesmo os utilizados pelo MySQL.

+--------------------+
| Database           |
+--------------------+
| information_schema |
| banco_01           |
| livraria           |
| mysql              |
| performance_schema |
| post_sql           |
| sys                |
| banco_02           |
+--------------------+
Listar as tabelas do banco de dados

Abra o terminal acesso o MySQL, em seguida acesse o banco de dados desejado e digite:

 show tables;
Exemplo de resultado.

+--------------------+
| Tables_in_livraria |
+--------------------+
| autores            |
| capitulos          |
| livros             |
| vendas             |
+--------------------+
Visualizar estrutura da tabela

Abra o terminal acesso o MySQL, em seguida acesse o banco de dados desejado e digite:

describe table_name;
Parâmetro: table_name
Substitua pelo nome da tabela desejada.
Exemplo de resultado.

+--------------------+---------------+------+-----+---------+----------------+
| Field              | Type          | Null | Key | Default | Extra          |
+--------------------+---------------+------+-----+---------+----------------+
| id                 | int(11)       | NO   | PRI | NULL    | auto_increment |
| nome               | varchar(100)  | NO   |     | NULL    |                |
| data_de_lancamento | date          | NO   |     | NULL    |                |
| autor_id           | int(11)       | NO   |     | NULL    |                |
| preco              | decimal(10,2) | NO   |     | NULL    |                |
+--------------------+---------------+------+-----+---------+----------------+
5 rows in set (0,00 sec)
Dump da base de dados

Para criar uma cópia da base de dados desejados abara o terminal, acesse o diretório no qual deseja criar o arquivo em seguida digite o comando:

mysqldump -u root -p database_name > database_name.sql;
Parâmetro: database_name
Substitua pelo nome do banco de dados ao qual deseja realizar a cópia.
Após executar o comando, será criado um arquivo .sql no local de desetino desejado. Caso você tenha o costume de utilizar por exemplo o PHPMyAdmin para gear o dump, recomendo que passe a utilizar o terminal, pois a interface gráfica em alguns casos pode gerar um arquivo .sql que ao ser importado por outro membro da sua equipe pode conter erros. Já o arquivo gerado pelo terminal as chances são mínimas, pois se o comando executado não apresentar erro seu resultado será correto e o arquivo gerado poderá ser importado sem maiores eventualidades.

Dump somente da estrutura da base de dados

Abra o terminal vá ao diretório onde deseja criar o arquivo de backup e digite:

 mysqldump -u root -p database_name --no-data > database_name.sql;
Parâmetro: –no-data
Indica que desejamos criar uma cópia do bando de dados sem as informações contidas nas tabelas.
Este comando é bem similar ao mencionado anteriormente, porém com a diferença que ele criar uma cópia da estrutura do banco de dados não realizando a exportação dos dados contidos nas tabelas.

Importar banco de dados

Abra o terminal vá ao diretório onde encontra-se o bando de dados que deseja importar e digite:

mysql -u root -p database_name < database_name.sql;
Após execução do comando e o arquivo a ser importado não conter erros, sua importação será realizada com sucesso. Em casos de importação onde as tabelas do banco de dados contenham 100, 200, 300 mil (esse volume é até pequeno em comparação com banco de milhões de registros) ou mais registros isso acarretará em um tempo maior de processamento, basta aguardar até a finalização e liberação do terminal pelo processo.

Dump de todos os bancos de dados

Abra o terminal, entre no diretório desejado para armazenar o arquivo de backup e digite:

mysqldump -u user -p --all-databases > full_path_to\file.sql
Parâmetro: –all-databases

Indica que desejamos exportar todas as bases de dados disponíveis no MySQL.
Após término da execução, será gerado um arquivo conforme especificado contento todos os bancos de dados do MySQL.

Apagar tabela

Abra o terminal acesse o MySQL em seguida o banco de dados desejado e digite:

 drop table nome_da_tabela;
Parâmetro: drop table
Responsável por apagar a tabela do banco de dados.
Parâmetro: nome_da_tabela
Nome da tabela ao qual se deseja apagar.
Utilize com muita cautela, pois após executar o comando a tabela será apagada do seu banco de dados!

Apagar a base de dados

Abra o terminal acesse o MySQL e digite:

 drop database nome_do_banco_de_dados;
Parâmetro: drop database
Responsável por apagar o banco de dados.
Parâmetro: nome_do_banco_de_dados
Nome do banco de dados ao qual se deseja apagar.
Utilize com muita cautela, pois após executar o comando o banco de dados será apagado!

Limpar o terminal

Acesse o terminal e pressione o seguinte comando:

ctrl+l
Este é um comando do terminal, porém muito útil quando estamos trabalhando com o MySQL ou qualquer banco de dados ou atividade no terminal, pois o mesmo limpa a tela do terminal para que possamos utilizá-lo com mais clareza e sem poluição de informações na tela.

Todos os comandos listados acima são recomendados para uso em ambiente local, não recomendo seu uso em ambiente de produção, caso vá utilizar tenha MUITA CAUTELA e PARCIMÔNIA com os comandos utilizados. Siga as boas práticas e com isso você verá que o uso do terminal irá maximizar sua performance.

Não tenha medo do terminal, sabendo utilizá-lo é uma ferramenta poderosíssima, podendo abrir um leque de opções fantásticas.

Espero que tenham apreciado este post e caso tenham alguma duvidas, sugestões ou crítica por favor deixe nos comentários e com isso podemos debater e aprender cada vez mais.

Grande abraço e até a próxima 🙂

YOU MAY ALSO LIKE

Publicado 14/06/2018
Calculando intervalo entre datas excluindo os finais de semana – MySQL
6 Comentários
Olá, tudo bem?!   O problema Calcular a diferença entre duas datas no MySQL é algo muito simples e fácil de se […]


Publicado 28/12/2019
Configuração automática de estação de trabalho
Olá, tudo bem! Para facilitar o processo de configuração de uma estação de trabalho, criei um projeto open soucer chamado workstation_configuration, responsável […]

Deixe um comentário
O seu endereço de e-mail não será publicado. Campos obrigatórios são marcados com *

COMENTÁRIO*

NOME
E-MAIL
SITE

13 pensamentos em “Comandos básicos do MySQL no terminal”
13 Comentários
Victor Modecai06/02/2018, 12:46
Amigo, bom dia, por favor espero que possa me ajudar! quando digito o seguinte comando: mysql -u root -p, ele me fornece para dar enter, até ai tudo bem, porém depois me aparece esse erro: ERROR 2002 (HY000): Can’t connect to local MySQL server through socket ‘/var/run/mysqld/mysqld.sock’ (2 “No such file or directory”).
espero que possa me ajudar, to quebrando cabeça com isso faz um tempinho, desde já obrigado!

Diego Brocanelli Autor do post09/02/2018, 18:45
Olá, Victor.
Para poder lhe auxiliar necessito das seguintes informações, sendo:

– Qual SO você está usando?
– Qual versão do MySQL você está usando?
– Como você instalou o MySQL.

Sem essas informações o erro que você está descrevendo aparentar ser erro de configuração do MySQL.

Fico no aguardo.

Att:.

Fabricio ventura28/02/2018, 09:05
Bom dia amigo, consigo fazer tudo como você diz. Porém gostaria de um exemplo solicitando senha. Já tentei fazer da seguinte forma:

mysqldump -u root -p 123456 BD_Teste > c:/backupteste

Porém não consigo, dá um erro.

Pode me ajudar?

Fabricio ventura28/02/2018, 09:06
Sem solicitar senha, desculpa errei no post anterior.

Diego Brocanelli Autor do post28/02/2018, 09:27
Olá, Fabricio Ventura.

Para realizar o dump do banco de dados sem a solicitação de senha basta omitir o parâmetro -p, exemplo:

mysqldump -u root BD_Teste > c:/backupteste

Espero ter lhe auxiliado.

Sucesso em seus projetos.

Fabricio ventura28/02/2018, 14:10
boa tarde Diego Brocanelli, fiz da forma que você falou. Realmente não pediu senha, mas também não executou o processo solicitado.
Busquei um pouco mais na internet e acabei achando, a forma que conseguir foi essa:

mysqldump -u root –password=123456 BD_Teste > c:/backupteste

Espero que te ajude caso necessário.

Diego Brocanelli Autor do post28/02/2018, 14:38
Olá, Fabricio Ventura.

O comando abaixo indica que você utilizou senha para realizar a operação, e se executou com sucesso quer dizer que o usuário somente é acessível com senha, com isso o processo anterior mencionado não funcionaria mesmo.
E a primeira instrução que você mencionou em seu comentário está incorreta, sendo;

mysqldump -u root -p 123456 BD_Teste > c:/backupteste

O Correto seria, sem digitar a senha, para que após o enter do comando (listado abaixo) o terminal abriria ação para inserção da senha.

mysqldump -u root -p BD_Teste > c:/backupteste

Que bom que teve seu problema resolvido, sucesso em seus projetos.

Edna Coelho04/01/2020, 20:18
Olá Diego,
Escrevi: mysql -u root -p
e apareceu: -bash: mysql: command not found
Pode ajudar?

Diego Brocanelli Autor do post06/01/2020, 07:49
Olá, Edna.

Com base na mensagem de erro que você informou, demonstra que o MySQL não foi instalado em seu computador.

Os comandos abaixo devem ser executados no terminal.

Para verificar se o MySQL está instalado.


dpkg -s mysql-server | grep Status

O retorno deve ser Status: install ok installed.

Caso o MySQL não esteja instalado, segue os comandos para instalação.

Para que o mesmo seja instalado execute o comando abaixo.


sudo apt install mysql-server

O comando abaixo é para realizar as configurações de segurança do MySQL.


sudo mysql_secure_installation

Espero ter lhe auxiliado.

Thiago Gambati de Souza22/03/2020, 19:44
Olá Diego, sou estagiário no ambiente de produção, lá usa o CentOS no servidor e eu tenho acesso pelo putty via linha de comando, esses comandos seriam viáveis?

Diego Brocanelli Autor do post23/03/2020, 08:35
Olá, Thiago.

Obrigado por prestigiar o conteúdo.

Sim o comando funcionará, desde que o acesso ao banco de dados permita, pois pode ser que o usuário que esteja utilizando tenha restrições.

Espero ter lhe auxiliado.

Sucesso em seus projetos.

Joao D'Silva08/11/2021, 22:38
Ola Diego,

Minha conexão funcionou apenas quando usei – sudo mysql -u root
Sem o sudo aparecia o ERRO 1698

Diego Brocanelli Autor do post09/11/2021, 11:35
Olá, João.

Pela linha de código que você mandou, a tentativa de conexão é utilizando o usuário root.

O mesmo funciona pois você está executando com sudo. Esse comando sobrepõem os privilégios e concede acesso ao MySQL.

O erro 1698 é justamente informando acesso não permitido pelo usuário, provavelmente pelo fato de conexão sem senha.

Dependendo do modo em que foi instalado o MySQL, temos 2 possibilidades:

Ter instalado e configurado uma senha para o usuário root;
Ter instalado e não ter configurado uma senha para o usuário root.
Para rápida solução pode ser criado um novo usuário, onde você define nome e senha para ele, e passe a utilizar o mesmo.

Pode ser reinstalado o MySQL, porém claramente essa maneira é a mais drástica a se tomar.

Definir uma nova senha para o usuário root.

Eu mesmo prefiro após instalação do MySQL criar um usuário e senha, e passo a utilizar o mesmo. Pois a utilização do usuário root não é uma boa pratica, pois trata-se do usuário com alto nível de permissão e privilégio.

