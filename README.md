# HyperGlassLevel_01
# The Pyramid: Core logic temple running enders!
# Download Open
# CHANGE .md->.html

 #------------------------------------------
<!DOCTYPE html>
<html>
<head>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.4.2/p5.min.js"></script>
  <style>
    body {
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      background: url('https://images.unsplash.com/photo-1451187580459-43490279c0fa') no-repeat center center fixed;
      background-size: cover;
      font-family: 'Courier New', Courier, monospace;
      color: #000;
    }
    .shockos-header {
      width: 100%;
      background: linear-gradient(90deg, #ff00ff, #00ffff);
      padding: 10px;
      box-shadow: 0 0 20px #ff00ff, 0 0 30px #00ffff;
      text-align: center;
      position: fixed;
      top: 0;
      z-index: 10;
      background-image: url('https://www.transparenttextures.com/patterns/dark-mosaic.png');
      background-blend-mode: overlay;
    }
    .shockos-header h1 {
      color: #000;
      font-size: 20px;
      margin: 0;
      background: none;
      text-shadow: 0 0 5px #fff, 0 0 10px #ff00ff;
    }
    .shockos-status {
      color: #000;
      font-size: 12px;
      background: rgba(255, 255, 255, 0.8);
      padding: 5px;
      border-radius: 5px;
      margin-top: 5px;
      text-shadow: 0 0 3px #00ffff;
    }
    .container {
      margin-top: 80px;
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      max-width: 800px;
    }
    canvas {
      border: 3px solid #ff00ff;
      box-shadow: 0 0 15px #00ffff, 0 0 25px #ff00ff;
      margin-bottom: 20px;
    }
    .button-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 10px;
      margin-bottom: 20px;
      width: 90%;
    }
    .element-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 10px;
      justify-content: center;
      width: 90%;
    }
    .shel-button, .element-button {
      padding: 15px;
      font-size: 14px;
      font-weight: bold;
      color: #000;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: transform 0.2s, box-shadow 0.3s;
      text-transform: uppercase;
      background-image: url('https://www.transparenttextures.com/patterns/dark-mosaic.png');
      background-blend-mode: overlay;
    }
    .shel-button:hover, .element-button:hover {
      transform: scale(1.1);
      box-shadow: 0 0 15px #ff00ff, 0 0 25px #00ffff;
    }
    .btn-glow-graffiti { background: #ff6666; }
    .btn-tiktok-rave { background: #ff6666; }
    .btn-distort { background: #ff6666; }
    .btn-signalblaze { background: #ff6666; }
    .btn-summon-ghost { background: #66ffff; }
    .btn-purple-ball { background: #cc99ff; }
    .btn-fire { background: #99ff99; }
    .btn-ghost { background: #66ffff; }
    .btn-wave { background: #66ffff; }
    select {
      background: #fff;
      color: #000;
      border: 2px solid #ff00ff;
      padding: 10px;
      font-size: 16px;
      margin: 10px 0;
      width: 300px;
      max-width: 90%;
      font-family: 'Courier New', Courier, monospace;
      box-shadow: 0 0 10px #00ffff;
    }
    .info-text {
      color: #000;
      font-size: 14px;
      margin: 10px 0;
      background: #fff;
      padding: 5px 10px;
      border-radius: 5px;
      box-shadow: 0 0 10px #ff00ff;
    }
    .gateway-text {
      color: #000;
      font-size: 14px;
      margin: 10px 0;
      background: #66ffff;
      padding: 5px 10px;
      border-radius: 5px;
      box-shadow: 0 0 10px #00ffff;
    }
    .waveform-canvas {
      border: 2px solid #ff00ff;
      box-shadow: 0 0 15px #00ffff, 0 0 25px #ff00ff;
      margin-top: 10px;
    }
    .resonance-text {
      color: #000;
      font-size: 14px;
      margin-top: 5px;
      background: #fff;
      padding: 5px 10px;
      border-radius: 5px;
      box-shadow: 0 0 10px #ff00ff;
    }
    .dialogue-box {
      color: #000;
      font-size: 14px;
      margin: 10px 0;
      background: #ffccff;
      padding: 5px 10px;
      border-radius: 5px;
      width: 300px;
      max-width: 90%;
      text-align: center;
      box-shadow: 0 0 10px #00ffff;
    }
    .emoji-display {
      color: #000;
      font-size: 20px;
      margin: 5px 0;
      background: #fff;
      padding: 5px 10px;
      border-radius: 5px;
      width: 300px;
      max-width: 90%;
      text-align: center;
      box-shadow: 0 0 10px #ff00ff;
    }
    @media (max-width: 600px) {
      .container {
        margin-top: 100px;
      }
      canvas {
        width: 90% !important;
        height: auto !important;
      }
      .waveform-canvas {
        width: 90% !important;
        height: auto !important;
      }
      .button-grid, .element-buttons {
        grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      }
    }
  </style>
</head>
<body>
  <div class="shockos-header">
    <h1>ShockOS v9.0 - box.exe</h1>
    <div class="shockos-status" id="statusBar">CPU Usage: 0% | Graffiti: OFF | Rave: OFF | Distort: OFF | Signalblaze: OFF | Ghost: OFF | Purple Ball: OFF | Fire: OFF | Ghost Effect: OFF | Wave: OFF</div>
  </div>
  <div class="container">
    <div class="info-text">The Pyramid: Core logic temple running enders!</div>
    <div id="gameCanvas"></div>
    <div class="button-grid">
      <button class="shel-button btn-glow-graffiti" onclick="paintGlowingGraffiti()">Paint Glowing Graffiti</button>
      <button class="shel-button btn-tiktok-rave" onclick="tiktokRave()">Hjdac Tiktok Rave</button>
      <button class="shel-button btn-distort" onclick="distortReality()">Distort Reality</button>
      <button class="shel-button btn-signalblaze" onclick="runSignalblaze()">Run Signalblaze.exe</button>
      <button class="shel-button btn-summon-ghost" onclick="summonGhost()">Summon Ghost</button>
      <button class="shel-button btn-purple-ball" onclick="activePurpleBall()">Active Purple Ball</button>
    </div>
    <select id="portalSelect" onchange="teleport(this.value)">
      <option value="">Choose an element to integrate:</option>
      <option value="0">Portal 0 (Glow Rave)</option>
      <option value="1">Portal 1 (Distort)</option>
      <option value="2">Portal 2 (Summon Warp)</option>
    </select>
    <div class="element-buttons">
      <button class="element-button btn-fire" onclick="integrateFire()">Fire</button>
      <button class="element-button btn-ghost" onclick="integrateGhost()">Ghost</button>
      <button class="element-button btn-wave" onclick="integrateWave()">Wave</button>
    </div>
    <div class="dialogue-box" id="dialogueBox">Element Dialogue...</div>
    <div class="gateway-text">Gateway to synthwave skater dimension opened!</div>
    <div class="emoji-display" id="emojiDisplay"></div>
    <div id="waveformCanvas"></div>
    <div class="resonance-text">Resonance Score: 90% STEM (Sicilian Inferno Echo Metric)</div>
  </div>

  <script>
    let player;
    let portals = [];
    let obstacles = [];
    let ghostObstacle = null;
    let canvasWidth = 600;
    let canvasHeight = 400;
    let graffitiBackground = false;
    let raveMode = false;
    let distortMode = false;
    let signalblazeMode = false;
    let fireTrail = [];
    let ghostMode = false;
    let waveMode = false;
    let waveAngle = 0;
    let buttonPressCount = 0;
    let waveformAmplitude = 10;
    let waveformFrequency = 0.05;
    let waveformSpeed = 0.05;
    let waveformLayers = 3;
    let pulseAngle = 0;
    let glitchMode = false;
    let glitterParticles = [];
    let danceShapes = [];
    let showEmojis = false;
    let currentEmojis = [];

    const emojiList = ['🔥', '🌟', '💥', '⚡', '🌈', '🌀', '🎉', '✨', '💫', '🌺'];

    function setup() {
      let canvas = createCanvas(canvasWidth, canvasHeight);
      canvas.parent('gameCanvas');
      player = { 
        x: 50, 
        y: 50, 
        size: 20, 
        col: [255, 255, 0], 
        alpha: 255, 
        speedX: 0, 
        speedY: 0,
        glitchAlpha: 255
      };
      
      portals.push({ x: 50, y: 50, size: 40, col: [255, 0, 255], swirl: 0 });
      portals.push({ x: 500, y: 50, size: 40, col: [0, 255, 255], swirl: 0 });
      portals.push({ x: 300, y: 300, size: 40, col: [255, 0, 0], swirl: 0 });
      
      for (let i = 0; i < 3; i++) {
        obstacles.push({
          x: random(canvasWidth),
          y: random(canvasHeight),
          size: 30,
          col: [random(255), random(255), random(255)],
          speedX: random(-2, 2),
          speedY: random(-2, 2)
        });
      }
    }

    function draw() {
      pulseAngle += 0.05;

      if (graffitiBackground) {
        let gradient = drawingContext.createLinearGradient(0, 0, canvasWidth, canvasHeight);
        gradient.addColorStop(0, '#ff00ff');
        gradient.addColorStop(1, '#00ffff');
        drawingContext.fillStyle = gradient;
        drawingContext.fillRect(0, 0, canvasWidth, canvasHeight);
        for (let i = 0; i < 50; i++) {
          fill(random(255), random(255), random(255), 150);
          noStroke();
          ellipse(random(canvasWidth), random(canvasHeight), 10, 10);
        }
      } else {
        background(26, 11, 46);
      }

      if (glitchMode) {
        player.x += player.speedX;
        player.y += player.speedY;

        if (player.x < player.size / 2 || player.x > canvasWidth - player.size / 2) {
          player.speedX *= -1;
          player.speedX += random(-1, 1);
        }
        if (player.y < player.size / 2 || player.y > canvasHeight - player.size / 2) {
          player.speedY *= -1;
          player.speedY += random(-1, 1);
        }

        if (random(100) < 10) {
          player.glitchAlpha = player.glitchAlpha === 255 ? 100 : 255;
        }
      }

      for (let p of portals) {
        p.swirl += raveMode ? 0.3 : 0.1;
        p.col = raveMode ? [random(255), random(255), random(255)] : p.col;
        fill(p.col);
        noStroke();
        push();
        translate(p.x, p.y);
        rotate(p.swirl);
        for (let i = 0; i < 10; i++) {
          ellipse(0, 0, p.size - i * 3, p.size - i * 3);
          rotate(PI / 5);
        }
        fill(255);
        let dotSize = 5 + sin(pulseAngle) * 2;
        ellipse(0, 0, dotSize, dotSize);
        pop();
      }

      if (fireTrail.length > 0) {
        for (let i = fireTrail.length - 1; i >= 0; i--) {
          let particle = fireTrail[i];
          fill(255, 69, 0, particle.alpha);
          noStroke();
          ellipse(particle.x, particle.y, 5, 5);
          particle.alpha -= 5;
          if (particle.alpha <= 0) fireTrail.splice(i, 1);
        }
      }

      if (waveMode) {
        waveAngle += 0.1;
        player.y += sin(waveAngle) * 2;
      }

      for (let o of obstacles) {
        o.x += signalblazeMode ? o.speedX * 2 : o.speedX;
        o.y += signalblazeMode ? o.speedY * 2 : o.speedY;
        if (o.x < 0 || o.x > canvasWidth) o.speedX *= -1;
        if (o.y < 0 || o.y > canvasHeight) o.speedY *= -1;
        
        fill(o.col);
        noStroke();
        push();
        translate(o.x, o.y);
        for (let i = 0; i < 5; i++) {
          ellipse(0, 0, o.size - i * 5, o.size - i * 5);
          rotate(PI / 3);
        }
        fill(255);
        let dotSize = 5 + sin(pulseAngle) * 2;
        ellipse(0, 0, dotSize, dotSize);
        pop();

        let d = dist(player.x, player.y, o.x, o.y);
        if (d < (player.size + o.size) / 2) {
          teleport(0);
        }
      }

      if (ghostObstacle) {
        let dx = player.x - ghostObstacle.x;
        let dy = player.y - ghostObstacle.y;
        let distance = dist(player.x, player.y, ghostObstacle.x, ghostObstacle.y);
        ghostObstacle.x += (dx / distance) * 1;
        ghostObstacle.y += (dy / distance) * 1;

        fill(255, 255, 255, 150);
        noStroke();
        push();
        translate(ghostObstacle.x, ghostObstacle.y);
        for (let i = 0; i < 5; i++) {
          ellipse(0, 0, ghostObstacle.size - i * 5, ghostObstacle.size - i * 5);
          rotate(PI / 3);
        }
        fill(0);
        let dotSize = 5 + sin(pulseAngle) * 2;
        ellipse(0, 0, dotSize, dotSize);
        pop();

        let d = dist(player.x, player.y, ghostObstacle.x, ghostObstacle.y);
        if (d < (player.size + ghostObstacle.size) / 2) {
          teleport(0);
        }
      }

      let drawX = player.x;
      let drawY = player.y;
      if (glitchMode) {
        drawX += random(-5, 5);
        drawY += random(-5, 5);
      }
      fill(player.col[0], player.col[1], player.col[2], glitchMode ? player.glitchAlpha : player.alpha);
      let currentSize = distortMode ? player.size + sin(frameCount * 0.1) * 5 : player.size;
      ellipse(drawX, drawY, currentSize, currentSize);
      fill(0);
      let dotSize = 5 + sin(pulseAngle) * 2;
      ellipse(drawX, drawY, dotSize, dotSize);

      if (fireTrail.length > 0) {
        fireTrail.push({ x: player.x, y: player.y, alpha: 255 });
        if (fireTrail.length > 20) fireTrail.splice(0, 1);
      }
    }

    let waveformSketch = function(p) {
      let waveWidth = 400;
      let waveHeight = 60;
      let offset = 0;

      p.setup = function() {
        let waveformCanvas = p.createCanvas(waveWidth, waveHeight);
        waveformCanvas.addClass('waveform-canvas');
      };

      p.draw = function() {
        p.background(26, 11, 46);
        p.noFill();
        p.strokeWeight(2);

        // Draw waveforms
        for (let layer = 0; layer < waveformLayers; layer++) {
          let hue = p.lerpColor(p.color(255, 0, 0), p.color(0, 255, 255), layer / (waveformLayers - 1));
          p.stroke(hue);
          p.beginShape();
          for (let x = 0; x <= waveWidth; x += 5) {
            let y = waveHeight / 2 + sin(x * waveformFrequency + offset + layer * 0.5) * waveformAmplitude;
            p.vertex(x, y);
          }
          p.endShape();
        }

        // Draw glitter particles for Ghost mode
        if (glitterParticles.length > 0) {
          for (let i = glitterParticles.length - 1; i >= 0; i--) {
            let particle = glitterParticles[i];
            p.fill(255, 255, random(100, 255));
            p.noStroke();
            p.ellipse(particle.x, particle.y, 3, 3);
            particle.x += particle.speedX;
            particle.y += particle.speedY;
            particle.life--;
            if (particle.life <= 0) glitterParticles.splice(i, 1);
          }
        }

        // Draw dancing shapes for Wave mode
        if (danceShapes.length > 0) {
          for (let shape of danceShapes) {
            p.fill(0);
            p.noStroke();
            p.ellipse(shape.x, shape.y, 5, 5);
            shape.y += shape.speed * sin(shape.angle);
            shape.angle += 0.1;
          }
        }

        // Draw emojis for Fire mode
        if (showEmojis && currentEmojis.length > 0) {
          p.textSize(20);
          p.fill(255);
          p.textAlign(CENTER, CENTER);
          for (let i = 0; i < currentEmojis.length; i++) {
            p.text(currentEmojis[i], waveWidth / 2 - 30 + i * 30, 10);
          }
        }

        offset += waveformSpeed;
      };
    };

    new p5(waveformSketch, 'waveformCanvas');

    function updateWaveform() {
      buttonPressCount++;
      waveformAmplitude = 5 + (buttonPressCount % 3) * 5;
      waveformFrequency = 0.02 + (buttonPressCount % 4) * 0.02;
      updateStatus();
    }

    function updateStatus() {
      let cpuUsage = Math.floor(random(10, 90));
      document.getElementById('statusBar').innerText = `CPU Usage: ${cpuUsage}% | Graffiti: ${graffitiBackground ? 'ON' : 'OFF'} | Rave: ${raveMode ? 'ON' : 'OFF'} | Distort: ${distortMode ? 'ON' : 'OFF'} | Signalblaze: ${signalblazeMode ? 'ON' : 'OFF'} | Ghost: ${ghostObstacle ? 'ON' : 'OFF'} | Purple Ball: ${glitchMode ? 'ON' : 'OFF'} | Fire: ${fireTrail.length > 0 ? 'ON' : 'OFF'} | Ghost Effect: ${ghostMode ? 'ON' : 'OFF'} | Wave: ${waveMode ? 'ON' : 'OFF'}`;
    }

    function teleport(portalIndex) {
      portalIndex = parseInt(portalIndex);
      player.x = portals[portalIndex].x;
      player.y = portals[portalIndex].y;
      updateWaveform();
    }

    function paintGlowingGraffiti() {
      graffitiBackground = !graffitiBackground;
      updateWaveform();
    }

    function tiktokRave() {
      raveMode = !raveMode;
      for (let p of portals) {
        p.col = [p.col[0], p.col[1], p.col[2]];
      }
      updateWaveform();
    }

    function distortReality() {
      distortMode = !distortMode;
      updateWaveform();
    }

    function runSignalblaze() {
      signalblazeMode = !signalblazeMode;
      updateWaveform();
    }

    function summonGhost() {
      if (!ghostObstacle) {
        ghostObstacle = {
          x: random(canvasWidth),
          y: random(canvasHeight),
          size: 30,
          speed: 1
        };
      } else {
        ghostObstacle = null;
      }
      updateWaveform();
    }

    function activePurpleBall() {
      glitchMode = !glitchMode;
      if (glitchMode) {
        player.col = [128, 0, 128];
        player.size = 30;
        player.speedX = random(-3, 3);
        player.speedY = random(-3, 3);
      } else {
        player.speedX = 0;
        player.speedY = 0;
        player.glitchAlpha = 255;
      }
      updateWaveform();
    }

    function integrateFire() {
      fireTrail = fireTrail.length > 0 ? [] : [{}];
      waveformAmplitude = 25;
      waveformFrequency = 0.08;
      waveformSpeed = 0.1;
      waveformLayers = 3;
      glitterParticles = [];
      danceShapes = [];
      showEmojis = true;
      currentEmojis = [];
      for (let i = 0; i < 3; i++) {
        currentEmojis.push(emojiList[Math.floor(random(emojiList.length))]);
      }
      document.getElementById('emojiDisplay').innerText = currentEmojis.join(' ');
      document.getElementById('dialogueBox').innerText = "🔥 Igniting the Field Strings! Feel the Heat! 🔥";
      updateWaveform();
    }

    function integrateGhost() {
      ghostMode = !ghostMode;
      player.alpha = ghostMode ? 150 : 255;
      waveformSpeed = 0.05;
      waveformAmplitude = 10;
      waveformFrequency = 0.05;
      waveformLayers = 3;
      glitterParticles = [];
      for (let i = 0; i < 20; i++) {
        glitterParticles.push({
          x: random(400),
          y: random(60),
          speedX: random(-1, 1),
          speedY: random(-1, 1),
          life: random(50, 100)
        });
      }
      danceShapes = [];
      showEmojis = false;
      document.getElementById('emojiDisplay').innerText = '';
      document.getElementById('dialogueBox').innerText = "👻 Spooky Vibes! The Strings are Haunted! 👻";
      updateWaveform();
    }

    function integrateWave() {
      waveMode = !waveMode;
      waveAngle = 0;
      waveformSpeed = 0.02;
      waveformAmplitude = 10;
      waveformFrequency = 0.05;
      waveformLayers = 6;
      glitterParticles = [];
      danceShapes = [];
      for (let i = 0; i < 5; i++) {
        danceShapes.push({
          x: i % 2 === 0 ? -20 : 420,
          y: random(60),
          speed: random(0.5, 1.5),
          angle: random(TWO_PI)
        });
      }
      showEmojis = false;
      document.getElementById('emojiDisplay').innerText = '';
      document.getElementById('dialogueBox').innerText = "🌊 Waving Through the Field! Ride the Tide! 🌊";
      updateWaveform();
    }
  </script>
</body>
</html>
