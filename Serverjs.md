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
    const express = require('express');<br>
    const cors = require('cors');<br>
    const app = express();<br>
    const port = 3000;<br>
  </details>

  ### Continuação
  Agora tente usar o cors e o express utilizando a variável "app" que você criou antes utilizando "use" logo após.
      > A ordem não importa.
      > Note que quando utilizar o express, faça questão que colocar ".json" em seguida.
  Fazer isso com que o express e o cors possam ser utilizados; sem isso não será possível.

  <details>
    <summary>Correção</summary>
    app.use(cors());<br>
    app.use(express.json());
  </details>
