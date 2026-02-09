<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Para Wilenny 💖</title>

<style>
body{
margin:0;
font-family: 'Segoe UI', sans-serif;
background: linear-gradient(135deg,#ff758c,#ff7eb3,#ffc3a0);
height:100vh;
display:flex;
justify-content:center;
align-items:center;
overflow:hidden;
}

/* Contenedor */
.container{
text-align:center;
color:white;
z-index:2;
}

h1{
font-size:32px;
text-shadow:0 0 15px rgba(255,255,255,0.8);
animation: latido 1.5s infinite;
}

@keyframes latido{
0%{transform:scale(1);}
50%{transform:scale(1.1);}
100%{transform:scale(1);}
}

button{
padding:15px 30px;
font-size:18px;
border:none;
border-radius:30px;
margin:10px;
cursor:pointer;
transition:0.3s;
}

#si{
background:white;
color:#ff4d6d;
box-shadow:0 0 20px rgba(255,255,255,0.8);
}

#si:hover{
transform:scale(1.2);
}

#no{
background:#444;
color:white;
position:absolute;
}

/* Sobre */
.sobre{
position:fixed;
width:200px;
height:120px;
background:#ff4d6d;
bottom:-200px;
left:50%;
transform:translateX(-50%);
border-radius:10px;
display:flex;
justify-content:center;
align-items:center;
color:white;
font-size:30px;
transition:1s;
}

.sobre.abrir{
bottom:50%;
transform:translate(-50%,-50%) scale(1.2);
}

/* Carta */
.carta{
position:fixed;
background:white;
padding:30px;
border-radius:15px;
width:320px;
text-align:center;
transform:scale(0);
transition:0.5s;
box-shadow:0 0 30px rgba(0,0,0,0.3);
}

.carta.mostrar{
transform:scale(1);
}

.carta h2{
color:#ff4d6d;
}

.carta p{
color:#333;
font-size:18px;
}

/* Corazones */
.corazon{
position:absolute;
color:white;
animation:flotar linear infinite;
}

@keyframes flotar{
from{
transform:translateY(100vh);
opacity:1;
}
to{
transform:translateY(-10vh);
opacity:0;
}
}

/* brillo */
.brillo{
position:absolute;
width:5px;
height:5px;
background:white;
border-radius:50%;
animation:brillar 2s infinite;
}

@keyframes brillar{
0%,100%{opacity:0;}
50%{opacity:1;}
}
</style>

</head>
<body>

<div class="container">
<h1>Wilenny, ¿quieres ser mi San Valentín? 💖</h1>
<button id="si" onclick="animacion()">Sí 💕</button>
<button id="no" onmouseover="escapar()">No 💔</button>
</div>

<div class="sobre" id="sobre">💌</div>

<div class="carta" id="carta">
<h2>Para Wilenny 💖</h2>
<p>
Wilenny,<br><br>
Desde que llegaste, todo es más bonito.  
Tu sonrisa ilumina mis días y haces que mi corazón lata más fuerte.  
<br><br>
Hoy quiero preguntarte algo especial...  
<br><br>
¿Quieres ser mi San Valentín? 🌹  
<br><br>
Con cariño 💕
</p>
</div>

<script>

function escapar(){
let b=document.getElementById("no");
b.style.left=Math.random()*window.innerWidth+"px";
b.style.top=Math.random()*window.innerHeight+"px";
}

function animacion(){

let sobre=document.getElementById("sobre");
let carta=document.getElementById("carta");

sobre.classList.add("abrir");

setTimeout(()=>{
carta.classList.add("mostrar");
},800);

explosionCorazones();
}

/* corazones flotando */
function crearCorazon(){
let c=document.createElement("div");
c.className="corazon";
c.innerHTML="💖";
c.style.left=Math.random()*100+"vw";
c.style.fontSize=(Math.random()*20+15)+"px";
c.style.animationDuration=(Math.random()*3+3)+"s";
document.body.appendChild(c);

setTimeout(()=>c.remove(),6000);
}

setInterval(crearCorazon,300);

/* explosion */
function explosionCorazones(){

for(let i=0;i<20;i++){
let c=document.createElement("div");
c.innerHTML="💖";
c.style.position="fixed";
c.style.left="50%";
c.style.top="50%";
c.style.fontSize="30px";
c.style.transition="1s";
document.body.appendChild(c);

setTimeout(()=>{
c.style.left=Math.random()*window.innerWidth+"px";
c.style.top=Math.random()*window.innerHeight+"px";
c.style.opacity="0";
},50);

setTimeout(()=>c.remove(),1000);
}

}

</script>

</body>
</html>
