<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Hydro Monitor</title>
  <style>
    body {
      margin: 0;
      background: #0f172a;
      color: white;
      font-family: Arial, sans-serif;
    }
    .hydro-container {
      padding: 15px;
      min-height: 100vh;
      box-sizing: border-box;
    }
    .card {
      background: #1e293b;
      padding: 15px;
      border-radius: 15px;
      margin-bottom: 15px;
    }
    .big {
      font-size: 36px;
      font-weight: bold;
    }
    .battery {
      width: 100%;
      height: 20px;
      background: #333;
      border-radius: 10px;
      overflow: hidden;
      margin: 8px 0;
    }
    #batteryFill {
      height: 100%;
      width: 70%;
      background: limegreen;
      transition: width 0.3s ease;
    }
  </style>
</head>
<body>
  <div class="hydro-container">
    <div class="card">
      <h2>⚡ 發電系統</h2>
      <div class="big" id="power">120 W</div>
      <p>電流：<span id="current">2.5</span> A</p>
      <p>累積發電：<span id="energy">350</span> Wh</p>
    </div>

    <div class="card">
      <h2>🔋 電池資訊</h2>
      <p>電壓：<span id="voltage">12.5</span> V</p>
      <div class="battery">
        <div id="batteryFill"></div>
      </div>
      <p>容量：<span id="capacity">70</span>%</p>
    </div>

    <div class="card">
      <h2>🧪 殺菌系統</h2>
      <p>運轉時間：<span id="runtime">5</span> hr</p>
      <p>用電量：<span id="usage">40</span> Wh</p>
    </div>
  </div>

  <script>
    setInterval(() => {
      const power = Math.floor(100 + Math.random() * 50);
      const current = (2 + Math.random()).toFixed(2);
      const energy = Math.floor(300 + Math.random() * 50);
      const voltage = (12 + Math.random()).toFixed(2);
      const capacity = Math.floor(20 + Math.random() * 80);
      const runtime = (5 + Math.random()).toFixed(1);
      const usage = Math.floor(30 + Math.random() * 20);

      document.getElementById('power').textContent = `${power} W`;
      document.getElementById('current').textContent = current;
      document.getElementById('energy').textContent = energy;
      document.getElementById('voltage').textContent = voltage;
      document.getElementById('capacity').textContent = capacity;
      document.getElementById('runtime').textContent = runtime;
      document.getElementById('usage').textContent = usage;
      document.getElementById('batteryFill').style.width = `${capacity}%`;
    }, 2000);
  </script>
</body>
</html>
