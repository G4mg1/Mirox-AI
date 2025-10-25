<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mirox AI — Stay Tuned</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff416c, #ff4b2b);
      overflow: hidden;
      color: #fff;
      animation: fadeIn 1.5s ease-in-out;
    }

    /* Loader overlay */
    .loader-overlay {
      position: absolute;
      inset: 0;
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      z-index: 10;
      animation: fadeIn 0.5s ease-in-out;
    }

    .loader {
      width: 60px;
      height: 60px;
      border: 5px solid rgba(255,255,255,0.3);
      border-top-color: #fff;
      border-radius: 50%;
      animation: spin 1s linear infinite;
      margin-bottom: 15px;
    }

    .loader-text {
      font-size: 1.2rem;
      opacity: 0.9;
      animation: pulse 1.5s infinite;
    }

    @keyframes spin {
      to { transform: rotate(360deg); }
    }

    @keyframes pulse {
      0%, 100% { opacity: 0.7; }
      50% { opacity: 1; }
    }

    .container {
      position: relative;
      background: rgba(255, 255, 255, 0.15);
      backdrop-filter: blur(25px);
      -webkit-backdrop-filter: blur(25px);
      border-radius: 25px;
      padding: 60px 80px;
      text-align: center;
      box-shadow: 0 10px 40px rgba(0, 0, 0, 0.25);
      transform: translateY(20px);
      opacity: 0;
      animation: fadeUp 1.5s ease forwards 0.5s;
    }

    h1 {
      font-size: 2.7rem;
      margin-bottom: 15px;
      background: linear-gradient(to right, #ff7eb3, #ff758c);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    p {
      font-size: 1.1rem;
      margin-bottom: 35px;
      opacity: 0.9;
    }

    .btn {
      background: linear-gradient(135deg, #ff4b2b, #ff416c);
      border: none;
      color: white;
      padding: 15px 45px;
      border-radius: 35px;
      font-size: 1rem;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 0 15px rgba(255, 107, 150, 0.4);
    }

    .btn:hover {
      transform: scale(1.05);
      box-shadow: 0 0 25px rgba(255, 107, 150, 0.7);
    }

    .btn:active {
      transform: scale(0.97);
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    footer {
      position: absolute;
      bottom: 20px;
      font-size: 0.9rem;
      opacity: 0.6;
    }

  </style>
</head>
<body>
  <!-- Checking overlay -->
  <div class="loader-overlay" id="loaderOverlay">
    <div class="loader"></div>
    <div class="loader-text" id="loaderText">Checking tuned list...</div>
  </div>

  <div class="container">
    <h1>Stay Tuned</h1>
    <p>Mirox AI might release soon 🚀</p>
    <button class="btn" id="tuneButton" onclick="stayTuned()">Click to Stay Tuned</button>
  </div>

  <footer>© 2025 Mirox AI — The Future is Coming</footer>

  <script>
    const btn = document.getElementById('tuneButton');
    const loader = document.getElementById('loaderOverlay');
    const loaderText = document.getElementById('loaderText');

  
    window.addEventListener('load', () => {
      setTimeout(() => {
        const isTuned = localStorage.getItem('miroxTuned');
        if (isTuned === 'true') {
          setTunedState();
          loaderText.textContent = 'Already on the list ✅';
        } else {
          loaderText.textContent = 'You’re not tuned yet.';
        }
        
        setTimeout(() => {
          loader.style.opacity = '0';
          loader.style.transition = 'opacity 0.8s ease';
          setTimeout(() => loader.style.display = 'none', 800);
        }, 1200);
      }, 1500);
    });

    function stayTuned() {
      localStorage.setItem('miroxTuned', 'true');
      setTunedState();
    }

    function setTunedState() {
      btn.textContent = 'You’re on the list! ✅';
      btn.style.background = 'linear-gradient(135deg, #ff758c, #ff7eb3)';
      btn.style.boxShadow = '0 0 25px rgba(255, 118, 157, 0.8)';
      btn.disabled = true;
    }
  </script>
</body>
</html>
