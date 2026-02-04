<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>For Cherie ❤️</title>

<style>
body{
  margin:0;
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  font-family:Arial, sans-serif;
  background:linear-gradient(135deg,#ff9a9e,#fad0c4);
  overflow:hidden;
  text-align:center;
}

.card{
  background:white;
  padding:40px;
  border-radius:20px;
  box-shadow:0 10px 25px rgba(0,0,0,0.2);
  max-width:340px;
}

h1{color:#ff4b6e;margin-bottom:8px;}
h3{color:#666;margin-bottom:20px;}

button{
  padding:12px 25px;
  margin:8px;
  font-size:18px;
  border:none;
  border-radius:10px;
  cursor:pointer;
}

#yes{background:#ff4b6e;color:white;}
#no{background:#ddd;position:relative;}

.message{
  margin-top:20px;
  font-size:18px;
  color:#ff4b6e;
  min-height:70px;
  font-weight:bold;
}

.heart{
  position:absolute;
  font-size:22px;
  animation:float 3s linear infinite;
}

@keyframes float{
  from{transform:translateY(0);opacity:1;}
  to{transform:translateY(-250px);opacity:0;}
}
</style>
</head>

<body>

<div class="card">
  <h1>Cherie ❤️</h1>
  <h3>Will you be my Valentine?<br>— from Mine 💌</h3>

  <button id="yes">Yes 💖</button>
  <button id="no">No 😢</button>

  <div id="typing" class="message"></div>
</div>

<script>
const yes=document.getElementById("yes");
const no=document.getElementById("no");
const typing=document.getElementById("typing");

const loveText =
"Cherie...\nFrom the day you came into my life,\nEverything feels brighter ❤️\nWill you be my Valentine? 🥰";

yes.onclick=()=>{
  typeWriter(loveText);
  hearts();

  // opens Taylor Swift Lover
  window.open("https://www.youtube.com/watch?v=-BjZmE2gtdo","_blank");
};

no.onmouseover=()=>{
  const x=Math.random()*300-150;
  const y=Math.random()*200-100;
  no.style.transform=`translate(${x}px,${y}px)`;
};

function typeWriter(text){
  let i=0;
  typing.innerHTML="";

  function type(){
    if(i<text.length){
      typing.innerHTML+=text.charAt(i)==="\n"?"<br>":text.charAt(i);
      i++;
      setTimeout(type,40);
    }
  }
  type();
}

function hearts(){
  for(let i=0;i<25;i++){
    const h=document.createElement("div");
    h.innerHTML="❤️";
    h.className="heart";
    h.style.left=Math.random()*window.innerWidth+"px";
    h.style.top=window.innerHeight+"px";
    document.body.appendChild(h);
    setTimeout(()=>h.remove(),3000);
  }
}
</script>

</body>
</html>
