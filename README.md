<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>📊 XAU/USD Market Analyzer</title>
  <style>
    body { font-family: Arial, sans-serif; background: #0d1117; color: #fff; text-align: center; padding: 50px; }
    h1 { color: #ffcc00; }
    .box { background: #161b22; padding: 20px; border-radius: 10px; display: inline-block; width: 300px; margin: 10px; }
    .price { font-size: 2em; color: #00ff88; }
  </style>
</head>
<body>
  <h1>📈 Analisa XAU/USD Real-Time</h1>
  <p>Harga emas dunia (XAU/USD) update otomatis setiap 10 detik</p>
  <div id="box" class="box">
    <h3>Harga Saat Ini:</h3>
    <div id="xau" class="price">Loading...</div>
  </div>
  <script>
    async function updatePrice() {
      const res = await fetch("https://api.exchangerate.host/latest?base=XAU&symbols=USD");
      const data = await res.json();
      document.getElementById("xau").innerText = data.rates.USD.toFixed(2) + " USD";
    }
    updatePrice();
    setInterval(updatePrice, 10000);
  </script>
</body>
</html>
