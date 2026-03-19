<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="UTF-8">
<header class="site-header">

<div class="header-container">

<img src="logo2.png" alt="CozyStitch Threads Logo" class="logo">

</div>

</header>


<div id="imagePopup" class="popup">
<span class="close" onclick="closeImage()">&times;</span>
<img class="popup-content" id="popupImg">
</div>



<script>

function openImage(src){
document.getElementById("imagePopup").style.display="block";
document.getElementById("popupImg").src=src;
}

function closeImage(){
document.getElementById("imagePopup").style.display="none";
}

</script>




<style>

body{
font-family: Arial, sans-serif;
margin:0;
background:#faf7f4;
color:#333;
}



.site-header{
background:#ffffff;
border-bottom:1px solid #eee;
padding:15px 0;
position:sticky;
top:0;
z-index:100;
}

.header-container{
display:flex;
justify-content:center;
align-items:center;
}

.logo{
height:90px;
width:auto;
}



header{
text-align:center;
padding:40px 20px 10px 20px;
}


.tagline{
color:#8b5e3c;
margin-top:10px;
}

.container{
width:90%;
max-width:1100px;
margin:auto;
padding:40px 0;
}


.popup{
display:none;
position:fixed;
z-index:999;
padding-top:60px;
left:0;
top:0;
width:100%;
height:100%;
background-color:rgba(0,0,0,0.9);
}

.popup-content{
margin:auto;
display:block;
max-width:80%;
max-height:80%;
}

.close{
position:absolute;
top:20px;
right:40px;
color:white;
font-size:40px;
cursor:pointer;
}

.product img{
cursor:pointer;
}



.products{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:30px;
}

.product{
background:white;
border-radius:12px;
overflow:hidden;
box-shadow:0 6px 15px rgba(0,0,0,0.08);
text-align:center;
transition:0.3s;
}

.product:hover{
transform:translateY(-5px);
}

.product img{
width:100%;
height:260px;
object-fit:cover;
}

.product h3{
margin:15px 0 5px 0;
}

.price{
color:#c26a4a;
font-weight:bold;
font-size:18px;
margin-bottom:15px;
}

footer{
background:#eee;
text-align:center;
padding:25px;
margin-top:40px;
}

.whatsapp{
display:inline-block;
background:#c26a4a;
color:white;
padding:10px 20px;
border-radius:25px;
text-decoration:none;
margin-top:10px;
}

</style>
</head>

<body>

<header>


<h2 class="tagline">Handmade Crochet Creations</h2>

</header>

<div class="container">

<h2 style="text-align:center;margin-bottom:30px;">Our Products</h2>

<div class="products">

<div class="product">
<img src="Hand bag.png" onclick="openImage(this.src)">
<h3>Crochet Handbag</h3>
<p class="price">₹499</p>
</div>

<div class="product">
<img src="mobile pouch.png" onclick="openImage(this.src)">
<h3>Mobile / Sunglass Pouch</h3>
<p class="price">₹199</p>
</div>


<div class="product">
<img src="Sling mobile.png" onclick="openImage(this.src)">
<h3>Mobile / Sunglass Pouch</h3>
<p class="price">₹199</p>
</div>


<div class="product">
<img src="Red scarf.png" onclick="openImage(this.src)">
<h3>Winter Crochet Scarf with Bow</h3>
<p class="price">₹499</p>
</div>

<div class="product">
<img src="Green scarf1.png" onclick="openImage(this.src)">
<h3>Winter Crochet Scarf</h3>
<p class="price">₹499</p>
</div>

<div class="product">
<img src="white scarf1.png" onclick="openImage(this.src)">
<h3>Winter Crochet Scarf</h3>
<p class="price">₹499</p>
</div>

<div class="product">
<img src="white scarf with bow.png" onclick="openImage(this.src)">
<h3>Winter Crochet Scarf with Bow</h3>
<p class="price">₹499</p>
</div>

<div class="product">
<img src="bluepink scarf.png" onclick="openImage(this.src)">
<h3>Winter Crochet Scarf</h3>
<p class="price">₹499</p>
</div>

<div class="product">
<img src="Blue scarf1.png" onclick="openImage(this.src)">
<h3>Winter Crochet Scarf</h3>
<p class="price">₹499</p>
</div>


<div class="product">
<img src="Sling bag.png" onclick="openImage(this.src)">
<h3>Crochet Handbag</h3>
<p class="price">₹399</p>
</div>


<div class="product">
<img src="brown jumpsuit.png" onclick="openImage(this.src)">
<h3>Baby Jumpsuit</h3>
<p class="price">₹499</p>
</div>


<div class="product">
<img src="orange jumpsuit.png" onclick="openImage(this.src)">
<h3>Baby Jumpsuit</h3>
<p class="price">₹499</p>
</div>


<div class="product">
<img src="red white frock.png" onclick="openImage(this.src)">
<h3>Baby Dress with Cap and Socks</h3>
<p class="price">₹499</p>
</div>


<div class="product">
<img src="white baby frock.png" onclick="openImage(this.src)">
<h3>Baby Dress with Cap and Socks</h3>
<p class="price">₹499</p>
</div>


<div class="product">
<img src="multicolor baby dress.png" onclick="openImage(this.src)">
<h3>Baby jacket with Cap and Socks</h3>
<p class="price">₹499</p>
</div>

<div class="product">
<img src="ombre frock.png" onclick="openImage(this.src)">
<h3>Baby jacket with Cap and Socks</h3>
<p class="price">₹499</p>
</div>

<div class="product">
<img src="blue sweater.png" onclick="openImage(this.src)">
<h3>Baby Sweater with Cap and Socks</h3>
<p class="price">₹499</p>
</div>

<div class="product">
<img src="purple sweater.png" onclick="openImage(this.src)">
<h3>Small Baby Sweater with Cap</h3>
<p class="price">₹399</p>
</div>

<div class="product">
<img src="tricolor.png" onclick="openImage(this.src)">
<h3>Tricolour Baby Sweater with Cap and Socks</h3>
<p class="price">₹499</p>
</div>

</div>

</div>

<footer>

<p>Interested in ordering?</p>

<a class="whatsapp" href="#">Contact on WhatsApp</a>

<p style="margin-top:15px;">© 2026 CozyStitch Threads</p>

</footer>

</body>
</html>
