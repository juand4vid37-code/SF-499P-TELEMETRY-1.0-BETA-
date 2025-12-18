<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>SF 499P Telemetry</title>

<style>
body {
  background:#0b0e11;
  color:#e6e6e6;
  font-family: monospace;
}
header {
  padding:20px;
  border-bottom:2px solid #ff2e2e;
}
.panel {
  background:#111418;
  padding:15px;
  margin:15px;
  border:1px solid #222;
}
.value {
  font-size:38px;
}
</style>
</head>

<body>

<header>
<h2>SCUDERIA FRAMEWORK — SF 499P</h2>
<span>LIVE HUMAN TELEMETRY</span>
</header>

<div class="panel">ENERGY: <span id="energy" class="value">--</span></div>
<div class="panel">DEEP WORK (min): <span id="deepwork" class="value">--</span></div>
<div class="panel">MENTAL CALLOUS: <span id="callus" class="value">--</span></div>
<div class="panel">OUTPUT: <span id="output" class="value">--</span></div>
<div class="panel">STREAK: <span id="streak" class="value">--</span></div>

<script>
fetch("PEGA_AQUI_TU_LINK_CSV")
.then(res => res.text())
.then(text => {
  let rows = text.trim().split("\n");
  let last = rows[rows.length - 1].split(",");

  document.getElementById("energy").innerText = last[1];
  document.getElementById("deepwork").innerText = last[2];
  document.getElementById("callus").innerText = last[3];
  document.getElementById("output").innerText = last[4];
  document.getElementById("streak").innerText = last[5];
});
</script>

</body>
</html>
