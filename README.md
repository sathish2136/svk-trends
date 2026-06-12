<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SVK Trends | Mobile Shop</title>
    <!-- Premium Google Font -->
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&display=swap" rel="stylesheet">

    <!-- ALL YOUR CSS STYLING DESIGN IS INSIDE HERE -->
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }
        body {
            background-color: #fcfcfc;
            color: #111;
        }
        .app-header {
            background: #ffffff;
            padding: 16px;
            text-align: center;
            border-bottom: 1px solid #f0f0f0;
            position: sticky;
            top: 0;
            z-index: 90;
        }
        .brand-logo {
            font-size: 20px;
            font-weight: 800;
            letter-spacing: 2px;
            text-transform: uppercase;
        }
        .category-tabs {
            display: flex;
            justify-content: space-around;
            background: #ffffff;
            padding: 10px 0;
            border-bottom: 1px solid #eaeaea;
            position: sticky;
            top: 54px;
            z-index: 90;
        }
        .tab-btn {
            background: transparent;
            border: none;
            font-size: 12px;
            font-weight: 700;
            text-transform: uppercase;
            color: #888;
            padding: 6px 12px;
            cursor: pointer;
        }
        .tab-btn.active {
            color: #000;
            border-bottom: 2px solid #111;
        }
        .promo-banner {
            background: #f7f7f7;
            padding: 30px 20px;
            text-align: center;
            border-bottom: 1px solid #eee;
        }
        .promo-banner h2 {
            font-size: 20px;
            font-weight: 800;
            text-transform: uppercase;
            margin-bottom: 4px;
        }
        .promo-banner p {
            font-size: 11px;
            color: #666;
        }
        .mobile-catalog {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
            padding: 15px;
        }
        .clothing-card {
            background: #ffffff;
            border: 1px solid #eee;
            border-radius: 8px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
        }
        .image-box {
            width: 100%;
            height: 200px;
            background: #fdfdfd;
        }
        .image-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .card-details {
            padding: 10px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }
        .card-details h3 {
            font-size: 13px;
            font-weight: 600;
            margin-bottom: 2px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .tag {
            font-size: 10px;
            color: #999;
            text-transform: uppercase;
            margin-bottom: 8px;
        }
        .size-row {
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 11px;
            font-weight: 600;
            margin-bottom: 12px;
        }
        .size-row select {
            padding: 2px 4px;
            border: 1px solid #ccc;
            background: #fff;
            font-size: 11px;
            border-radius: 4px;
        }
        .price-action {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: auto;
        }
        .cost {
            font-weight: 800;
            font-size: 14px;
        }
        .bag-btn {
            background: #111;
            color: #fff;
            border: none;
            width: 28px;
            height: 28px;
            border-radius: 50%;
            font-size: 16px;
            font-weight: 700;
            cursor: pointer;
        }
        .floating-bag-icon {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #111;
            color: #fff;
            width: 56px;
            height: 56px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
            cursor: pointer;
            z-index: 100;
        }
        #cart-counter-bubble {
            position: absolute;
            top: 6px;
            right: 6px;
            background: #ff3b30;
            color: white;
            font-size: 10px;
            font-weight: 800;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .mobile-drawer {
            position: fixed;
            top: 0;
            right: -100%;
            width: 100%;
            height: 100%;
            background: #ffffff;
            z-index: 200;
            display: flex;
            flex-direction: column;
            transition: right 0.3s ease;
        }
        .mobile-drawer.active {
            right: 0;
        }
        .drawer-header {
            padding: 16px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .close-drawer {
            background: none;
            border: none;
            font-size: 20px;
            cursor: pointer;
        }
        .drawer-body {
            flex-grow: 1;
            padding: 16px;
            overflow-y: auto;
        }
        .empty-txt {
            text-align: center;
            color: #888;
            margin-top: 40px;
            font-size: 13px;
        }
        .item-basket-row {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid #f9f9f9;
            font-size: 13px;
        }
        .shipping-form {
            padding: 16px;
            background: #fafafa;
            border-top: 1px solid #eee;
        }
        .shipping-form h4 {
            font-size: 12px;
            text-transform: uppercase;
            margin-bottom: 8px;
            letter-spacing: 0.5px;
        }
        .shipping-form input,
        .shipping-form textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 8px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 12px;
        }
        .drawer-footer {
            padding: 16px;
            border-top: 1px solid #eee;
        }
        .bill-row {
            display: flex;
            justify-content: space-between;
            font-weight: 700;
            font-size: 15px;
            margin-bottom: 12px;
        }
        .app-checkout-btn {
            width: 100%;
            background: #111;
            color: #fff;
            border: none;
            padding: 14px;
            font-size: 13px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            border-radius: 6px;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <!-- Mobile Top Navigation Bar -->
    <header class="app-header">
        <div class="brand-logo">SVK Trends</div>
    </header>

    <!-- Category Filter Controls -->
    <nav class="category-tabs">
        <button class="tab-btn active" onclick="switchCategory('all', event)">All Shop</button>
        <button class="tab-btn" onclick="switchCategory('men', event)">Men</button>
        <button class="tab-btn" onclick="switchCategory('women', event)">Women</button>
        <button class="tab-btn" onclick="switchCategory('kids', event)">Kids</button>
    </nav>

    <!-- App Promotional Banner -->
    <div class="promo-banner">
        <h2>Creative Premium Fashion</h2>
        <p>Premium trends tailored for your family</p>
    </div>

    <!-- Mobile 2-Column Catalog -->
    <main class="mobile-catalog">
        
        <!-- Card 1: Men -->
        <div class="clothing-card men">
            <div class="image-box">
                <img src="https://images.unsplash.com/photo-1507679799987-c73779587ccf?auto=format&fit=crop&w=400&q=80" alt="Men's Shirt">
            </div>
            <div class="card-details">
                <h3>Classic Regular Shirt</h3>
                <p class="tag">Men Collection</p>
                <div class="size-row">
                    <label>Size:</label>
                    <select id="size-item-1">
                        <option value="S">S</option>
                        <option value="M" selected>M</option>
                        <option value="L">L</option>
                        <option value="XL">XL</option>
                    </select>
                </div>
                <div class="price-action">
                    <span class="cost">₹1,539</span>
                    <button class="bag-btn" onclick="addItemToBag('Classic Regular Shirt', 1539, 'size-item-1')">+</button>
                </div>
            </div>
        </div>

        <!-- Card 2: Women -->
        <div class="clothing-card women">
            <div class="image-box">
                <img src="https://images.unsplash.com/photo-1595777457583-95e059d581b8?auto=format&fit=crop&w=400&q=80" alt="Women Dress">
            </div>
            <div class="card-details">
                <h3>Minimal Evening Gown</h3>
                <p class="tag">Women Apparel</p>
                <div class="size-row">
                    <label>Size:</label>
                    <select id="size-item-2">
                        <option value="S">S</option>
                        <option value="M" selected>M</option>
                        <option value="L">L</option>
                    </select>
                </div>
                <div class="price-action">
                    <span class="cost">₹3,199</span>
                    <button class="bag-btn" onclick="addItemToBag('Minimal Evening Gown', 3199, 'size-item-2')">+</button>
                </div>
            </div>
        </div>

        <!-- Card 3: Kids -->
        <div class="clothing-card kids">
            <div class="image-box">
                <img src="https://images.unsplash.com/photo-1519457431-44ccd64a579b?auto=format&fit=crop&w=400&q=80" alt="Kids Suit">
            </div>
            <div class="card-details">
                <h3>Premium Cotton Outfit</h3>
                <p class="tag">Kids Wardrobe</p>
                <div class="size-row">
                    <label>Size:</label>
                    <select id="size-item-3">
                        <option value="2-3 Yrs">2-3Y</option>
                        <option value="4-5 Yrs" selected>4-5Y</option>
                        <option value="6-7 Yrs">6-7Y</option>
                    </select>
                </div>
                <div class="price-action">
                    <span class="cost">₹949</span>
                    <button class="bag-btn" onclick="addItemToBag('Premium Cotton Outfit', 949, 'size-item-3')">+</button>
                </div>
            </div>
        </div>

    </main>

    <!-- Floating Bag Button -->
    <div class="floating-bag-icon" onclick="openAppCart()">
        💼 <span id="cart-counter-bubble">0</span>
    </div>

    <!-- Side Checkout App Drawer Layout -->
    <div id="app-cart-drawer" class="mobile-drawer">
        <div class="drawer-header">
            <h3>Your Selection</h3>
            <button class="close-drawer" onclick="closeAppCart()">✕</button>
        </div>
        
        <div id="drawer-items-container" class="drawer-body">
            <p class="empty-txt">Your shopping bag is completely empty.</p>
        </div>

        <!-- Customer Form -->
        <div class="shipping-form">
            <h4>Customer Delivery Details</h4>
            <input type="text" id="user-name" placeholder="Full Name">
            <input type="text" id="user-phone" placeholder="Mobile Number">
            <textarea id="user-address" placeholder="Complete Shipping Address" rows="2"></textarea>
        </div>

        <div class="drawer-footer">
            <div class="bill-row">
                <span>Total Bill Amount:</span>
                <span id="bill-total-price">₹0</span>
            </div>
            <button class="app-checkout-btn" onclick="sendOrderDataToWhatsApp()">Submit Order via WhatsApp</button>
        </div>
    </div>

    <!-- ALL YOUR JAVASCRIPT LOGIC DYNAMICS ARE INSIDE HERE -->
    <script>
        let appShoppingBag = [];

        function switchCategory(category, event) {
            let tabs = document.querySelectorAll('.tab-btn');
            tabs.forEach(tab => tab.classList.remove('active'));
            event.target.classList.add('active');

            let pieces = document.querySelectorAll('.clothing-card');
            pieces.forEach(piece => {
                if (category === 'all') {
                    piece.style.display = 'flex';
                } else if (piece.classList.contains(category)) {
                    piece.style.display = 'flex';
                } else {
                    piece.style.display = 'none';
                }
            });
        }

        function addItemToBag(name, price, sizeSelectId) {
            let sizeField = document.getElementById(sizeSelectId);
            let selectedSize = sizeField.value;
            
            appShoppingBag.push({ name: name, price: price, size: selectedSize });
            refreshBagUI();
            openAppCart();
        }

        // Change this to change your WhatsApp Number (Include country code 91, no symbols)
        let businessNumber = "919876543210"; 

        function openAppCart() {
            document.getElementById('app-cart-drawer').classList.add('active');
        }

        function closeAppCart() {
            document.getElementById('app-cart-drawer').classList.remove('active');
        }

        function refreshBagUI() {
            document.getElementById('cart-counter-bubble').innerText = appShoppingBag.length;
            let container = document.getElementById('drawer-items-container');
            
            if (appShoppingBag.length === 0) {
                container.innerHTML = '<p class="empty-txt">Your shopping bag is completely empty.</p>';
                document.getElementById('bill-total-price').innerText = "₹0";
                return;
            }
            
            container.innerHTML = "";
            let finalBill = 0;
            
            appShoppingBag.forEach(item => {
                finalBill += item.price;
                let block = document.createElement('div');
                block.className = 'item-basket-row';
                block.innerHTML = `
                    <div>
                        <strong>${item.name}</strong><br>
                        <span style="color:#777; font-size:11px;">Size: ${item.size}</span>
                    </div>
                    <strong>₹${item.price}</strong>
                `;
                container.appendChild(block);
            });
            
            document.getElementById('bill-total-price').innerText = "₹" + finalBill.toLocaleString('en-IN');
        }

        function sendOrderDataToWhatsApp() {
            if (appShoppingBag.length === 0) {
                alert("Your shopping bag is empty!");
                return;
            }
            
            let name = document.getElementById('user-name').value.trim();
            let phone = document.getElementById('user-phone').value.trim();
            let address = document.getElementById('user-address').value.trim();
            
            if (!name || !phone || !address) {
                alert("Please provide your delivery info parameters before proceeding to checkout.");
                return;
            }
            
            let template = "🛍️ *SVK Trends Mobile Order Receipt* 🛍️\n\n";
            template += `*Buyer Name:* ${name}\n`;
            template += `*Contact:* ${phone}\n`;
            template += `*Delivery Destination:* ${address}\n`;
            template += "----------------------------------------\n";
            
            let sumTotal = 0;
            appShoppingBag.forEach((item, i) => {
                template += `${i + 1}. ${item.name} (Size: ${item.size}) - ₹${item.price.toLocaleString('en-IN')}\n`;
                sumTotal += item.price;
            });
            
            template += "----------------------------------------\n";
            template += `*Total Order Value:* ₹${sumTotal.toLocaleString('en-IN')}\n\n`;
            template += "Please confirm stock dispatch availability! ✨";
            
            let processedMessage = encodeURIComponent(template);
            let finalGatewayLink = `https://wa.me/${businessNumber}?text=${processedMessage}`;
            
            window.open(finalGatewayLink, '_blank');
        }
    </script>
</body>
</html>
