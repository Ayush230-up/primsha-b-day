
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Happy Birthday to My Favorite Person! 🌸✨</title>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;600&family=Nunito:wght@400;700&display=swap" rel="stylesheet">
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: radial-gradient(circle at top left, #ffeef5, #ffd1dc, #fbc2eb);
      font-family: 'Nunito', sans-serif;
      overflow: hidden;
      perspective: 1000px;
    }

    /* Floating ambient shapes */
    .bubble {
      position: absolute;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.45);
      animation: floatUp 8s infinite linear;
      pointer-events: none;
    }
    @keyframes floatUp {
      0% { transform: translateY(110vh) scale(0.8); opacity: 0; }
      20% { opacity: 0.8; }
      100% { transform: translateY(-20vh) scale(1.2); opacity: 0; }
    }

    /* Main Card Container */
    .card-container {
      width: 90%;
      max-width: 440px;
      position: relative;
      z-index: 10;
    }

    .card {
      background: rgba(255, 255, 255, 0.85);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      border-radius: 30px;
      padding: 35px 25px;
      text-align: center;
      border: 2px solid rgba(255, 255, 255, 0.9);
      box-shadow: 0 20px 45px rgba(244, 114, 182, 0.25), 0 0 0 8px rgba(255, 255, 255, 0.35);
      transition: transform 0.4s ease;
      min-height: 480px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .layer {
      display: none;
      opacity: 0;
      transform: scale(0.92);
      transition: all 0.5s ease;
      width: 100%;
    }
    .layer.active {
      display: flex;
      flex-direction: column;
      align-items: center;
      opacity: 1;
      transform: scale(1);
    }

    .sticker {
      font-size: 4rem;
      margin-bottom: 12px;
      animation: bounce 2s infinite ease-in-out;
      display: inline-block;
    }
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px) scale(1.05); }
    }

    h1 {
      font-family: 'Fredoka', sans-serif;
      font-size: 1.85rem;
      color: #ff477e;
      margin-bottom: 15px;
      line-height: 1.3;
    }

    p {
      color: #4a5568;
      font-size: 1.05rem;
      line-height: 1.7;
      margin-bottom: 25px;
      padding: 0 10px;
    }

    .pill-tag {
      background: #ffecf2;
      color: #ff477e;
      padding: 6px 16px;
      border-radius: 50px;
      font-size: 0.85rem;
      font-weight: 700;
      margin-bottom: 18px;
      letter-spacing: 0.5px;
      text-transform: uppercase;
      display: inline-block;
    }

    .btn {
      background: linear-gradient(135deg, #ff758c 0%, #ff7eb3 100%);
      color: white;
      border: none;
      padding: 14px 34px;
      font-size: 1rem;
      font-weight: 700;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 8px 20px rgba(255, 117, 140, 0.4);
      transition: all 0.25s ease;
      outline: none;
    }
    .btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 12px 24px rgba(255, 117, 140, 0.5);
    }
    .btn:active {
      transform: scale(0.96);
    }

    /* Floating emojis effect */
    .particle {
      position: absolute;
      pointer-events: none;
      font-size: 1.4rem;
      animation: floatParticle 2.5s ease-out forwards;
    }
    @keyframes floatParticle {
      0% { transform: translateY(0) scale(1); opacity: 1; }
      100% { transform: translateY(-120px) scale(1.4) rotate(45deg); opacity: 0; }
    }
  </style>
</head>
<body>

  <!-- Background Ambience -->
  <div class="bubble" style="width: 80px; height: 80px; left: 10%; animation-duration: 9s;"></div>
  <div class="bubble" style="width: 50px; height: 50px; left: 80%; animation-duration: 6s; animation-delay: 1s;"></div>
  <div class="bubble" style="width: 100px; height: 100px; left: 60%; animation-duration: 11s; animation-delay: 2s;"></div>

  <div class="card-container">
    <div class="card">
      
      <!-- Layer 1: The Cute Surprise Knock -->
      <div class="layer active" id="layer1">
        <div class="sticker">🎂💌</div>
        <div class="pill-tag">Special Delivery</div>
        <h1>Hey, Bestie! ✨</h1>
        <p>A very special day just began, and there's no way I was going to let it slide without celebrating the sweetest human ever!</p>
        <button class="btn" onclick="nextLayer(2)">Open Your Gift 🎁</button>
      </div>

      <!-- Layer 2: The Heartfelt Wish -->
      <div class="layer" id="layer2">
        <div class="sticker">💖🥺</div>
        <div class="pill-tag">A Note For You</div>
        <h1>Happy Birthday!</h1>
        <p>Thank you for being my anchor, my safe place, and the brightest spark in my life. You make everything so much lighter just by existing. Never stop being you.</p>
        <button class="btn" onclick="nextLayer(3)">Make a Wish 🕯️</button>
      </div>

      <!-- Layer 3: The Grand Celebration -->
      <div class="layer" id="layer3">
        <div class="sticker">🧁🎉</div>
        <div class="pill-tag">Forever & Always</div>
        <h1>May All Your Dreams Bloom!</h1>
        <p>Here’s to another year of endless laughs, crazy adventures, and achieving every goal you set your eyes on. Love you tons! 🤍</p>
        <button class="btn" onclick="triggerCelebration(event)">Shower Hugs & Sparks 🌸</button>
      </div>

    </div>
  </div>

  <script>
    function nextLayer(layerNum) {
      document.querySelectorAll('.layer').forEach(l => l.classList.remove('active'));
      const activeLayer = document.getElementById(`layer${layerNum}`);
      activeLayer.classList.add('active');
      createFloatingBatch();
    }

    function triggerCelebration(e) {
      const emojis = ['🌸', '✨', '💖', '🎉', '🍰', '⭐', '🎈'];
      for (let i = 0; i < 25; i++) {
        const particle = document.createElement('div');
        particle.classList.add('particle');
        particle.innerText = emojis[Math.floor(Math.random() * emojis.length)];
        particle.style.left = (window.innerWidth / 2 + (Math.random() * 260 - 130)) + 'px';
        particle.style.top = (window.innerHeight / 2 + (Math.random() * 120 - 60)) + 'px';
        document.body.appendChild(particle);

        setTimeout(() => particle.remove(), 2500);
      }
    }

    function createFloatingBatch() {
      const emojis = ['✨', '💕', '🥳'];
      for (let i = 0; i < 8; i++) {
        const p = document.createElement('div');
        p.classList.add('particle');
        p.innerText = emojis[Math.floor(Math.random() * emojis.length)];
        p.style.left = (window.innerWidth / 2 + (Math.random() * 200 - 100)) + 'px';
        p.style.top = (window.innerHeight / 2 + 50) + 'px';
        document.body.appendChild(p);
        setTimeout(() => p.remove(), 2200);
      }
    }
  </script>
</body>
</html>
