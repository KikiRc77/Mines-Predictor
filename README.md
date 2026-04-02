# Mines-Predictor
Outils de prediction Mines
<!DOCTYPE html>
<html>
<head>
  <title>Mines Predictor</title>
  <style>
    body { text-align:center; font-family:Arial; background:#111; color:white; }
    .grid { display:grid; grid-template-columns:repeat(5,60px); gap:10px; justify-content:center; margin-top:20px; }
    .cell { width:60px; height:60px; background:#222; display:flex; align-items:center; justify-content:center; border-radius:10px; }
    .safe { background:green; }
    .bomb { background:red; }
    button { padding:10px 20px; font-size:16px; }
  </style>
</head>
<body>

<h2>MINES PREDICTOR</h2>
<button onclick="generate()">Prédire</button>

<div class="grid" id="grid"></div>

<script>
function generate(){
  let grid = document.getElementById("grid");
  grid.innerHTML = "";
  
  for(let i=0;i<25;i++){
    let div = document.createElement("div");
    div.className="cell";
    
    if(Math.random() < 0.7){
      div.classList.add("safe");
      div.innerHTML="⭐";
    } else {
      div.classList.add("bomb");
      div.innerHTML="💣";
    }
    
    grid.appendChild(div);
  }
}
</script>

</body>
</html>
