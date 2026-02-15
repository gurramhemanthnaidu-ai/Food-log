
# Food-log
<!DOCTYPE html><html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FoodSwag Demo</title>
<style>
body{font-family:Arial;margin:0;background:#f6f6f6}
.header{background:#d84315;color:#fff;padding:15px;display:flex;justify-content:space-between;align-items:center}
.logo{font-weight:bold;font-size:22px}
.container{padding:20px}
.card{background:#fff;padding:12px;margin:10px;border-radius:8px;box-shadow:0 2px 5px rgba(0,0,0,.12);width:220px}
.card img{width:100%;height:140px;object-fit:cover;border-radius:6px}
.flex{display:flex;flex-wrap:wrap}
button{background:#d84315;color:#fff;border:none;padding:8px 12px;border-radius:5px;cursor:pointer;margin-left:5px}
button.secondary{background:#555}
input,select{padding:8px;margin:5px 0;width:100%}
.hidden{display:none}
.cart-badge{background:#fff;color:#d84315;padding:3px 8px;border-radius:12px;margin-left:6px;font-weight:bold}
.cart-box{background:#fff;padding:15px;margin:10px 0;border-radius:6px;display:flex;justify-content:space-between;align-items:center}
.actions button{margin-left:8px}
</style>
</head>
<body><!-- LOGIN PAGE --><div id="loginPage" class="container">
<h2>FoodSwag Login</h2>
<input type="text" id="username" placeholder="Username">
<input type="password" id="password" placeholder="Password">
<button onclick="login()">Login</button>
<p id="loginError" style="color:red"></p>
<p><b>Valid:</b> food_user / food_secret</p>
</div><!-- ITEMS PAGE --><div id="itemsPage" class="hidden">
<div class="header">
<div class="logo">FoodSwag</div>
<div>
<select onchange="sortItems(this.value)">
<option value="az">Name (A-Z)</option>
<option value="za">Name (Z-A)</option>
<option value="low">Price (Low-High)</option>
<option value="high">Price (High-Low)</option>
</select>
<button onclick="goCart()">Cart <span class="cart-badge" id="cartCount">0</span></button>
<button class="secondary" onclick="logout()">Logout</button>
</div>
</div>
<div class="container flex" id="itemsContainer"></div>
</div><!-- CART PAGE --><div id="cartPage" class="hidden container">
<h2>Your Cart</h2>
<div id="cartItems"></div>
