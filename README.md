<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Quiz Bíblico - AD Vitória Cristã</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <nav>
    <a href="index.html">Início</a>
    <a href="quiz.html">Quiz Bíblico</a>
  </nav>

  <header>
    <h1>Quiz Bíblico</h1>
    <p>Teste seus conhecimentos sobre a Palavra de Deus!</p>
  </header>

  <section>
    <form id="quizForm">
      <div class="question">
        <h3>1. Quem construiu a arca?</h3>
        <label><input type="radio" name="q1" value="N"> Noé</label>
        <label><input type="radio" name="q1" value="M"> Moisés</label>
        <label><input type="radio" name="q1" value="A"> Abraão</label>
      </div>

      <div class="question">
        <h3>2. Qual o primeiro livro da Bíblia?</h3>
        <label><input type="radio" name="q2" value="G"> Gênesis</label>
        <label><input type="radio" name="q2" value="E"> Êxodo</label>
        <label><input type="radio" name="q2" value="L"> Levítico</label>
      </div>

      <div class="question">
        <h3>3. Quem foi jogado na cova dos leões?</h3>
        <label><input type="radio" name="q3" value="D"> Daniel</label>
        <label><input type="radio" name="q3" value="J"> Jonas</label>
        <label><input type="radio" name="q3" value="E"> Elias</label>
      </div>

      <div class="question">
        <h3>4. Quem foi o traidor de Jesus?</h3>
        <label><input type="radio" name="q4" value="J"> Judas Iscariotes</label>
        <label><input type="radio" name="q4" value="P"> Pedro</label>
        <label><input type="radio" name="q4" value="T"> Tomé</label>
      </div>

      <div class="question">
        <h3>5. Em quantos dias Deus criou o mundo?</h3>
        <label><input type="radio" name="q5" value="6"> 6 dias</label>
        <label><input type="radio" name="q5" value="7"> 7 dias</label>
        <label><input type="radio" name="q5" value="8"> 8 dias</label>
      </div>

      <div class="question">
        <h3>6. Qual era o nome do pai de Jesus?</h3>
        <label><input type="radio" name="q6" value="J"> José</label>
        <label><input type="radio" name="q6" value="D"> Davi</label>
        <label><input type="radio" name="q6" value="I"> Isaque</label>
      </div>

      <div class="question">
        <h3>7. Qual o nome do mar que foi aberto por Moisés?</h3>
        <label><input type="radio" name="q7" value="V"> Vermelho</label>
        <label><input type="radio" name="q7" value="M"> Mediterrâneo</label>
        <label><input type="radio" name="q7" value="G"> Galileia</label>
      </div>

      <div class="question">
        <h3>8. Quem escreveu os Salmos?</h3>
        <label><input type="radio" name="q8" value="D"> Davi</label>
        <label><input type="radio" name="q8" value="S"> Salomão</label>
        <label><input type="radio" name="q8" value="M"> Moisés</label>
      </div>

      <div class="question">
        <h3>9. Onde Jesus nasceu?</h3>
        <label><input type="radio" name="q9" value="B"> Belém</label>
        <label><input type="radio" name="q9" value="N"> Nazaré</label>
        <label><input type="radio" name="q9" value="J"> Jerusalém</label>
      </div>

      <div class="question">
        <h3>10. Quantos discípulos Jesus teve?</h3>
        <label><input type="radio" name="q10" value="12"> 12</label>
        <label><input type="radio" name="q10" value="10"> 10</label>
        <label><input type="radio" name="q10" value="11"> 11</label>
      </div>

      <button type="button" onclick="checkAnswers()">Enviar Respostas</button>
    </form>

    <div id="result"></div>
  </section>

  <footer>
    <p>&copy; 2024 Assembleia de Deus Vitória Cristã</p>
  </footer>

  <script>
    function checkAnswers() {
      const answers = {
        q1: 'N', q2: 'G', q3: 'D', q4: 'J', q5: '6',
        q6: 'J', q7: 'V', q8: 'D', q9: 'B', q10: '12'
      };
      let score = 0;
      for (let key in answers) {
        const selected = document.querySelector(`input[name="${key}"]:checked`);
        if (selected && selected.value === answers[key]) score++;
      }

      let feedback = '';
      if (score === 10) {
        feedback = 'Excelente! Você conhece muito bem a Bíblia!';
      } else if (score >= 7) {
        feedback = 'Muito bem! Você tem um bom conhecimento bíblico.';
      } else if (score >= 4) {
        feedback = 'Bom esforço! Continue estudando a Palavra de Deus.';
      } else {
        feedback = 'Continue estudando! A Bíblia é fonte de sabedoria.';
      }

      document.getElementById('result').innerHTML = `<h2>Você acertou ${score} de 10 perguntas.</h2><p>${feedback}</p>`;
    }
  </script>
</body>
</html>
