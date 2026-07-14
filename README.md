<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CozyStitch Threads | Handmade Crochet Creations</title>
<meta name="description" content="Handmade crochet bags, scarves, baby wear and more from CozyStitch Threads. Order directly on WhatsApp.">
<meta property="og:title" content="CozyStitch Threads | Handmade Crochet Creations">
<meta property="og:description" content="Handmade crochet bags, scarves, baby wear and more. Order directly on WhatsApp.">
<meta property="og:image" content="logo2.png">
<meta property="og:type" content="website">
<link rel="icon" type="image/png" href="logo2.png">

<style>
:root{
  --cream:#faf7f4;
  --white:#ffffff;
  --ink:#333333;
  --clay:#c26a4a;
  --clay-dark:#a8553a;
  --brown:#8b5e3c;
  --line:#eeeeee;
}
*{ box-sizing:border-box; }
body{
  font-family: Arial, sans-serif;
  margin:0;
  background:var(--cream);
  color:var(--ink);
}
a{ color:inherit; }

/* Header */
.site-header{
  background:var(--white);
  border-bottom:1px solid var(--line);
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
header.intro{
  text-align:center;
  padding:40px 20px 10px 20px;
}
.tagline{
  color:var(--brown);
  margin-top:10px;
}

/* Layout */
.container{
  width:90%;
  max-width:1100px;
  margin:auto;
  padding:40px 0;
}
h2.section-title{
  text-align:center;
  margin-bottom:24px;
}

/* Category filters */
.filters{
  display:flex;
  flex-wrap:wrap;
  justify-content:center;
  gap:10px;
  margin-bottom:30px;
}
.filter-btn{
  background:var(--white);
  border:1px solid var(--line);
  color:var(--ink);
  padding:8px 18px;
  border-radius:20px;
  font-size:14px;
  cursor:pointer;
  transition:0.2s;
}
.filter-btn:hover{
  border-color:var(--clay);
}
.filter-btn.active{
  background:var(--clay);
  border-color:var(--clay);
  color:var(--white);
}
.filter-btn:focus-visible{
  outline:2px solid var(--clay-dark);
  outline-offset:2px;
}

/* Product grid */
.products{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
  gap:30px;
}
.product{
  background:var(--white);
  border-radius:12px;
  overflow:hidden;
  box-shadow:0 6px 15px rgba(0,0,0,0.08);
  text-align:center;
  transition:0.3s;
  display:flex;
  flex-direction:column;
}
.product:hover{
  transform:translateY(-5px);
}
.product img{
  cursor:pointer;
  width:100%;
  height:260px;
  object-fit:cover;
}
.product h3{
  margin:15px 15px 5px 15px;
  font-size:17px;
  min-height:44px;
}
.price{
  color:var(--clay);
  font-weight:bold;
  font-size:18px;
  margin:0 15px 15px 15px;
}
.order-btn{
  display:block;
  background:#25D366;
  color:var(--white);
  text-decoration:none;
  font-size:14px;
  font-weight:bold;
  padding:10px 0;
  margin:0 15px 18px 15px;
  border-radius:20px;
  transition:0.2s;
}
.order-btn:hover{
  background:#1ebe57;
}
.order-btn:focus-visible{
  outline:2px solid var(--clay-dark);
  outline-offset:2px;
}

/* Empty state */
.empty-state{
  text-align:center;
  color:#888;
  padding:40px 0;
  display:none;
}

/* Popup */
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
  max-width:90%;
  max-height:80%;
}
.close{
  position:absolute;
  top:20px;
  right:30px;
  color:white;
  font-size:40px;
  cursor:pointer;
  line-height:1;
}
.close:focus-visible{
  outline:2px solid var(--white);
  outline-offset:4px;
}

/* Footer */
footer{
  background:#eeeeee;
  text-align:center;
  padding:25px;
  margin-top:40px;
}
.whatsapp{
  display:inline-block;
  background:var(--clay);
  color:white;
  padding:10px 20px;
  border-radius:25px;
  text-decoration:none;
  margin-top:10px;
}
.whatsapp:hover{
  background:var(--clay-dark);
}

