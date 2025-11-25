<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Your Destiny Has Been Written</title>
    <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
    <script src="https://js.stripe.com/v3/"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* All the CSS styles from your original code remain the same */
        /* ... [CSS styles remain unchanged] ... */
    </style>
</head>
<body>
    <!-- Skip to main content -->
    <a href="#mainContent" class="skip-link">Skip to main content</a>

    <!-- Accessibility Controls -->
    <button class="accessibility-toggle" id="accessibilityToggle" aria-label="Accessibility Controls">
        <i class="fas fa-universal-access"></i>
    </button>

    <div class="accessibility-controls" id="accessibilityControls">
        <div class="control-group">
            <h4>Text Size</h4>
            <div class="control-buttons">
                <button class="btn-accessibility" id="textSmaller">A-</button>
                <button class="btn-accessibility" id="textNormal">A</button>
                <button class="btn-accessibility" id="textLarger">A+</button>
            </div>
        </div>
        <div class="control-group">
            <h4>Contrast</h4>
            <div class="control-buttons">
                <button class="btn-accessibility" id="contrastNormal">Normal</button>
                <button class="btn-accessibility" id="contrastHigh">High Contrast</button>
            </div>
        </div>
        <div class="control-group">
            <h4>Reading</h4>
            <div class="control-buttons">
                <button class="btn-accessibility" id="readingGuide">Reading Guide</button>
                <button class="btn-accessibility" id="dyslexiaFont">Dyslexia Font</button>
            </div>
        </div>
    </div>

    <!-- Keyboard Shortcuts Help -->
    <button class="keyboard-toggle" id="keyboardToggle" aria-label="Keyboard Shortcuts">
        <i class="fas fa-keyboard"></i>
    </button>

    <div class="keyboard-shortcuts" id="keyboardShortcuts">
        <h4>Keyboard Shortcuts</h4>
        <div class="shortcut-item">
            <span>Open Search</span>
            <kbd class="shortcut-key">/</kbd>
        </div>
        <div class="shortcut-item">
            <span>Open Cart</span>
            <kbd class="shortcut-key">C</kbd>
        </div>
        <div class="shortcut-item">
            <span>Accessibility</span>
            <kbd class="shortcut-key">A</kbd>
        </div>
        <div class="shortcut-item">
            <span>Navigate Products</span>
            <kbd class="shortcut-key">P</kbd>
        </div>
        <div class="shortcut-item">
            <span>Close Modals</span>
            <kbd class="shortcut-key">Esc</kbd>
        </div>
    </div>

    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo">
                    <i class="fas fa-book-open"></i>
                    <h1>The Definitive <span>Word</span></h1>
                </a>
                <nav>
                    <ul>
                        <li><a href="#" class="nav-link" data-page="home">Home</a></li>
                        <li><a href="#" class="nav-link" data-page="products">Ebooks</a></li>
                        <li><a href="#" class="nav-link" data-page="products">Workshops</a></li>
                        <li><a href="#" class="nav-link" data-page="products">Resources</a></li>
                        <li><a href="#" class="nav-link" data-page="about">About</a></li>
                    </ul>
                </nav>
                <div class="auth-buttons" id="authButtons">
                    <div class="currency-selector">
                        <i class="fas fa-money-bill-wave"></i>
                        <select id="currencySelector">
                            <option value="ZAR">ZAR (R)</option>
                            <option value="USD">USD ($)</option>
                            <option value="EUR">EUR (€)</option>
                            <option value="GBP">GBP (£)</option>
                        </select>
                    </div>
                    <button class="btn btn-outline" id="loginBtn">
                        <i class="fas fa-sign-in-alt"></i>Login
                    </button>
                    <button class="btn btn-primary" id="signupBtn">
                        <i class="fas fa-user-plus"></i>Sign Up
                    </button>
                    <div class="cart-icon" id="cartIcon" tabindex="0" role="button" aria-label="Shopping cart">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </div>
                </div>
                <div class="user-menu" id="userMenu" style="display: none;">
                    <div class="user-avatar" id="userAvatar">U</div>
                    <span id="userName">User</span>
                    <button class="btn btn-outline btn-small" id="dashboardBtn">
                        <i class="fas fa-tachometer-alt"></i>Dashboard
                    </button>
                    <button class="btn btn-admin btn-small" id="adminBtn" style="display: none;">
                        <i class="fas fa-cog"></i>Admin
                    </button>
                    <button class="btn btn-outline btn-small" id="logoutBtn">
                        <i class="fas fa-sign-out-alt"></i>Logout
                    </button>
                    <div class="cart-icon" id="cartIconLoggedIn" tabindex="0" role="button" aria-label="Shopping cart">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- Quick Actions -->
    <section class="quick-actions">
        <div class="container">
            <div class="quick-actions-grid">
                <a href="#" class="quick-action" data-page="products" data-category="Ebook">
                    <i class="fas fa-book"></i>
                    <span>Browse Ebooks</span>
                </a>
                <a href="#" class="quick-action" data-page="products" data-category="Workshop">
                    <i class="fas fa-video"></i>
                    <span>Watch Workshops</span>
                </a>
                <a href="#" class="quick-action" data-page="products" data-category="Resource">
                    <i class="fas fa-tools"></i>
                    <span>Get Resources</span>
                </a>
                <a href="#" class="quick-action" data-page="products" data-category="Audio">
                    <i class="fas fa-headphones"></i>
                    <span>Listen to Audio</span>
                </a>
            </div>
        </div>
    </section>

    <!-- Main Content Area -->
    <main id="mainContent">
        <!-- Home Page -->
        <section id="homePage">
            <!-- Hero Section -->
            <section class="hero">
                <div class="container">
                    <div class="hero-content">
                        <h2>Your Destiny Has Been Written</h2>
                        <p>Discover transformative ebooks, workshops, and resources to unlock your potential and shape your future.</p>
                        <div class="hero-buttons">
                            <button class="btn btn-gold" id="exploreProductsBtn">
                                <i class="fas fa-book"></i>Explore Our Collection
                            </button>
                            <button class="btn btn-outline" id="joinCommunityBtn">
                                <i class="fas fa-users"></i>Join Our Community
                            </button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Featured Products -->
            <section class="container">
                <h2 class="section-title">Featured Products</h2>
                <div class="products-grid" id="featuredProducts">
                    <!-- Products will be loaded dynamically -->
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
        </section>

        <!-- Products Page -->
        <section id="productsPage" style="display: none;">
            <div class="container" style="padding: 2rem 0;">
                <div class="dashboard-header">
                    <h2 class="section-title">Our Products</h2>
                    <div class="filter-controls">
                        <select id="categoryFilter" class="form-control" style="max-width: 200px;">
                            <option value="">All Categories</option>
                            <option value="Ebook">Ebooks</option>
                            <option value="Workshop">Workshops</option>
                            <option value="Resource">Resources</option>
                            <option value="Audio">Audio</option>
                        </select>
                    </div>
                </div>
                <div class="products-grid" id="allProducts">
                    <!-- All products will be loaded dynamically -->
                </div>
            </div>
        </section>

        <!-- Dashboard Page -->
        <section id="dashboardPage" style="display: none;">
            <div class="dashboard">
                <div class="container">
                    <div class="dashboard-header">
                        <h2 class="section-title">My Dashboard</h2>
                        <div class="user-info">
                            <span>Welcome back, <span id="dashboardUserName">User</span>!</span>
                        </div>
                    </div>
                    <div class="dashboard-grid">
                        <div class="dashboard-sidebar">
                            <ul class="dashboard-nav">
                                <li><a href="#" class="dashboard-nav-link active" data-tab="purchases"><i class="fas fa-shopping-bag"></i> My Purchases</a></li>
                                <li><a href="#" class="dashboard-nav-link" data-tab="progress"><i class="fas fa-chart-line"></i> Progress Tracking</a></li>
                                <li><a href="#" class="dashboard-nav-link" data-tab="community"><i class="fas fa-users"></i> Community</a></li>
                                <li><a href="#" class="dashboard-nav-link" data-tab="settings"><i class="fas fa-cog"></i> Account Settings</a></li>
                            </ul>
                        </div>
                        <div class="dashboard-content">
                            <div id="purchasesTab" class="dashboard-tab">
                                <h3>My Purchases</h3>
                                <div class="purchases-grid" id="userPurchases">
                                    <!-- Purchases will be loaded dynamically -->
                                </div>
                            </div>
                            <div id="progressTab" class="dashboard-tab" style="display: none;">
                                <h3>Progress Tracking</h3>
                                <p>Track your learning progress across all purchased content.</p>
                                <div id="progressContent">
                                    <!-- Progress content will be loaded dynamically -->
                                </div>
                            </div>
                            <div id="communityTab" class="dashboard-tab" style="display: none;">
                                <h3>Community</h3>
                                <p>Connect with other learners and share insights.</p>
                                <div id="communityContent">
                                    <!-- Community content will be loaded dynamically -->
                                </div>
                            </div>
                            <div id="settingsTab" class="dashboard-tab" style="display: none;">
                                <h3>Account Settings</h3>
                                <form id="settingsForm">
                                    <div class="form-group">
                                        <label for="settingsName">Full Name</label>
                                        <input type="text" id="settingsName" class="form-control">
                                    </div>
                                    <div class="form-group">
                                        <label for="settingsEmail">Email Address</label>
                                        <input type="email" id="settingsEmail" class="form-control">
                                    </div>
                                    <div class="form-group">
                                        <label for="settingsPassword">New Password</label>
                                        <input type="password" id="settingsPassword" class="form-control">
                                    </div>
                                    <button type="submit" class="btn btn-primary">Update Settings</button>
                                </form>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Admin Page -->
        <section id="adminPage" style="display: none;">
            <div class="dashboard">
                <div class="container">
                    <div class="dashboard-header">
                        <h2 class="section-title">Admin Panel</h2>
                        <div class="user-info">
                            <span>Manage your store content</span>
                        </div>
                    </div>
                    <div class="admin-panel">
                        <div class="admin-actions">
                            <button class="btn btn-primary" id="addProductBtn">
                                <i class="fas fa-plus"></i>Add New Product
                            </button>
                            <button class="btn btn-outline" id="refreshProductsBtn">
                                <i class="fas fa-sync"></i>Refresh Products
                            </button>
                        </div>
                        <h3>Product Management</h3>
                        <table class="admin-table">
                            <thead>
                                <tr>
                                    <th>ID</th>
                                    <th>Name</th>
                                    <th>Category</th>
                                    <th>Price</th>
                                    <th>Status</th>
                                    <th>Actions</th>
                                </tr>
                            </thead>
                            <tbody id="adminProductsTable">
                                <!-- Products will be loaded dynamically -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Page -->
        <section id="aboutPage" style="display: none;">
            <div class="container" style="padding: 2rem 0;">
                <h2 class="section-title">About The Definitive Word</h2>
                <div style="max-width: 800px; margin: 0 auto;">
                    <p style="margin-bottom: 1.5rem; font-size: 1.1rem;">
                        The Definitive Word is a transformative platform dedicated to helping individuals unlock their potential 
                        and shape their destiny through carefully curated ebooks, workshops, and resources.
                    </p>
                    <p style="margin-bottom: 1.5rem;">
                        Our mission is to provide high-quality content that inspires growth, fosters self-discovery, 
                        and empowers our community to create the lives they envision.
                    </p>
                    <h3 style="color: var(--prophetic-blue); margin: 2rem 0 1rem;">Our Values</h3>
                    <ul style="margin-left: 1.5rem; margin-bottom: 2rem;">
                        <li>Authenticity in all our content and interactions</li>
                        <li>Excellence in the quality of our products</li>
                        <li>Community support and collaboration</li>
                        <li>Continuous growth and learning</li>
                    </ul>
                </div>
            </div>
        </section>
    </main>

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
                        <li><a href="#" class="nav-link" data-page="home"><i class="fas fa-chevron-right"></i>Home</a></li>
                        <li><a href="#" class="nav-link" data-page="products"><i class="fas fa-chevron-right"></i>Ebooks</a></li>
                        <li><a href="#" class="nav-link" data-page="products"><i class="fas fa-chevron-right"></i>Workshops</a></li>
                        <li><a href="#" class="nav-link" data-page="products"><i class="fas fa-chevron-right"></i>Resources</a></li>
                        <li><a href="#" class="nav-link" data-page="about"><i class="fas fa-chevron-right"></i>About Us</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Support</h3>
                    <ul>
                        <li><a href="#"><i class="fas fa-chevron-right"></i>Contact Us</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i>FAQs</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i>Terms of Service</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i>Privacy Policy</a></li>
                        <li><a href="#"><i class="fas fa-chevron-right"></i>Refund Policy</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Newsletter</h3>
                    <p>Subscribe to receive updates on new releases and exclusive content.</p>
                    <form id="newsletterForm">
                        <div class="form-group">
                            <input type="email" class="form-control" placeholder="Your email address" required>
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
            <button class="close-modal">&times;</button>
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
                <button type="submit" class="btn btn-primary" style="width: 100%;" id="loginSubmitBtn">
                    <span class="btn-text">Login</span>
                    <div class="spinner" style="display: none;"></div>
                </button>
                <div class="form-footer">
                    <p>Don't have an account? <a href="#" id="switchToSignup">Sign up</a></p>
                </div>
            </form>
        </div>
    </div>

    <!-- Signup Modal -->
    <div class="modal" id="signupModal">
        <div class="modal-content">
            <button class="close-modal">&times;</button>
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
                    <input type="password" id="signupPassword" class="form-control" required minlength="6">
                </div>
                <div class="form-group">
                    <label for="signupConfirmPassword">Confirm Password</label>
                    <input type="password" id="signupConfirmPassword" class="form-control" required>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;" id="signupSubmitBtn">
                    <span class="btn-text">Create Account</span>
                    <div class="spinner" style="display: none;"></div>
                </button>
                <div class="form-footer">
                    <p>Already have an account? <a href="#" id="switchToLogin">Login</a></p>
                </div>
            </form>
        </div>
    </div>

    <!-- Cart Modal -->
    <div class="modal" id="cartModal">
        <div class="modal-content cart-modal">
            <button class="close-modal">&times;</button>
            <h2 class="modal-title">Your Shopping Cart</h2>
            <div class="cart-items" id="cartItems">
                <!-- Cart items will be dynamically added here -->
            </div>
            <div class="cart-total">
                <span>Total:</span>
                <span id="cartTotal">R 0.00</span>
            </div>
            <button class="btn btn-primary" style="width: 100%;" id="checkoutBtn">
                <i class="fas fa-lock"></i>Proceed to Checkout
            </button>
        </div>
    </div>

    <!-- Preview Modal -->
    <div class="modal" id="previewModal">
        <div class="modal-content preview-modal">
            <button class="close-modal">&times;</button>
            <div class="preview-content" id="previewContent">
                <!-- Preview content will be dynamically added here -->
            </div>
        </div>
    </div>

    <!-- Checkout Modal -->
    <div class="modal" id="checkoutModal">
        <div class="modal-content">
            <button class="close-modal">&times;</button>
            <h2 class="modal-title">Complete Your Purchase</h2>
            <div id="checkoutForm">
                <div class="form-group">
                    <label for="checkoutName">Full Name</label>
                    <input type="text" id="checkoutName" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="checkoutEmail">Email Address</label>
                    <input type="email" id="checkoutEmail" class="form-control" required>
                </div>
                <div id="card-element" class="form-control">
                    <!-- Stripe Card Element will be inserted here -->
                </div>
                <div id="card-errors" role="alert" style="color: var(--red); margin-top: 0.5rem;"></div>
                <button class="btn btn-primary" style="width: 100%; margin-top: 1.5rem;" id="submitPaymentBtn">
                    <span class="btn-text">Pay Now</span>
                    <div class="spinner" style="display: none;"></div>
                </button>
            </div>
        </div>
    </div>

    <!-- Add/Edit Product Modal -->
    <div class="modal" id="productModal">
        <div class="modal-content">
            <button class="close-modal">&times;</button>
            <h2 class="modal-title" id="productModalTitle">Add New Product</h2>
            <form id="productForm">
                <input type="hidden" id="productId">
                <div class="form-group">
                    <label for="productName">Product Name</label>
                    <input type="text" id="productName" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="productDescription">Description</label>
                    <textarea id="productDescription" class="form-control" rows="3" required></textarea>
                </div>
                <div class="form-group">
                    <label for="productCategory">Category</label>
                    <select id="productCategory" class="form-control" required>
                        <option value="">Select Category</option>
                        <option value="Ebook">Ebook</option>
                        <option value="Workshop">Workshop</option>
                        <option value="Resource">Resource</option>
                        <option value="Audio">Audio</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="productType">Type</label>
                    <select id="productType" class="form-control" required>
                        <option value="">Select Type</option>
                        <option value="ebook">Ebook (PDF)</option>
                        <option value="video">Video Course</option>
                        <option value="audio">Audio Series</option>
                        <option value="pdf">Printable Resource</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="productPrice">Price (ZAR)</label>
                    <input type="number" id="productPrice" class="form-control" step="0.01" min="0" required>
                </div>
                <div class="form-group">
                    <label for="productOriginalPrice">Original Price (ZAR) - Leave empty if no discount</label>
                    <input type="number" id="productOriginalPrice" class="form-control" step="0.01" min="0">
                </div>
                <div class="form-group">
                    <label for="productBadge">Badge (Optional)</label>
                    <select id="productBadge" class="form-control">
                        <option value="">No Badge</option>
                        <option value="Bestseller">Bestseller</option>
                        <option value="New">New</option>
                        <option value="Popular">Popular</option>
                        <option value="Sale">Sale</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="productFeatured">
                        <input type="checkbox" id="productFeatured"> Featured Product
                    </label>
                </div>
                <div class="form-group">
                    <label for="productSample">Sample Content (First few paragraphs)</label>
                    <textarea id="productSample" class="form-control" rows="5" required></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;" id="productSubmitBtn">
                    <span class="btn-text">Save Product</span>
                    <div class="spinner" style="display: none;"></div>
                </button>
            </form>
        </div>
    </div>

    <!-- Toast Notification -->
    <div class="toast" id="toast">
        <i class="fas fa-check-circle"></i>
        <span id="toastMessage">Product added to cart!</span>
    </div>

    <script>
        // Enhanced store with full functionality and Stripe integration
        // Initialize Stripe with your publishable key
        const stripe = Stripe('pk_test_51NkFz2Kj5qX9X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X7X');
        const elements = stripe.elements();
        let cardElement;

        // Store state
        let currentUser = null;
        let currentCurrency = 'ZAR';
        let cart = [];
        let products = [];
        let wishlist = [];
        let exchangeRates = {
            USD: 0.054,
            EUR: 0.050,
            GBP: 0.043,
            ZAR: 1
        };

        // DOM Elements
        const loginModal = document.getElementById('loginModal');
        const signupModal = document.getElementById('signupModal');
        const cartModal = document.getElementById('cartModal');
        const previewModal = document.getElementById('previewModal');
        const checkoutModal = document.getElementById('checkoutModal');
        const productModal = document.getElementById('productModal');
        const toast = document.getElementById('toast');
        const currencySelector = document.getElementById('currencySelector');
        const categoryFilter = document.getElementById('categoryFilter');
        const featuredProductsContainer = document.getElementById('featuredProducts');
        const allProductsContainer = document.getElementById('allProducts');
        const adminProductsTable = document.getElementById('adminProductsTable');
        const userPurchasesContainer = document.getElementById('userPurchases');
        const cartItemsContainer = document.getElementById('cartItems');
        const cartTotalElement = document.getElementById('cartTotal');
        const cartCountElements = document.querySelectorAll('.cart-count');
        const authButtons = document.getElementById('authButtons');
        const userMenu = document.getElementById('userMenu');
        const userName = document.getElementById('userName');
        const userAvatar = document.getElementById('userAvatar');
        const dashboardUserName = document.getElementById('dashboardUserName');

        // Sample product data
        const sampleProducts = [
            {
                id: '1',
                name: 'The Path to Purpose',
                description: 'A comprehensive guide to discovering your life purpose and aligning your actions with your true calling.',
                category: 'Ebook',
                type: 'ebook',
                price: 299,
                originalPrice: 399,
                badge: 'Bestseller',
                featured: true,
                sample: 'In the journey of life, many wander without direction, feeling lost in a sea of possibilities. This book will guide you through the process of uncovering your unique purpose and creating a life of meaning and fulfillment.'
            },
            {
                id: '2',
                name: 'Mindful Living Workshop',
                description: 'A 5-part video series teaching practical mindfulness techniques for everyday life.',
                category: 'Workshop',
                type: 'video',
                price: 499,
                originalPrice: null,
                badge: 'New',
                featured: true,
                sample: 'Welcome to the Mindful Living Workshop. In our first session, we will explore the foundations of mindfulness and how to incorporate simple practices into your daily routine.'
            },
            {
                id: '3',
                name: 'Productivity Blueprint',
                description: 'A complete system for organizing your tasks, managing time, and achieving your goals efficiently.',
                category: 'Resource',
                type: 'pdf',
                price: 199,
                originalPrice: 249,
                badge: 'Popular',
                featured: true,
                sample: 'The Productivity Blueprint is designed to help you transform how you approach your work and personal projects. With our proven system, you can accomplish more in less time while reducing stress.'
            },
            {
                id: '4',
                name: 'Meditation for Beginners',
                description: 'An audio series introducing meditation techniques for stress reduction and mental clarity.',
                category: 'Audio',
                type: 'audio',
                price: 349,
                originalPrice: null,
                badge: null,
                featured: false,
                sample: 'Find a comfortable position, either sitting or lying down. Close your eyes and take a deep breath in, then slowly exhale. Allow your body to relax with each breath.'
            },
            {
                id: '5',
                name: 'Financial Freedom Formula',
                description: 'Learn the principles of wealth building and financial independence through practical strategies.',
                category: 'Ebook',
                type: 'ebook',
                price: 399,
                originalPrice: 499,
                badge: 'Sale',
                featured: false,
                sample: 'Financial freedom is not about having vast amounts of money, but about having control over your time and choices. In this book, we will explore the mindset and strategies needed to achieve this state.'
            },
            {
                id: '6',
                name: 'Relationship Mastery',
                description: 'A workshop series on building and maintaining healthy, fulfilling relationships.',
                category: 'Workshop',
                type: 'video',
                price: 599,
                originalPrice: null,
                badge: null,
                featured: false,
                sample: 'Healthy relationships are the foundation of a happy life. In this workshop, we will explore communication techniques, boundary setting, and emotional intelligence skills.'
            }
        ];

        // Initialize the application
        function init() {
            // Load initial data
            products = [...sampleProducts];
            cart = JSON.parse(localStorage.getItem('cart')) || [];
            wishlist = JSON.parse(localStorage.getItem('wishlist')) || [];
            currentUser = JSON.parse(localStorage.getItem('currentUser'));
            
            // Initialize Stripe card element
            const card = elements.create('card', {
                style: {
                    base: {
                        fontSize: '16px',
                        color: '#424770',
                        '::placeholder': {
                            color: '#aab7c4',
                        },
                    },
                },
            });
            card.mount('#card-element');
            cardElement = card;

            // Set up event listeners
            setupEventListeners();
            
            // Render initial content
            renderFeaturedProducts();
            renderAllProducts();
            updateCartUI();
            
            // Check if user is logged in
            if (currentUser) {
                showUserMenu();
                if (currentUser.role === 'admin') {
                    document.getElementById('adminBtn').style.display = 'inline-block';
                    renderAdminProducts();
                }
            }
            
            // Load saved preferences
            loadSavedPreferences();
        }

        // Set up all event listeners
        function setupEventListeners() {
            // Navigation
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const page = this.getAttribute('data-page');
                    showPage(page);
                });
            });

            // Auth buttons
            document.getElementById('loginBtn').addEventListener('click', () => openModal(loginModal));
            document.getElementById('signupBtn').addEventListener('click', () => openModal(signupModal));
            document.getElementById('logoutBtn').addEventListener('click', logout);
            document.getElementById('dashboardBtn').addEventListener('click', () => showPage('dashboard'));
            document.getElementById('adminBtn').addEventListener('click', () => showPage('admin'));

            // Modal controls
            document.querySelectorAll('.close-modal').forEach(btn => {
                btn.addEventListener('click', function() {
                    const modal = this.closest('.modal');
                    closeModal(modal);
                });
            });

            // Auth form submissions
            document.getElementById('loginForm').addEventListener('submit', handleLogin);
            document.getElementById('signupForm').addEventListener('submit', handleSignup);
            document.getElementById('switchToSignup').addEventListener('click', (e) => {
                e.preventDefault();
                closeModal(loginModal);
                openModal(signupModal);
            });
            document.getElementById('switchToLogin').addEventListener('click', (e) => {
                e.preventDefault();
                closeModal(signupModal);
                openModal(loginModal);
            });

            // Cart and checkout
            document.getElementById('cartIcon').addEventListener('click', () => openModal(cartModal));
            document.getElementById('cartIconLoggedIn').addEventListener('click', () => openModal(cartModal));
            document.getElementById('checkoutBtn').addEventListener('click', () => {
                closeModal(cartModal);
                openModal(checkoutModal);
            });
            document.getElementById('submitPaymentBtn').addEventListener('click', handlePayment);

            // Product management
            document.getElementById('addProductBtn').addEventListener('click', () => {
                document.getElementById('productModalTitle').textContent = 'Add New Product';
                document.getElementById('productForm').reset();
                document.getElementById('productId').value = '';
                openModal(productModal);
            });
            document.getElementById('productForm').addEventListener('submit', handleProductSubmit);
            document.getElementById('refreshProductsBtn').addEventListener('click', renderAdminProducts);

            // Dashboard navigation
            document.querySelectorAll('.dashboard-nav-link').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const tab = this.getAttribute('data-tab');
                    showDashboardTab(tab);
                });
            });

            // Settings form
            document.getElementById('settingsForm').addEventListener('submit', handleSettingsUpdate);

            // Quick actions
            document.querySelectorAll('.quick-action').forEach(action => {
                action.addEventListener('click', function(e) {
                    e.preventDefault();
                    const page = this.getAttribute('data-page');
                    const category = this.getAttribute('data-category');
                    showPage(page);
                    
                    if (category) {
                        setTimeout(() => {
                            categoryFilter.value = category;
                            filterProducts();
                        }, 100);
                    }
                });
            });

            // Hero buttons
            document.getElementById('exploreProductsBtn').addEventListener('click', () => showPage('products'));
            document.getElementById('joinCommunityBtn').addEventListener('click', () => {
                if (currentUser) {
                    showPage('dashboard');
                    showDashboardTab('community');
                } else {
                    openModal(signupModal);
                }
            });

            // Currency selector
            currencySelector.addEventListener('change', function() {
                currentCurrency = this.value;
                localStorage.setItem('currency', currentCurrency);
                updateCurrencyDisplay();
            });

            // Category filter
            categoryFilter.addEventListener('change', filterProducts);

            // Newsletter form
            document.getElementById('newsletterForm').addEventListener('submit', function(e) {
                e.preventDefault();
                showToast('Thank you for subscribing to our newsletter!', 'success');
                this.reset();
            });

            // Close modals when clicking outside
            document.querySelectorAll('.modal').forEach(modal => {
                modal.addEventListener('click', function(e) {
                    if (e.target === this) {
                        closeModal(this);
                    }
                });
            });

            // Initialize accessibility features
            initAccessibility();
        }

        // Page navigation
        function showPage(page) {
            // Hide all pages
            document.querySelectorAll('main > section').forEach(section => {
                section.style.display = 'none';
            });
            
            // Show selected page
            document.getElementById(`${page}Page`).style.display = 'block';
            
            // Update active nav link
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });
            document.querySelector(`.nav-link[data-page="${page}"]`).classList.add('active');
            
            // Scroll to top
            window.scrollTo(0, 0);
        }

        // Dashboard tab navigation
        function showDashboardTab(tab) {
            // Hide all tabs
            document.querySelectorAll('.dashboard-tab').forEach(tab => {
                tab.style.display = 'none';
            });
            
            // Show selected tab
            document.getElementById(`${tab}Tab`).style.display = 'block';
            
            // Update active nav link
            document.querySelectorAll('.dashboard-nav-link').forEach(link => {
                link.classList.remove('active');
            });
            document.querySelector(`.dashboard-nav-link[data-tab="${tab}"]`).classList.add('active');
            
            // Load tab content if needed
            if (tab === 'purchases') {
                renderUserPurchases();
            }
        }

        // Product rendering
        function renderFeaturedProducts() {
            const featured = products.filter(product => product.featured);
            renderProducts(featured, featuredProductsContainer);
        }

        function renderAllProducts() {
            renderProducts(products, allProductsContainer);
        }

        function renderProducts(products, container) {
            container.innerHTML = '';
            
            if (products.length === 0) {
                container.innerHTML = '<p role="alert">No products found.</p>';
                return;
            }
            
            products.forEach(product => {
                const productCard = document.createElement('article');
                productCard.className = 'product-card';
                productCard.setAttribute('aria-labelledby', `product-title-${product.id}`);
                
                // Check if product is in wishlist
                const isInWishlist = wishlist.includes(product.id);
                
                productCard.innerHTML = `
                    ${product.badge ? `<div class="product-badge" aria-label="${product.badge} product">${product.badge}</div>` : ''}
                    <button class="wishlist-btn ${isInWishlist ? 'active' : ''}" data-id="${product.id}" aria-label="${isInWishlist ? 'Remove from' : 'Add to'} wishlist">
                        <i class="fas fa-heart"></i>
                    </button>
                    <button class="quick-view-btn" data-id="${product.id}" aria-label="Quick view ${product.name}">
                        <i class="fas fa-eye"></i> Quick View
                    </button>
                    <div class="product-image" aria-hidden="true">
                        <i class="fas ${getProductIcon(product.type)}"></i>
                    </div>
                    <div class="product-info">
                        <span class="product-category">${product.category}</span>
                        <h3 class="product-title" id="product-title-${product.id}">${product.name}</h3>
                        <p class="product-description">${product.description}</p>
                        <div class="product-price">
                            ${product.originalPrice ? `<span class="original-price" aria-label="Original price ${formatCurrency(product.originalPrice)}">${formatCurrency(product.originalPrice)}</span>` : ''}
                            <span aria-label="Current price ${formatCurrency(product.price)}">${formatCurrency(product.price)}</span>
                        </div>
                        <div class="product-actions">
                            <button class="btn btn-primary btn-small add-to-cart" data-id="${product.id}" data-name="${product.name}" data-price="${product.price}" aria-label="Add ${product.name} to cart">
                                <i class="fas fa-cart-plus"></i>Add to Cart
                            </button>
                            <button class="btn btn-outline btn-small preview-btn" data-id="${product.id}" aria-label="Preview ${product.name}">
                                <i class="fas fa-eye"></i>Preview
                            </button>
                        </div>
                    </div>
                `;
                
                container.appendChild(productCard);
            });
            
            // Add event listeners to new buttons
            container.querySelectorAll('.add-to-cart').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    const name = this.getAttribute('data-name');
                    const price = this.getAttribute('data-price');
                    
                    addToCart(id, name, price);
                    
                    // Show confirmation
                    showToast('Product added to cart!', 'success');
                    
                    // Button animation
                    const originalText = this.innerHTML;
                    this.innerHTML = '<i class="fas fa-check"></i>Added!';
                    this.disabled = true;
                    this.setAttribute('aria-label', `${name} added to cart`);
                    
                    setTimeout(() => {
                        this.innerHTML = originalText;
                        this.disabled = false;
                        this.setAttribute('aria-label', `Add ${name} to cart`);
                    }, 1500);
                });
            });
            
            container.querySelectorAll('.preview-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    showProductPreview(id);
                });
            });
            
            container.querySelectorAll('.quick-view-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    showProductPreview(id);
                });
            });
            
            container.querySelectorAll('.wishlist-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    toggleWishlist(id, this);
                });
            });
        }

        function renderAdminProducts() {
            adminProductsTable.innerHTML = '';
            
            products.forEach(product => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${product.id}</td>
                    <td>${product.name}</td>
                    <td>${product.category}</td>
                    <td>${formatCurrency(product.price)}</td>
                    <td>${product.featured ? 'Featured' : 'Standard'}</td>
                    <td class="action-buttons">
                        <button class="btn-edit edit-product" data-id="${product.id}">
                            <i class="fas fa-edit"></i> Edit
                        </button>
                        <button class="btn-delete delete-product" data-id="${product.id}">
                            <i class="fas fa-trash"></i> Delete
                        </button>
                    </td>
                `;
                adminProductsTable.appendChild(row);
            });
            
            // Add event listeners to admin buttons
            document.querySelectorAll('.edit-product').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    editProduct(id);
                });
            });
            
            document.querySelectorAll('.delete-product').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    deleteProduct(id);
                });
            });
        }

        function renderUserPurchases() {
            userPurchasesContainer.innerHTML = '';
            
            if (!currentUser || !currentUser.purchases || currentUser.purchases.length === 0) {
                userPurchasesContainer.innerHTML = `
                    <div style="text-align: center; padding: 2rem;">
                        <i class="fas fa-shopping-bag" style="font-size: 3rem; color: var(--light-blue); margin-bottom: 1rem;"></i>
                        <p>You haven't purchased any products yet.</p>
                        <button class="btn btn-primary" id="browseProductsBtn" style="margin-top: 1rem;">
                            <i class="fas fa-shopping-cart"></i> Browse Products
                        </button>
                    </div>
                `;
                
                document.getElementById('browseProductsBtn').addEventListener('click', () => {
                    showPage('products');
                });
                return;
            }
            
            currentUser.purchases.forEach(purchase => {
                const product = products.find(p => p.id === purchase.productId);
                if (!product) return;
                
                const purchaseCard = document.createElement('div');
                purchaseCard.className = 'purchase-card';
                purchaseCard.innerHTML = `
                    <div class="purchase-image">
                        <i class="fas ${getProductIcon(product.type)}"></i>
                    </div>
                    <div class="purchase-details">
                        <h4>${product.name}</h4>
                        <p>Purchased on ${new Date(purchase.date).toLocaleDateString()}</p>
                        <div class="progress-bar">
                            <div class="progress-fill" style="width: ${purchase.progress || 0}%"></div>
                        </div>
                        <p>Progress: ${purchase.progress || 0}%</p>
                    </div>
                `;
                userPurchasesContainer.appendChild(purchaseCard);
            });
        }

        // Product filtering
        function filterProducts() {
            const category = categoryFilter.value;
            let filteredProducts = products;
            
            if (category) {
                filteredProducts = products.filter(product => product.category === category);
            }
            
            renderProducts(filteredProducts, allProductsContainer);
        }

        // Cart functionality
        function addToCart(id, name, price) {
            // Check if product is already in cart
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
            
            // Update localStorage
            localStorage.setItem('cart', JSON.stringify(cart));
            
            // Update UI
            updateCartUI();
        }

        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            localStorage.setItem('cart', JSON.stringify(cart));
            updateCartUI();
            renderCartItems();
        }

        function updateCartUI() {
            // Update cart count
            const totalItems = cart.reduce((total, item) => total + item.quantity, 0);
            cartCountElements.forEach(element => {
                element.textContent = totalItems;
            });
            
            // Update cart total
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            cartTotalElement.textContent = formatCurrency(total);
        }

        function renderCartItems() {
            cartItemsContainer.innerHTML = '';
            
            if (cart.length === 0) {
                cartItemsContainer.innerHTML = `
                    <div class="empty-cart">
                        <i class="fas fa-shopping-cart"></i>
                        <p>Your cart is empty</p>
                    </div>
                `;
                return;
            }
            
            cart.forEach(item => {
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                cartItem.innerHTML = `
                    <div class="cart-item-image">
                        <i class="fas ${getProductIcon(products.find(p => p.id === item.id)?.type || 'book')}"></i>
                    </div>
                    <div class="cart-item-details">
                        <div class="cart-item-title">${item.name}</div>
                        <div class="cart-item-price">${formatCurrency(item.price)} x ${item.quantity}</div>
                    </div>
                    <button class="cart-item-remove" data-id="${item.id}" aria-label="Remove ${item.name} from cart">
                        <i class="fas fa-trash"></i>
                    </button>
                `;
                cartItemsContainer.appendChild(cartItem);
            });
            
            // Add event listeners to remove buttons
            document.querySelectorAll('.cart-item-remove').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    removeFromCart(id);
                });
            });
        }

        // Product preview
        function showProductPreview(id) {
            const product = products.find(p => p.id === id);
            if (!product) return;
            
            const previewContent = document.getElementById('previewContent');
            previewContent.innerHTML = `
                <div class="preview-header">
                    <h3>${product.name}</h3>
                    <span class="product-category">${product.category}</span>
                </div>
                <div class="preview-body">
                    <div class="preview-cover">
                        <i class="fas ${getProductIcon(product.type)}"></i>
                    </div>
                    <div class="preview-details">
                        <p>${product.description}</p>
                        <div class="product-price">
                            ${product.originalPrice ? `<span class="original-price">${formatCurrency(product.originalPrice)}</span>` : ''}
                            <span>${formatCurrency(product.price)}</span>
                        </div>
                        <div class="preview-sample">
                            <h4>Sample Content</h4>
                            <p>${product.sample}</p>
                        </div>
                        <div class="preview-actions">
                            <button class="btn btn-primary add-to-cart-preview" data-id="${product.id}" data-name="${product.name}" data-price="${product.price}">
                                <i class="fas fa-cart-plus"></i>Add to Cart
                            </button>
                            <button class="btn btn-outline" id="closePreviewBtn">
                                <i class="fas fa-times"></i>Close
                            </button>
                        </div>
                    </div>
                </div>
            `;
            
            // Add event listener to add to cart button in preview
            previewContent.querySelector('.add-to-cart-preview').addEventListener('click', function() {
                const id = this.getAttribute('data-id');
                const name = this.getAttribute('data-name');
                const price = this.getAttribute('data-price');
                
                addToCart(id, name, price);
                showToast('Product added to cart!', 'success');
                closeModal(previewModal);
            });
            
            // Add event listener to close button
            previewContent.querySelector('#closePreviewBtn').addEventListener('click', () => {
                closeModal(previewModal);
            });
            
            openModal(previewModal);
        }

        // Wishlist functionality
        function toggleWishlist(id, button) {
            if (wishlist.includes(id)) {
                // Remove from wishlist
                wishlist = wishlist.filter(item => item !== id);
                button.classList.remove('active');
                button.setAttribute('aria-label', 'Add to wishlist');
                showToast('Removed from wishlist');
            } else {
                // Add to wishlist
                wishlist.push(id);
                button.classList.add('active');
                button.setAttribute('aria-label', 'Remove from wishlist');
                showToast('Added to wishlist');
            }
            
            localStorage.setItem('wishlist', JSON.stringify(wishlist));
        }

        // Authentication
        function handleLogin(e) {
            e.preventDefault();
            
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            const submitBtn = document.getElementById('loginSubmitBtn');
            const spinner = submitBtn.querySelector('.spinner');
            const btnText = submitBtn.querySelector('.btn-text');
            
            // Show loading state
            btnText.textContent = 'Logging in...';
            spinner.style.display = 'inline-block';
            submitBtn.disabled = true;
            
            // Simulate API call
            setTimeout(() => {
                // For demo purposes, accept any login with email and password
                if (email && password) {
                    const user = {
                        id: '1',
                        name: email.split('@')[0],
                        email: email,
                        role: email === 'admin@definitiveword.com' ? 'admin' : 'user',
                        purchases: []
                    };
                    
                    // If this is the admin user, add some demo purchases
                    if (user.role === 'admin') {
                        user.purchases = [
                            { productId: '1', date: new Date().toISOString(), progress: 75 },
                            { productId: '3', date: new Date().toISOString(), progress: 100 }
                        ];
                    }
                    
                    currentUser = user;
                    localStorage.setItem('currentUser', JSON.stringify(user));
                    
                    showUserMenu();
                    closeModal(loginModal);
                    showToast('Login successful!', 'success');
                    
                    // Reset form
                    document.getElementById('loginForm').reset();
                } else {
                    showToast('Please enter both email and password', 'error');
                }
                
                // Reset button
                btnText.textContent = 'Login';
                spinner.style.display = 'none';
                submitBtn.disabled = false;
            }, 1500);
        }

        function handleSignup(e) {
            e.preventDefault();
            
            const name = document.getElementById('signupName').value;
            const email = document.getElementById('signupEmail').value;
            const password = document.getElementById('signupPassword').value;
            const confirmPassword = document.getElementById('signupConfirmPassword').value;
            const submitBtn = document.getElementById('signupSubmitBtn');
            const spinner = submitBtn.querySelector('.spinner');
            const btnText = submitBtn.querySelector('.btn-text');
            
            // Validate passwords match
            if (password !== confirmPassword) {
                showToast('Passwords do not match', 'error');
                return;
            }
            
            // Show loading state
            btnText.textContent = 'Creating account...';
            spinner.style.display = 'inline-block';
            submitBtn.disabled = true;
            
            // Simulate API call
            setTimeout(() => {
                const user = {
                    id: Date.now().toString(),
                    name: name,
                    email: email,
                    role: 'user',
                    purchases: []
                };
                
                currentUser = user;
                localStorage.setItem('currentUser', JSON.stringify(user));
                
                showUserMenu();
                closeModal(signupModal);
                showToast('Account created successfully!', 'success');
                
                // Reset form
                document.getElementById('signupForm').reset();
                
                // Reset button
                btnText.textContent = 'Create Account';
                spinner.style.display = 'none';
                submitBtn.disabled = false;
            }, 1500);
        }

        function logout() {
            currentUser = null;
            localStorage.removeItem('currentUser');
            
            authButtons.style.display = 'flex';
            userMenu.style.display = 'none';
            
            showPage('home');
            showToast('You have been logged out', 'success');
        }

        function showUserMenu() {
            authButtons.style.display = 'none';
            userMenu.style.display = 'flex';
            
            userName.textContent = currentUser.name;
            dashboardUserName.textContent = currentUser.name;
            userAvatar.textContent = currentUser.name.charAt(0).toUpperCase();
            
            if (currentUser.role === 'admin') {
                document.getElementById('adminBtn').style.display = 'inline-block';
            }
        }

        // Product management (admin)
        function handleProductSubmit(e) {
            e.preventDefault();
            
            const id = document.getElementById('productId').value;
            const name = document.getElementById('productName').value;
            const description = document.getElementById('productDescription').value;
            const category = document.getElementById('productCategory').value;
            const type = document.getElementById('productType').value;
            const price = parseFloat(document.getElementById('productPrice').value);
            const originalPrice = document.getElementById('productOriginalPrice').value ? 
                parseFloat(document.getElementById('productOriginalPrice').value) : null;
            const badge = document.getElementById('productBadge').value;
            const featured = document.getElementById('productFeatured').checked;
            const sample = document.getElementById('productSample').value;
            
            const submitBtn = document.getElementById('productSubmitBtn');
            const spinner = submitBtn.querySelector('.spinner');
            const btnText = submitBtn.querySelector('.btn-text');
            
            // Show loading state
            btnText.textContent = 'Saving...';
            spinner.style.display = 'inline-block';
            submitBtn.disabled = true;
            
            // Simulate API call
            setTimeout(() => {
                if (id) {
                    // Update existing product
                    const index = products.findIndex(p => p.id === id);
                    if (index !== -1) {
                        products[index] = {
                            ...products[index],
                            name,
                            description,
                            category,
                            type,
                            price,
                            originalPrice,
                            badge: badge || null,
                            featured,
                            sample
                        };
                    }
                } else {
                    // Add new product
                    const newProduct = {
                        id: Date.now().toString(),
                        name,
                        description,
                        category,
                        type,
                        price,
                        originalPrice,
                        badge: badge || null,
                        featured,
                        sample
                    };
                    products.push(newProduct);
                }
                
                // Update UI
                renderFeaturedProducts();
                renderAllProducts();
                renderAdminProducts();
                
                closeModal(productModal);
                showToast(`Product ${id ? 'updated' : 'added'} successfully!`, 'success');
                
                // Reset form
                document.getElementById('productForm').reset();
                
                // Reset button
                btnText.textContent = 'Save Product';
                spinner.style.display = 'none';
                submitBtn.disabled = false;
            }, 1000);
        }

        function editProduct(id) {
            const product = products.find(p => p.id === id);
            if (!product) return;
            
            document.getElementById('productModalTitle').textContent = 'Edit Product';
            document.getElementById('productId').value = product.id;
            document.getElementById('productName').value = product.name;
            document.getElementById('productDescription').value = product.description;
            document.getElementById('productCategory').value = product.category;
            document.getElementById('productType').value = product.type;
            document.getElementById('productPrice').value = product.price;
            document.getElementById('productOriginalPrice').value = product.originalPrice || '';
            document.getElementById('productBadge').value = product.badge || '';
            document.getElementById('productFeatured').checked = product.featured;
            document.getElementById('productSample').value = product.sample;
            
            openModal(productModal);
        }

        function deleteProduct(id) {
            if (confirm('Are you sure you want to delete this product?')) {
                products = products.filter(p => p.id !== id);
                renderFeaturedProducts();
                renderAllProducts();
                renderAdminProducts();
                showToast('Product deleted successfully!', 'success');
            }
        }

        // Payment handling with Stripe
        function handlePayment(e) {
            e.preventDefault();
            
            if (!currentUser) {
                showToast('Please log in to complete your purchase', 'error');
                closeModal(checkoutModal);
                openModal(loginModal);
                return;
            }
            
            if (cart.length === 0) {
                showToast('Your cart is empty', 'error');
                return;
            }
            
            const submitBtn = document.getElementById('submitPaymentBtn');
            const spinner = submitBtn.querySelector('.spinner');
            const btnText = submitBtn.querySelector('.btn-text');
            
            // Show loading state
            btnText.textContent = 'Processing...';
            spinner.style.display = 'inline-block';
            submitBtn.disabled = true;
            
            // Get customer details
            const name = document.getElementById('checkoutName').value || currentUser.name;
            const email = document.getElementById('checkoutEmail').value || currentUser.email;
            
            // Calculate total amount in cents (Stripe requires amount in smallest currency unit)
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const amount = Math.round(total * 100); // Convert to cents
            
            // In a real application, you would create a payment intent on your server
            // For this demo, we'll simulate a successful payment
            setTimeout(() => {
                // Simulate successful payment
                processSuccessfulPayment();
                
                // Reset button
                btnText.textContent = 'Pay Now';
                spinner.style.display = 'none';
                submitBtn.disabled = false;
            }, 2000);
        }

        function processSuccessfulPayment() {
            // Add purchases to user account
            const purchaseDate = new Date().toISOString();
            cart.forEach(item => {
                currentUser.purchases.push({
                    productId: item.id,
                    date: purchaseDate,
                    progress: 0
                });
            });
            
            // Update user in localStorage
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            
            // Clear cart
            cart = [];
            localStorage.setItem('cart', JSON.stringify(cart));
            updateCartUI();
            renderCartItems();
            
            // Close modals
            closeModal(checkoutModal);
            
            // Show success message
            showToast('Payment successful! Your products are now available in your dashboard.', 'success');
            
            // Redirect to dashboard
            showPage('dashboard');
            showDashboardTab('purchases');
        }

        // Settings
        function handleSettingsUpdate(e) {
            e.preventDefault();
            
            if (!currentUser) return;
            
            const name = document.getElementById('settingsName').value;
            const email = document.getElementById('settingsEmail').value;
            const password = document.getElementById('settingsPassword').value;
            
            // Update user
            if (name) currentUser.name = name;
            if (email) currentUser.email = email;
            
            // In a real app, you would update the password securely
            
            // Save to localStorage
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            
            // Update UI
            showUserMenu();
            
            showToast('Settings updated successfully!', 'success');
            document.getElementById('settingsForm').reset();
        }

        // Utility functions
        function getProductIcon(type) {
            switch(type) {
                case 'ebook': return 'fa-book';
                case 'video': return 'fa-video';
                case 'audio': return 'fa-headphones';
                case 'pdf': return 'fa-file-pdf';
                default: return 'fa-book';
            }
        }

        function formatCurrency(amount) {
            const convertedAmount = amount * exchangeRates[currentCurrency];
            
            switch(currentCurrency) {
                case 'USD': return `$${convertedAmount.toFixed(2)}`;
                case 'EUR': return `€${convertedAmount.toFixed(2)}`;
                case 'GBP': return `£${convertedAmount.toFixed(2)}`;
                case 'ZAR': return `R ${convertedAmount.toFixed(2)}`;
                default: return `R ${amount.toFixed(2)}`;
            }
        }

        function updateCurrencyDisplay() {
            // Update all product prices
            renderFeaturedProducts();
            renderAllProducts();
            renderAdminProducts();
            
            // Update cart total
            updateCartUI();
            renderCartItems();
        }

        function openModal(modal) {
            modal.style.display = 'flex';
            document.body.style.overflow = 'hidden';
            
            // If opening cart modal, render cart items
            if (modal === cartModal) {
                renderCartItems();
            }
            
            // If opening checkout modal, prefill user info if logged in
            if (modal === checkoutModal && currentUser) {
                document.getElementById('checkoutName').value = currentUser.name;
                document.getElementById('checkoutEmail').value = currentUser.email;
            }
        }

        function closeModal(modal) {
            modal.style.display = 'none';
            document.body.style.overflow = 'auto';
        }

        function showToast(message, type = 'success') {
            const toastMessage = document.getElementById('toastMessage');
            const toastIcon = toast.querySelector('i');
            
            toastMessage.textContent = message;
            toast.className = 'toast';
            
            // Set icon based on type
            switch(type) {
                case 'success':
                    toastIcon.className = 'fas fa-check-circle';
                    toast.classList.add('success');
                    break;
                case 'error':
                    toastIcon.className = 'fas fa-exclamation-circle';
                    toast.classList.add('error');
                    break;
                case 'warning':
                    toastIcon.className = 'fas fa-exclamation-triangle';
                    toast.classList.add('warning');
                    break;
            }
            
            toast.classList.add('show');
            
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }

        function loadSavedPreferences() {
            // Load currency
            const savedCurrency = localStorage.getItem('currency');
            if (savedCurrency) {
                currentCurrency = savedCurrency;
                currencySelector.value = savedCurrency;
            }
            
            // Load text size
            const savedSize = localStorage.getItem('textSize');
            if (savedSize) {
                document.body.style.fontSize = savedSize + 'px';
            }
            
            // Load contrast mode
            if (localStorage.getItem('highContrast') === 'true') {
                document.body.classList.add('high-contrast');
            }
        }

        // Accessibility Features
        function initAccessibility() {
            // Text size controls
            document.getElementById('textSmaller').addEventListener('click', () => changeTextSize(-1));
            document.getElementById('textNormal').addEventListener('click', () => changeTextSize(0));
            document.getElementById('textLarger').addEventListener('click', () => changeTextSize(1));

            // Contrast controls
            document.getElementById('contrastNormal').addEventListener('click', () => setContrast('normal'));
            document.getElementById('contrastHigh').addEventListener('click', () => setContrast('high'));

            // Reading aids
            document.getElementById('readingGuide').addEventListener('click', toggleReadingGuide);
            document.getElementById('dyslexiaFont').addEventListener('click', toggleDyslexiaFont);

            // Toggle accessibility controls
            document.getElementById('accessibilityToggle').addEventListener('click', toggleAccessibilityControls);
            document.getElementById('keyboardToggle').addEventListener('click', toggleKeyboardShortcuts);

            // Keyboard shortcuts
            document.addEventListener('keydown', handleKeyboardShortcuts);
        }

        function changeTextSize(direction) {
            const currentSize = parseFloat(getComputedStyle(document.body).fontSize);
            let newSize;

            if (direction === 0) {
                newSize = 16; // Reset to default
            } else {
                newSize = currentSize + (direction * 2);
                newSize = Math.max(12, Math.min(24, newSize)); // Limit between 12px and 24px
            }

            document.body.style.fontSize = newSize + 'px';
            localStorage.setItem('textSize', newSize);
        }

        function setContrast(mode) {
            if (mode === 'high') {
                document.body.classList.add('high-contrast');
                localStorage.setItem('highContrast', 'true');
            } else {
                document.body.classList.remove('high-contrast');
                localStorage.setItem('highContrast', 'false');
            }
        }

        function toggleReadingGuide() {
            document.body.classList.toggle('reading-guide');
            showToast('Reading guide ' + (document.body.classList.contains('reading-guide') ? 'enabled' : 'disabled'));
        }

        function toggleDyslexiaFont() {
            document.body.classList.toggle('dyslexia-font');
            showToast('Dyslexia-friendly font ' + (document.body.classList.contains('dyslexia-font') ? 'enabled' : 'disabled'));
        }

        function toggleAccessibilityControls() {
            document.getElementById('accessibilityControls').classList.toggle('show');
        }

        function toggleKeyboardShortcuts() {
            document.getElementById('keyboardShortcuts').classList.toggle('show');
        }

        function handleKeyboardShortcuts(e) {
            // Don't trigger if user is typing in an input
            if (e.target.tagName === 'INPUT' || e.target.tagName === 'TEXTAREA') return;

            switch(e.key) {
                case '/':
                    e.preventDefault();
                    showToast('Press C for cart, A for accessibility controls');
                    break;
                case 'c':
                case 'C':
                    e.preventDefault();
                    openModal(cartModal);
                    break;
                case 'a':
                case 'A':
                    e.preventDefault();
                    toggleAccessibilityControls();
                    break;
                case 'p':
                case 'P':
                    e.preventDefault();
                    showPage('products');
                    break;
                case 'Escape':
                    closeAllModals();
                    break;
            }
        }

        function closeAllModals() {
            document.querySelectorAll('.modal').forEach(modal => {
                closeModal(modal);
            });
        }

        // Initialize the application when DOM is loaded
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
