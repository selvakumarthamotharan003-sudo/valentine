<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>For You 💖</title>

  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(to right, #ff9a9e, #fad0c4);
      text-align: center;
      margin: 0;
      height: 100vh;
      overflow: hidden;
    }

    h1 {
      color: #b30059;
      margin-top: 120px;
    }

    p {
      font-size: 20px;
      color: #800040;
    }

    button {
      padding: 15px 30px;
      font-size: 18px;
      margin: 20px;
      border-radius: 10px;
      border: none;
      cursor: pointer;
    }

    #yes {
      background-color: #ff4d88;
      color: white;
    }

    #no {
      background-color: #777;
      color: white;
      position: absolute;
    }

    .hint {
      font-size: 14px;
      opacity: 0.7;
    }
  </style>
</head>

<body onclick="startMusic()">

  <h1>Hey VEE 💕</h1>
  <p>Will you be my Valentine? 💘</p>

  <button id="yes" onclick="yesClicked()">Yes 😍</button>
  <button id="no" onmouseover="moveNo()">No 🙈</button>

  <p class="hint">(Tap anywhere if music doesn’t start 🎶)</p>

  <audio id="bgMusic" loop>
    <source src="music.mp3" type="audio/mpeg">
  </audio>

  <script>
    const music = document.getElementById("bgMusic");
    let started = false;

    function startMusic() {
      if (!started) {
        music.play();
        started = true;
      }
    }

    function yesClicked() {
      document.body.innerHTML = `
        <h1>Yayyy 💖</h1>
        <p>VEE, you just made me the happiest person 😘</p>
        <p>Happy Valentine’s Day 💕</p>
      `;
    }

    function moveNo() {
      const noBtn = document.getElementById("no");
      const x = Math.random() * (window.innerWidth - 120);
      const y = Math.random() * (window.innerHeight - 60);
      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    }
  </script>

</body>
</html>
