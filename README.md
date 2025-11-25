<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Your Destiny Has Been Written</title>
    <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
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
            --success: #10B981;
            --warning: #F59E0B;
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
            overflow-x: hidden;
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
            text-decoration: none;
            color: var(--white);
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
            position: relative;
        }

        nav a:hover {
            color: var(--gold);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gold);
            transition: width 0.3s;
        }

        nav a:hover::after {
            width: 100%;
        }

        .auth-buttons {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .user-menu {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--gold);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: var(--prophetic-blue);
        }

        .btn {
            padding: 0.6rem 1.2rem;
            border-radius: 4px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
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
            transform: translateY(-2px);
        }

        .cart-icon {
            position: relative;
            margin-left: 1rem;
            font-size: 1.5rem;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .cart-icon:hover {
            transform: scale(1.1);
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
            font-weight: bold;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(30, 58, 138, 0.9), rgba(15, 27, 58, 0.9)), url('https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: var(--white);
            padding: 5rem 0;
            text-align: center;
            position: relative;
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
            font-weight: 700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
        }

        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .btn-gold {
            background: var(--gold);
            color: var(--prophetic-blue);
            font-weight: 700;
        }

        .btn-gold:hover {
            background: #c19b2e;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(212, 175, 55, 0.3);
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
            border-radius: 2px;
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
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
        }

        .product-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: var(--red);
            color: white;
            padding: 0.3rem 0.6rem;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: bold;
            z-index: 2;
        }

        .product-image {
            height: 200px;
            background-color: var(--light-blue);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--prophetic-blue);
            font-size: 3rem;
            position: relative;
            overflow: hidden;
        }

        .product-image::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, rgba(30, 58, 138, 0.1), rgba(212, 175, 55, 0.1));
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
            display: block;
        }

        .product-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--dark-blue);
            line-height: 1.3;
        }

        .product-description {
            color: var(--dark-gray);
            margin-bottom: 1rem;
            font-size: 0.95rem;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }

        .product-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--prophetic-blue);
            margin-bottom: 1rem;
        }

        .product-price .original-price {
            font-size: 1rem;
            color: var(--dark-gray);
            text-decoration: line-through;
            margin-right: 0.5rem;
        }

        .product-actions {
            display: flex;
            justify-content: space-between;
            gap: 0.5rem;
        }

        .btn-small {
            padding: 0.5rem 1rem;
            font-size: 0.9rem;
            flex: 1;
        }

        /* Dashboard Styles */
        .dashboard {
            padding: 2rem 0;
            background: var(--gray);
            min-height: 60vh;
        }

        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
        }

        .dashboard-grid {
            display: grid;
            grid-template-columns: 250px 1fr;
            gap: 2rem;
        }

        .dashboard-sidebar {
            background: var(--white);
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
        }

        .dashboard-nav {
            list-style: none;
        }

        .dashboard-nav li {
            margin-bottom: 0.5rem;
        }

        .dashboard-nav a {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.8rem 1rem;
            color: var(--dark-blue);
            text-decoration: none;
            border-radius: 4px;
            transition: all 0.3s;
        }

        .dashboard-nav a:hover, .dashboard-nav a.active {
            background: var(--prophetic-blue);
            color: var(--white);
        }

        .dashboard-content {
            background: var(--white);
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
        }

        .purchases-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .purchase-card {
            border: 1px solid #eee;
            border-radius: 8px;
            padding: 1.5rem;
            display: flex;
            gap: 1rem;
        }

        .purchase-image {
            width: 80px;
            height: 80px;
            background: var(--light-blue);
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 4px;
            color: var(--prophetic-blue);
            font-size: 1.5rem;
            flex-shrink: 0;
        }

        .purchase-details {
            flex: 1;
        }

        .progress-bar {
            height: 8px;
            background: var(--gray);
            border-radius: 4px;
            overflow: hidden;
            margin-top: 0.5rem;
        }

        .progress-fill {
            height: 100%;
            background: var(--gold);
            border-radius: 4px;
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
            transition: transform 0.3s, box-shadow 0.3s;
            position: relative;
            overflow: hidden;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gold);
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
            position: relative;
            padding-bottom: 0.5rem;
        }

        .footer-column h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 2px;
            background: var(--gold);
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
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .footer-column a:hover {
            color: var(--gold);
            transform: translateX(5px);
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
            transition: all 0.3s;
        }

        .social-icons a:hover {
            background: var(--gold);
            transform: translateY(-3px);
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
            padding: 20px;
            animation: fadeIn 0.3s;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal-content {
            background: var(--white);
            width: 90%;
            max-width: 500px;
            border-radius: 8px;
            padding: 2rem;
            position: relative;
            animation: slideIn 0.3s;
            max-height: 90vh;
            overflow-y: auto;
        }

        @keyframes slideIn {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-gray);
            transition: color 0.3s;
            background: none;
            border: none;
            width: 30px;
            height: 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }

        .close-modal:hover {
            color: var(--red);
            background: var(--gray);
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
            color: var(--dark-blue);
        }

        .form-control {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
            transition: border-color 0.3s, box-shadow 0.3s;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--prophetic-blue);
            box-shadow: 0 0 0 3px rgba(30, 58, 138, 0.1);
        }

        .form-footer {
            text-align: center;
            margin-top: 1.5rem;
        }

        .form-footer a {
            color: var(--prophetic-blue);
            text-decoration: none;
            font-weight: 500;
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
            border: 1px solid #eee;
            border-radius: 4px;
            padding: 1rem;
        }

        .cart-item {
            display: flex;
            align-items: center;
            padding: 1rem 0;
            border-bottom: 1px solid #eee;
        }

        .cart-item:last-child {
            border-bottom: none;
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
            flex-shrink: 0;
        }

        .cart-item-details {
            flex: 1;
        }

        .cart-item-title {
            font-weight: 600;
            margin-bottom: 0.3rem;
            color: var(--dark-blue);
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
            transition: transform 0.3s;
            padding: 0.5rem;
            border-radius: 4px;
        }

        .cart-item-remove:hover {
            transform: scale(1.1);
            background: rgba(185, 28, 28, 0.1);
        }

        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.3rem;
            font-weight: 700;
            padding: 1rem 0;
            border-top: 2px solid #eee;
            color: var(--prophetic-blue);
        }

        .empty-cart {
            text-align: center;
            padding: 2rem;
            color: var(--dark-gray);
        }

        .empty-cart i {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--light-blue);
        }

        /* Toast Notification */
        .toast {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--prophetic-blue);
            color: white;
            padding: 1rem 1.5rem;
            border-radius: 4px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            z-index: 1001;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transform: translateX(150%);
            transition: transform 0.3s;
        }

        .toast.show {
            transform: translateX(0);
        }

        .toast.success {
            background: var(--success);
        }

        .toast.error {
            background: var(--red);
        }

        .toast.warning {
            background: var(--warning);
        }

        /* Loading Spinner */
        .spinner {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: #fff;
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                gap: 1rem;
                flex-wrap: wrap;
                justify-content: center;
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

            .product-actions {
                flex-direction: column;
            }

            .cart-item {
                flex-direction: column;
                text-align: center;
                gap: 1rem;
            }

            .cart-item-image {
                margin-right: 0;
            }

            .dashboard-grid {
                grid-template-columns: 1fr;
            }

            .dashboard-sidebar {
                order: 2;
            }

            .dashboard-content {
                order: 1;
            }
        }

        @media (max-width: 480px) {
            .hero h2 {
                font-size: 1.8rem;
            }

            .section-title {
                font-size: 1.8rem;
            }

            .modal-content {
                padding: 1.5rem;
            }
        }
    </style>
