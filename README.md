<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>💖 Website Cinta Kita 💖</title>
  <style>
    body {
      margin: 0;
      font-family: 'Arial', sans-serif;
      text-align: center;
      background: linear-gradient(to right, #ffdde1, #ee9ca7);
      overflow: hidden;
      color: white;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    h1 {
      font-size: 3em;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.5);
      margin-bottom: 20px;
    }

    p {
      font-size: 1.3em;
      margin-bottom: 30px;
    }

    /* Hati Jatuh */
    .heart {
      position: fixed;
      top: -10px;
      font-size: 24px;
      color: red;
      animation: fall 5s linear infinite;
    }

    @keyframes fall {
      0% { transform: translateY(-10px); opacity: 1; }
      100% { transform: translateY(100vh); opacity: 0; }
    }

    /* Tombol I Love You */
    #loveBtn {
      background: #ff4081;
      color: white;
      border: none;
      padding: 15px 30px;
      font-size: 1.2em;
      border-radius: 30px;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(0,0,0,0.3);
      transition: transform 0.2s;
    }

    #loveBtn:hover {
      transform: scale(1.1);
    }

    footer {
      margin-top: 40px;
      font-size: 1.1em;
      color: #fff5f7;
      position: absolute;
      bottom: 20px;
    }
  </style>
</head>
<body>
  <h1>💖 Untuk Kamu, Cintaku 💖</h1>
  <p>Terima kasih sudah selalu ada di sisiku. Aku akan mencintaimu selamanya 😘</p>

  <!-- Tombol I Love You -->
  <button id="loveBtn">I Love You ❤️</button>

  <!-- Musik Romantis -->
  <audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mpeg">
    Browser kamu tidak mendukung audio.
  </audio>

  <footer>❤️ Selamanya Milikmu ❤️</footer>

  <script>
    // Hati jatuh otomatis
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.innerHTML = "💖";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 5000);
    }
    setInterval(createHeart, 300);

    // Tombol "I Love You" bikin hati tambahan + kata-kata romantis
    const loveBtn = document.getElementById("loveBtn");
    const kataRomantis = [
      "Aku mencintaimu lebih dari kata-kata bisa ungkapkan 💖",
      "Aku + Kamu = Selamanya ❤️",
      "Kamu adalah bahagiaku setiap hari 😘",
      "Setiap detik bersamamu terasa indah ✨",
      "Aku bersyukur memilikimu di sisiku 💞"
    ];

    loveBtn.addEventListener("click", () => {
      for (let i=0; i<30; i++) createHeart();
      const pesan = kataRomantis[Math.floor(Math.random()*kataRomantis.length)];
      alert(pesan);
    });
  </script>
</body>
</html>
