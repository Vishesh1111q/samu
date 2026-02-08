# samu
valentine
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>For Sam 💖</title>

  <style>
    * {
      box-sizing: border-box;
      font-family: "Poppins", system-ui, -apple-system;
    }

    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(180deg, #ff9a9e, #fad0c4);
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    .container {
      background: #fff;
      width: 92%;
      max-width: 360px;
      padding: 28px 20px;
      border-radius: 22px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
    }

    h1 {
      margin: 0;
      font-size: 28px;
      color: #ff4f7b;
    }

    p {
      font-size: 18px;
      margin: 14px 0 24px;
      color: #444;
    }

    .buttons {
      display: flex;
      gap: 14px;
      position: relative;
    }

    button {
      flex: 1;
      border: none;
      padding: 14px 0;
      font-size: 18px;
      font-weight: 600;
      border-radius: 999px;
      color: #fff;
      background: linear-gradient(135deg, #ff4f7b, #ff7eb3);
      cursor: pointer;
      transition: transform 0.15s ease;
    }

    button:active {
      transform: scale(0.95);
    }

    #message {
      margin-top: 20px;
      font-size: 22px;
      font-weight: 700;
      color: #ff4f7b;
      display: none;
      animation: pop 0.6s ease;
    }

    .heart {
      position: fixed;
      font-size: 22px;
      animation: floatUp 3s ease forwards;
      pointer-events: none;
    }

    @keyframes floatUp {
      from { opacity: 1; transform: translateY(0) scale(1); }
      to { opacity: 0; transform: translateY(-250px) scale(1.5); }
    }

    @keyframes pop {
      from { transform: scale(0.6); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    iframe {
      display: none;
    }
  </style>
</head>

<body>
  <div class="container">
    <h1>Hey Sam 💕</h1>
    <p>Will you be my Valentine?</p>

    <div class="buttons">
      <button id="yes">Yes 💖</button>
      <button id="no">No 😅</button>
    </div>

    <div id="message">
      IT’S A DATE 💘<br />
      Happy Valentine’s, Sam 🥰
    </div>
  </div>

  <iframe id="music" allow="autoplay"></iframe>

  <script>
    const yesBtn = document.getElementById("yes");
    const noBtn = document.getElementById("no");

    yesBtn.addEventListener("click", startLove);
    noBtn.addEventListener("mouseover", moveNo);
    noBtn.addEventListener("touchstart", moveNo);

    function startLove() {
      document.getElementById("message").style.display = "block";
      document.getElementById("music").src =
        "https://www.youtube.com/embed/GxldQ9eX2wo?autoplay=1";

      for (let i = 0; i < 25; i++) createHeart();
    }

    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.textContent = "💖";
      heart.style.left = Math.random() * window.innerWidth + "px";
      heart.style.top = window.innerHeight - 30 + "px";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 3000);
    }

    function moveNo() {
      const x = Math.random() * 200 - 100;
      const y = Math.random() * 200 - 100;
      noBtn.style.transform = `translate(${x}px, ${y}px)`;
    }
  </script>
</body>
</html>
