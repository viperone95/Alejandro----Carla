<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abel ❤️ Carla</title>

<style>
body{
  margin:0;
  background:black;
  overflow:hidden;
  font-family:Arial;
  color:white;
  text-align:center;
}

/* BOTÓN */
#btn{
  position:absolute;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%);
  padding:15px 30px;
  border-radius:30px;
  background:rgba(255,100,150,0.3);
  border:1px solid pink;
  cursor:pointer;
  font-size:20px;
  backdrop-filter:blur(10px);
}

/* CONTENIDO OCULTO */
#contenido{
  display:none;
  animation:fade 2s ease;
}

/* FOTO */
#foto{
  width:80%;
  max-width:350px;
  border-radius:20px;
  margin-top:20px;
  box-shadow:0 0 30px pink;
  transform:scale(0.8);
  animation:zoom 2s forwards;
}

/* TEXTO */
#mensaje{
  margin-top:20px;
  font-size:18px;
  padding:0 20px;
  animation:fade 3s;
}

/* EFECTOS */
@keyframes fade{
  from{opacity:0;}
  to{opacity:1;}
}

@keyframes zoom{
  to{transform:scale(1);}
}

/* CORAZONES FLOTANDO */
.corazon{
  position:absolute;
  color:pink;
  animation:flotar 5s linear infinite;
}

@keyframes flotar{
  0%{transform:translateY(100vh) scale(0);}
  100%{transform:translateY(-10vh) scale(1.5);}
}
</style>
</head>

<body>

<div id="btn">Tócame 💖</div>

<div id="contenido">
  <h1>Abel ❤️ Carla</h1>

  <!-- TU FOTO -->
  <img id="foto" src="foto.jpg">

  <div id="mensaje">
    Desde que llegaste a mi vida…<br><br>
    todo cambió.<br><br>
    No sé cómo explicarlo… pero contigo<br>
    todo se siente más bonito, más real… más yo 💖<br><br>
    Y si tuviera que elegir otra vez…<br>
    te elegiría a ti… mil veces más ✨
  </div>
</div>

<!-- MÚSICA -->
<audio id="music" loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
</audio>

<script>
const btn = document.getElementById("btn");
const contenido = document.getElementById("contenido");
const music = document.getElementById("music");

btn.onclick = () => {
  btn.style.display="none";
  contenido.style.display="block";
  music.play();
  crearCorazones();
}

/* CORAZONES */
function crearCorazones(){
  setInterval(()=>{
    let heart = document.createElement("div");
    heart.className="corazon";
    heart.innerHTML="❤️";
    heart.style.left=Math.random()*100+"vw";
    heart.style.fontSize=(10+Math.random()*20)+"px";
    document.body.appendChild(heart);

    setTimeout(()=>heart.remove(),5000);
  },300);
}
</script>

</body>
</html>
