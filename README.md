<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HB store</title>

<style>
body{
margin:0;
font-family:'Segoe UI',sans-serif;
background:#111;
color:white;
}

header{
text-align:center;
padding:20px;
font-size:28px;
font-weight:bold;
letter-spacing:2px;
}

.container{
padding:20px;
}

.card{
background:#1c1c1c;
border-radius:20px;
overflow:hidden;
box-shadow:0 20px 40px rgba(0,0,0,0.6);
}

img{
width:100%;
transition:0.3s;
}

.content{
padding:20px;
}

.price{
font-size:28px;
color:#00ff88;
font-weight:bold;
margin-bottom:10px;
}

select{
width:100%;
padding:12px;
margin-bottom:12px;
border-radius:10px;
border:none;
font-size:16px;
}

.btn{
display:block;
text-align:center;
padding:15px;
border-radius:12px;
text-decoration:none;
font-size:18px;
margin-top:10px;
transition:0.3s;
}

.whatsapp{
background:#25D366;
color:white;
}

.whatsapp:hover{
background:#1ebe5d;
}

.nequi{
background:#6c2bd9;
color:white;
}

.nequi:hover{
background:#5a23b5;
}

footer{
text-align:center;
padding:15px;
font-size:14px;
color:#aaa;
}

.badge{
background:#00ff88;
color:black;
padding:5px 10px;
border-radius:20px;
font-size:12px;
display:inline-block;
margin-bottom:10px;
}

</style>
</head>

<body>

<header>
HB store
</header>

<div class="container">
<div class="card">

<img id="productImg" src="negro.jpg">

<div class="content">

<span class="badge">ENVÍOS A TODA COLOMBIA 🇨🇴</span>

<div class="price">$165.000 COP</div>

<p>Zapatillas urbanas premium. Comodidad, estilo y calidad garantizada.</p>

<label>Color:</label>
<select id="color" onchange="updateImage(); updateLinks();">
<option value="negro.jpg">Negro</option>
<option value="blanco.jpg">Blanco</option>
<option value="rojo.jpg">Rojo</option>
<option value="azul.jpg">Azul</option>
</select>

<label>Talla:</label>
<select id="talla" onchange="updateLinks();">
<option>37</option>
<option>38</option>
<option>39</option>
<option>40</option>
<option>41</option>
<option>42</option>
<option>43</option>
</select>

<a id="waBtn" class="btn whatsapp" target="_blank">
Comprar por WhatsApp
</a>

<a id="nequiBtn" class="btn nequi" target="_blank">
Pagar por Nequi
</a>

</div>
</div>
</div>

<footer>
© 2026 HB store - Todos los derechos reservados
</footer>

<script>

function updateImage(){
var color = document.getElementById("color").value;
document.getElementById("productImg").src = color;
}

function updateLinks(){

var numero = "573XXXXXXXXX"; 
var nequi = "300XXXXXXX";

var colorSelect = document.getElementById("color");
var colorText = colorSelect.options[colorSelect.selectedIndex].text;

var talla = document.getElementById("talla").value;

var mensaje = "Hola, quiero comprar las zapatillas HB store color " + colorText + ", talla " + talla + " por $165.000 COP";

var waLink = "https://wa.me/" + numero + "?text=" + encodeURIComponent(mensaje);

document.getElementById("waBtn").href = waLink;

var nequiMensaje = "Pago zapatillas HB store - Color " + colorText + " - Talla " + talla + " - $165.000 COP";
var nequiLink = "https://wa.me/" + numero + "?text=" + encodeURIComponent(nequiMensaje + " (Pago por Nequi al número " + nequi + ")");

document.getElementById("nequiBtn").href = nequiLink;

}

window.onload = updateLinks;

</script>

</body>
</html>
