<!DOCTYPE html>
<html>
<head>
<title></title>
</head>

<body>

<h1>Nexora GX</h1>
<p>Bem vindo ao nexora GX!</p>
<h6>version 1.1.1</h6>


<input id="url"
style="background:#000;color:#0f0;border:1px solid #0f0;font-family:monospace;padding:6px;width:220px;outline:none;"
placeholder="url ou pesquisa..."
onkeydown="if(event.key==='Enter') ir()">

<button onclick="ir()"
style="background:#000;color:#0f0;border:1px solid #0f0;font-family:monospace;padding:6px;">
Ir
</button>

<script>
function ir(){
  let v = document.getElementById("url").value.trim();

  // detecta URL
  let ehURL = v.includes(".") && !v.includes(" ");

  if(ehURL){
    if(!v.startsWith("http")) v = "https://" + v;
    location.href = v;
  } else {
    // qualquer outra coisa → Google
    location.href = "https://www.google.com/search?q=" + encodeURIComponent(v);
  }
}
</script>

<h5>temos também o chat do nexora GX!<br>
(fiz no base 44 pois não sei programar chats)</h5>
<a href="https://hungry-nexora-connect-hub.base44.app" class="hacker-btn" target="_blank">
  chat do nexora GX
</a>

<style>
  .hacker-btn {
    display: inline-block;

    padding: 12px 18px;
    color: #00ff88;
    font-family: monospace;
    text-decoration: none;
    border: 1px solid #00ff88;
    background: transparent;
    letter-spacing: 2px;
    transition: 0.2s;
    box-shadow: 0 0 8px #00ff88;
  }

  .hacker-btn:hover {
    background: #00ff88;
    color: black;
    box-shadow: 0 0 20px #00ff88, 0 0 40px #00ff88;
    transform: scale(1.05);
  }
</style>
<style>
body {
  background: #0f0f0f;
  font-family: monospace;
  color: #0f0;
}

/* empurra pra direita */
.wrapper {
  display: flex;
  justify-content: flex-end;
  padding: 20px;
}

.calc {
  width: 180px;
  background: #111;
  padding: 10px;
  border: 1px solid #0f0;
  border-radius: 6px;
}

#display {
  width: 100%;
  height: 30px;
  margin-bottom: 8px;
  background: black;
  border: 1px solid #0f0;
  color: #0f0;
  text-align: right;
  font-family: monospace;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 4px;
}

button {
  background: black;
  border: 1px solid #0f0;
  color: #0f0;
  padding: 6px;
  cursor: pointer;
  font-family: monospace;
}

button:hover {
  background: #0f0;
  color: black;
}

.equal {
  grid-column: span 2;
}

.ac {
  grid-column: span 2;
  border-color: red;
  color: red;
}

.back {
  grid-column: span 2;
}
</style>

<div class="wrapper">
  <div class="calc">
    <input id="display" disabled>

    <div class="buttons">
      <button onclick="add('7')">7</button>
      <button onclick="add('8')">8</button>
      <button onclick="add('9')">9</button>
      <button onclick="add('/')">/</button>

      <button onclick="add('4')">4</button>
      <button onclick="add('5')">5</button>
      <button onclick="add('6')">6</button>
      <button onclick="add('*')">*</button>

      <button onclick="add('1')">1</button>
      <button onclick="add('2')">2</button>
      <button onclick="add('3')">3</button>
      <button onclick="add('-')">-</button>

      <button onclick="add('0')">0</button>
      <button onclick="add('.')">.</button>

      <button onclick="calc()" class="equal">=</button>
      <button onclick="add('+')">+</button>

      <button onclick="backspace()" class="back">⌫</button>
      <button onclick="clearAll()" class="ac">AC</button>
    </div>
  </div>
</div>

<script>
let display = document.getElementById("display");

function add(v) {
  display.value += v;
}

function calc() {
  try {
    display.value = eval(display.value);
  } catch {
    display.value = "ERR";
  }
}

function clearAll() {
  display.value = "";
}

function backspace() {
  display.value = display.value.slice(0, -1);
}
</script>

</body>
</html>
