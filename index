<!DOCTYPE html><html><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Sky Shopping - Markaz Style</title><link rel="stylesheet" href="style9.css"></head>
<body>
  <link rel="stylesheet" href="css.css">
<header><div class="top"><div style="display:flex;align-items:center;gap:10px"><div class="logo"></div><h1>SKY <span>SHOPPING</span></h1></div><button class="btn" style="width:auto;padding:8px 18px" onclick="location.href='supplier.html'">Become Supplier</button></div>
<nav><a href="sky.html" class="active">Home</a><a href="products.html">Products</a><a href="order.html">Order</a><a href="account.html">My Account</a><a href="withdraw.html">Withdraw</a><a href="supplier.html">Supplier</a><a href="admin.html">Admin</a><a href="return.html">Return</a><a href="help.html">Help</a></nav></header>

<div class="hero"><h2>Pakistan Ka Apna<br>Markaz - Earn From Home</h2><p>Zero Investment • Daily Profit • 24h Payment • Supplier Bano Ya Reseller Bano</p><button onclick="location.href='products.html'">🛍️ Products Dekho</button><button onclick="location.href='#join'" style="background:#fff">🚀 Join as Reseller</button></div>

<div class="search-box"><input id="searchInput" placeholder="Search Shoes, Kurta, Watch..."><button onclick="doSearch()">Search</button></div>

<div class="sec"><h2>🔥 Trending Products</h2><div class="grid" id="homeGrid"></div></div>

<div class="sec"><h2>⭐ Resellers Reviews</h2><div class="grid"><div class="card"><div class="pad">★★★★★<p>"Pehle mahine 22,000 kamaya, payment time par mili."</p><b>- Ayesha, Lahore</b></div></div><div class="card"><div class="pad">★★★★★<p>"Shoe wala hun, Sky par product lagaya, daily 5 orders."</p><b>- Bilal Shoes, Lahore</b></div></div><div class="card"><div class="pad">★★★★★<p>"Return bhi easy hai, customer khush."</p><b>- Sana, Karachi</b></div></div></div></div>

<div class="sec" id="join"><div class="form-box"><h2>🚀 Become Reseller - Free Join</h2><p style="font-size:13px;color:#666">Form bharein, 24h me contact karenge.</p>
<form id="resellerForm"><input name="Full Name" placeholder="Full Name" required><input name="WhatsApp Number" placeholder="WhatsApp 03xx..." required><input name="Email" type="email" placeholder="Email" required><input name="City" placeholder="City" required><textarea name="Address" placeholder="Full Address" required></textarea><input name="Account Number" placeholder="JazzCash / EasyPaisa Number" required><button class="btn btn-gold">Apply Now - FREE</button><p id="msg"></p></form></div></div>

<footer><h3>SKY SHOPPING</h3><p>support@skyshopping109@gmail.com | Lahore, Pakistan</p><p>© 2026 Sky Shopping - Markaz Style Platform</p></footer>
<script>
let defaultProducts=[{code:'P001',name:'Women Kurta Set',price:4000,img:'pic1.jpg',shop:'Sky Official'},{code:'P002',name:'Smart Watch',price:2300,img:'BNB.jpg',shop:'Sky Official'},{code:'P003',name:'Nike Air Shoes',price:2800,img:'https://raw.githubusercontent.com/USERNAME/sky-images/main/part%20c14.jpg',shop:'Bilal Shoes'}];
let sup=JSON.parse(localStorage.getItem('supplierProducts')||'[]').filter(p=>p.status.includes('Approved')).map(p=>({code:p.id,name:p.productName,price:p.resellerPrice+500,img:p.image,shop:p.shopName}));
let all=[...defaultProducts,...sup];
document.getElementById('homeGrid').innerHTML=all.map(p=>`<div class="card"><img src="${p.img}"><div class="pad"><h3>${p.name}</h3><p>By ${p.shop} • Code ${p.code}</p><div class="price">Rs. ${p.price} <s>Rs. ${p.price+500}</s></div><div class="profit">Reseller Profit: Rs. 500</div><button class="btn" onclick="orderNow('${p.code}','${p.name}','${p.price-500}')">Order Now</button></div></div>`).join('');
function orderNow(code,name,price){localStorage.setItem('selectedProduct',JSON.stringify({code,name,price}));location.href='order.html';}
function doSearch(){localStorage.setItem('searchQ',document.getElementById('searchInput').value);location.href='products.html';}
document.getElementById('resellerForm').addEventListener('submit',async e=>{e.preventDefault();let data=Object.fromEntries(new FormData(e.target).entries());let list=JSON.parse(localStorage.getItem('resellers')||'[]');list.push({...data,date:new Date().toLocaleString()});localStorage.setItem('resellers',JSON.stringify(list));localStorage.setItem('userName',data['Full Name']);try{await fetch('http://localhost:8080/api/resellers',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify(data)});}catch(err){}document.getElementById('msg').innerText='✅ Saved! Welcome to Sky Shopping';setTimeout(()=>location.href='products.html',800);});
</script></body></html>
