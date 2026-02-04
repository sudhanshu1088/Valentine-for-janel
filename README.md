# Valentine-for-janel
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Will You Be My Valentine?</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Poppins', sans-serif;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 30px 25px;
      border-radius: 20px;
      text-align: center;
      width: 90%;
      max-width: 400px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.2);
      animation: pop 1s ease;
    }

    @keyframes pop {
      0% { transform: scale(0.7); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }

    h1 {
      color: #ff4d6d;
      margin-bottom: 10px;
    }

    p {
      font-size: 16px;
      color: #444;
      margin-bottom: 25px;
    }

    .btns {
      display: flex;
      justify-content: center;
      gap: 15px;
    }

    button {
      border: none;
      padding: 12px 25px;
      border-radius: 25px;
      font-size: 16px;
      cursor: pointer;
      transition: 0.3s;
    }

    .yes {
      background: #ff4d6d;
      color: white;
    }

    .yes:hover {
      background: #e63956;
    }

    .no {
      background: #eee;
      color: #333;
      position: relative;
    }

    .hearts span {
      position: absolute;
      color: red;
      font-size: 20px;
      animation: float 5s linear infinite;
    }

    @keyframes float {
      0% {
        transform: translateY(0);
        opacity: 1;
      }
      100% {
        transform: translateY(-100vh);
        opacity: 0;
      }
    }

    .hidden {
      display: none;
    }

    .final {
      font-size: 20px;
      color: #ff4d6d;
    }
  </style>
</head>
<body>

  <div class="card" id="card">
    <h1>Hey Janel Anthony ❤️</h1>
    <p>
      From the moment you came into my life,<br>
      every day felt a little brighter ✨<br><br>
      So I have one important question…
    </p>

    <h2>Will you be my Valentine? 💘</h2>

    <div class="btns">
      <button class="yes" onclick="sayYes()">Yes 💖</button>
      <button class="no" onmouseover="moveNo()">No 🙈</button>
    </div>
  </div>

  <div class="card hidden" id="finalCard">
    <h1>YAYYYYY 🥰💃</h1>
    <p class="final">
      You just made me the happiest person 💕<br><br>
      Happy Valentine’s Day, Janel ❤️<br>
      I can’t wait to create more memories with you 🌹
    </p>
  </div>

  <div class="hearts" id="hearts"></div>

  <script>
    function sayYes() {
      document.getElementById("card").classList.add("hidden");
      document.getElementById("finalCard").classList.remove("hidden");
      createHearts();
    }

    function moveNo() {
      const noBtn = document.querySelector(".no");
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 200 - 100;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    }

    function createHearts() {
      const hearts = document.getElementById("hearts");
      for (let i = 0; i < 30; i++) {
        const span = document.createElement("span");
        span.innerHTML = "❤️";
        span.style.left = Math.random() * 100 + "vw";
        span.style.top = "100vh";
        span.style.fontSize = Math.random() * 20 + 15 + "px";
        span.style.animationDuration = Math.random() * 3 + 3 + "s";
        hearts.appendChild(span);
      }
    }
  </script>

</body>
</html>
