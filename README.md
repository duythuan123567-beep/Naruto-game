# Naruto-game
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>One Piece GOD+++</title>

<style>
body {background:black;color:white;text-align:center;font-family:sans-serif;}
.box {margin:20px;padding:20px;border:3px solid gold;display:inline-block;}
button {padding:10px;margin:5px;}
select {padding:5px;}
</style>
</head>

<body>

<h1>🏴‍☠️ ONE PIECE GOD+++ 🏴‍☠️</h1>

<div class="box">
<h2 id="money"></h2>
<h2 id="gem"></h2>

<select onchange="changeMap(this.value)">
<option value="0">East Blue</option>
<option value="1">Alabasta</option>
<option value="2">Dressrosa</option>
<option value="3">Wano</option>
<option value="4">Marineford</option>
</select>

<h3 id="map"></h3>

<h2 id="char">Chưa có nhân vật</h2>

<button onclick="roll()">🎲 Random (50💰)</button>

<h3 id="hp"></h3>

<button onclick="attack()">⚔️ Đánh</button>
<button onclick="skill()">💥 Skill</button>
</div>

<script>

let money = 200;
let gem = 0;
let dmg=5, skillDmg=10;
let hp=100;

const maps = [
{name:"East Blue",hp:100,reward:50},
{name:"Alabasta",hp:150,reward:80},
{name:"Dressrosa",hp:200,reward:120},
{name:"Wano",hp:300,reward:200},
{name:"Marineford",hp:500,reward:400}
];

const characters = [
["S","Usopp",5,10],
["S+","Sanji",8,15],
["SS","Zoro",12,25],
["SS+","Ace",16,30],
["SR","Crocodile",20,40],
["SR+","Sabo",25,50],
["UR","Akainu",35,60],
["UR+","Luffy Gear 5",50,100]
];

function roll(){
let pick = characters[Math.floor(Math.random()*characters.length)];
dmg=pick[2];
skillDmg=pick[3];

document.getElementById("char").innerHTML =
"🔥 "+pick[1]+" ("+pick[0]+")";

update();
}

function attack(){
hp-=dmg;
if(hp<=0){
money+=50;
hp=100;
}
update();
}

function skill(){
hp-=skillDmg;
if(hp<=0){
money+=80;
hp=100;
}
update();
}

function update(){
document.getElementById("money").innerHTML="💰 "+money;
document.getElementById("gem").innerHTML="💎 "+gem;
document.getElementById("hp").innerHTML="❤️ "+hp;
}

update();

</script>

</body>
</html>
