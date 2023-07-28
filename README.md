# calculadoradeidade
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-color: #ADD8E6;
	  font-family: courier,arial,helvetica;
      font-size: 16px;
      line-height: 1.5;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .container {
      max-width: 400px;
      background-color: #fff;
      padding: 50px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    /* Estilo para o cabeçalho */
    h1 {
      color: #333;
	  font-family: courier,arial,helvetica;
      font-size: 36px;
      font-weight: bold;
      margin-bottom: 20px;
      text-align: center;
      text-transform: uppercase;
    }

    /* Estilo para os rótulos */
    label {
      display: inline-block;
      font-size: 18px;
      margin-bottom: 5px;
      color: #0073ff; /* Cor para os rótulos */
    }

    /* Estilo para as entradas de texto e números */
    input[type="text"], input[type="number"] {
      border: 1px solid #ccc;
      border-radius: 5px;
      font-size: 18px;
      padding: 10px;
      width: 100%;
      margin-bottom: 15px;
    }

    /* Estilo para o botão */
    .button-container {
      display: flex;
      justify-content: space-between;
    }

    .button-container button {
      background-color: #87CEFA; /* Cor para o botão */
      border: none;
      border-radius: 5px;
      color: #fff;
      cursor: pointer;
      font-size: 18px;
      padding: 10px 20px;
      text-transform: uppercase;
      transition: background-color 0.2s ease-in-out;
      width: calc(50% - 10px);
    }

    .button-container button:hover {
      background-color: #00a2ff; /* Cor para o botão no hover */
    }

    /* Estilo para o resultado */
    #resultado {
      background-color: #ffffff; /* Cor para o fundo do resultado */
      border: 1px solid #ffffff;
      border-radius: 5px;
      font-size: 18px;
      margin-top: 20px;
      padding: 20px;
      text-align: center;
      color: #333; /* Cor para o texto do resultado */
    }
  </style>
  <title>Ver sua idade</title>
  <meta charset="UTF-8">
  <script>
    function verificarFaseVida() {
      var nome = document.getElementById("nome").value;
      var idade = parseInt(document.getElementById("idade").value);
      var fase;

      if (idade <= 11) {
        fase = "Criança";
      } else if (idade >= 12 && idade <= 20) {
        fase = "Adolescente";
      } else if (idade >= 21 && idade <= 64) {
        fase = "Adulto"; 
      } else if (idade >= 65 && idade <= 100) { /* Corrigindo o erro aqui */
        fase = "Idoso";
      } else {
        fase = "Idade inválida"; /* Tratando caso de idade inválida */
      }

      document.getElementById("resultado").innerHTML = nome + ", você está na fase da vida: " + fase;
    }
  </script>
</head>
<body>
  <div class="container">
    <h1>Ver sua idade</h1>
    <label for="nome">Nome:</label>
    <input type="text" id="nome"><br>
    <label for="idade">Idade:</label>
    <input type="number" id="idade"><br>
    <div class="button-container">
      <button onclick="verificarFaseVida()">Verificar</button>
      <button>Limpar</button>
    </div>
    <div id="resultado"></div>
  </div>
</body>
</html>
