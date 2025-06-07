<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Quiz de Fisiologia Celular</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      margin: 0;
      padding: 20px;
    }
    .container {
      max-width: 800px;
      margin: auto;
      background: #fff;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    h1 {
      text-align: center;
      color: #333;
    }
    .question {
      margin-bottom: 20px;
    }
    .question h3 {
      margin-bottom: 10px;
    }
    .options label {
      display: block;
      margin-bottom: 5px;
    }
    .submit {
      display: block;
      margin: 20px auto;
      padding: 10px 20px;
      font-size: 16px;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    .submit:hover {
      background-color: #218838;
    }
    .result {
      font-weight: bold;
      color: #0069d9;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Quiz de Fisiologia Celular</h1>
    <form id="quizForm">
      <div class="question">
        <h3>1. Quais são as principais características da membrana celular?</h3>
        <div class="options">
          <label><input type="radio" name="q1" value="A"> A) Impermeável e espessa</label>
          <label><input type="radio" name="q1" value="B"> B) Fina e composta de peptídeos</label>
          <label><input type="radio" name="q1" value="C"> C) Fluida e seletivamente permeável</label>
          <label><input type="radio" name="q1" value="D"> D) Totalmente rígida e impermeável</label>
        </div>
      </div>

      <div class="question">
        <h3>2. Qual é a principal função da bicamada fosfolipídica?</h3>
        <div class="options">
          <label><input type="radio" name="q2" value="A"> A) Realizar a síntese proteica</label>
          <label><input type="radio" name="q2" value="B"> B) Fornecer energia à célula</label>
          <label><input type="radio" name="q2" value="C"> C) Regular a entrada e saída de substâncias</label>
          <label><input type="radio" name="q2" value="D"> D) Produzir ATP</label>
        </div>
      </div>

      <button type="button" class="submit" onclick="checkAnswers()">Verificar Respostas</button>
      <div id="result" class="result"></div>
    </form>
  </div>

  <script>
    function checkAnswers() {
      const answers = {
        q1: 'C',
        q2: 'C'
      };
      let score = 0;
      let total = Object.keys(answers).length;
      for (let key in answers) {
        let radios = document.getElementsByName(key);
        for (let i = 0; i < radios.length; i++) {
          if (radios[i].checked && radios[i].value === answers[key]) {
            score++;
          }
        }
      }
      document.getElementById('result').innerText = `Você acertou ${score} de ${total} questões.`;
    }
  </script>
</body>
</html>
