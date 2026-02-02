# Echuuu

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Just Us ❤️</title>
  <style>u
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0;
    }
    .card {
      background: white;
      padding: 25px;
      border-radius: 20px;
      width: 90%;
      max-width: 400px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
      text-align: center;
    }
    h1 { color: #e63946; }
    button {
      padding: 12px 20px;
      border: none;
      border-radius: 25px;
      font-size: 16px;
      cursor: pointer;
      background: #e63946;
      color: white;
      margin-top: 15px;
    }
    input {
      padding: 10px;
      width: 90%;
      border-radius: 10px;
      border: 1px solid #ccc;
      margin-top: 10px;
    }
    .hidden { display: none; }
  </style>
</head>
<body>
  <div class="card" id="login">
    <h1>🔒 Private</h1>
    <p>This page is only for us.</p>
    <input type="password" id="pass" placeholder="Our secret code" />
    <button onclick="checkPass()">Enter</button>
  </div>

  <div class="card hidden" id="questions">
    <h1>For You ❤️</h1>
    <p id="q"></p>
    <input type="text" id="ans" placeholder="Your answer..." />
    <button onclick="nextQ()">Next</button>
  </div>

  <div class="card hidden" id="final">
    <h1>One Last Question 💖</h1>
    <p>Will you be my Valentine?</p>
    <button onclick="yes()">YES 💘</button>
  </div>

  <div class="card hidden" id="yes">
    <h1>❤️❤️❤️</h1>
    <p>You just made me the happiest person.</p>
  </div>

  <script>
    const password = "1504"; // CHANGE THIS
    const qs = [
      "Do you remember how we first talked?",
      "What is one thing you love about us?",
      "What Something I always used to say?",
      "What do you wish for us?",
      "What is one thing u loves abt me no matter what?"
    ];
    let i = 0;

    function checkPass() {
      if (document.getElementById('pass').value === password) {
        document.getElementById('login').classList.add('hidden');
        document.getElementById('questions').classList.remove('hidden');
        document.getElementById('q').innerText = qs[i];
      } else {
        alert('Wrong code 😅');
      }
    }

    function nextQ() {
      i++;
      if (i < qs.length) {
        document.getElementById('q').innerText = qs[i];
        document.getElementById('ans').value = "";
      } else {
        document.getElementById('questions').classList.add('hidden');
        document.getElementById('final').classList.remove('hidden');
      }
    }

    function yes() {
      document.getElementById('final').classList.add('hidden');
      document.getElementById('yes').classList.remove('hidden');
    }
  </script>
</body>
</html>
