## Hi there 👋

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BUY BAZAAR</title>
    <style>
        /* Base styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            transition: background-color 0.3s, color 0.3s;
        }

        .dark-mode {
            background-color: #1a1a1a;
            color: white;
        }

        .light-mode {
            background-color: #f3f4f6;
            color: #333;
        }

        /* Header styles */
        header {
            padding: 1rem 2rem;
            background-color: #fff;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .dark-mode header {
            background-color: #2d2d2d;
            box-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

        header button {
            padding: 0.5rem 1rem;
            margin-left: 1rem;
            border: none;
            border-radius: 4px;
            background-color: #007bff;
            color: white;
            cursor: pointer;
        }

        /* Main layout */
        .container {
            display: grid;
            grid-template-columns: 250px 1fr;
            gap: 2rem;
            padding: 2rem;
        }

        /* Sidebar styles */
        aside {
            padding: 1rem;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .dark-mode aside {
            background-color: #2d2d2d;
            box-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

        /* Product grid */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background-color: #fff;
            border-radius: 8px;
            padding: 1rem;
            text-align: center;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .dark-mode .product-card {
            background-color: #2d2d2d;
            box-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

        .product-card img {
            width: 100%;
            border-radius: 4px;
        }

        .product-card button {
            margin-top: 1rem;
            padding: 0.5rem 1rem;
            border: none;
            border-radius: 4px;
            background-color: #007bff;
            color: white;
            cursor: pointer;
        }

        .btn-admin {
            padding: 0.5rem 1rem;
            margin-left: 1rem;
            border: none;
            border-radius: 4px;
            background-color: #2d2d2d;
            color: white;
            text-decoration: none;
            cursor: pointer;
        }

        .dark-mode .btn-admin {
            background-color: #f3f4f6;
            color: #1a1a1a;
        }

        /* Add these new cart-related styles */
        .cart-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        .cart-content {
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            width: 90%;
            max-width: 600px;
            max-height: 80vh;
            overflow-y: auto;
        }

        .dark-mode .cart-content {
            background-color: #2d2d2d;
            color: white;
        }

        .cart-item {
            display: grid;
            grid-template-columns: 80px 1fr auto auto;
            gap: 1rem;
            align-items: center;
            padding: 1rem 0;
            border-bottom: 1px solid #eee;
        }

        .cart-item img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 4px;
        }

        .cart-quantity {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .cart-quantity button {
            padding: 0.25rem 0.5rem;
        }

        .cart-total {
            margin-top: 1rem;
            text-align: right;
            font-weight: bold;
            font-size: 1.2rem;
        }

        .cart-badge {
            background-color: #dc3545;
            color: white;
            border-radius: 50%;
            padding: 0.2rem 0.5rem;
            font-size: 0.8rem;
            position: absolute;
            top: -8px;
            right: -8px;
        }

        .cart-button {
            position: relative;
        }

        /* Add these payment-related styles */
        .payment-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            justify-content: center;
            align-items: center;
            z-index: 1001;
        }

        .payment-content {
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            width: 90%;
            max-width: 500px;
        }

        .dark-mode .payment-content {
            background-color: #2d2d2d;
            color: white;
        }

        .payment-methods {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1rem;
            margin: 1rem 0;
        }

        .payment-method {
            padding: 1rem;
            border: 2px solid #ddd;
            border-radius: 8px;
            cursor: pointer;
            text-align: center;
            transition: all 0.3s;
        }

        .payment-method:hover {
            border-color: #007bff;
        }

        .payment-method.selected {
            border-color: #007bff;
            background-color: #f8f9fa;
        }

        .dark-mode .payment-method.selected {
            background-color: #3d3d3d;
        }

        .payment-form {
            margin-top: 1rem;
        }

        .payment-form .form-group {
            margin-bottom: 1rem;
        }

        .payment-form input {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }

        .card-info {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr;
            gap: 1rem;
        }
    </style>
</head>
<body class="light-mode">
    <!-- Header -->
    <header>
        <h1>BUY BAZAAR</h1>
        <div>
            <button>Search</button>
            <button class="cart-button" onclick="showCart()">
                Cart
                <span class="cart-badge" id="cartBadge">0</span>
            </button>
            <button>Profile</button>
            <button onclick="toggleDarkMode()">Toggle Dark Mode</button>
            <a href="admin.html" class="btn-admin">Admin Panel</a>
        </div>
    </header>

    <div class="container">
        <!-- Sidebar Filters -->
        <aside>
            <h2>Filters</h2>
            <p>Price Range</p>
            <input type="range" min="10" max="100">
        </aside>

        <!-- Product Grid -->
        <div class="product-grid">
            <div class="product-card">
                <img src="https://via.placeholder.com/150" alt="Product">
                <h2>Product 1</h2>
                <p>$20.00</p>
                <button>Add to Cart</button>
            </div>
            <div class="product-card">
                <img src="https://via.placeholder.com/150" alt="Product">
                <h2>Product 2</h2>
                <p>$25.00</p>
                <button>Add to Cart</button>
            </div>
            <div class="product-card">
                <img src="https://via.placeholder.com/150" alt="Product">
                <h2>Product 3</h2>
                <p>$30.00</p>
                <button>Add to Cart</button>
            </div>
            <div class="product-card">
                <img src="https://via.placeholder.com/150" alt="Product">
                <h2>Product 4</h2>
                <p>$15.00</p>
                <button>Add to Cart</button>
            </div>
            <div class="product-card">
                <img src="https://via.placeholder.com/150" alt="Product">
                <h2>Product 5</h2>
                <p>$40.00</p>
                <button>Add to Cart</button>
            </div>
            <div class="product-card">
                <img src="https://via.placeholder.com/150" alt="Product">
                <h2>Product 6</h2>
                <p>$35.00</p>
                <button>Add to Cart</button>
            </div>
        </div>
    </div>

    <!-- Add this before closing body tag -->
    <div class="cart-modal" id="cartModal">
        <div class="cart-content">
            <h2>Shopping Cart</h2>
            <div id="cartItems">
                <!-- Cart items will be inserted here -->
            </div>
            <div class="cart-total">
                Total: $<span id="cartTotal">0.00</span>
            </div>
            <div class="modal-buttons">
                <button class="btn btn-success" onclick="checkout()">Checkout</button>
                <button class="btn btn-primary" onclick="hideCart()">Continue Shopping</button>
            </div>
        </div>
    </div>

    <!-- Add this before closing body tag, after cart modal -->
    <div class="payment-modal" id="paymentModal">
        <div class="payment-content">
            <h2>Payment Method</h2>
            <div class="payment-methods">
                <div class="payment-method" onclick="selectPaymentMethod('card')">
                    <i class="fas fa-credit-card"></i>
                    <p>Credit Card</p>
                </div>
                <div class="payment-method" onclick="selectPaymentMethod('paypal')">
                    <i class="fab fa-paypal"></i>
                    <p>PayPal</p>
                </div>
            </div>
            
            <form id="cardPaymentForm" class="payment-form" style="display: none;" onsubmit="processPayment(event)">
                <div class="form-group">
                    <label for="cardName">Cardholder Name</label>
                    <input type="text" id="cardName" required>
                </div>
                <div class="form-group">
                    <label for="cardNumber">Card Number</label>
                    <input type="text" id="cardNumber" maxlength="16" required>
                </div>
                <div class="card-info">
                    <div class="form-group">
                        <label for="expiryDate">Expiry Date</label>
                        <input type="text" id="expiryDate" placeholder="MM/YY" maxlength="5" required>
                    </div>
                    <div class="form-group">
                        <label for="cvv">CVV</label>
                        <input type="text" id="cvv" maxlength="3" required>
                    </div>
                </div>
                <div class="modal-buttons">
                    <button type="submit" class="btn btn-success">Pay $<span id="paymentAmount">0.00</span></button>
                    <button type="button" class="btn btn-danger" onclick="hidePaymentModal()">Cancel</button>
                </div>
            </form>

            <div id="paypalPaymentForm" class="payment-form" style="display: none;">
                <p>You will be redirected to PayPal to complete your payment.</p>
                <div class="modal-buttons">
                    <button class="btn btn-success" onclick="processPayPalPayment()">Continue to PayPal</button>
                    <button class="btn btn-danger" onclick="hidePaymentModal()">Cancel</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Add Font Awesome for payment icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">

    <script>
        // Cart functionality
        let cart = [];

        // Update the products loading
        let products = [];
        
        function loadProducts() {
            const savedProducts = localStorage.getItem('storeProducts');
            if (savedProducts) {
                products = JSON.parse(savedProducts);
            } else {
                products = [
                    { id: 1, name: 'Product 1', price: 20.00, stock: 50 },
                    { id: 2, name: 'Product 2', price: 25.00, stock: 35 },
                    { id: 3, name: 'Product 3', price: 30.00, stock: 42 },
                    { id: 4, name: 'Product 4', price: 15.00, stock: 45 },
                    { id: 5, name: 'Product 5', price: 40.00, stock: 30 },
                    { id: 6, name: 'Product 6', price: 35.00, stock: 25 }
                ];
                localStorage.setItem('storeProducts', JSON.stringify(products));
            }
            updateProductGrid();
        }

        function updateProductGrid() {
            const productGrid = document.querySelector('.product-grid');
            productGrid.innerHTML = '';

            products.forEach(product => {
                const stockStatus = product.stock > 0 
                    ? `<button onclick="addToCart(${product.id}, '${product.name}', ${product.price})">Add to Cart</button>`
                    : '<button disabled>Out of Stock</button>';

                productGrid.innerHTML += `
                    <div class="product-card">
                        <img src="https://via.placeholder.com/150" alt="${product.name}">
                        <h2>${product.name}</h2>
                        <p>$${product.price.toFixed(2)}</p>
                        <p>Stock: ${product.stock}</p>
                        ${stockStatus}
                    </div>
                `;
            });
        }

        // Update addToCart to handle stock
        function addToCart(productId, name, price) {
            const product = products.find(p => p.id === productId);
            if (product.stock <= 0) {
                alert('Sorry, this item is out of stock!');
                return;
            }

            const existingItem = cart.find(item => item.id === productId);
            
            if (existingItem) {
                if (existingItem.quantity >= product.stock) {
                    alert('Sorry, no more items in stock!');
                    return;
                }
                existingItem.quantity += 1;
            } else {
                cart.push({
                    id: productId,
                    name: name,
                    price: price,
                    quantity: 1
                });
            }
            
            updateCartBadge();
            updateCartModal();
        }

        function updateCartBadge() {
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            document.getElementById('cartBadge').textContent = totalItems;
        }

        function updateCartModal() {
            const cartItems = document.getElementById('cartItems');
            cartItems.innerHTML = '';
            
            cart.forEach(item => {
                cartItems.innerHTML += `
                    <div class="cart-item">
                        <img src="https://via.placeholder.com/150" alt="${item.name}">
                        <div>
                            <h3>${item.name}</h3>
                            <p>$${item.price.toFixed(2)}</p>
                        </div>
                        <div class="cart-quantity">
                            <button onclick="updateQuantity(${item.id}, ${item.quantity - 1})">-</button>
                            <span>${item.quantity}</span>
                            <button onclick="updateQuantity(${item.id}, ${item.quantity + 1})">+</button>
                        </div>
                        <button class="btn btn-danger" onclick="removeFromCart(${item.id})">Remove</button>
                    </div>
                `;
            });

            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            document.getElementById('cartTotal').textContent = total.toFixed(2);
        }

        function updateQuantity(productId, newQuantity) {
            if (newQuantity < 1) {
                removeFromCart(productId);
                return;
            }

            const item = cart.find(item => item.id === productId);
            if (item) {
                item.quantity = newQuantity;
                updateCartBadge();
                updateCartModal();
            }
        }

        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCartBadge();
            updateCartModal();
        }

        function showCart() {
            document.getElementById('cartModal').style.display = 'flex';
        }

        function hideCart() {
            document.getElementById('cartModal').style.display = 'none';
        }

        function checkout() {
            if (cart.length === 0) {
                alert('Your cart is empty!');
                return;
            }
            showPaymentModal();
        }

        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
            document.body.classList.toggle('light-mode');
        }

        // Payment functionality
        function showPaymentModal() {
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            document.getElementById('paymentAmount').textContent = total.toFixed(2);
            document.getElementById('paymentModal').style.display = 'flex';
            hideCart();
        }

        function hidePaymentModal() {
            document.getElementById('paymentModal').style.display = 'none';
            document.getElementById('cardPaymentForm').style.display = 'none';
            document.getElementById('paypalPaymentForm').style.display = 'none';
            showCart();
        }

        function selectPaymentMethod(method) {
            const methods = document.querySelectorAll('.payment-method');
            methods.forEach(m => m.classList.remove('selected'));
            
            if (method === 'card') {
                document.querySelector('.payment-method:first-child').classList.add('selected');
                document.getElementById('cardPaymentForm').style.display = 'block';
                document.getElementById('paypalPaymentForm').style.display = 'none';
            } else {
                document.querySelector('.payment-method:last-child').classList.add('selected');
                document.getElementById('cardPaymentForm').style.display = 'none';
                document.getElementById('paypalPaymentForm').style.display = 'block';
            }
        }

        function processPayment(event) {
            event.preventDefault();
            // In a real application, you would send the payment details to a secure server
            completePayment();
        }

        function processPayPalPayment() {
            // In a real application, you would redirect to PayPal
            completePayment();
        }

        function completePayment() {
            alert('Payment successful! Thank you for your purchase.');
            cart = [];
            updateCartBadge();
            updateCartModal();
            hidePaymentModal();
        }

        // Add input validation for card details
        document.getElementById('cardNumber').addEventListener('input', function(e) {
            this.value = this.value.replace(/\D/g, '');
        });

        document.getElementById('cvv').addEventListener('input', function(e) {
            this.value = this.value.replace(/\D/g, '');
        });

        document.getElementById('expiryDate').addEventListener('input', function(e) {
            this.value = this.value
                .replace(/\D/g, '')
                .replace(/(\d{2})(\d)/, '$1/$2')
                .replace(/(\d{2}\/\d{2}).*/, '$1');
        });

        // Load products when page loads
        loadProducts();
    </script>
</body>
</html>
