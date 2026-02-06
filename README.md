<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Ritika ❤️</title>

<style>
body{
  margin:0;
  height:100vh;
  background:url("background.jpg") center/cover no-repeat;
  display:flex;
  justify-content:center;
  align-items:center;
  font-family:Arial, sans-serif;
  overflow:hidden;
}

/* dark overlay */
body::before{
  content:"";
  position:absolute;
  inset:0;
  background:rgba(0,0,0,0.65);
}

/* card */
.card{
  position:relative;
  z-index:2;
  background:rgba(0,0,0,0.75);
  width:90%;
  max-width:330px;
  padding:24px;
  border-radius:20px;
  color:white;
  text-align:center;
  animation:idleFloat 3s ease-in-out infinite;
}

@keyframes idleFloat{
  0%,100%{transform:translateY(0);}
  50%{transform:translateY(-6px);}
}

button{
  padding:12px 22px;
  margin:10px;
  border:none;
  border-radius:25px;
  font-size:14px;
  cursor:pointer;
}

#yes{background:#ff4da6;color:white;}
#no{background:#444;color:white;}

/* celebration */
.burst{
  position:absolute;
  font-size:30px;
  animation:burst 1s ease-out forwards;
}

@keyframes burst{
  to{
    transform:translate(var(--x), var(--y)) scale(0);
    opacity:0;
  }
}

/* raining hearts */
.rain{
  position:absolute;
  top:-30px;
  font-size:22px;
  animation:rain 4s linear forwards;
}

@keyframes rain{
  to{
    transform:translateY(120vh);
    opacity:0;
  }
}

/* glow pulse */
.glow{
  animation:glowPulse 1.2s ease-in-out infinite;
}

@keyframes glowPulse{
  0%,100%{box-shadow:0 0 20px #ff4da6;}
  50%{box-shadow:0 0 60px #ff4da6;}
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
// start music on tap
document.body.addEventListener("click",()=>{
  const m=document.getElementById("music");
  if(m) m.play();
},{once:true});

// YES clicked
document.getElementById("yes").onclick=function(){
  const card=document.getElementById("card");
  card.classList.add("glow");

  // burst explosion
  for(let i=0;i<25;i++){
    let b=document.createElement("div");
    b.className="burst";
    b.innerHTML="💖";
    b.style.left="50%";
    b.style.top="50%";
    b.style.setProperty("--x",(Math.random()*400-200)+"px");
    b.style.setProperty("--y",(Math.random()*400-200)+"px");
    document.body.appendChild(b);
    setTimeout(()=>b.remove(),1000);
  }

  // heart rain
  setInterval(()=>{
    let r=document.createElement("div");
    r.className="rain";
    r.innerHTML="💘";
    r.style.left=Math.random()*100+"vw";
    document.body.appendChild(r);
    setTimeout(()=>r.remove(),4000);
  },200);
};

// NO button moves
document.getElementById("no").onmouseover=function(){
  this.style.position="relative";
  this.style.left=Math.random()*120-60+"px";
  this.style.top=Math.random()*80-40+"px";
};
</script>

</body>
</html>