@media (prefers-reduced-motion: reduce){
  .product, .order-btn, .whatsapp, .filter-btn{ transition:none; }
}
</style>
</head>
<body>

<header class="site-header">
  <div class="header-container">
    <img src="logo2.png" alt="CozyStitch Threads Logo" class="logo">
  </div>
</header>

<header class="intro">
  <h2 class="tagline">Handmade Crochet Creations</h2>
</header>

<!-- IMAGE POPUP -->
<div id="imagePopup" class="popup" role="dialog" aria-modal="true" aria-label="Product image preview">
  <span class="close" onclick="closeImage()" role="button" tabindex="0" aria-label="Close image" onkeydown="if(event.key==='Enter')closeImage()">&times;</span>
  <img class="popup-content" id="popupImg" alt="Enlarged product photo">
</div>

<div class="container">
  <h2 class="section-title">Our Products</h2>

  <!-- CATEGORY FILTERS -->
  <div class="filters" role="tablist" aria-label="Filter products by category">
    <button class="filter-btn active" data-filter="all">All</button>
    <button class="filter-btn" data-filter="bags">Bags &amp; Pouches</button>
    <button class="filter-btn" data-filter="scarves">Scarves</button>
    <button class="filter-btn" data-filter="baby">Baby Wear</button>
    <button class="filter-btn" data-filter="women">Women's Wear</button>
    <button class="filter-btn" data-filter="blankets">Blankets</button>
  </div>

  <div class="products" id="productGrid">

    <div class="product" data-category="bags">
      <img src="handbag.png" alt="Crochet Handbag" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Crochet Handbag</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Crochet%20Handbag%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="bags">
      <img src="mobile-pouch.png" alt="Mobile / Sunglass Pouch - Classic style" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Mobile / Sunglass Pouch — Classic</h3>
      <p class="price">₹199</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Mobile%2FSunglass%20Pouch%20-%20Classic%20(%E2%82%B9199).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="bags">
      <img src="sling-mobile.png" alt="Mobile / Sunglass Pouch - Sling style" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Mobile / Sunglass Pouch — Sling Style</h3>
      <p class="price">₹199</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Mobile%2FSunglass%20Pouch%20-%20Sling%20Style%20(%E2%82%B9199).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="scarves">
      <img src="red-scarf.png" alt="Winter Crochet Scarf with Bow - Red" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Winter Scarf with Bow — Red</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Winter%20Scarf%20with%20Bow%20-%20Red%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="scarves">
      <img src="green-scarf.png" alt="Winter Crochet Scarf - Green" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Winter Scarf — Green</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Winter%20Scarf%20-%20Green%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="scarves">
      <img src="white-scarf.png" alt="Winter Crochet Scarf - White" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Winter Scarf — White</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Winter%20Scarf%20-%20White%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="scarves">
      <img src="whitescarfwithbow.png" alt="Winter Crochet Scarf with Bow - White" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Winter Scarf with Bow — White</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Winter%20Scarf%20with%20Bow%20-%20White%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="scarves">
      <img src="bluepink-scarf.png" alt="Winter Crochet Scarf - Blue and Pink" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Winter Scarf — Blue &amp; Pink</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Winter%20Scarf%20-%20Blue%20%26%20Pink%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="scarves">
      <img src="blue-scarf.png" alt="Winter Crochet Scarf - Blue" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Winter Scarf — Blue</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Winter%20Scarf%20-%20Blue%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="bags">
      <img src="sling-bag.png" alt="Crochet Sling Bag" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Crochet Sling Bag</h3>
      <p class="price">₹399</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Crochet%20Sling%20Bag%20(%E2%82%B9399).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="baby">
      <img src="brown-jumpsuit.png" alt="Baby Jumpsuit - Brown" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Baby Jumpsuit — Brown</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Baby%20Jumpsuit%20-%20Brown%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="baby">
      <img src="orange-jumpsuit.png" alt="Baby Jumpsuit - Orange" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Baby Jumpsuit — Orange</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Baby%20Jumpsuit%20-%20Orange%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="baby">
      <img src="redwhite-frock.png" alt="Baby Dress with Cap and Socks - Red and White" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Baby Dress with Cap &amp; Socks — Red &amp; White</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Baby%20Dress%20-%20Red%20%26%20White%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="baby">
      <img src="white-babyfrock.png" alt="Baby Dress with Cap and Socks - White" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Baby Dress with Cap &amp; Socks — White</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Baby%20Dress%20-%20White%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="baby">
      <img src="multicolor-babydress.png" alt="Baby Jacket with Cap and Socks - Multicolor" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Baby Jacket with Cap &amp; Socks — Multicolor</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Baby%20Jacket%20-%20Multicolor%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="baby">
      <img src="ombre-frock.png" alt="Baby Jacket with Cap and Socks - Ombre" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Baby Jacket with Cap &amp; Socks — Ombre</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Baby%20Jacket%20-%20Ombre%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="baby">
      <img src="blue-sweater.png" alt="Baby Sweater with Cap and Socks - Blue" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Baby Sweater with Cap &amp; Socks — Blue</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Baby%20Sweater%20-%20Blue%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="baby">
      <img src="purple-sweater.png" alt="Small Baby Sweater with Cap - Purple" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Small Baby Sweater with Cap — Purple</h3>
      <p class="price">₹399</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Small%20Baby%20Sweater%20-%20Purple%20(%E2%82%B9399).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="baby">
      <img src="tricolor.png" alt="Tricolour Baby Sweater with Cap and Socks" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Tricolour Baby Sweater with Cap &amp; Socks</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Tricolour%20Baby%20Sweater%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="women">
      <img src="lady-sweater.png" alt="Women's Crochet Top" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Women's Top</h3>
      <p class="price">₹499</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Women's%20Top%20(%E2%82%B9499).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="blankets">
      <img src="baby-blanketS.png" alt="Baby Blanket - Small" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Baby Blanket — Small</h3>
      <p class="price">₹799</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Baby%20Blanket%20-%20Small%20(%E2%82%B9799).">Order on WhatsApp</a>
    </div>

    <div class="product" data-category="blankets">
      <img src="baby-blanketL.png" alt="Baby Blanket - Large" loading="lazy" onclick="openImage(this.src, this.alt)">
      <h3>Baby Blanket — Large</h3>
      <p class="price">₹999</p>
      <a class="order-btn" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'm%20interested%20in%20the%20Baby%20Blanket%20-%20Large%20(%E2%82%B9999).">Order on WhatsApp</a>
    </div>

  </div>

  <p class="empty-state" id="emptyState">No products in this category yet.</p>
