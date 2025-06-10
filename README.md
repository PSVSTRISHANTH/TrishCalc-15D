<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>TrishCalc 15D</title>
  <style>
    body {
      background-color: #e0f7fa;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      flex-direction: column;
    }
    h1 {
      color: #00796b;
      font-size: 36px;
    }
    input {
      padding: 10px;
      font-size: 18px;
      width: 250px;
      margin: 10px;
    }
    button {
      padding: 10px 20px;
      font-size: 18px;
      background-color: #00796b;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    button:hover {
      background-color: #004d40;
    }
    .result {
      margin-top: 20px;
      font-size: 20px;
      color: #004d40;
    }
  </style>
</head>
<body>

  <h1>TrishCalc 15D</h1>
  <input type="text" id="numberInput" maxlength="15" placeholder="Enter up to 15 digits">
  <button onclick="calculateSum()">Get Sum</button>
  <div class="result" id="result"></div>

  <script>
    function calculateSum() {
      const input = document.getElementById('numberInput').value;
      if (!/^\d{1,15}$/.test(input)) {
        document.getElementById('result').innerText = 'Please enter only digits (up to 15).';
        return;
      }
      let sum = 0;
      for (let digit of input) {
        sum += parseInt(digit);
      }
      document.getElementById('result').innerText = `Sum of digits: ${sum}`;
    }
  </script>

</body>
</html>
