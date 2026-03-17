
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #1c1c1c, #444);
      color: #fff;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
    }
    h1 {
      font-size: 3em;
      margin-bottom: 0.5em;
    }
    p {
      font-size: 1.5em;
      margin-bottom: 2em;
    }
    .countdown {
      display: flex;
      gap: 20px;
      font-size: 1.5em;
    }
    .countdown div {
      background: rgba(255,255,255,0.1);
      padding: 20px;
      border-radius: 10px;
    }
    footer {
      position: absolute;
      bottom: 20px;
      font-size: 0.9em;
      opacity: 0.7;
    }
  </style>
</head>
<body>
  <h1>Latest Vapes</h1>
  <p>Our website is launching soon!</p>

  <div class="countdown">
    <div><span id="days">00</span><br>Days</div>
    <div><span id="hours">00</span><br>Hours</div>
    <div><span id="minutes">00</span><br>Minutes</div>
    <div><span id="seconds">00</span><br>Seconds</div>
  </div>

  <footer>&copy; 2026 Latest Vapes. All rights reserved.</footer>

  <script>
    // Set your launch date here (YYYY, M-1, D, H, M, S)
    const launchDate = new Date(2026, 3, 30, 12, 0, 0); // April 30, 2026, 12:00:00

    function updateCountdown() {
      const now = new Date();
      const diff = launchDate - now;

      if (diff <= 0) return;

      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);

      document.getElementById('days').textContent = String(days).padStart(2,'0');
      document.getElementById('hours').textContent = String(hours).padStart(2,'0');
      document.getElementById('minutes').textContent = String(minutes).padStart(2,'0');
      document.getElementById('seconds').textContent = String(seconds).padStart(2,'0');
    }

    setInterval(updateCountdown, 1000);
    updateCountdown();
  </script>
</body>
</html>
