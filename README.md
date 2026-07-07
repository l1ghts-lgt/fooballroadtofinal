<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<title>FIFA 16 Teams Bracket</title>

<style>
body{
margin:0;
font-family:Arial;
background:#0b1220;
color:white;
}

header{
text-align:center;
padding:15px;
background:#111827;
font-size:26px;
font-weight:bold;
}

.container{
max-width:1400px;
margin:auto;
padding:20px;
}

.bracket{
display:flex;
justify-content:space-between;
gap:15px;
}

/* COLUMNS */
.column{
flex:1;
display:flex;
flex-direction:column;
gap:12px;
}

/* MATCH BOX */
.match{
background:#1e293b;
padding:10px;
border-radius:10px;
text-align:center;
}

.title{
font-size:12px;
opacity:0.7;
margin-bottom:5px;
}

/* INPUTS */
input{
width:90px;
padding:5px;
margin:3px;
border-radius:6px;
border:none;
background:#334155;
color:white;
text-align:center;
}

/* BUTTON */
button{
margin-top:5px;
padding:6px 10px;
border:none;
border-radius:6px;
background:#16a34a;
color:white;
cursor:pointer;
}

button:hover{background:#15803d;}

/* WINNER */
.winner{
margin-top:5px;
color:#facc15;
font-weight:bold;
font-size:13px;
}

/* VISUAL LINES */
.column:not(:last-child){
border-right:2px solid #334155;
padding-right:10px;
}
</style>
</head>

<body>

<header>🏆 FIFA 16 TEAMS ROAD TO FINAL</header>

<div class="container">

<div class="bracket">

<!-- ROUND 1 (16 TEAMS) -->
<div class="column">

<div class="match"><div class="title">1/8</div>
<input id="a1" value="PSV"><input id="a2" value="Arsenal">
<br><button onclick="play(1)">PLAY</button>
<div id="w1" class="winner"></div>
</div>

<div class="match"><div class="title">1/8</div>
<input id="b1" value="Real Madrid"><input id="b2" value="Atletico">
<br><button onclick="play(2)">PLAY</button>
<div id="w2" class="winner"></div>
</div>

<div class="match"><div class="title">1/8</div>
<input id="c1" value="Barcelona"><input id="c2" value="PSG">
<br><button onclick="play(3)">PLAY</button>
<div id="w3" class="winner"></div>
</div>

<div class="match"><div class="title">1/8</div>
<input id="d1" value="Man City"><input id="d2" value="Chelsea">
<br><button onclick="play(4)">PLAY</button>
<div id="w4" class="winner"></div>
</div>

<div class="match"><div class="title">1/8</div>
<input id="e1" value="Bayern"><input id="e2" value="Dortmund">
<br><button onclick="play(5)">PLAY</button>
<div id="w5" class="winner"></div>
</div>

<div class="match"><div class="title">1/8</div>
<input id="f1" value="Inter"><input id="f2" value="Milan">
<br><button onclick="play(6)">PLAY</button>
<div id="w6" class="winner"></div>
</div>

<div class="match"><div class="title">1/8</div>
<input id="g1" value="Juventus"><input id="g2" value="Napoli">
<br><button onclick="play(7)">PLAY</button>
<div id="w7" class="winner"></div>
</div>

<div class="match"><div class="title">1/8</div>
<input id="h1" value="Ajax"><input id="h2" value="Benfica">
<br><button onclick="play(8)">PLAY</button>
<div id="w8" class="winner"></div>
</div>

</div>

<!-- QUARTER FINAL -->
<div class="column">

<div class="match"><div class="title">1/4</div>
<input id="q1"><input id="q2">
<br><button onclick="play(9)">PLAY</button>
<div id="w9" class="winner"></div>
</div>

<div class="match"><div class="title">1/4</div>
<input id="q3"><input id="q4">
<br><button onclick="play(10)">PLAY</button>
<div id="w10" class="winner"></div>
</div>

<div class="match"><div class="title">1/4</div>
<input id="q5"><input id="q6">
<br><button onclick="play(11)">PLAY</button>
<div id="w11" class="winner"></div>
</div>

<div class="match"><div class="title">1/4</div>
<input id="q7"><input id="q8">
<br><button onclick="play(12)">PLAY</button>
<div id="w12" class="winner"></div>
</div>

</div>

<!-- SEMI + FINAL -->
<div class="column">

<div class="match"><div class="title">1/2</div>
<input id="s1"><input id="s2">
<br><button onclick="play(13)">PLAY</button>
<div id="w13" class="winner"></div>
</div>

<div class="match"><div class="title">1/2</div>
<input id="s3"><input id="s4">
<br><button onclick="play(14)">PLAY</button>
<div id="w14" class="winner"></div>
</div>

<div class="match"><div class="title">FINAL</div>
<input id="f1"><input id="f2">
<br><button onclick="play(15)">PLAY FINAL</button>
<div id="w15" class="winner"></div>
</div>

</div>

</div>

</div>

<script>

function play(m){

let w="";

if(m<=8){
w=random(get(m,1),get(m,2));
setNext(m,w);
}

if(m>8 && m<=12){
w=random(get(m,1),get(m,2));
setNext(m,w);
}

if(m>12 && m<=14){
w=random(get(m,1),get(m,2));
setNext(m,w);
}

if(m==15){
w=random(get(m,1),get(m,2));
document.getElementById("w15").innerText="🏆 CHAMPION: "+w;
}
}

function get(m,i){
return document.getElementById(idMap(m,i)).value;
}

function setNext(m,w){

document.getElementById("w"+m).innerText="Winner: "+w;

if(m==1) q1.value=w;
if(m==2) q2.value=w;
if(m==3) q3.value=w;
if(m==4) q4.value=w;
if(m==5) q5.value=w;
if(m==6) q6.value=w;
if(m==7) q7.value=w;
if(m==8) q8.value=w;

if(m==9) s1.value=w;
if(m==10) s2.value=w;
if(m==11) s3.value=w;
if(m==12) s4.value=w;

if(m==13) f1.value=w;
if(m==14) f2.value=w;
}

function idMap(m,i){

const map={
1:["a1","a2"],2:["b1","b2"],3:["c1","c2"],4:["d1","d2"],
5:["e1","e2"],6:["f1","f2"],7:["g1","g2"],8:["h1","h2"],
9:["q1","q2"],10:["q3","q4"],11:["q5","q6"],12:["q7","q8"],
13:["s1","s2"],14:["s3","s4"],15:["f1","f2"]
};

return map[m][i-1];
}

</script>

</body>
</html>****
