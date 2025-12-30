# Back-Front-DB
Explicação básica do que são cada coisa, com exemplos e comandos importantes para utilizar.

# Banco de dados:

 ### Função:
 O banco de dados tem como função armazenar informações, permitir buscar, atualizar e apagar informações, garantir que nada se perca

 ### Exemplos de banco de dados:
 MySQL, PostgreSQL, SQLite, MongoBD

 ### Comandos importantes:
  - Criar database:
    <br>CREATE DATABASE [nome da database];
    
  - Deletar database:
    <br>DROP DATABASE [nome da database] IF EXISTS;

  - Criar tabela:
    <br>CREATE TABLE [nome da tabela] (
      infos
    )
    
    Ex: ```
    CREATE TABLE usuarios (
        nome VARCHAR(100),
        idade INT
    )```

  - Deletar tabela:
    <br>DROP TABLE [nome da database];

  - Alterar tabela:  ```ALTER TABLE```<br>Utilizado para alterar sem precisar apagar o código apenas para colocar de novo com tudo corrigido; poupa tempo se tiver que alterar 2-3 colunas, tabelas, etc.

    - Adicionar coluna:
      <br>ALTER TABLE [nome da tabela] ADD [nome da coluna] [tipo de dado];

       Ex: ```ALTER TABLE usuarios ADD profissao VARCHAR(100)``` 

    - Remover coluna:
      <br>ALTER TABLE [nome da tabela] DROP COLUMN [nome da coluna];

    - Modificar coluna:
      <br>ALTER TABLE [nome da tabela] ALTER COLUMN [nome da coluna] [tipo de dado];

      Ex: tornar o campo “email" **obrigatório**: ```ALTER TABLE Clientes ALTER COLUMN Email VARCHAR(100) NOT NULL;```

    - Renomear tabela:
      <br>ALTER TABLE [nome da tabela] RENAME TO [novo nome];

  - Ver todas as informações de uma tabela:
    <br>SELECT * FROM [nome da tabela];
 
---
# Back-end:

  ### O que é:

  ### Para que serve:

  ### Comandos importantes:
   - Const;
   - Let;

   - Require;
   - Async;
   - Await
   - Res, Res;
   - Status;
   - Json;
   - Params;
   - Module.exports;

  ### Server.js:

  ### Controllers:

  ### Data:

  ### Routes:

---
# Front-end:

  ### O que é:

  ### Para que serve:
