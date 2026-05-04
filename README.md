<!DOCTYPE html>
<html lang="lt">
<head>
    <meta charset="UTF-8">
    <title>Trigonometrijos testas</title>
</head>
<body>

<h1>Trigonometrijos testas (20 klausimų)</h1>

<p>Pasirink teisingą atsakymą</p>

<hr>

<div id="testas"></div>

<h2 id="rezultatas"></h2>

<script>
let score = 0;
let atsakyta = Array(20).fill(false);

const klausimai = [
    {k: "sin(90°) = ?", a: ["0","1","-1"], t: 1},
    {k: "cos(0°) = ?", a: ["0","1","-1"], t: 1},
    {k: "tan(45°) = ?", a: ["0","1","2"], t: 1},
    {k: "sin(0°) = ?", a: ["0","1","-1"], t: 0},
    {k: "cos(90°) = ?", a: ["0","1","-1"], t: 0},
    {k: "tan(0°) = ?", a: ["0","1","-1"], t: 0},
    {k: "sin(30°) = ?", a: ["1/2","1","0"], t: 0},
    {k: "cos(60°) = ?", a: ["1/2","1","0"], t: 0},
    {k: "sin(45°) ≈ ?", a: ["0.7","0.5","1"], t: 0},
    {k: "cos(45°) ≈ ?", a: ["0.7","0.5","1"], t: 0},
    {k: "tan(30°) ≈ ?", a: ["0.58","1","2"], t: 0},
    {k: "sin(180°) = ?", a: ["0","1","-1"], t: 0},
    {k: "cos(180°) = ?", a: ["-1","1","0"], t: 0},
    {k: "tan(90°) = ?", a: ["neapibrėžta","0","1"], t: 0},
    {k: "sin(270°) = ?", a: ["-1","1","0"], t: 0},
    {k: "cos(270°) = ?", a: ["0","1","-1"], t: 0},
    {k: "sin(x) yra ?", a: ["funkcija","kampas","lygtis"], t: 0},
    {k: "cos(x) yra ?", a: ["funkcija","skaičius","kampas"], t: 0},
    {k: "tan(x) = sin/cos ?", a: ["taip","ne","kartais"], t: 0},
    {k: "Trigonometrija tiria ?", a: ["kampus","kvadratus","tieses"], t: 0}
];

function tikrinti(i, pasirinkimas){
    if(!atsakyta[i]){
        atsakyta[i] = true;
        if(pasirinkimas === klausimai[i].t) score++;

        document.getElementById("rez"+i).innerText =
        "Teisingas atsakymas: " + klausimai[i].a[klausimai[i].t];

        if(atsakyta.every(v => v)){
            document.getElementById("rezultatas").innerText =
            "Tavo rezultatas: " + score + " / 20";
        }
    }
}

let html = "";

for(let i=0;i<klausimai.length;i++){
    html += "<h3>" + (i+1) + ". " + klausimai[i].k + "</h3>";

    for(let j=0;j<3;j++){
        html += `<button onclick="tikrinti(${i},${j})">${klausimai[i].a[j]}</button> `;
    }

    html += `<p id="rez${i}"></p><hr>`;
}

document.getElementById("testas").innerHTML = html;
</script>

</body>
</html>
