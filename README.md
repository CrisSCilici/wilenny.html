<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Para Wilenny 💖</title>

<style>

/* Fondo optimizado */
body{
margin:0;
height:100vh;
display:flex;
justify-content:center;
align-items:center;
font-family:'Segoe UI',sans-serif;
background:linear-gradient(270deg,#ff758c,#ff7eb3,#ffc2d1,#ff758c);
background-size:400% 400%;
animation:fondo 12s ease infinite;
overflow:hidden;
}

@keyframes fondo{
0%{background-position:0% 50%;}
50%{background-position:100% 50%;}
100%{background-position:0% 50%;}
}

/* Contenedor */
.container{
text-align:center;
color:white;
padding:20px;
}

/* Texto */
h1{
font-size: clamp(24px,5vw,40px);
text-shadow:0 0 20px rgba(255,255,255,0.8);
animation:latido 2s infinite;
}

@keyframes latido{
0%,100%{transform:scale(1);}
50%{transform:scale(1.08);}
}

/* Botones */
button{
padding:14px 28px;
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
transform:scale(1.15);
}

#no{
background:rgba(0,0,0,0.5);
color:white;
position:absolute;
}

/* Sobre */
.sobre{
position:fixed;
width:220px;
height:140px;
background:linear-gradient(145deg,#ff4d6d,#ff758c);
bottom:-200px;
left:50%;
transform:translateX(-50%);
border-radius:12px;
display:flex;
justify-content:center;
align-items:center;
font-size:40px;
color:white;
box-shadow:0 10px 30px rgba(0,0,0,0.3);
transition:1s;
}

.sobre.abrir{
bottom:50%;
transform:translate(-50%,-50%) scale(1.1);
}

/* Carta */
.carta{
position:fixed;
background:white;
padding:30px;
border-radius:15px;
width:min(90%,350px);
text-align:center;
transform:scale(0);
transition:0.5s;
box-shadow:0 10px 40px rgba(0,0,0,0.3);
}

.carta.mostrar{
transform:scale(1);
}

.carta h2{
color:#ff4d6d;
}

.carta p{
color:#444;
line-height:1.5;
}

/* Corazones optimizados */
.corazon{
position:absolute;
pointer-events:none;
animation:flotar linear forwards;
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

/* Partículas */
.particula{
position:fixed;
width:6px;
height:6px;
background:white;
border-radius:50%;
opacity:0.7;
animation:particula 2s forwards;
}

@keyframes particula{
to{
transform:translate(var(--x),var(--y));
opacity:0;
}
}

</style>
</head>
<body>

<div class="container">
<h1>Wilenny, ¿quieres ser mi San Valentín? 💖</h1>

<button id="si" onclick="abrir()">Sí 💕</button>

<button id="no" ontouchstart="escapar()" onmouseover="escapar()">No 💔</button>
</div>

<div class="sobre" id="sobre">💌</div>

<div class="carta" id="carta">

<h2>Para Wilenny 💖</h2>

<p>
Wilenny,<br><br>

Eres alguien muy especial.  
Desde que apareciste, todo se siente diferente... más bonito.  

Tu sonrisa ilumina todo y haces que mi corazón lata más fuerte.  

<br><br>

Hoy quiero preguntarte algo desde el corazón...  

<br><br>

¿Quieres ser mi San Valentín? 🌹  

<br><br>

💖
</p>

</div>

<script>

/* Botón No escapa */
function escapar(){

let b=document.getElementById("no");

let x=Math.random()*(window.innerWidth-100);
let y=Math.random()*(window.innerHeight-50);

b.style.left=x+"px";
b.style.top=y+"px";

}

/* Abrir carta */
function abrir(){

let sobre=document.getElementById("sobre");
let carta=document.getElementById("carta");

sobre.classList.add("abrir");

explosion();

setTimeout(()=>{
carta.classList.add("mostrar");
},700);

}

/* Corazones suaves optimizados */
function crearCorazon(){

let c=document.createElement("div");

c.className="corazon";
c.innerHTML="💖";

c.style.left=Math.random()*100+"vw";
c.style.fontSize=(Math.random()*15+15)+"px";

c.style.animationDuration=(Math.random()*3+4)+"s";

document.body.appendChild(c);

setTimeout(()=>c.remove(),7000);

}

setInterval(crearCorazon,500);

/* Explosión optimizada */
function explosion(){

for(let i=0;i<25;i++){

let p=document.createElement("div");

p.className="particula";

p.style.left="50%";
p.style.top="50%";

p.style.setProperty("--x",(Math.random()*400-200)+"px");
p.style.setProperty("--y",(Math.random()*400-200)+"px");

document.body.appendChild(p);

setTimeout(()=>p.remove(),2000);

}

}

</script>

</body>
</html>
