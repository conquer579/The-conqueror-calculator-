# The-conqueror-calculator-
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Conqueror Calculator</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            margin: 0;
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(to right, #4b0082, #2e0854);
            color: white;
            text-align: center;
            padding: 20px;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            color: #ffcc00;
        }

        .calculator-container {
            margin: auto;
            max-width: 600px;
            background: rgba(0, 0, 0, 0.7);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
        }

        .section-title {
            font-size: 1.5rem;
            color: #ffcc00;
            margin: 20px 0;
        }

        label {
            display: block;
            margin: 10px 0 5px;
            font-size: 1rem;
        }

        input, button {
            width: 90%;
            padding: 10px;
            margin-bottom: 15px;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
        }

        input {
            background: #3a3a3a;
            color: white;
        }

        button {
            background: #ffcc00;
            color: black;
            cursor: pointer;
            transition: background 0.3s;
        }

        button:hover {
            background: #ffd633;
        }

        .output {
            margin-top: 15px;
            padding: 10px;
            background: #4b0082;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <h1>The Conqueror Calculator</h1>

    <!-- Forex Calculator Section -->
    <div class="calculator-container">
        <div class="section-title">Forex Calculator</div>
        <label for="forex-balance">Account Balance:</label>
        <input type="number" id="forex-balance" placeholder="Enter account balance">
        
        <label for="forex-risk">Risk Percentage (%):</label>
        <input type="number" id="forex-risk" placeholder="Enter risk percentage">
        
        <label for="forex-stoploss">Stop Loss (PIPs):</label>
        <input type="number" id="forex-stoploss" placeholder="Enter stop loss in PIPs">
        
        <label for="forex-takeprofit">Take Profit (PIPs):</label>
        <input type="number" id="forex-takeprofit" placeholder="Enter take profit in PIPs">
        
        <button onclick="calculateForex()">Calculate</button>

        <div id="forex-output" class="output"></div>
    </div>

    <!-- Indices Calculator Section -->
    <div class="calculator-container">
        <div class="section-title">Indices Calculator (NASDAQ & S&P 500)</div>
        <label for="indices-balance">Account Balance:</label>
        <input type="number" id="indices-balance" placeholder="Enter account balance">
        
        <label for="indices-risk">Risk Percentage (%):</label>
        <input type="number" id="indices-risk" placeholder="Enter risk percentage">
        
        <label for="indices-stoploss">Stop Loss (Points):</label>
        <input type="number" id="indices-stoploss" placeholder="Enter stop loss in points">
        
        <label for="indices-takeprofit">Take Profit (Points):</label>
        <input type="number" id="indices-takeprofit" placeholder="Enter take profit in points">
        
        <button onclick="calculateIndices()">Calculate</button>

        <div id="indices-output" class="output"></div>
    </div>

    <script>
        function calculateForex() {
            const balance = parseFloat(document.getElementById('forex-balance').value);

£, [1/25/2025 9:05 AM]
const risk = parseFloat(document.getElementById('forex-risk').value) / 100;
            const stopLoss = parseFloat(document.getElementById('forex-stoploss').value);
            const takeProfit = parseFloat(document.getElementById('forex-takeprofit').value);

            if (isNaN(balance)  isNaN(risk)  isNaN(stopLoss) || isNaN(takeProfit)) {
                document.getElementById('forex-output').textContent = "Please fill in all fields!";
                return;
            }

            const moneyRisked = balance * risk;
            const lotSize = moneyRisked / stopLoss / 10; // Simplified lot size calculation
            const profitGained = (moneyRisked / stopLoss) * takeProfit;
            const riskReward = (takeProfit / stopLoss).toFixed(2);

            document.getElementById('forex-output').innerHTML = 
                Money Risked: $${moneyRisked.toFixed(2)}<br>
                Profit Gained: $${profitGained.toFixed(2)}<br>
                Lot Size: ${lotSize.toFixed(2)}<br>
                Risk-Reward Ratio: 1:${riskReward}
            ;
        }

        function calculateIndices() {
            const balance = parseFloat(document.getElementById('indices-balance').value);
            const risk = parseFloat(document.getElementById('indices-risk').value) / 100;
            const stopLoss = parseFloat(document.getElementById('indices-stoploss').value);
            const takeProfit = parseFloat(document.getElementById('indices-takeprofit').value);

            if (isNaN(balance)  isNaN(risk)  isNaN(stopLoss) || isNaN(takeProfit)) {
                document.getElementById('indices-output').textContent = "Please fill in all fields!";
                return;
            }

            const moneyRisked = balance * risk;
            const lotSize = moneyRisked / stopLoss;
            const profitGained = (moneyRisked / stopLoss) * takeProfit;
            const riskReward = (takeProfit / stopLoss).toFixed(2);

            document.getElementById('indices-output').innerHTML = 
                Money Risked: $${moneyRisked.toFixed(2)}<br>
                Profit Gained: $${profitGained.toFixed(2)}<br>
                Lot Size: ${lotSize.toFixed(2)}<br>
                Risk-Reward Ratio: 1:${riskReward}
            ;
        }
    </script>
</body>
</html>
