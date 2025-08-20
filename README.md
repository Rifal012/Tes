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
    }

    h1 {
      margin-top: 30px;
      font-size: 3em;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.5);
    }

    p {
      font-size: 1.3em;
      margin-bottom: 20px;
    }

    #countdown {
      font-size: 2em;
      margin: 20px 0;
      font-weight: bold;
      color: #ffeb3b;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
    }

    /* Slideshow Foto */
    .slideshow {
      max-width: 400px;
      margin: 30px auto;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 8px 20px rgba(0,0,0,0.3);
    }

    .slides {
      display: flex;
      width: 100%;
      animation: slide 25s infinite;
    }

    .slides img {
      width: 100%;
      border-radius: 20px;
    }

    @keyframes slide {
      0% { transform: translateX(0%); }
      20% { transform: translateX(0%); }
      25% { transform: translateX(-100%); }
      45% { transform: translateX(-100%); }
      50% { transform: translateX(-200%); }
      70% { transform: translateX(-200%); }
      75% { transform: translateX(-300%); }
      95% { transform: translateX(-300%); }
      100% { transform: translateX(-400%); }
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
      margin: 20px 0;
      transition: transform 0.2s;
    }

    #loveBtn:hover {
      transform: scale(1.1);
    }

    footer {
      margin-top: 40px;
      font-size: 1.1em;
      color: #fff5f7;
    }
  </style>
</head>
<body>
  <h1>💖 Untuk Kamu, Cintaku 💖</h1>
  <p>Terima kasih sudah selalu ada di sisiku. Aku akan mencintaimu selamanya 😘</p>

  <!-- Countdown -->
  <div id="countdown">Loading...</div>

  <!-- Slideshow Foto -->
  <div class="slideshow">
    <div class="slides">
      <img src="https://picsum.photos/400/300?random=1" alt="Foto Kita 1">
      <img src="https://picsum.photos/400/300?random=2" alt="Foto Kita 2">
      <img src="https://picsum.photos/400/300?random=3" alt="Foto Kita 3">
      <img src="https://picsum.photos/400/300?random=4" alt="Foto Kita 4">
      <img src="https://picsum.photos/400/300?random=5" alt="Foto Kita 5">
    </div>
  </div>

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

    // Countdown ke tanggal jadian (ubah sesuai tanggalmu)
    const countDownDate = new Date("2025-09-25T00:00:00").getTime();
    function updateCountdown() {
      const now = new Date().getTime();
      const distance = countDownDate - now;

      if (distance < 0) {
        document.getElementById("countdown").innerHTML = "Hari Spesial Kita Telah Tiba! ❤️";
        return;
      }

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000*60*60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000*60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById("countdown").innerHTML = 
        `${days} Hari ${hours} Jam ${minutes} Menit ${seconds} Detik Menuju Hari Spesial Kita 💖`;
    }
    setInterval(updateCountdown, 1000);
    updateCountdown();

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
