# Back-Front-DB
Explicação básica do que são cada coisa, com exemplos e comandos importantes para utilizar.

---
  <center>![divisor](https://art.ngfiles.com/comments/1077000/iu_1077885_9224881.gif)</center>

---

# Banco de dados:

 ### Função:
 O banco de dados tem como função armazenar informações, permitir buscar, atualizar e apagar informações, garantir que nada se perca

 ### Exemplos de banco de dados:
 MySQL, PostgreSQL, SQLite, MongoBD

 ---
  ![divisor](https://art.ngfiles.com/comments/1077000/iu_1077885_9224881.gif)

---

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

---
  ![divisor](https://art.ngfiles.com/comments/1077000/iu_1077885_9224881.gif)

---

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
    <br><br>
    Sintaxe básica:
    
    ![imagem da sintaxe](https://github.com/lisismari/back-front-db/blob/main/sintaxe%20INNER%20JOIN.png?raw=true)

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
  ![divisor](https://art.ngfiles.com/comments/1077000/iu_1077885_9224881.gif)

---
# Back-end:

  ### O que é:
  O back-end é a "parte de trás" de um site ou aplicativo, o "motor" que o usuário não vê, responsável pela lógica, bancos de dados, servidores e APIs, garantindo que as funcionalidades funcionem, os dados sejam armazenados e a aplicação seja segura, rápida e eficiente.

  ### Para que serve:
  Receber pedidos do front end, aplicar regras de negócio, conversar com o banco de dados, mandar respostas prontas para o front. Verifica login e senha, calcula resultados, decidir quem pode acessar o que, validar dados
  
---
  ![divisor](https://art.ngfiles.com/comments/1077000/iu_1077885_9224881.gif)

---

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

   - **Arrow function (=>)**:<br>
     Define uma função de forma mais curta e moderna. Torna o código mais limpo e legível, além de lidar melhor com o contexto em muitos casos. _**Quando usar?**_ Em callbacks, funções simples ou quando quiser um código mais enxuto (muito comum em projetos atuais). O ```=>``` vem sempre depois do ```(req, res)``` no começo da função, seguido por chaves '{}'.

     Ex: ```const deletar = async (req, res) => {
     }```
     
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

     Ex: `res.status(200).json({"Essa mensagem vai aparecer depois de rodar o código e funcionar.})` ou `res.status(200).json(lista)`. O `lista` dentro do json retorna uma lista de objetos, como: `[{nome: cecilia}, {nome: gustavo}, {nome: marta}]`

   - **Body**:<br>
     Contém os dados enviados peelo cliente no corpo da requisição. Receber informações mais complexas, como formulários ou objetos JSON. _**Quando usar?**_ Principalmente em requisições `POST`, `PUT` ou `PATCH`
     
   - **Params**:<br>
     Armazena parâmetros enviados pela URL. Indentificar recursos específicos (ex: ID de um usuário ou produto). _**Quando usar?**_ Quando a informação vem diretamente na rota.

     Ex: quando for buscar um usuário, quero que busque por id, então na função buscarUsuário crio um parâmetro assim: `const id = req.params.id;`, para que assim, na rota eu possa colocar, por exemplo: `('/buscar/id')`. Depois, quando for buscar pela URL, basta colocar "/buscar/" e o ID de um usuário logo após a barra.

   - **Try / Catch**:<br>
     Permite capturar e tratar erros durante a execução do código. Evitar que a aplicação quebre quando ocorre um erro inesperado. _**Quando usar?**_ Ao lidar com operações que podem falhar, como acesso a banco de dados, APIs ou código assíncrono.

     ![imagem do exemplo](https://github.com/lisismari/back-front-db/blob/main/exemplo%20try-catch.png?raw=true)

   - **Query**:<br>
     Armazena parâmetros enviados pela URL após o '?'. Recebe filtros, buscar ou informações opcionais do cliente. _**Quando usar?**_ Quando os dados não fazem parte da rota em si, mas ajudam a refinar uma requisição. O `query` vem depois do nome que você deu a função que usa o banco de dados (isso deve ter sido feito no começo do código.

     Ex: `const db = require('link do arquivo da pasta data, onde o banco de dados está')` para que você possa usar em uma função, eventualmente, `await db.query`
     
   - **Module.exports**:<br>
     Define o que um arquivo exporta. Permite que funções, objetos ou variáveis sejam usados em outros arquivos. _**Quando usar?**_ Sempre que quiser reutilizar código em diferentes partes do projeto.

     Ex: no final de um código em algum arquivo controller, você normalmente verá ```module.exports = { cadastrar, buscar, atualizar }```, o que quer dizer que as funções que estão dentro do module.exposts foram exportadas e poderão ser utilizadas nas rotas.

   - **Return**:<br>
     Encerra a execução de uma função e devolve um valor. Envia um resultado para quem chamou a função. _**Quando usar?**_ Sempre que uma função precisar produzir algum resultado ou resposta.

---
  ![divisor](https://art.ngfiles.com/comments/1077000/iu_1077885_9224881.gif)

---

  ### Baixar dependências:
  Este é um passo muito importante parao código, já que não adiantará de nada ter colocado um "require express" sendo que você não o instalou antes de rodas o código.

  _**Como posso começar a instalar as dependências?**_ Abra o terminal e digite ```npm init``` para começar o processo. Terá de preencher algumas coisas ou simplesmente deixar em branco apertando a tecla de enter. Para um processo mais rápido, basta digitar -y depos do init, como: ```npm init -y```, assim os campos serão preenchidos automáticamente.<br>
  Em seguida, basta digitar npm install e o que você deseja instalar, sendo os mais comuns e frequêntes: express, cors, mysql2, dotenv. Como: ```npm install express``` ou ```npm install mysql2```
  
---
  ![divisor](https://art.ngfiles.com/comments/1077000/iu_1077885_9224881.gif)

---
# Front-end:

  ### O que é:

  ### Para que serve:
