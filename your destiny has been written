<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Your Destiny Has Been Written</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --white: #FFFFFF;
            --gold: #D4AF37;
            --prophetic-blue: #1E3A8A;
            --red: #B91C1C;
            --light-blue: #E0F2FE;
            --dark-blue: #0F1B3A;
            --gray: #F3F4F6;
            --dark-gray: #6B7280;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--white);
            color: var(--dark-blue);
            line-height: 1.6;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--prophetic-blue), var(--dark-blue));
            color: var(--white);
            padding: 1rem 0;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo i {
            color: var(--gold);
            font-size: 2rem;
        }

        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }

        .logo span {
            color: var(--gold);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--gold);
        }

        .auth-buttons {
            display: flex;
            gap: 1rem;
        }

        .btn {
            padding: 0.6rem 1.2rem;
            border-radius: 4px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--gold);
            color: var(--gold);
        }

        .btn-outline:hover {
            background: var(--gold);
            color: var(--prophetic-blue);
        }

        .btn-primary {
            background: var(--red);
            color: var(--white);
        }

        .btn-primary:hover {
            background: #9c1a1a;
        }

        .cart-icon {
            position: relative;
            margin-left: 1rem;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--red);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(30, 58, 138, 0.9), rgba(15, 27, 58, 0.9)), url('https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            padding: 5rem 0;
            text-align: center;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }

        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 2rem;
        }

        .btn-gold {
            background: var(--gold);
            color: var(--prophetic-blue);
            font-weight: 700;
        }

        .btn-gold:hover {
            background: #c19b2e;
        }

        /* Products Section */
        .section-title {
            text-align: center;
            margin: 3rem 0 2rem;
            font-size: 2.2rem;
            color: var(--prophetic-blue);
            position: relative;
        }

        .section-title:after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--gold);
            margin: 10px auto;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        .product-card {
            background: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
        }

        .product-image {
            height: 200px;
            background-color: var(--light-blue);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--prophetic-blue);
            font-size: 3rem;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-category {
            color: var(--red);
            font-size: 0.9rem;
            font-weight: 600;
            text-transform: uppercase;
            margin-bottom: 0.5rem;
        }

        .product-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--dark-blue);
        }

        .product-description {
            color: var(--dark-gray);
            margin-bottom: 1rem;
            font-size: 0.95rem;
        }

        .product-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--prophetic-blue);
            margin-bottom: 1rem;
        }

        .product-actions {
            display: flex;
            justify-content: space-between;
        }

        .btn-small {
            padding: 0.5rem 1rem;
            font-size: 0.9rem;
        }

        /* Features Section */
        .features {
            background: var(--gray);
            padding: 4rem 0;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            background: var(--white);
            padding: 2rem;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-5px);
        }

        .feature-icon {
            font-size: 2.5rem;
            color: var(--gold);
            margin-bottom: 1rem;
        }

        .feature-title {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--prophetic-blue);
        }

        /* Footer */
        footer {
            background: var(--dark-blue);
            color: var(--white);
            padding: 3rem 0 1.5rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-column h3 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            color: var(--gold);
        }

        .footer-column ul {
            list-style: none;
        }

        .footer-column ul li {
            margin-bottom: 0.8rem;
        }

        .footer-column a {
            color: var(--white);
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-column a:hover {
            color: var(--gold);
        }

        .social-icons {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 36px;
            height: 36px;
            background: var(--prophetic-blue);
            border-radius: 50%;
            transition: background 0.3s;
        }

        .social-icons a:hover {
            background: var(--gold);
        }

        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: var(--dark-gray);
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: var(--white);
            width: 90%;
            max-width: 500px;
            border-radius: 8px;
            padding: 2rem;
            position: relative;
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-gray);
        }

        .modal-title {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--prophetic-blue);
            text-align: center;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--prophetic-blue);
        }

        .form-footer {
            text-align: center;
            margin-top: 1.5rem;
        }

        .form-footer a {
            color: var(--prophetic-blue);
            text-decoration: none;
        }

        .form-footer a:hover {
            text-decoration: underline;
        }

        /* Cart Styles */
        .cart-modal {
            max-width: 800px;
        }

        .cart-items {
            max-height: 400px;
            overflow-y: auto;
            margin-bottom: 1.5rem;
        }

        .cart-item {
            display: flex;
            align-items: center;
            padding: 1rem 0;
            border-bottom: 1px solid #eee;
        }

        .cart-item-image {
            width: 80px;
            height: 80px;
            background: var(--light-blue);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 1rem;
            border-radius: 4px;
            color: var(--prophetic-blue);
            font-size: 1.5rem;
        }

        .cart-item-details {
            flex: 1;
        }

        .cart-item-title {
            font-weight: 600;
            margin-bottom: 0.3rem;
        }

        .cart-item-price {
            color: var(--prophetic-blue);
            font-weight: 600;
        }

        .cart-item-remove {
            color: var(--red);
            cursor: pointer;
            background: none;
            border: none;
            font-size: 1.2rem;
        }

        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.3rem;
            font-weight: 700;
            padding: 1rem 0;
            border-top: 2px solid #eee;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                gap: 1rem;
            }

            .hero h2 {
                font-size: 2.2rem;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .btn {
                width: 100%;
                max-width: 250px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-book-open"></i>
                    <h1>The Definitive <span>Word</span></h1>
                </div>
                <nav>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">Ebooks</a></li>
                        <li><a href="#">Workshops</a></li>
                        <li><a href="#">Resources</a></li>
                        <li><a href="#">About</a></li>
                    </ul>
                </nav>
                <div class="auth-buttons">
                    <button class="btn btn-outline" id="loginBtn">Login</button>
                    <button class="btn btn-primary" id="signupBtn">Sign Up</button>
                    <div class="cart-icon" id="cartIcon">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h2>Your Destiny Has Been Written</h2>
            <p>Discover transformative ebooks, workshops, and resources to unlock your potential and shape your future.</p>
            <div class="hero-buttons">
                <button class="btn btn-gold">Explore Our Collection</button>
                <button class="btn btn-outline">Join Our Community</button>
            </div>
        </div>
    </section>

    <!-- Featured Products -->
    <section class="container">
        <h2 class="section-title">Featured Products</h2>
        <div class="products-grid">
            <!-- Product 1 -->
            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-book"></i>
                </div>
                <div class="product-info">
                    <div class="product-category">Ebook</div>
                    <h3 class="product-title">The Path to Enlightenment</h3>
                    <p class="product-description">A comprehensive guide to spiritual growth and personal transformation.</p>
                    <div class="product-price">$24.99</div>
                    <div class="product-actions">
                        <button class="btn btn-primary btn-small add-to-cart" data-id="1" data-name="The Path to Enlightenment" data-price="24.99">Add to Cart</button>
                        <button class="btn btn-outline btn-small">Preview</button>
                    </div>
                </div>
            </div>

            <!-- Product 2 -->
            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-video"></i>
                </div>
                <div class="product-info">
                    <div class="product-category">Workshop</div>
                    <h3 class="product-title">Manifesting Your Destiny</h3>
                    <p class="product-description">A 5-part video series on creating the life you desire through manifestation.</p>
                    <div class="product-price">$49.99</div>
                    <div class="product-actions">
                        <button class="btn btn-primary btn-small add-to-cart" data-id="2" data-name="Manifesting Your Destiny" data-price="49.99">Add to Cart</button>
                        <button class="btn btn-outline btn-small">Preview</button>
                    </div>
                </div>
            </div>

            <!-- Product 3 -->
            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-tools"></i>
                </div>
                <div class="product-info">
                    <div class="product-category">Resource</div>
                    <h3 class="product-title">Daily Reflection Journal</h3>
                    <p class="product-description">Printable journal with prompts for daily self-reflection and growth tracking.</p>
                    <div class="product-price">$12.99</div>
                    <div class="product-actions">
                        <button class="btn btn-primary btn-small add-to-cart" data-id="3" data-name="Daily Reflection Journal" data-price="12.99">Add to Cart</button>
                        <button class="btn btn-outline btn-small">Preview</button>
                    </div>
                </div>
            </div>

            <!-- Product 4 -->
            <div class="product-card">
                <div class="product-image">
                    <i class="fas fa-headphones"></i>
                </div>
                <div class="product-info">
                    <div class="product-category">Audio</div>
                    <h3 class="product-title">Meditation Series</h3>
                    <p class="product-description">Guided meditation sessions for stress relief, focus, and inner peace.</p>
                    <div class="product-price">$19.99</div>
                    <div class="product-actions">
                        <button class="btn btn-primary btn-small add-to-cart" data-id="4" data-name="Meditation Series" data-price="19.99">Add to Cart</button>
                        <button class="btn btn-outline btn-small">Preview</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features">
        <div class="container">
            <h2 class="section-title">Why Choose The Definitive Word?</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h3 class="feature-title">Secure Platform</h3>
                    <p>Your data and purchases are protected with enterprise-grade security.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3 class="feature-title">Access Anywhere</h3>
                    <p>Enjoy our content on any device, online or offline.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-graduation-cap"></i>
                    </div>
                    <h3 class="feature-title">Expert Content</h3>
                    <p>All materials are created by leading experts in personal development.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-users"></i>
                    </div>
                    <h3 class="feature-title">Community Support</h3>
                    <p>Join our community of like-minded individuals on the same journey.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>The Definitive Word</h3>
                    <p>Your destiny has been written. Discover the path to your true potential with our transformative resources.</p>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">Ebooks</a></li>
                        <li><a href="#">Workshops</a></li>
                        <li><a href="#">Resources</a></li>
                        <li><a href="#">About Us</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Support</h3>
                    <ul>
                        <li><a href="#">Contact Us</a></li>
                        <li><a href="#">FAQs</a></li>
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Refund Policy</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Newsletter</h3>
                    <p>Subscribe to receive updates on new releases and exclusive content.</p>
                    <form>
                        <div class="form-group">
                            <input type="email" class="form-control" placeholder="Your email address">
                        </div>
                        <button type="submit" class="btn btn-gold">Subscribe</button>
                    </form>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 The Definitive Word. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Login Modal -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <h2 class="modal-title">Login to Your Account</h2>
            <form id="loginForm">
                <div class="form-group">
                    <label for="loginEmail">Email Address</label>
                    <input type="email" id="loginEmail" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="loginPassword">Password</label>
                    <input type="password" id="loginPassword" class="form-control" required>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">Login</button>
                <div class="form-footer">
                    <p>Don't have an account? <a href="#" id="switchToSignup">Sign up</a></p>
                </div>
            </form>
        </div>
    </div>

    <!-- Signup Modal -->
    <div class="modal" id="signupModal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <h2 class="modal-title">Create Your Account</h2>
            <form id="signupForm">
                <div class="form-group">
                    <label for="signupName">Full Name</label>
                    <input type="text" id="signupName" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="signupEmail">Email Address</label>
                    <input type="email" id="signupEmail" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="signupPassword">Password</label>
                    <input type="password" id="signupPassword" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="signupConfirmPassword">Confirm Password</label>
                    <input type="password" id="signupConfirmPassword" class="form-control" required>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">Create Account</button>
                <div class="form-footer">
                    <p>Already have an account? <a href="#" id="switchToLogin">Login</a></p>
                </div>
            </form>
        </div>
    </div>

    <!-- Cart Modal -->
    <div class="modal" id="cartModal">
        <div class="modal-content cart-modal">
            <span class="close-modal">&times;</span>
            <h2 class="modal-title">Your Shopping Cart</h2>
            <div class="cart-items" id="cartItems">
                <!-- Cart items will be dynamically added here -->
            </div>
            <div class="cart-total">
                <span>Total:</span>
                <span id="cartTotal">$0.00</span>
            </div>
            <button class="btn btn-primary" style="width: 100%;" id="checkoutBtn">Proceed to Checkout</button>
        </div>
    </div>

    <script>
        // DOM Elements
        const loginBtn = document.getElementById('loginBtn');
        const signupBtn = document.getElementById('signupBtn');
        const cartIcon = document.getElementById('cartIcon');
        const loginModal = document.getElementById('loginModal');
        const signupModal = document.getElementById('signupModal');
        const cartModal = document.getElementById('cartModal');
        const closeModalButtons = document.querySelectorAll('.close-modal');
        const switchToSignup = document.getElementById('switchToSignup');
        const switchToLogin = document.getElementById('switchToLogin');
        const addToCartButtons = document.querySelectorAll('.add-to-cart');
        const cartItemsContainer = document.getElementById('cartItems');
        const cartTotalElement = document.getElementById('cartTotal');
        const cartCount = document.querySelector('.cart-count');
        const checkoutBtn = document.getElementById('checkoutBtn');

        // Cart state
        let cart = [];

        // Modal Functions
        function openModal(modal) {
            modal.style.display = 'flex';
        }

        function closeModal(modal) {
            modal.style.display = 'none';
        }

        // Event Listeners for Modals
        loginBtn.addEventListener('click', () => openModal(loginModal));
        signupBtn.addEventListener('click', () => openModal(signupModal));
        cartIcon.addEventListener('click', () => openModal(cartModal));

        closeModalButtons.forEach(button => {
            button.addEventListener('click', function() {
                const modal = this.closest('.modal');
                closeModal(modal);
            });
        });

        // Switch between login and signup modals
        switchToSignup.addEventListener('click', (e) => {
            e.preventDefault();
            closeModal(loginModal);
            openModal(signupModal);
        });

        switchToLogin.addEventListener('click', (e) => {
            e.preventDefault();
            closeModal(signupModal);
            openModal(loginModal);
        });

        // Close modal when clicking outside
        window.addEventListener('click', (e) => {
            if (e.target.classList.contains('modal')) {
                closeModal(e.target);
            }
        });

        // Cart Functions
        function addToCart(id, name, price) {
            const existingItem = cart.find(item => item.id === id);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    id,
                    name,
                    price: parseFloat(price),
                    quantity: 1
                });
            }
            
            updateCartUI();
        }

        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            updateCartUI();
        }

        function updateCartUI() {
            // Update cart count
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            // Update cart items
            cartItemsContainer.innerHTML = '';
            
            if (cart.length === 0) {
                cartItemsContainer.innerHTML = '<p>Your cart is empty</p>';
                cartTotalElement.textContent = '$0.00';
                return;
            }
            
            let total = 0;
            
            cart.forEach(item => {
                const itemTotal = item.price * item.quantity;
                total += itemTotal;
                
                const cartItemElement = document.createElement('div');
                cartItemElement.className = 'cart-item';
                cartItemElement.innerHTML = `
                    <div class="cart-item-image">
                        <i class="fas fa-book"></i>
                    </div>
                    <div class="cart-item-details">
                        <div class="cart-item-title">${item.name}</div>
                        <div class="cart-item-price">$${item.price.toFixed(2)} x ${item.quantity}</div>
                    </div>
                    <button class="cart-item-remove" data-id="${item.id}">
                        <i class="fas fa-trash"></i>
                    </button>
                `;
                
                cartItemsContainer.appendChild(cartItemElement);
            });
            
            // Update total
            cartTotalElement.textContent = `$${total.toFixed(2)}`;
            
            // Add event listeners to remove buttons
            document.querySelectorAll('.cart-item-remove').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    removeFromCart(id);
                });
            });
        }

        // Add to cart event listeners
        addToCartButtons.forEach(button => {
            button.addEventListener('click', function() {
                const id = this.getAttribute('data-id');
                const name = this.getAttribute('data-name');
                const price = this.getAttribute('data-price');
                
                addToCart(id, name, price);
                
                // Show confirmation
                const originalText = this.textContent;
                this.textContent = 'Added!';
                this.disabled = true;
                
                setTimeout(() => {
                    this.textContent = originalText;
                    this.disabled = false;
                }, 1500);
            });
        });

        // Checkout button
        checkoutBtn.addEventListener('click', () => {
            if (cart.length === 0) {
                alert('Your cart is empty!');
                return;
            }
            
            alert('Proceeding to checkout! In a real implementation, this would redirect to Stripe.');
            // In a real implementation, this would integrate with Stripe
            // For now, we'll just clear the cart
            cart = [];
            updateCartUI();
            closeModal(cartModal);
        });

        // Form submission handlers
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            // In a real implementation, this would authenticate with Supabase
            alert('Login functionality would be implemented with Supabase authentication.');
            closeModal(loginModal);
        });

        document.getElementById('signupForm').addEventListener('submit', function(e) {
            e.preventDefault();
            // In a real implementation, this would create a user with Supabase
            alert('Signup functionality would be implemented with Supabase authentication.');
            closeModal(signupModal);
        });

        // Initialize cart UI
        updateCartUI();
    </script>
</body>
</html>