</div>

<footer>
  <p>Interested in ordering?</p>
  <a class="whatsapp" target="_blank" rel="noopener" href="https://wa.me/91XXXXXXXXXX?text=Hi!%20I'd%20like%20to%20know%20more%20about%20CozyStitch%20Threads.">Contact on WhatsApp</a>
  <p style="margin-top:15px;">© 2026 CozyStitch Threads</p>
</footer>

<script>
function openImage(src, alt){
  document.getElementById("imagePopup").style.display = "block";
  var img = document.getElementById("popupImg");
  img.src = src;
  img.alt = alt || "Enlarged product photo";
}
function closeImage(){
  document.getElementById("imagePopup").style.display = "none";
}
document.addEventListener("keydown", function(e){
  if(e.key === "Escape") closeImage();
});
document.getElementById("imagePopup").addEventListener("click", function(e){
  if(e.target === this) closeImage();
});

// Category filtering
var filterBtns = document.querySelectorAll(".filter-btn");
var products = document.querySelectorAll(".product");
var emptyState = document.getElementById("emptyState");

filterBtns.forEach(function(btn){
  btn.addEventListener("click", function(){
    filterBtns.forEach(function(b){ b.classList.remove("active"); });
    btn.classList.add("active");
    var filter = btn.getAttribute("data-filter");
    var visibleCount = 0;
    products.forEach(function(p){
      var show = filter === "all" || p.getAttribute("data-category") === filter;
      p.style.display = show ? "" : "none";
      if(show) visibleCount++;
    });
    emptyState.style.display = visibleCount === 0 ? "block" : "none";
  });
});
</script>

</body>
</html>
