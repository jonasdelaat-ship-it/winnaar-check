# winnaar-check
<!DOCTYPE html>
<html lang="nl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Resultaat</title>
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
max-width: 400px;
text-align: center;
}
</style>
</head>
<body>
<div class="container" id="content">
<img id="resultImage" src="" alt="resultaat" style="max-width:100%; border-radius:10px; margin-bottom:20px; display:none;" />
<h2>Even geduld…</h2>
</div>


<script>
// GEHEIME CODES
const winnerCodes = [
"THIBAUT2025"
];


const loserCodes = [
"PAPA2025",
"TANJA2025",
"ROSSE2025",
"ARNAUD2025",
"DINKSE2025"
];


const params = new URLSearchParams(window.location.search);
const code = params.get("code");
const content = document.getElementById("content");


if (!code) {
content.innerHTML = "<h2>❌ Ongeldige link</h2><p>Deze link is niet correct.</p>";
} else if (winnerCodes.includes(code)) {
document.getElementById("resultImage").src = "winner.jpg";
document.getElementById("resultImage").style.display = "block";
content.innerHTML += "<h2>🎉 Gefeliciteerd!</h2><p>Thibaut, jij hebt gewonnen! 🏆</p>";
} else if (loserCodes.includes(code)) {
document.getElementById("resultImage").src = "loser.jpg";
document.getElementById("resultImage").style.display = "block";
content.innerHTML += "<h2>❌ Helaas</h2><p>Deze keer niet gewonnen.</p>";
} else {
content.innerHTML = "<h2>❌ Ongeldige code</h2><p>Deze link werkt niet.</p>";
}
</script>
</body>
</html>
