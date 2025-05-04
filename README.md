Code
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>May Secret Countdown</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(270deg, #ff9a9e, #fad0c4, #fbc2eb, #a6c1ee);
      background-size: 800% 800%;
      animation: gradientBG 20s ease infinite;
      color: #fff;
      text-align: center;
      padding-top: 100px;
    }

    @keyframes gradientBG {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    h1 {
      font-size: 2.5em;
      margin-bottom: 20px;
    }

    #countdown {
      font-size: 2em;
      margin-bottom: 30px;
    }

    .download-button {
      display: inline-block;
      background-color: #ffffff;
      color: #ff1493;
      text-decoration: none;
      padding: 15px 30px;
      border-radius: 10px;
      font-size: 1.2em;
      font-weight: bold;
      transition: background-color 0.3s;
    }

    .download-button:hover {
      background-color: #f0f0f0;
    }
  </style>
</head>
<body>
  <h1>Hello Queen TJ Temi See your secret for the month of May</h1>
  <div id="countdown"></div>

  <!-- https://ibb.co/RGy1Tqgd -->
  <a href="https://ibb.co/RGy1Tqgd" download class="download-button">Click to view</a>

  <script>
    const targetDate = new Date("May 20, 2025 00:00:00").getTime();
    const countdown = document.getElementById("countdown");

    const timer = setInterval(() => {
      const now = new Date().getTime();
      const distance = targetDate - now;

      if (distance < 0) {
        clearInterval(timer);
        countdown.innerHTML = "It's May 20! Unlock your secret!";
        return;
      }

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      countdown.innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;
    }, 1000);
  </script>
</body>
</html>
