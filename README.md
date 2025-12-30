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

    --> Isso vai fazer com que 
 
---
# Back-end:

  ### O que é:
  O back-end é a "parte de trás" de um site ou aplicativo, o "motor" que o usuário não vê, responsável pela lógica, bancos de dados, servidores e APIs, garantindo que as funcionalidades funcionem, os dados sejam armazenados e a aplicação seja segura, rápida e eficiente.

  ### Para que serve:
  Receber pedidos do front end, aplicar regras de negócio, conversar com o banco de dados, mandar respostas prontas para o front. Verifica login e senha, calcula resultados, decidir quem pode acessar o que, validar dados

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
