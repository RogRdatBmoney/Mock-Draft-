# Mock-Draft-<!DOCTYPE html>
<html>
<head>
  <title>Brendan's NBA Draft Simulator</title>
  <style>
    body { font-family: Arial; background: #0a0a0a; color: white; text-align: center; }
    button { padding: 8px 16px; margin: 5px; cursor: pointer; }
    .container { display: flex; justify-content: space-around; margin-top: 20px; }
    .column { width: 45%; }
    .team { margin: 4px; }
    .player { margin: 4px; }
  </style>
</head>
<body>

<h1>🏀 Brendan's NBA Draft Simulator</h1>

<div class="container">

<div class="column">
<h2>Draft Order</h2>
<div id="teams"></div>
</div>

<div class="column">
<h2>Available Players</h2>
<div id="players"></div>
</div>

</div>

<script>

let teams = [
"Hawks","Celtics","Nets","Hornets","Bulls","Cavaliers",
"Mavericks","Nuggets","Pistons","Warriors","Rockets",
"Pacers","Clippers","Lakers","Grizzlies","Heat",
"Bucks","Timberwolves","Pelicans","Knicks","Thunder",
"Magic","76ers","Suns","Blazers","Kings","Spurs",
"Raptors","Jazz","Wizards"
];

// 👇 EDIT THIS LIST TO PICK YOUR OWN DRAFT CLASS
let players = [
"Cooper Flagg",
"Darren Peterson",
"Bronny James",
"Future Star 1",
"Future Star 2",
"Your Custom Prospect"
];

function renderTeams() {
  let output = "";
  teams.forEach((team, index) => {
    output += `<div class="team">
      ${index+1}. ${team}
      <button onclick="draftPlayer(${index})">Draft</button>
    </div>`;
  });
  document.getElementById("teams").innerHTML = output;
}

function renderPlayers() {
  let output = "";
  players.forEach(player => {
    output += `<div class="player">${player}</div>`;
  });
  document.getElementById("players").innerHTML = output;
}

function draftPlayer(teamIndex) {
  if(players.length === 0) return;
  let drafted = players.shift();
  alert(teams[teamIndex] + " drafted " + drafted);
  renderPlayers();
}

renderTeams();
renderPlayers();

</script>

</body>
</html>