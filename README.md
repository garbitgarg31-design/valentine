<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">

<!-- Mobile-first viewport -->
<meta name="viewport"
      content="width=device-width,
               initial-scale=1.0,
               maximum-scale=1.0,
               user-scalable=no">

<title>For Ritika ❤️</title>

<style>
/* ---------- RESET ---------- */
*{
  box-sizing:border-box;
}

html, body{
  margin:0;
  padding:0;
  height:100%;
}

/* ---------- BODY BACKGROUND ---------- */
body{
  position:relative;
  min-height:100svh;
  background-image:url("background.jpg");
  background-repeat:no-repeat;
  background-size:cover;
  background-position:center top;

  display:flex;
  justify-content:center;
  align-items:flex-end;

  font-family:-apple-system, BlinkMacSystemFont, "Segoe UI", Arial, sans-serif;
  overflow:hidden;
}

/* ---------- DARK GRADIENT OVERLAY ---------- */
body::before{
  content:"";
  position:absolute;
  inset:0;
  background:linear-gradient(
    to top,
    rgba(0,0,0,0.75),
    rgba(0,0,0,0.35),
    rgba(0,0,0,0.15)
  );
  pointer-events:none;
}

/* ---------- CARD ---------- */
.card{
  position:relative;
  z-index:2;

  width:92%;
  max-width:380px;

  margin-bottom:calc(env(safe-area-inset-bottom) + 32px);
  padding:22px 20px;

  background:rgba(0,0,0,0.7);
  color:white;
  border-radius:22px;
  text-align:center;

  animation:floatCard 4s ease-in-out infinite;
}

@keyframes floatCard{
  0%,100%{transform:translateY(0);}
  50%{transform:translateY(-8px);}
}

h2{
  margin:0 0 10px;
  font-size:22px;
}

p{
  margin:0 0 18px;
  font-size:15px;
  line-height:1.6;
}

/* ---------- BUTTONS ---------- */
button{
  width:100%;
  padding:14px 0;
  margin:8px 0;
  border:none;
  border-radius:30px;
  font-size:16px;
  font-weight:600;
  cursor:pointer;
}

#yes{
  background:linear-gradient(135deg,#ff4da6,#ff87c5);
  color:white;
}

#no{
  background:#444;
  color:white;
}

/* ---------- EFFECTS ---------- */
.glow{
  animation:glowPulse 1.4s ease-in-out infinite;
}

@keyframes glowPulse{
  0%,100%{box-shadow:0 0 18px #ff4da6;}
  50%{box-shadow:0 0 50px #ff4da6;}
}

.burst{
  position:absolute;
  font-size:28px;
  animation:burst 1s ease-out forwards;
}

@keyframes burst{
  to{
    transform:translate(var(--x),var(--y)) scale(0);
    opacity:0;
  }
}

.rain{
  position:absolute;
  top:-30px;
  font-size:22px;
  animation:rain 4.5s linear forwards;
}

@keyframes rain{
  to{
    transform:translateY(120svh);
    opacity:0;
  }
}

/* ---------- LAPTOP / DESKTOP ADJUSTMENTS ---------- */
@media (min-width: 900px){

  body{
    align-items:center;
    background-position:center center;
  }

  .card{
    max-width:420px;
    padding:28px;
  }

  h2{
    font-size:26px;
  }

  p{
    font-size:16px;
  }

  button{
    font-size:17px;
  }
}
</style>
</head>

<body>

<audio id="music">
  <source src="music.mp3" type="audio/mpeg">
</audio>

<div class="card" id="card">
  <h2>Ritika 💖</h2>

  <p>
    My heart already chose you…<br><br>
    Will you be my Valentine?
  </p>

  <button id="yes">YES 💕</button>
  <button id="no">NO 🙈</button>
</div>

<script>
/* Music – iPhone safe */
document.body.addEventListener("touchstart",()=>{
  const m=document.getElementById("music");
  if(m) m.play();
},{once:true});

/* YES action */
document.getElementById("yes").onclick=function(){
  const

