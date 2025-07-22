# 3D-Dark-Calculator
I have maked a calculator it is very cool and it is easy to use.

HTML


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Davie's Calculator</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <div class="calculator">
    <input type="text" id="display" disabled value="">

    <div class="buttons">
      <button class="clear" onclick="clearDisplay()">Clear</button>
      <button onclick="appendValue('/')">/</button>
      <button onclick="appendValue('*')">*</button>
      <button onclick="appendValue('-')">-</button>

      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('+')">+</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('.')">.</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button class="equal" onclick="calculateResult()">=</button>

      <button onclick="appendValue('0')" style="grid-column: span 4;">0</button>
    </div>

    <div class="label">Calculator</div>
  </div>

  <script src="script.js"></script>
</body>
</html>

CSS

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  body {
    background-color: #111;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-family: 'Segoe UI', sans-serif;
  }
  
  .calculator {
    background: #1c1c1c;
    padding: 25px;
    border-radius: 20px;
    box-shadow: 0 0 30px rgba(0, 255, 255, 0.1);
  }
  
  #display {
    width: 100%;
    height: 60px;
    font-size: 26px;
    text-align: right;
    margin-bottom: 20px;
    border: none;
    background: #a9c190;
    color: #111;
    padding: 10px;
    border-radius: 10px;
    box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.6);
  }
  
  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 60px);
    gap: 15px;
    justify-content: center;
  }
  
  button {
    height: 60px;
    width: 60px;
    font-size: 18px;
    border: none;
    border-radius: 10px;
    background: #333;
    color: #fff;
    cursor: pointer;
    box-shadow: 0 4px #222;
    transition: 0.2s;
  }
  
  button:active {
    transform: translateY(2px);
    box-shadow: 0 2px #111;
  }
  
  .clear {
    background: #e74c3c;
  }
  
  .equal {
    background: #27ae60;
  }
  
  .label {
    text-align: center;
    margin-top: 20px;
    font-size: 18px;
    color: #00ffee;
    text-shadow: 0 0 10px #00ffee, 0 0 5px #00ffee;
  }


  JAVA SCRIPT

  function appendValue(value) {
    const display = document.getElementById("display");
    display.value += value;
  }
  
  function clearDisplay() {
    document.getElementById("display").value = "";
  }
  
  function calculateResult() {
    const display = document.getElementById("display");
    try {
      display.value = eval(display.value);
    } catch {
      display.value = "Error";
    }
  }
  
