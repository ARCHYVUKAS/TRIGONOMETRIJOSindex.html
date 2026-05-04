<!DOCTYPE html>
<html>
<body>

<h1>Trigonometrijos testas</h1>

<p>1. sin(90°) = ?</p>
<button onclick="ats(1,1,this)">1</button>
<button onclick="ats(1,0,this)">0</button>
<button onclick="ats(1,-1,this)">-1</button>

<p>2. cos(0°) = ?</p>
<button onclick="ats(2,0,this)">0</button>
<button onclick="ats(2,1,this)">1</button>
<button onclick="ats(2,-1,this)">-1</button>

<p>3. tan(45°) = ?</p>
<button onclick="ats(3,0,this)">0</button>
<button onclick="ats(3,1,this)">1</button>
<button onclick="ats(3,2,this)">2</button>

<h3 id="rezultatas"></h3>

<script>
let score = 0;
let done = {1:false,2:false,3:false};

function ats(q, correct, btn){
    if(done[q]) return;

    done[q] = true;

    if((q===1 && correct===1) || (q===2 && correct===1) || (q===3 && correct===1)){
        score++;
        btn.style.background = "lightgreen";
    } else {
        btn.style.background = "red";
    }

    if(done[1] && done[2] && done[3]){
        document.getElementById("rezultatas").innerText =
        "Tavo rezultatas: " + score + " / 3";
    }
}
</script>

</body>
</html>
