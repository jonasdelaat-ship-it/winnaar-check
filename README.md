<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Winnaar checker</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .container {
      background: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      max-width: 500px;
      width: 100%;
      text-align: center;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
      margin-top: 15px;
    }
    button {
      cursor: pointer;
    }
    img {
      max-width: 100%;
      margin: 20px 0;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <div class="container" id="app">
    <h2>Vul je naam in</h2>
    <input type="text" id="nameInput" placeholder="Je naam" />
    <br />
    <button onclick="start()">Check</button>
  </div>

  <script>
    const winners = ["tanja", "dinkske", "arnaud", "rosse", "papa", "audrey"];

    function start() {
      const name = document.getElementById("nameInput").value.trim().toLowerCase();
      if (!name) return;

      if (name === "thibaut") {
        stepThibaut1();
      } else if (winners.includes(name)) {
        stepWinner1();
      } else {
        document.getElementById("app").innerHTML = "<h2>Naam niet herkend</h2>";
      }
    }

    // ----- GEWONE WINNAARS -----
    function stepWinner1() {
      document.getElementById("app").innerHTML = `
        <h2>🎉 Proficiat!</h2>
        <p>U hebt gewonnen.</p>
        <button onclick="stepWinner2()">Next</button>
      `;
    }

    function stepWinner2() {
      document.getElementById("app").innerHTML = `
        <h1>In het leven</h1>
        <img src="https://github.com/jonasdelaat-ship-it/winnaar-check/raw/925870e74ee05079cf44150fc704ee31e429b329/20260104_174621.jpg" alt="leven" />
        <p>Want je hebt mij.</p>
        <button onclick="stepWinner3()">Next</button>
      `;
    }

    function stepWinner3() {
      document.getElementById("app").innerHTML = `
        <h1>Maar helaas heb je dit jaar niet gewonnen</h1>
        <p>Probeer volgend jaar opnieuw</p>
      `;
    }

    // ----- THIBAUT -----
    function stepThibaut1() {
      document.getElementById("app").innerHTML = `
        <h2>🎉 Proficiat!</h2>
        <p>U hebt gewonnen</p>
        <button onclick="stepThibaut2()">Next</button>
      `;
    }

    function stepThibaut2() {
      document.getElementById("app").innerHTML = `
        <h1>In het leven</h1>
        <img src="https://github.com/jonasdelaat-ship-it/winnaar-check/raw/925870e74ee05079cf44150fc704ee31e429b329/20260104_174621.jpg" alt="leven" />
        <p>Want je hebt mij.</p>
        <button onclick="stepThibaut3()">Next</button>
      `;
    }

    function stepThibaut3() {
      document.getElementById("app").innerHTML = `
        <p>En ook met de sokken wedstrijd</p>
        <button onclick="stepThibaut4()">Next</button>
      `;
    }

    function stepThibaut4() {
      document.getElementById("app").innerHTML = `
        <h1>Maar heb je echt gewonnen?</h1>
        <img src="https://raw.githubusercontent.com/jonasdelaat-ship-it/winnaar-check/fdd751dcbbcb1ec8060b7351e274d1585b2c7ba9/20260104_175209.jpg" alt="twijfel" />
      `;
    }
  </script>
</body>
</html>
