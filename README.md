<!DOCTYPE html>
<html>
<head>
    <title>RAN GAME SHOP</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body { font-family: sans-serif; background-color: #f4f4f9; padding: 20px; }
        .card { background: white; border-radius: 12px; padding: 15px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); }
        h2 { text-align: center; color: #0088cc; }
        label { display: block; margin-top: 10px; font-weight: bold; }
        select, input { width: 100%; padding: 12px; margin: 8px 0; border: 1px solid #ccc; border-radius: 8px; box-sizing: border-box; }
        button { width: 100%; padding: 15px; background: #0088cc; color: white; border: none; border-radius: 8px; cursor: pointer; font-size: 16px; font-weight: bold; }
    </style>
</head>
<body>
    <div class="card">
        <h2>RAN GAME SHOP</h2>
        <label>Select Game</label>
        <select id="game">
            <option value="MLBB">Mobile Legends</option>
            <option value="PUBG">PUBG Mobile</option>
        </select>
        <label>Player ID</label>
        <input type="text" id="gameid" placeholder="Enter ID">
        <label>Amount</label>
        <input type="text" id="amount" placeholder="e.g. 86 Diamonds">
        <button id="orderBtn">Order Now</button>
    </div>
    <script>
        const tg = window.Telegram.WebApp;
        tg.expand(); 
        document.getElementById('orderBtn').addEventListener('click', () => {
            const data = {
                game: document.getElementById('game').value,
                id: document.getElementById('gameid').value,
                amount: document.getElementById('amount').value
            };
            tg.sendData(JSON.stringify(data));
            tg.close();
        });
    </script>
</body>
</html>
