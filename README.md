<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Untuk Sang Rembulan 🌙</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
  <style>
    * {margin:0;padding:0;box-sizing:border-box;font-family:'Poppins',sans-serif;}

    body {
      min-height:100vh;
      display:flex;
      justify-content:center;
      align-items:center;
      color:white;
      background-size:cover;
      background-position:center;
      overflow:auto;
    }

    .overlay {
      position:fixed;
      top:0;left:0;width:100%;height:100%;
      background:rgba(0,0,0,0.5);
      z-index:0;
    }

    .container {
      position:relative;
      z-index:1;
      max-width:700px;
      padding:30px;
      text-align:center;
      background:rgba(255,255,255,0.1);
      backdrop-filter:blur(12px);
      border-radius:20px;
      box-shadow:0 10px 30px rgba(0,0,0,0.5);
      animation:fadeIn 2s ease;
    }

    h1 {font-size:2.5em;margin-bottom:10px;}
    p {margin:10px 0;line-height:1.8;text-align:left;}

    button {
      margin-top:15px;
      padding:10px 20px;
      border:none;
      border-radius:25px;
      background:#ff6b81;
      color:white;
      cursor:pointer;
      transition:0.3s;
    }

    button:hover {transform:scale(1.05);}

    .hidden {display:none;}

    .flowers {
      margin-top:20px;
      font-size:24px;
      opacity:0.8;
    }

    #noBtn {position:relative;}

    .heart {
      position:fixed;
      top:-20px;
      font-size:20px;
      animation:fall linear forwards;
      z-index:999;
    }

    @keyframes fall {
      to {
        transform: translateY(110vh);
        opacity:0;
      }
    }

    @keyframes fadeIn {
      from {opacity:0; transform:translateY(20px);} 
      to {opacity:1; transform:translateY(0);} }
  </style>
</head>

<body style="background-image:url('GANTI_LINK_GAMBAR_KAMU_DI_SINI');">

<div class="overlay"></div>

<div class="container" id="intro">
  <h1>🌙 Untuk Sang Rembulan</h1>
  <p style="text-align:center">Dari: <b>Mu'adz Hafidz</b></p>
  <p style="text-align:center">Untuk: seseorang yang paling indah seperti bulan di malam hari ✨</p>
  <button onclick="start()">Masuk 💙</button>
</div>

<div class="container hidden" id="content">
  <h1>Maaf ya...</h1>
  <p id="text"></p>

  <div id="question" class="hidden" style="text-align:center">
    <h2>Kamu maafin aku gak? 🥺</h2>
    <button onclick="yesClick()">IYAAAAA</button>
    <button id="noBtn">TIDAK</button>
  </div>

  <div class="flowers">🌸 🌹 🌼 🌺</div>
</div>

<script>
const message = `Aku bener-bener minta maaf atas semua kesalahan yang aku lakukan.\n\nAku sadar aku sudah bikin kamu kecewa, dan itu bukan hal yang seharusnya aku lakukan.\n\nAku gak mau kehilangan kamu, karena kamu itu sangat berarti buat aku.\n\nAku janji akan belajar dari kesalahan ini, memperbaiki diri, dan berusaha jadi lebih baik lagi.\n\nAku akan lebih menjaga perasaan kamu, lebih ngerti kamu, dan gak akan mengulangi kesalahan yang sama.\n\nAku harap kamu masih mau kasih aku kesempatan untuk memperbaiki semuanya.`;

function start(){
  document.getElementById('intro').classList.add('hidden');
  document.getElementById('content').classList.remove('hidden');

  let i = 0;
  const speed = 35;
  function type(){
    if(i < message.length){
      let char = message.charAt(i);
      if(char === "\n"){
        document.getElementById('text').innerHTML += "<br><br>";
      } else {
        document.getElementById('text').innerHTML += char;
      }
      i++;
      setTimeout(type, speed);
    } else {
      document.getElementById('question').classList.remove('hidden');
    }
  }
  type();
}

function createHeart(){
  const heart = document.createElement('div');
  heart.classList.add('heart');
  heart.innerHTML = '❤️';
  heart.style.left = Math.random() * 100 + 'vw';
  heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
  document.body.appendChild(heart);

  setTimeout(()=>{
    heart.remove();
  },5000);
}

function yesClick(){
  alert('Makasih yaa ❤️');

  let count = 0;
  const interval = setInterval(()=>{
    createHeart();
    count++;
    if(count > 30) clearInterval(interval);
  },150);
}

const noBtn = document.getElementById('noBtn');
noBtn.addEventListener('mouseover', () => {
  const x = Math.random() * 200 - 100;
  const y = Math.random() * 200 - 100;
  noBtn.style.transform = `translate(${x}px, ${y}px)`;
});
</script>

</body>
</html>
