<!DOCTYPE html>
<html>
<body>

<h1>Trigonometrijos testas</h1>

<h3>1. sin(90°) = ?</h3>
<button onclick="check(this, true)">1</button>
<button onclick="check(this, false)">0</button>
<button onclick="check(this, false)">-1</button>

<h3>2. cos(0°) = ?</h3>
<button onclick="check(this, false)">0</button>
<button onclick="check(this, true)">1</button>
<button onclick="check(this, false)">-1</button>

<h3>3. tan(45°) = ?</h3>
<button onclick="check(this, false)">0</button>
<button onclick="check(this, true)">1</button>
<button onclick="check(this, false)">2</button>

<p id="rez"></p>

<script>
let score = 0;
let answered = 0;

function check(btn, correct){
    if(btn.disabled) return;

    if(correct){
        score++;
        btn.style.background = "lightgreen";
    } else {
        btn.style.background = "red";
    }

    btn.disabled = true;
    answered++;

    if(answered === 3){
        document.getElementById("rez").innerText =
        "Tavo rezultatas: " + score + " / 3";
    }
}
</script>

</body>
</html>
