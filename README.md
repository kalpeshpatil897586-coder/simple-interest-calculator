# simple-interest-calculator
simple-interest-calculator/ 
│ ├── index.html 
├── style.css
├── script.js 
└── README.md
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Interest Calculator</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(135deg, #667eea, #764ba2);
        }

        .calculator {
            width: 380px;
            padding: 30px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
        }

        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 25px;
        }

        .input-group {
            margin-bottom: 18px;
        }

        label {
            display: block;
            margin-bottom: 7px;
            font-weight: bold;
            color: #444;
        }

        input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 16px;
        }

        input:focus {
            outline: none;
            border-color: #667eea;
        }

        button {
            width: 100%;
            padding: 13px;
            border: none;
            border-radius: 8px;
            background: #667eea;
            color: white;
            font-size: 17px;
            font-weight: bold;
            cursor: pointer;
        }

        button:hover {
            background: #5568d9;
        }

        .result {
            margin-top: 20px;
            padding: 15px;
            background: #f2f4ff;
            border-radius: 8px;
            text-align: center;
            color: #333;
            line-height: 1.8;
        }
    </style>
</head>

<body>

    <div class="calculator">

        <h1>Simple Interest Calculator</h1>

        <div class="input-group">
            <label>Principal Amount (₹)</label>
            <input type="number" id="principal" placeholder="Enter principal amount">
        </div>

        <div class="input-group">
            <label>Rate of Interest (%)</label>
            <input type="number" id="rate" placeholder="Enter interest rate">
        </div>

        <div class="input-group">
            <label>Time (Years)</label>
            <input type="number" id="time" placeholder="Enter time in years">
        </div>

        <button onclick="calculateInterest()">Calculate</button>

        <div class="result" id="result">
            Enter values and click Calculate
        </div>

    </div>

    <script>
        function calculateInterest() {

            // Get input values
            const principal = parseFloat(
                document.getElementById("principal").value
            );

            const rate = parseFloat(
                document.getElementById("rate").value
            );

            const time = parseFloat(
                document.getElementById("time").value
            );

            const result = document.getElementById("result");

            // Validate input
            if (isNaN(principal) || isNaN(rate) || isNaN(time)) {
                result.innerHTML = "⚠️ Please enter all values.";
                return;
            }

            if (principal <= 0 || rate < 0 || time <= 0) {
                result.innerHTML = "⚠️ Please enter valid values.";
                return;
            }

            // Simple Interest Formula
            // SI = (P × R × T) / 100
            const simpleInterest = (principal * rate * time) / 100;

            // Total Amount
            const totalAmount = principal + simpleInterest;

            // Display result
            result.innerHTML = `
                <strong>Simple Interest:</strong>
                ₹${simpleInterest.toFixed(2)}
                <br>
                <strong>Total Amount:</strong>
                ₹${totalAmount.toFixed(2)}
            `;
        }
    </script>

</body>
</html>
