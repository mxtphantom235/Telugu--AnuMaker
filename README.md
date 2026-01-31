<!DOCTYPE html>
<html lang="te">
<head>
<meta charset="UTF-8">
<title>Telugu Unicode to Non-Unicode Converter</title>

<style>
body{
    font-family: Arial, sans-serif;
    background:#f4f4f4;
    padding:20px;
}
.header{
    font-size:20px;
    font-weight:bold;
    margin-bottom:15px;
}
.box{
    background:#ffffff;
    padding:20px;
    border-radius:6px;
}
textarea{
    width:100%;
    height:180px;
    font-size:16px;
    padding:10px;
    margin-top:8px;
}
button{
    margin-top:12px;
    padding:10px 30px;
    font-size:16px;
    cursor:pointer;
}
.footer{
    margin-top:20px;
    font-size:14px;
    color:#555;
}
</style>
</head>

<body>

<div class="header">Developer name: Shiva</div>

<div class="box">

<h2>Telugu Unicode Input</h2>
<textarea id="unicodeInput" placeholder="తెలుగు యూనికోడ్ టెక్స్ట్ ఇక్కడ పెట్టండి..."></textarea>

<button onclick="convertText()">Convert</button>

<h2>Telugu Non-Unicode Output (Anu / AnuScript)</h2>
<textarea id="nonUnicodeOutput" placeholder="Converted text will appear here..."></textarea>

</div>

<div class="footer">
Works directly on this website • No external services • Personal use
</div>

<script>
function convertText(){

let t = document.getElementById("unicodeInput").value;

/* ===== STEP 1: Complex Conjuncts ===== */
t = t.replace(/క్ష/g,"kZ");
t = t.replace(/జ్ఞ/g,"jY");
t = t.replace(/త్ర/g,"wR");
t = t.replace(/శ్ర/g,"Sr");
t = t.replace(/గ్ర/g,"gr");
t = t.replace(/ప్ర/g,"pr");

/* ===== STEP 2: Independent Vowels ===== */
t = t.replace(/అ/g,"a");
t = t.replace(/ఆ/g,"A");
t = t.replace(/ఇ/g,"i");
t = t.replace(/ఈ/g,"I");
t = t.replace(/ఉ/g,"u");
t = t.replace(/ఊ/g,"U");
t = t.replace(/ఋ/g,"R");
t = t.replace(/ఎ/g,"e");
t = t.replace(/ఏ/g,"E");
t = t.replace(/ఐ/g,"Y");
t = t.replace(/ఒ/g,"o");
t = t.replace(/ఓ/g,"O");
t = t.replace(/ఔ/g,"W");

/* ===== STEP 3: Consonants ===== */
t = t.replace(/క/g,"k");
t = t.replace(/ఖ/g,"K");
t = t.replace(/గ/g,"g");
t = t.replace(/ఘ/g,"G");
t = t.replace(/ఙ/g,"f");

t = t.replace(/చ/g,"c");
t = t.replace(/ఛ/g,"C");
t = t.replace(/జ/g,"j");
t = t.replace(/ఝ/g,"J");
t = t.replace(/ఞ/g,"F");

t = t.replace(/ట/g,"t");
t = t.replace(/ఠ/g,"T");
t = t.replace(/డ/g,"d");
t = t.replace(/ఢ/g,"D");
t = t.replace(/ణ/g,"N");

t = t.replace(/త/g,"w");
t = t.replace(/థ/g,"W");
t = t.replace(/ద/g,"x");
t = t.replace(/ధ/g,"X");
t = t.replace(/న/g,"n");

t = t.replace(/ప/g,"p");
t = t.replace(/ఫ/g,"P");
t = t.replace(/బ/g,"b");
t = t.replace(/భ/g,"B");
t = t.replace(/మ/g,"m");

t = t.replace(/య/g,"y");
t = t.replace(/ర/g,"r");
t = t.replace(/ల/g,"l");
t = t.replace(/వ/g,"v");
t = t.replace(/శ/g,"S");
t = t.replace(/ష/g,"z");
t = t.replace(/స/g,"s");
t = t.replace(/హ/g,"h");
t = t.replace(/ళ/g,"L");
t = t.replace(/ఱ/g,"R");

/* ===== STEP 4: Guninthalu ===== */
t = t.replace(/ా/g,"A");
t = t.replace(/ి/g,"i");
t = t.replace(/ీ/g,"I");
t = t.replace(/ు/g,"u");
t = t.replace(/ూ/g,"U");
t = t.replace(/ృ/g,"R");
t = t.replace(/ె/g,"e");
t = t.replace(/ే/g,"E");
t = t.replace(/ై/g,"Y");
t = t.replace(/ొ/g,"o");
t = t.replace(/ో/g,"O");
t = t.replace(/ౌ/g,"W");
t = t.replace(/్/g,"~");

/* ===== STEP 5: Signs ===== */
t = t.replace(/ం/g,"M");
t = t.replace(/ః/g,"H");
t = t.replace(/ఁ/g,"~M");

/* ===== STEP 6: Numbers ===== */
t = t.replace(/౦/g,"0");
t = t.replace(/౧/g,"1");
t = t.replace(/౨/g,"2");
t = t.replace(/౩/g,"3");
t = t.replace(/౪/g,"4");
t = t.replace(/౫/g,"5");
t = t.replace(/౬/g,"6");
t = t.replace(/౭/g,"7");
t = t.replace(/౮/g,"8");
t = t.replace(/౯/g,"9");

document.getElementById("nonUnicodeOutput").value = t;
}
</script>

</body>
</html>
