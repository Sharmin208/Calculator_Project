# Calculator_Project
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mobile Calculator</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="calculator">
    <div class="display">
      <input type="text" id="result" readonly />
    </div>
    <div class="buttons">
      <!-- Row 1 -->
      <button onclick="clearDisplay()">C</button>
      <button onclick="deleteChar()">DEL</button>
      <button onclick="appendOperator('%')">%</button>
      <button onclick="appendOperator('/')">÷</button>
      <!-- Row 2 -->
      <button onclick="appendNumber('7')">7</button>
      <button onclick="appendNumber('8')">8</button>
      <button onclick="appendNumber('9')">9</button>
      <button onclick="appendOperator('*')">×</button>
      <!-- Row 3 -->
      <button onclick="appendNumber('4')">4</button>
      <button onclick="appendNumber('5')">5</button>
      <button onclick="appendNumber('6')">6</button>
      <button onclick="appendOperator('-')">−</button>
      <!-- Row 4 -->
      <button onclick="appendNumber('1')">1</button>
      <button onclick="appendNumber('2')">2</button>
      <button onclick="appendNumber('3')">3</button>
      <button onclick="appendOperator('+')">+</button>
      <!-- Row 5 -->
      <button onclick="appendNumber('0')">0</button>
      <button onclick="appendNumber('.')">.</button>
      <button onclick="calculateResult()" colspan="2">=</button>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
// script.js

let resultDisplay = document.getElementById("result");

function appendNumber(number) {
  resultDisplay.value += number;
}

function appendOperator(operator) {
  resultDisplay.value += operator;
}

function clearDisplay() {
  resultDisplay.value = "";
}

function deleteChar() {
  resultDisplay.value = resultDisplay.value.slice(0, -1);
}

function calculateResult() {
  try {
    resultDisplay.value = eval(resultDisplay.value);
  } catch (error) {
    resultDisplay.value = "Error";
  }
}

/* styles.css */
body {
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  margin: 0;
  background-color: #f3f4f6;
}

.calculator {
  width: 300px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  overflow: hidden;
}

.display input {
  width: 100%;
  height: 60px;
  font-size: 1.5em;
  text-align: right;
  border: none;
  padding: 10px;
  box-sizing: border-box;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1px;
  background-color: #ddd;
}

button {
  background-color: #f0f0f0;
  border: none;
  padding: 20px;
  font-size: 1.2em;
  cursor: pointer;
  outline: none;
}

button:hover {
  background-color: #e0e0e0;
}

button:active {
  background-color: #ccc;
}