</head>
<body>
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
                    <button class="btn btn-outline" id="loginBtn">
                        <i class="fas fa-sign-in-alt"></i>Login
                    </button>
                    <button class="btn btn-primary" id="signupBtn">
                        <i class="fas fa-user-plus"></i>Sign Up
                    </button>
                    <div class="cart-icon" id="cartIcon">
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
                    <button class="btn btn-outline btn-small" id="logoutBtn">
                        <i class="fas fa-sign-out-alt"></i>Logout
                    </button>
                    <div class="cart-icon" id="cartIconLoggedIn">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </div>
                </div>
            </div>
        </div>
    </header>

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
                <h2 class="section-title">Our Products</h2>
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
                <span id="cartTotal">$0.00</span>
            </div>
            <button class="btn btn-primary" style="width: 100%;" id="checkoutBtn">
                <i class="fas fa-lock"></i>Proceed to Checkout
            </button>
        </div>
    </div>

    <!-- Toast Notification -->
    <div class="toast" id="toast">
        <i class="fas fa-check-circle"></i>
        <span id="toastMessage">Product added to cart!</span>
    </div>

    <script>
        // Supabase Configuration
        const SUPABASE_URL = 'https://your-project.supabase.co';
        const SUPABASE_ANON_KEY = 'your-anon-key';
        
        // Initialize Supabase client
        const supabase = window.supabase.createClient(SUPABASE_URL, SUPABASE_ANON_KEY);

        // Sample Data (In a real app, this would come from Supabase)
        const sampleProducts = [
            {
                id: 1,
                name: "The Path to Enlightenment",
                description: "A comprehensive guide to spiritual growth and personal transformation.",
                price: 24.99,
                originalPrice: 29.99,
                category: "Ebook",
                type: "ebook",
                badge: "Bestseller",
                featured: true
            },
            {
                id: 2,
                name: "Manifesting Your Destiny",
                description: "A 5-part video series on creating the life you desire through manifestation.",
                price: 49.99,
                category: "Workshop",
                type: "video",
                badge: "New",
                featured: true
            },
            {
                id: 3,
                name: "Daily Reflection Journal",
                description: "Printable journal with prompts for daily self-reflection and growth tracking.",
                price: 12.99,
                category: "Resource",
                type: "pdf",
                featured: true
            },
            {
                id: 4,
                name: "Meditation Series",
                description: "Guided meditation sessions for stress relief, focus, and inner peace.",
                price: 19.99,
                category: "Audio",
                type: "audio",
                badge: "Popular",
                featured: true
            },
            {
                id: 5,
                name: "Financial Freedom Blueprint",
                description: "Step-by-step guide to achieving financial independence and security.",
                price: 34.99,
                category: "Ebook",
                type: "ebook",
                featured: false
            },
            {
                id: 6,
                name: "Relationship Mastery",
                description: "Workshop on building healthy, fulfilling relationships in all areas of life.",
                price: 39.99,
                category: "Workshop",
                type: "video",
                featured: false
            }
        ];

        // Sample User Purchases
        const samplePurchases = [
            {
                id: 1,
                productId: 1,
                productName: "The Path to Enlightenment",
                purchaseDate: "2023-10-15",
                price: 24.99,
                progress: 75
            },
            {
                id: 2,
                productId: 4,
                productName: "Meditation Series",
                purchaseDate: "2023-11-02",
                price: 19.99,
                progress: 30
            }
        ];

        // DOM Elements
        const loginBtn = document.getElementById('loginBtn');
        const signupBtn = document.getElementById('signupBtn');
        const cartIcon = document.getElementById('cartIcon');
        const cartIconLoggedIn = document.getElementById('cartIconLoggedIn');
        const loginModal = document.getElementById('loginModal');
        const signupModal = document.getElementById('signupModal');
        const cartModal = document.getElementById('cartModal');
        const closeModalButtons = document.querySelectorAll('.close-modal');
        const switchToSignup = document.getElementById('switchToSignup');
        const switchToLogin = document.getElementById('switchToLogin');
        const cartItemsContainer = document.getElementById('cartItems');
        const cartTotalElement = document.getElementById('cartTotal');
        const cartCount = document.querySelector('.cart-count');
        const checkoutBtn = document.getElementById('checkoutBtn');
        const loginForm = document.getElementById('loginForm');
        const signupForm = document.getElementById('signupForm');
        const newsletterForm = document.getElementById('newsletterForm');
        const loginSubmitBtn = document.getElementById('loginSubmitBtn');
        const signupSubmitBtn = document.getElementById('signupSubmitBtn');
        const toast = document.getElementById('toast');
        const toastMessage = document.getElementById('toastMessage');
        const authButtons = document.getElementById('authButtons');
        const userMenu = document.getElementById('userMenu');
        const userAvatar = document.getElementById('userAvatar');
        const userName = document.getElementById('userName');
        const dashboardBtn = document.getElementById('dashboardBtn');
        const logoutBtn = document.getElementById('logoutBtn');
        const exploreProductsBtn = document.getElementById('exploreProductsBtn');
        const joinCommunityBtn = document.getElementById('joinCommunityBtn');
        const featuredProductsContainer = document.getElementById('featuredProducts');
        const allProductsContainer = document.getElementById('allProducts');
        const userPurchasesContainer = document.getElementById('userPurchases');
        const navLinks = document.querySelectorAll('.nav-link');
        const dashboardNavLinks = document.querySelectorAll('.dashboard-nav-link');
        const dashboardTabs = document.querySelectorAll('.dashboard-tab');
        const homePage = document.getElementById('homePage');
        const productsPage = document.getElementById('productsPage');
        const dashboardPage = document.getElementById('dashboardPage');
        const aboutPage = document.getElementById('aboutPage');
        const dashboardUserName = document.getElementById('dashboardUserName');
        const settingsForm = document.getElementById('settingsForm');

        // App State
        let currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;
        let cart = JSON.parse(localStorage.getItem('cart')) || [];

        // Initialize the application
        function init() {
            updateCartUI();
            setupEventListeners();
            loadProducts();
            checkAuthState();
        }

        // Setup all event listeners
        function setupEventListeners() {
            // Modal Events
            loginBtn.addEventListener('click', () => openModal(loginModal));
            signupBtn.addEventListener('click', () => openModal(signupModal));
            cartIcon.addEventListener('click', () => openModal(cartModal));
            cartIconLoggedIn.addEventListener('click', () => openModal(cartModal));

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

            // Checkout button
            checkoutBtn.addEventListener('click', handleCheckout);

            // Form submissions
            loginForm.addEventListener('submit', handleLogin);
            signupForm.addEventListener('submit', handleSignup);
            newsletterForm.addEventListener('submit', handleNewsletter);
            settingsForm.addEventListener('submit', handleSettingsUpdate);

            // Auth buttons
            dashboardBtn.addEventListener('click', () => showPage('dashboard'));
            logoutBtn.addEventListener('click', handleLogout);

            // Navigation
            exploreProductsBtn.addEventListener('click', () => showPage('products'));
            joinCommunityBtn.addEventListener('click', () => {
                if (currentUser) {
                    showPage('dashboard');
                    switchDashboardTab('community');
                } else {
                    openModal(signupModal);
                }
            });

            navLinks.forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const page = e.target.getAttribute('data-page');
                    showPage(page);
                });
            });

            dashboardNavLinks.forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const tab = e.target.getAttribute('data-tab');
                    switchDashboardTab(tab);
                });
            });
        }

        // Check authentication state and update UI
        function checkAuthState() {
            if (currentUser) {
                authButtons.style.display = 'none';
                userMenu.style.display = 'flex';
                userName.textContent = currentUser.name;
                dashboardUserName.textContent = currentUser.name;
                userAvatar.textContent = currentUser.name.charAt(0).toUpperCase();
                loadUserPurchases();
            } else {
                authButtons.style.display = 'flex';
                userMenu.style.display = 'none';
            }
        }

        // Show specific page
        function showPage(page) {
            // Hide all pages
            homePage.style.display = 'none';
            productsPage.style.display = 'none';
            dashboardPage.style.display = 'none';
            aboutPage.style.display = 'none';

            // Show selected page
            switch(page) {
                case 'home':
                    homePage.style.display = 'block';
                    break;
                case 'products':
                    productsPage.style.display = 'block';
                    break;
                case 'dashboard':
                    if (currentUser) {
                        dashboardPage.style.display = 'block';
                    } else {
                        openModal(loginModal);
                        return;
                    }
                    break;
                case 'about':
                    aboutPage.style.display = 'block';
                    break;
            }

            // Scroll to top
            window.scrollTo(0, 0);
        }

        // Switch dashboard tabs
        function switchDashboardTab(tab) {
            // Remove active class from all nav links
            dashboardNavLinks.forEach(link => {
                link.classList.remove('active');
            });

            // Hide all tabs
            dashboardTabs.forEach(tab => {
                tab.style.display = 'none';
            });

            // Activate selected tab
            document.querySelector(`.dashboard-nav-link[data-tab="${tab}"]`).classList.add('active');
            document.getElementById(`${tab}Tab`).style.display = 'block';
        }

        // Load products from Supabase (using sample data for demo)
        function loadProducts() {
            // In a real app, this would be:
            // const { data: products, error } = await supabase.from('products').select('*');
            
            const featuredProducts = sampleProducts.filter(product => product.featured);
            const allProducts = sampleProducts;
            
            renderProducts(featuredProducts, featuredProductsContainer);
            renderProducts(allProducts, allProductsContainer);
        }

        // Render products to the DOM
        function renderProducts(products, container) {
            container.innerHTML = '';
            
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                
                productCard.innerHTML = `
                    ${product.badge ? `<div class="product-badge">${product.badge}</div>` : ''}
                    <div class="product-image">
                        <i class="fas ${getProductIcon(product.type)}"></i>
                    </div>
                    <div class="product-info">
                        <span class="product-category">${product.category}</span>
                        <h3 class="product-title">${product.name}</h3>
                        <p class="product-description">${product.description}</p>
                        <div class="product-price">
                            ${product.originalPrice ? `<span class="original-price">$${product.originalPrice.toFixed(2)}</span>` : ''}
                            $${product.price.toFixed(2)}
                        </div>
                        <div class="product-actions">
                            <button class="btn btn-primary btn-small add-to-cart" data-id="${product.id}" data-name="${product.name}" data-price="${product.price}">
                                <i class="fas fa-cart-plus"></i>Add to Cart
                            </button>
                            <button class="btn btn-outline btn-small preview-btn" data-id="${product.id}">
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
                    
                    setTimeout(() => {
                        this.innerHTML = originalText;
                        this.disabled = false;
                    }, 1500);
                });
            });
            
            container.querySelectorAll('.preview-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    showToast('Preview feature coming soon!', 'success');
                });
            });
        }

        // Get appropriate icon for product type
        function getProductIcon(type) {
            switch(type) {
                case 'ebook': return 'fa-book';
                case 'video': return 'fa-video';
                case 'audio': return 'fa-headphones';
                case 'pdf': return 'fa-file-pdf';
                default: return 'fa-file';
            }
        }

        // Load user purchases (using sample data for demo)
        function loadUserPurchases() {
            // In a real app, this would be:
            // const { data: purchases, error } = await supabase
            //   .from('purchases')
            //   .select(`
            //     *,
            //     products (*)
            //   `)
            //   .eq('user_id', currentUser.id);
            
            userPurchasesContainer.innerHTML = '';
            
            if (samplePurchases.length === 0) {
                userPurchasesContainer.innerHTML = '<p>You haven\'t purchased any products yet.</p>';
                return;
            }
            
            samplePurchases.forEach(purchase => {
                const purchaseCard = document.createElement('div');
                purchaseCard.className = 'purchase-card';
                
                purchaseCard.innerHTML = `
                    <div class="purchase-image">
                        <i class="fas fa-book"></i>
                    </div>
                    <div class="purchase-details">
                        <h4>${purchase.productName}</h4>
                        <p>Purchased on: ${new Date(purchase.purchaseDate).toLocaleDateString()}</p>
                        <p>Price: $${purchase.price.toFixed(2)}</p>
                        <div class="progress-bar">
                            <div class="progress-fill" style="width: ${purchase.progress}%"></div>
                        </div>
                        <small>Progress: ${purchase.progress}%</small>
                    </div>
                `;
                
                userPurchasesContainer.appendChild(purchaseCard);
            });
        }

        // Modal Functions
        function openModal(modal) {
            modal.style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }

        function closeModal(modal) {
            modal.style.display = 'none';
            document.body.style.overflow = 'auto';
        }

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
            saveCartToStorage();
        }

        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            updateCartUI();
            saveCartToStorage();
        }

        function updateCartUI() {
            // Update cart count
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            document.querySelectorAll('.cart-count').forEach(el => {
                el.textContent = totalItems;
            });
            
            // Update cart items
            cartItemsContainer.innerHTML = '';
            
            if (cart.length === 0) {
                cartItemsContainer.innerHTML = `
                    <div class="empty-cart">
                        <i class="fas fa-shopping-cart"></i>
                        <p>Your cart is empty</p>
                    </div>
                `;
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
                    showToast('Item removed from cart', 'success');
                });
            });
        }

        function saveCartToStorage() {
            localStorage.setItem('cart', JSON.stringify(cart));
        }

        // Toast Notification
        function showToast(message, type = 'success') {
            toastMessage.textContent = message;
            toast.className = `toast ${type} show`;
            
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }

        // Form Handlers
        async function handleLogin(e) {
            e.preventDefault();
            
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            
            // Show loading state
            const btnText = loginSubmitBtn.querySelector('.btn-text');
            const spinner = loginSubmitBtn.querySelector('.spinner');
            btnText.style.display = 'none';
            spinner.style.display = 'inline-block';
            loginSubmitBtn.disabled = true;
            
            try {
                // In a real app, this would be:
                // const { data, error } = await supabase.auth.signInWithPassword({
                //   email,
                //   password,
                // });
                
                // For demo purposes, we'll simulate a successful login
                await new Promise(resolve => setTimeout(resolve, 1500));
                
                // Simulate user data
                currentUser = {
                    id: 'user123',
                    name: email.split('@')[0],
                    email: email
                };
                
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                
                showToast('Login successful!', 'success');
                closeModal(loginModal);
                loginForm.reset();
                checkAuthState();
                
            } catch (error) {
                showToast('Login failed. Please check your credentials.', 'error');
            } finally {
                // Reset button state
                btnText.style.display = 'inline';
                spinner.style.display = 'none';
                loginSubmitBtn.disabled = false;
            }
        }

        async function handleSignup(e) {
            e.preventDefault();
            
            const name = document.getElementById('signupName').value;
            const email = document.getElementById('signupEmail').value;
            const password = document.getElementById('signupPassword').value;
            const confirmPassword = document.getElementById('signupConfirmPassword').value;
            
            if (password !== confirmPassword) {
                showToast('Passwords do not match!', 'error');
                return;
            }
            
            // Show loading state
            const btnText = signupSubmitBtn.querySelector('.btn-text');
            const spinner = signupSubmitBtn.querySelector('.spinner');
            btnText.style.display = 'none';
            spinner.style.display = 'inline-block';
            signupSubmitBtn.disabled = true;
            
            try {
                // In a real app, this would be:
                // const { data, error } = await supabase.auth.signUp({
                //   email,
                //   password,
                //   options: {
                //     data: {
                //       name: name
                //     }
                //   }
                // });
                
                // For demo purposes, we'll simulate a successful signup
                await new Promise(resolve => setTimeout(resolve, 1500));
                
                // Simulate user data
                currentUser = {
                    id: 'user123',
                    name: name,
                    email: email
                };
                
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                
                showToast('Account created successfully!', 'success');
                closeModal(signupModal);
                signupForm.reset();
                checkAuthState();
                
            } catch (error) {
                showToast('Signup failed. Please try again.', 'error');
            } finally {
                // Reset button state
                btnText.style.display = 'inline';
                spinner.style.display = 'none';
                signupSubmitBtn.disabled = false;
            }
        }

        function handleLogout() {
            // In a real app, this would be:
            // await supabase.auth.signOut();
            
            currentUser = null;
            localStorage.removeItem('currentUser');
            showToast('Logged out successfully', 'success');
            checkAuthState();
            showPage('home');
        }

        async function handleCheckout() {
            if (cart.length === 0) {
                showToast('Your cart is empty!', 'error');
                return;
            }
            
            if (!currentUser) {
                showToast('Please log in to checkout', 'warning');
                openModal(loginModal);
                return;
            }
            
            // Simulate checkout process
            checkoutBtn.disabled = true;
            checkoutBtn.innerHTML = '<div class="spinner"></div> Processing...';
            
            try {
                // In a real app, this would integrate with Stripe
                // const { data, error } = await supabase
                //   .from('orders')
                //   .insert({
                //     user_id: currentUser.id,
                //     items: cart,
                //     total: cart.reduce((sum, item) => sum + (item.price * item.quantity), 0)
                //   });
                
                await new Promise(resolve => setTimeout(resolve, 2000));
                
                showToast('Order placed successfully!', 'success');
                cart = [];
                updateCartUI();
                closeModal(cartModal);
                
                // In a real app, we would redirect to order confirmation or dashboard
                showPage('dashboard');
                
            } catch (error) {
                showToast('Checkout failed. Please try again.', 'error');
            } finally {
                checkoutBtn.disabled = false;
                checkoutBtn.innerHTML = '<i class="fas fa-lock"></i>Proceed to Checkout';
            }
        }

        function handleNewsletter(e) {
            e.preventDefault();
            const email = e.target.querySelector('input[type="email"]').value;
            
            // In a real app, this would save to Supabase
            // await supabase.from('newsletter_subscriptions').insert({ email });
            
            showToast('Thank you for subscribing!', 'success');
            e.target.reset();
        }

        function handleSettingsUpdate(e) {
            e.preventDefault();
            const name = document.getElementById('settingsName').value;
            const email = document.getElementById('settingsEmail').value;
            
            // In a real app, this would update the user in Supabase
            // await supabase.auth.updateUser({
            //   email: email,
            //   data: { name: name }
            // });
            
            if (currentUser) {
                currentUser.name = name;
                currentUser.email = email;
                localStorage.setItem('currentUser', JSON.stringify(currentUser));
                checkAuthState();
            }
            
            showToast('Settings updated successfully!', 'success');
        }

        // Initialize the app
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
