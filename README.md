# Back-Front-DB
Explicação básica do que são cada coisa, com exemplos e comandos importantes para utilizar.

# Banco de dados:

 ### Função:
 O banco de dados tem como função armazenar informações, permitir buscar, atualizar e apagar informações, garantir que nada se perca

 ### Exemplos de banco de dados:
 MySQL, PostgreSQL, SQLite, MongoBD

 ### Tipos de dados:
  - **INT/INTEGER**:
    <br>Números inteiros

  - **DECIMAL**:
    <br>Números com precisão exata para valores monetários ou científicos. Números com vírgula, onde INT não tem

  - **FLOAT**:
    <br>Números de ponto flutuante (aproximados). Números com vírgula, onde INT não tem

  - **VARCHAR**:
    <br>Texto de comprimento variável (até 8.000 caracteres, ou mais com (MAX)

  - **DATE**:
    <br>Apenas data (AAAA-MM-DD | Ano, mês e data)

  - **TIME**:
    Apenas hora (horas-minutos-segundos)

  - **DATETIME**:
    Data e hora, em sequência (AAAA-MM-DD HH:MM:SS)

 ### Comandos importantes:
  - **Criar database**:
    <br>CREATE DATABASE [nome da database];
    
  - **Deletar database**:
    <br>DROP DATABASE IF EXISTS [nome da database];

  - **Criar tabela**:
    <br>CREATE TABLE [nome da tabela] (
      infos
    )
    
    Ex: ```CREATE TABLE usuarios (
        nome VARCHAR(100),
        idade INT
    )```

  - **Deletar tabela**:
    <br>DROP TABLE [nome da database];

  - **Alterar tabela**:  ```ALTER TABLE```<br>Utilizado para alterar sem precisar apagar o código apenas para colocar de novo com tudo corrigido; poupa tempo se tiver que alterar 2-3 colunas, tabelas, etc.

    - **Adicionar coluna**:
      <br>ALTER TABLE [nome da tabela] ADD [nome da coluna] [tipo de dado];

       Ex: ```ALTER TABLE usuarios ADD profissao VARCHAR(100)``` 

    - **Remover coluna**:
      <br>ALTER TABLE [nome da tabela] DROP COLUMN [nome da coluna];

    - **Modificar coluna**:
      <br>ALTER TABLE [nome da tabela] ALTER COLUMN [nome da coluna] [tipo de dado];

      Ex: tornar o campo “email" **obrigatório**: ```ALTER TABLE Clientes ALTER COLUMN Email VARCHAR(100) NOT NULL;```

    - **Renomear tabela**:
      <br>ALTER TABLE [nome da tabela] RENAME TO [novo nome];

  - **Ver todas as informações de uma tabela**:
    <br>SELECT * FROM [nome da tabela];

  - **Adicionar informações em uma tabela**:
    <br>INSERT INTO [nome da tabela] (coluna 1, coluna 2...) VALUES [valor 1, valor 2...];

    Ex: ```INSERT INTO usuarios (nome, idade) VALUES ("cristina", 40);```

  - **Combinar linhas de tabelas diferentes**:
    <br>No começo, entender o inner join parece difícil, mas aprende-lo ajuda a retornar informações mais específicas. A função do ```INNER JOIN``` no SQL é combinar linhas de duas ou mais tabelas, retornando apenas os registros que possuem valores correspondentes em uma coluna comum em todas as tabelas envolvidas, criando uma "interseção" de dados para apresentar informações relacionadas de diferentes fontes de forma unificada.
    <br>Veja melhor no vídeo [aqui](https://youtu.be/dYM1ATLVtAg?si=mTEV9Fu_SkkDDv5R&t=127).
    <br>Sintaxe básica: ```t1.nome_coluna, t2.nome_coluna AS coluna2...
    FROM tabela1 t1
    INNER JOIN tabela2 t2
    ON t1.coluna_chave_t1 = t2.coluna_chave_t2;```

    **Explicação dos componentes**:
    <br>  ```SELECT colunas```: Define quais colunas você quer ver no resultado final;
    <br>  ```AS```: "Como", ou seja, como vc nomeia a coluna;
    <br>  ```FROM tabela1```: A primeira tabela da qual você quer buscar dados, seguida por um alias (apelido, como t1) para facilitar a escrita;
    <br>  ```INNER JOIN tabela2```: Indica que você está unindo a tabela1 com a tabela2;
    <br>  ```ON t1.coluna_chave_t1 = t2.coluna_chve_t2```: A condição crucial que especifica como as tabelas devem ser relacionadas, comparando valores em colunas comuns.

    **Exemplo prático**:
    <br> Imagine as tabelas 'produtos' e 'pedidos'

    ```SELECT p.nome AS Nome_do_produto, pe.data AS Data_do_pedido FROM produtos p INNER JOIN pedidos pe ON p.id = pe.id_produto;```

    --> Isso vai fazer com que retorne duas colunas, o ```Nome_do_produto``` e o ```Data_do_pedido```, mostrando todos os produtos e as datas em que foram feito os pedidos dos tais produtos
 
---
# Back-end:

  ### O que é:
  O back-end é a "parte de trás" de um site ou aplicativo, o "motor" que o usuário não vê, responsável pela lógica, bancos de dados, servidores e APIs, garantindo que as funcionalidades funcionem, os dados sejam armazenados e a aplicação seja segura, rápida e eficiente.

  ### Para que serve:
  Receber pedidos do front end, aplicar regras de negócio, conversar com o banco de dados, mandar respostas prontas para o front. Verifica login e senha, calcula resultados, decidir quem pode acessar o que, validar dados

  ![divisor](https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/98ead744-a515-4ae5-acdd-bd3f8581a3d7/dgrriix-618b2aba-2a75-469d-84fc-48d241852a51.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiIvZi85OGVhZDc0NC1hNTE1LTRhZTUtYWNkZC1iZDNmODU4MWEzZDcvZGdycmlpeC02MThiMmFiYS0yYTc1LTQ2OWQtODRmYy00OGQyNDE4NTJhNTEuZ2lmIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.cbabQV918AZ5F6skPk37utgfDVW3sBWtvaESEHfCw7c)

  ### Comandos importantes:
   - **Const**:<br>
     Declara uma variável cujo valor não pode ser reatribuído. Garante que aquele valor não será alterado ao longo do código. _**Quando usar?**_ Quando você sabe que a variável não deve mudar (ex: funções, objetos de configuração, imports)
     
   - **Let**:<br>
     Declara uma variável que pode ter seu valor alterado. Armazenar dados que vão mudar durante a execução do programa. _**Quando usar?**_ Quando o valor da variável precisa ser atualizado (contadores, resultados, estados temporários)
     
     ----------------------------------------
   - **Require**:<br>
     Importa módulos, arquivos ou bibliotecas em JavaScript. Reutiliza códigos de outros arquivos ou bibliotecas externas. _**Quando usar?**_ Principalmente em Node.js, quando voc~e precisa acessar funções, objetos ou pacotes de outros arquivos.

     Ex: se eu preciso usar o express que eu instalei, então: ```const express = require('express');```
     <br>**OU**<br>
     se eu preciso usar um arquivo do controllers no routes: ```const pedidosControllers = require('../controllers/pedidos.controller');```
     
   - **Async**:<br>
     Define que uma função é assíncrona. Permite o uso de ```await``` dentro da função e facilita o trabalho com operações que demoram (ex: banco de dados, APIs). _**Quando usar?**_ Sempre que a função depender de algo que não acontece instantaneamente. O ```async```sempre vem depois do '='. Ex: ```const funcao = async ...```
     
   - **Await**:<br>
     Pausa a execução da função até que uma Promise seja resolvida. Evitar o uso excessivo de ```then()``` e deixar o código mais legivel. _**Quando usar?**_ Dentro de funções async, ao lidar com Promises (fetch, queries, etc).

     Por exemplo: eu quero usar o banco de dados para cadastrar algo: ```async (req, res) => { await db.query('INSERT INTO alunos ....')}```. O ```await```, nesse caso, virá sempre antes do query (e antes do db automáticamente).

   - **Promises**:<br>
     Representa um valor que pode estar disponível agora, no futuro ou nunca. Controla operações assíncronas e lida com sucesso ou falha de forma organizada. _**Quando usar?**_ Quando uma operação depende de tempo (requisições, leitura de arquivos, timers). Hoje em dia, a maneira mais limpa de usar Promise é async/await, explicados anteriormente.
     
   - **Res, Res**:<br>
     - req (request): representa a requisição feita pelo cliente.
     - res (responde): representa a resposta que o servidor vai enviar.
    
     Permitir que o servidor receba dados do cliente e envie uma resposta adequada. _**Quando usar?**_ Em aplicações back-end (ex: Express), sempre que criar rotas.
     
   - **Status**:<br>
     Define o código de status HTTP da resposta. Informa o cliente se a requisição foi bem-sucedida ou se ocorreu algum erro. _**Quando usar?**_ Sempre que quiser indicar o resultado da operação (200, 201, 400, 404, 500, etc). Para mais informações sobre os status, veja [aqui](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Reference/Status).
     
   - **Json**:<br>
     Envia uma resposta no formato JSON. Retorna dados estruturados para o cliente (mensagens, objetos, listas). _**Quando usar?**_ Em APIs, quando o front-end precisa receber dados do back-end.

     Ex: ```res.status(200).json({"Essa mensagem vai aparecer depois de rodar o código e funcionar.})``` ou ```res.status(200).json(lista)```. O ```lista```dentro do json retorna uma lista de objetos, como: ```[{nome: cecilia}, {nome: gustavo}, {nome: marta}]```
     
   - **Params**:<br>
     Armazena parâmetros enviados pela URL. Indentificar recursos específicos (ex: ID de um usuário ou produto). _**Quando usar?**_ Quando a informação vem diretamente na rota.

     Ex: quando for buscar um usuário, quero que busque por id, então na função buscarUsuário crio um parâmetro assim: ```const id = req.params.id;```, para que assim, na rota eu possa colocar, por exemplo: ```('/buscar/id'). Depois, quando for buscar pela URL, basta colocar "/buscar/" e o ID de um usuário logo após a barra.
     
   - **Module.exports**:<br>
     Define o que um arquivo exporta. Permite que funções, objetos ou variáveis sejam usados em outros arquivos. _**Quando usar?**_ Sempre que quiser reutilizar código em diferentes partes do projeto.

     Ex: no final de um código em algum arquivo controller, você normalmente verá ```module.exports = { cadastrar, buscar, atualizar }```, o que quer dizer que as funções que estão dentro do module.exposts foram exportadas e poderão ser utilizadas nas rotas.


  ### Baixar dependências:
  Este é um passo muito importante parao código, já que não adiantará de nada ter colocado um "require express" sendo que você não o instalou antes de rodas o código.

  _**Como posso começar a instalar as dependências?**_ Abra o terminal e digite ```npm init``` para começar o processo. Terá de preencher algumas coisas ou simplesmente deixar em branco apertando a tecla de enter. Para um processo mais rápido, basta digitar -y depos do init, como: ```npm init -y```, assim os campos serão preenchidos automáticamente.<br>
  Em seguida, basta digitar npm install e o que você deseja instalar, sendo os mais comuns e frequêntes: express, cors, mysql2, dotenv. Como: ```npm install express``` ou ```npm install mysql2```

  ### Server.js:

  ### Controllers:

  ### Data:

  ### Routes:

---
# Front-end:

  ### O que é:

  ### Para que serve:
