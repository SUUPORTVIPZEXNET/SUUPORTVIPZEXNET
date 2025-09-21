<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>About Me - Alessandro</title>
<style>
  body {
    margin: 0;
    overflow: hidden;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color: #e0e0e0;
    background: #0a0a0a;
    position: relative;
  }

  canvas {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 0;
  }

  .content {
    position: relative;
    z-index: 2;
    padding: 40px 20px;
    max-width: 900px;
    margin: auto;
  }

  h1 {
    color: #ffffff;
    font-size: 2.5em;
    margin-bottom: 10px;
    text-shadow: 0 0 12px #ffffff80;
    text-align: left;
  }

  h2 {
    color: #f0f0f0;
    font-size: 1.8em;
    margin-bottom: 20px;
    text-shadow: 0 0 8px #ffffff60;
    text-align: left;
  }

  ul {
    padding-left: 20px;
    list-style: none;
  }

  ul li {
    color: #d0d0d0;
    font-size: 1.2em;
    margin-bottom: 12px;
    line-height: 1.6;
    text-align: left;
  }

  .section {
    margin-bottom: 50px;
  }

  .tech-stack img {
    margin: 5px;
    border-radius: 6px;
    height: 40px;
    transition: transform 0.3s;
    vertical-align: middle;
  }

  .tech-stack img:hover {
    transform: scale(1.2);
  }
</style>
</head>
<body>

<canvas id="matrix"></canvas>

<div class="content">
  <div class="section">
    <h1>🌟 About Me</h1>
    <h2>👋 Hi! I'm Alessandro</h2>
    <ul>
      <li>💻 Developer at <strong>VIPZEXNET</strong>, passionate about modern digital solutions.</li>
      <li>🛠 Expertise:</li>
      <ul>
        <li>🌐 Website Design & Web Server Development</li>
        <li>📱 App Design & Bot Creation</li>
        <li>🔒 Security & System Protection</li>
      </ul>
    </ul>
  </div>

  <div class="section">
    <h1>💻 Tech Stack</h1>
    <div class="tech-stack">
      <img src="https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3"/>
      <img src="https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5"/>
      <img src="https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E" alt="JavaScript"/>
      <img src="https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white" alt="PHP"/>
      <img src="https://img.shields.io/badge/python-%2314354C.svg?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
    </div>
  </div>
</div>

<script>
  const canvas = document.getElementById("matrix");
  const ctx = canvas.getContext("2d");
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

  const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
  const fontSize = 16;
  const columns = Math.floor(canvas.width / fontSize);
  const drops = [];
  for(let x=0; x<columns; x++) drops[x] = Math.random() * canvas.height;

  function draw() {
    ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = '#00ffcc';
    ctx.font = fontSize + "px monospace";

    for(let i=0; i<drops.length; i++) {
      const text = letters.charAt(Math.floor(Math.random() * letters.length));
      ctx.fillText(text, i * fontSize, drops[i] * fontSize);
      drops[i]++;
      if(drops[i] * fontSize > canvas.height && Math.random() > 0.975) drops[i] = 0;
    }
  }

  setInterval(draw, 50);

  window.addEventListener('resize', () => {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  });
</script>

</body>
</html>
