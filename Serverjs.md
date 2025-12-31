# Server.js

## Início
Antes de começar a fazer o server.js você deve ter feito a instalação das dependênciads, pois sem eles o programa não rodará.

  ### Primeiras linhas
  Agora que você já viu sobre os comandos importantes, tente fazer as seguintes coisas:
  
  1. Importar o cors e o express
  2. Criar uma variável de nome "app" que use o express
  3. Crie uma variável de nome "port" com o número 3000
     > Note que tudo isso deve ser feito em apenas 4 linhas.

  Após tentar fazer o código, veja se está correto:<br>
  <details>
    <summary>Correção</summary>
    const express = require('express');
    const cors = require('cors');
    const app = express();
    const port = 3000;
  </details>
