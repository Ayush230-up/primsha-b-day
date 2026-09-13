<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy Birthday Bestie! 🎉</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    body {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #1f1c2c, #928dab);
      overflow: hidden;
      color: #fff;
    }
    .card {
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(15px);
      border-radius: 20px;
      padding: 30px;
      width: 90%;
      max-width: 420px;
      text-align: center;
      border: 1px solid rgba(255, 255, 255, 0.2);
      box-shadow: 0 15px 35px rgba(0,0,0,0.4);
      animation: popIn 0.8s ease-out;
    }
    @keyframes popIn {
      0% { transform: scale(0.6); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }
    h1 {
      font-size: 2rem;
      margin-bottom: 15px;
      color: #ff6b81;
    }
    p {
      font-size: 1.05rem;
      line-height: 1.6;
      color: #f1f2f6;
      margin-bottom: 25px;
    }
    .btn {
      background: linear-gradient(45deg, #ff4757, #ff6b81);
      color: white;
      border: none;
      padding: 12px 28px;
      font-size: 1rem;
      font-weight: bold;
      border-radius: 25px;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(255, 71, 87, 0.4);
      transition: transform 0.2s, box-shadow 0.2s;
    }
    .btn:active {
      transform: scale(0.95);
    }
    .confetti {
      position: absolute;
      width: 10px;
      height: 10px;
      animation: fall 3s linear infinite;
    }
    @keyframes fall {
      0% { transform: translateY(-10vh) rotate(0deg); opacity: 1; }
      100% { transform: translateY(110vh) rotate(720deg); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Happy Birthday! 🎂✨</h1>
    <p>
      Mere sabse acche dost ko janamdin ki dher saari shubhkaamnayein! 🤍 <br><br>
      Meri life ka sabse strong support banne ke liye aur har bewakoofi mein saath dene ke liye thank you. Dua hai tera har sapna sach ho aur teri smile hamesha aisi hi chamakti rahe!
    </p>
    <button class="btn" onclick="startConfetti()">Tap for Magic ✨</button>
  </div>

  <script>
    function createConfetti() {
      const colors = ['#ff4757', '#2ed573', '#1e90ff', '#ffa502', '#ffffff'];
      for (let i = 0; i < 40; i++) {
        const confetti = document.createElement('div');
        confetti.classList.add('confetti');
        confetti.style.left = Math.random() * 100 + 'vw';
        confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
        confetti.style.animationDuration = (Math.random() * 2 + 1.5) + 's';
        confetti.style.opacity = Math.random();
        document.body.appendChild(confetti);

        setTimeout(() => confetti.remove(), 3000);
      }
    }

    function startConfetti() {
      createConfetti();
      setInterval(createConfetti, 1200);
    }
  </script>
</body>
</html>
