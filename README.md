# treasure-hunt-2-mai
[![Netlify Status](https://api.netlify.com/api/v1/badges/3dcddae5-859c-4a77-90bb-2f829f28bf82/deploy-status)](https://app.netlify.com/sites/checkpointstadion/deploys)
<!DOCTYPE html>
<html lang="ro">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Quiz cu 3 întrebări</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f4f8;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
    }

    .quiz-container {
      background: white;
      padding: 30px 20px;
      border-radius: 15px;
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
      width: 90%;
      max-width: 500px;
    }

    .question, .intro, .success-message {
      display: none;
      margin-bottom: 20px;
    }

    .active {
      display: block;
    }

    h1, h2 {
      margin-bottom: 15px;
      text-align: center;
    }

    p {
      text-align: center;
      margin-bottom: 20px;
    }

    button {
      background: #007bff;
      color: white;
      border: none;
      padding: 10px 20px;
      margin: 5px 0;
      border-radius: 8px;
      cursor: pointer;
      transition: background 0.2s;
      width: 100%;
    }

    button:hover {
      background: #0056b3;
    }

    .success-message {
      font-size: 1.5em;
      color: green;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="quiz-container">
    <div id="intro" class="intro active">
      <h1>Bine ai venit la cel de-al doilea checkpoint!</h1>
      <p>Înainte de a porni mai departe în căutarea comorii, testați-vă puțin cunoștiințele legate de sport, în legătură cu Uniunea Europeană</p>
      <button onclick="startQuiz()">Start</button>
    </div>

    <div id="q1" class="question">
      <h2>1. Când este săptămâna europeană a sportului în 2025?</h2>
      <button onclick="checkAnswer(1, 'a')">a) 23-30 septembrie</button>
      <button onclick="checkAnswer(1, 'b')">b) 15-22 septembrie</button>
      <button onclick="checkAnswer(1, 'c')">c) 1-8 septembrie</button>
    </div>

    <div id="q2" class="question">
      <h2>2. Naționala cărui stat membru a câștigat ultimul campionat de fotbal european?</h2>
      <button onclick="checkAnswer(2, 'a')">a) Anglia</button>
      <button onclick="checkAnswer(2, 'b')">b) Spania</button>
      <button onclick="checkAnswer(2, 'c')">c) Italia</button>
    </div>

    <div id="q3" class="question">
      <h2>3. Care dintre următoarele orașe a fost desemnat Capitala Europeană a Sportului în anul 2019?</h2>
      <button onclick="checkAnswer(3, 'a')">a) Sofia, Bulgaria</button>
      <button onclick="checkAnswer(3, 'b')">b) Paris, Franța</button>
      <button onclick="checkAnswer(3, 'c')">c) București, România</button>
    </div>

    <div id="success" class="success-message">
      <h1>🎉 Felicitări! Ai terminat quiz-ul! </h1><br>
      <h5>Pentru a putea porni spre următorul checkpoint trimite o poză (la același număr de telefon) cu toată echipa stând într-o poziție de yoga langă stadion :D</h5>
    </div>
  </div>

  <script>
    function startQuiz() {
      document.getElementById('intro').classList.remove('active');
      document.getElementById('q1').classList.add('active');
    }

    function checkAnswer(q, answer) {
      const correct = {1: 'a', 2: 'b', 3: 'a'};
      if (answer === correct[q]) {
        document.getElementById('q' + q).classList.remove('active');
        if (q < 3) {
          document.getElementById('q' + (q + 1)).classList.add('active');
        } else {
          document.getElementById('success').classList.add('active');
        }
      } else {
        alert("Răspuns greșit! Încearcă din nou.");
      }
    }
  </script>
</body>
</html>
