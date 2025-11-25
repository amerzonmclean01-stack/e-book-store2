<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Your Destiny Has Been Written</title>
    <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
    <script src="https://js.stripe.com/v3/"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --white: #FFFFFF;
            --gold: #D4AF37;
            --gold-light: #f4e8c1;
            --prophetic-blue: #1E3A8A;
            --prophetic-blue-light: #3b5998;
            --red: #B91C1C;
            --light-blue: #E0F2FE;
            --dark-blue: #0F1B3A;
            --gray: #F3F4F6;
            --dark-gray: #6B7280;
            --success: #10B981;
            --warning: #F59E0B;
            --focus-ring: 0 0 0 3px rgba(212, 175, 55, 0.5);
            --shadow-sm: 0 2px 4px rgba(0,0,0,0.1);
            --shadow-md: 0 4px 12px rgba(0,0,0,0.15);
            --shadow-lg: 0 8px 30px rgba(0,0,0,0.2);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-slow: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--white);
            color: var(--dark-blue);
            line-height: 1.6;
            overflow-x: hidden;
            font-size: 16px;
            scroll-behavior: smooth;
        }

        /* Enhanced Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes fadeInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }

        @keyframes shimmer {
            0% {
                background-position: -468px 0;
            }
            100% {
                background-position: 468px 0;
            }
        }

        @keyframes bounceIn {
            0% {
                opacity: 0;
                transform: scale(0.3);
            }
            50% {
                opacity: 1;
                transform: scale(1.05);
            }
            70% {
                transform: scale(0.9);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        /* Loading Animation */
        .loading-shimmer {
            animation: shimmer 1.5s infinite linear;
            background: linear-gradient(to right, #f6f7f8 8%, #edeef1 18%, #f6f7f8 33%);
            background-size: 800px 104px;
        }

        /* Enhanced Header with Sticky Animation */
        header {
            background: linear-gradient(135deg, var(--prophetic-blue), var(--dark-blue));
            color: var(--white);
            padding: 1rem 0;
            box-shadow: var(--shadow-md);
            position: sticky;
            top: 0;
            z-index: 1000;
            transition: var(--transition);
        }

        header.scrolled {
            padding: 0.5rem 0;
            backdrop-filter: blur(10px);
            background: rgba(30, 58, 138, 0.95);
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            text-decoration: none;
            color: var(--white);
            transition: var(--transition);
        }

        .logo:hover {
            transform: translateY(-2px);
        }

        .logo i {
            color: var(--gold);
            font-size: 2rem;
            transition: var(--transition);
        }

        .logo:hover i {
            transform: rotate(-10deg) scale(1.1);
        }

        /* Enhanced Navigation */
        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
            padding: 0.5rem;
            border-radius: 4px;
            overflow: hidden;
        }

        nav a::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gold);
            transition: var(--transition);
        }

        nav a:hover::before, nav a:focus::before {
            width: 100%;
        }

        nav a:hover, nav a:focus {
            color: var(--gold);
            transform: translateY(-2px);
        }

        /* Enhanced Buttons */
        .btn {
            padding: 0.8rem 1.5rem;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            border: none;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            font-size: 1rem;
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: var(--transition-slow);
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-lg);
        }

        .btn:active {
            transform: translateY(-1px);
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--red), #9c1a1a);
            color: var(--white);
        }

        .btn-primary:hover {
            background: linear-gradient(135deg, #9c1a1a, var(--red));
        }

        .btn-gold {
            background: linear-gradient(135deg, var(--gold), #b8941f);
            color: var(--prophetic-blue);
            font-weight: 700;
        }

        .btn-gold:hover {
            background: linear-gradient(135deg, #b8941f, var(--gold));
            transform: translateY(-3px) scale(1.05);
        }

        /* Enhanced Hero Section */
        .hero {
            background: linear-gradient(rgba(30, 58, 138, 0.9), rgba(15, 27, 58, 0.9)), url('https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: var(--white);
            padding: 8rem 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at center, transparent 0%, rgba(0,0,0,0.3) 100%);
        }

        .hero-content {
            position: relative;
            z-index: 2;
            animation: fadeInUp 1s ease-out;
        }

        .hero h2 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            font-weight: 700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            font-family: 'Playfair Display', serif;
            animation: fadeInUp 0.8s ease-out 0.2s both;
        }

        .hero p {
            font-size: 1.3rem;
            max-width: 700px;
            margin: 0 auto 3rem;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
            animation: fadeInUp 0.8s ease-out 0.4s both;
        }

        .hero-buttons {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 2rem;
            flex-wrap: wrap;
            animation: fadeInUp 0.8s ease-out 0.6s both;
        }

        /* Floating Elements */
        .floating-element {
            animation: float 3s ease-in-out infinite;
        }

        /* Enhanced Product Cards */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        .product-card {
            background: var(--white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
            position: relative;
            border: 1px solid transparent;
            animation: fadeInUp 0.6s ease-out;
        }

        .product-card:hover, .product-card:focus-within {
            transform: translateY(-8px) scale(1.02);
            box-shadow: var(--shadow-lg);
            border-color: var(--gold);
        }

        .product-image {
            height: 220px;
            background: linear-gradient(135deg, var(--light-blue), var(--prophetic-blue-light));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--prophetic-blue);
            font-size: 3.5rem;
            position: relative;
            overflow: hidden;
            transition: var(--transition);
        }

        .product-card:hover .product-image {
            transform: scale(1.05);
        }

        .product-image::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, rgba(30, 58, 138, 0.1), rgba(212, 175, 55, 0.1));
            opacity: 0;
            transition: var(--transition);
        }

        .product-card:hover .product-image::after {
            opacity: 1;
        }

        .product-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background: var(--red);
            color: white;
            padding: 0.4rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            z-index: 2;
            animation: bounceIn 0.6s ease-out;
        }

        /* Enhanced Wishlist Button */
        .wishlist-btn {
            position: absolute;
            top: 15px;
            left: 15px;
            background: rgba(255,255,255,0.95);
            border: none;
            border-radius: 50%;
            width: 45px;
            height: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            color: var(--dark-gray);
            transition: var(--transition);
            z-index: 2;
            backdrop-filter: blur(10px);
        }

        .wishlist-btn:hover, .wishlist-btn:focus {
            background: var(--white);
            color: var(--red);
            transform: scale(1.1) rotate(8deg);
            box-shadow: var(--shadow-md);
        }

        .wishlist-btn.active {
            color: var(--red);
            animation: pulse 0.6s ease-out;
        }

        /* Enhanced Quick View */
        .quick-view-btn {
            position: absolute;
            bottom: 15px;
            right: 15px;
            background: rgba(255,255,255,0.95);
            border: none;
            border-radius: 25px;
            padding: 0.7rem 1.2rem;
            cursor: pointer;
            color: var(--dark-blue);
            transition: var(--transition);
            z-index: 2;
            backdrop-filter: blur(10px);
            font-weight: 500;
            opacity: 0;
            transform: translateY(10px);
        }

        .product-card:hover .quick-view-btn {
            opacity: 1;
            transform: translateY(0);
        }

        .quick-view-btn:hover, .quick-view-btn:focus {
            background: var(--white);
            color: var(--prophetic-blue);
            transform: translateY(-2px) scale(1.05);
        }

        /* Enhanced Cart Icon */
        .cart-icon {
            position: relative;
            margin-left: 1rem;
            font-size: 1.5rem;
            cursor: pointer;
            transition: var(--transition);
            padding: 0.5rem;
            border-radius: 8px;
        }

        .cart-icon:hover, .cart-icon:focus {
            transform: scale(1.1) rotate(-5deg);
            background: rgba(255,255,255,0.1);
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--red);
            color: white;
            border-radius: 50%;
            width: 22px;
            height: 22px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: bold;
            animation: bounceIn 0.4s ease-out;
        }

        /* Enhanced Features Section */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2.5rem;
        }

        .feature-card {
            background: var(--white);
            padding: 2.5rem 2rem;
            border-radius: 12px;
            text-align: center;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            animation: fadeInUp 0.6s ease-out;
        }

        .feature-card:hover, .feature-card:focus-within {
            transform: translateY(-8px);
            box-shadow: var(--shadow-lg);
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--gold), var(--prophetic-blue));
            transform: scaleX(0);
            transition: var(--transition);
        }

        .feature-card:hover::before {
            transform: scaleX(1);
        }

        .feature-icon {
            font-size: 3rem;
            color: var(--gold);
            margin-bottom: 1.5rem;
            transition: var(--transition);
        }

        .feature-card:hover .feature-icon {
            transform: scale(1.1) rotate(5deg);
        }

        /* Enhanced Modals */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            padding: 20px;
            animation: fadeIn 0.4s ease-out;
            backdrop-filter: blur(5px);
        }

        .modal-content {
            background: var(--white);
            width: 90%;
            max-width: 500px;
            border-radius: 16px;
            padding: 2.5rem;
            position: relative;
            animation: slideIn 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: var(--shadow-lg);
            transform-origin: center;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: scale(0.8) translateY(-20px);
            }
            to {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-gray);
            transition: var(--transition);
            background: none;
            border: none;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
        }

        .close-modal:hover, .close-modal:focus {
            color: var(--red);
            background: var(--gray);
            transform: rotate(90deg) scale(1.1);
        }

        /* Enhanced Toast Notifications */
        .toast {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: var(--prophetic-blue);
            color: white;
            padding: 1.2rem 1.8rem;
            border-radius: 12px;
            box-shadow: var(--shadow-lg);
            z-index: 3000;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            transform: translateX(400px);
            transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            backdrop-filter: blur(10px);
        }

        .toast.show {
            transform: translateX(0);
        }

        .toast.success {
            background: linear-gradient(135deg, var(--success), #0da371);
        }

        .toast.error {
            background: linear-gradient(135deg, var(--red), #9c1a1a);
        }

        .toast.warning {
            background: linear-gradient(135deg, var(--warning), #d97706);
        }

        /* Progress Bar Animation */
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--gold), var(--prophetic-blue));
            border-radius: 4px;
            transition: width 1s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .progress-fill::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            animation: shimmer 2s infinite;
        }

        /* Enhanced Form Elements */
        .form-control {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e5e7eb;
            border-radius: 8px;
            font-size: 1rem;
            transition: var(--transition);
            background: var(--white);
        }

        .form-control:focus {
            outline: none;
            border-color: var(--prophetic-blue);
            box-shadow: 0 0 0 3px rgba(30, 58, 138, 0.1);
            transform: translateY(-2px);
        }

        /* Scroll Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Enhanced Quick Actions */
        .quick-actions-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 1.5rem;
        }

        .quick-action {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1.2rem;
            background: var(--white);
            border-radius: 12px;
            text-decoration: none;
            color: var(--dark-blue);
            transition: var(--transition);
            border: 2px solid transparent;
            animation: fadeInUp 0.6s ease-out;
        }

        .quick-action:hover, .quick-action:focus {
            border-color: var(--gold);
            transform: translateY(-5px) scale(1.02);
            box-shadow: var(--shadow-md);
        }

        .quick-action i {
            color: var(--gold);
            font-size: 1.5rem;
            transition: var(--transition);
        }

        .quick-action:hover i {
            transform: scale(1.2) rotate(10deg);
        }

        /* Enhanced Footer */
        footer {
            background: linear-gradient(135deg, var(--dark-blue), #1a237e);
            color: var(--white);
            padding: 4rem 0 2rem;
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 100" fill="%23ffffff" opacity="0.05"><polygon points="0,0 1000,50 1000,100 0,100"/></svg>');
            background-size: cover;
        }

        .social-icons a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            transition: var(--transition);
            backdrop-filter: blur(10px);
        }

        .social-icons a:hover, .social-icons a:focus {
            background: var(--gold);
            transform: translateY(-3px) scale(1.1);
        }

        /* Enhanced Loading States */
        .btn-loading {
            position: relative;
            color: transparent !important;
        }

        .btn-loading::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            border: 2px solid transparent;
            border-top: 2px solid currentColor;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        /* Pulse Animation for Special Elements */
        .pulse-gold {
            animation: pulse 2s infinite;
            box-shadow: 0 0 0 0 rgba(212, 175, 55, 0.7);
        }

        .pulse-gold:hover {
            animation: none;
        }

        /* Enhanced Typography */
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Playfair Display', serif;
            font-weight: 700;
        }

        .section-title {
            text-align: center;
            margin: 4rem 0 3rem;
            font-size: 2.5rem;
            color: var(--prophetic-blue);
            position: relative;
            animation: fadeInUp 0.8s ease-out;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, var(--gold), var(--prophetic-blue));
            margin: 1rem auto;
            border-radius: 2px;
            animation: fadeInUp 0.8s ease-out 0.2s both;
        }

        /* Responsive Design Enhancements */
        @media (max-width: 768px) {
            .hero h2 {
                font-size: 2.5rem;
            }
            
            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .btn {
                width: 100%;
                max-width: 280px;
            }
            
            .products-grid {
                grid-template-columns: 1fr;
            }
            
            .quick-view-btn {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Dark mode support */
        @media (prefers-color-scheme: dark) {
            :root {
                --white: #1a1a1a;
                --dark-blue: #ffffff;
                --gray: #2d2d2d;
                --light-blue: #2a2a2a;
            }
        }

        /* Print styles */
        @media print {
            .btn, .quick-view-btn, .wishlist-btn, .cart-icon {
                display: none !important;
            }
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--gray);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--gold);
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--prophetic-blue);
        }
    </style>
</head>
<body>
    <!-- Skip to main content -->
    <a href="#mainContent" class="skip-link">Skip to main content</a>

    <!-- Header -->
    <header id="mainHeader">
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo floating-element">
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
                    <button class="btn btn-primary pulse-gold" id="signupBtn">
                        <i class="fas fa-user-plus"></i>Sign Up Free
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

    <!-- Main Content -->
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
                        <div class="feature-card fade-in">
                            <div class="feature-icon">
                                <i class="fas fa-shield-alt"></i>
                            </div>
                            <h3 class="feature-title">Secure Platform</h3>
                            <p>Your data and purchases are protected with enterprise-grade security.</p>
                        </div>
                        <div class="feature-card fade-in">
                            <div class="feature-icon">
                                <i class="fas fa-mobile-alt"></i>
                            </div>
                            <h3 class="feature-title">Access Anywhere</h3>
                            <p>Enjoy our content on any device, online or offline.</p>
                        </div>
                        <div class="feature-card fade-in">
                            <div class="feature-icon">
                                <i class="fas fa-graduation-cap"></i>
                            </div>
                            <h3 class="feature-title">Expert Content</h3>
                            <p>All materials are created by leading experts in personal development.</p>
                        </div>
                        <div class="feature-card fade-in">
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

        <!-- Other page sections remain the same but with enhanced styling -->
        <!-- ... [Rest of the HTML structure remains similar but with enhanced classes] ... -->
    </main>

    <!-- Footer -->
    <footer>
        <!-- ... [Enhanced footer structure] ... -->
    </footer>

    <!-- Modals -->
    <!-- ... [Enhanced modal structures] ... -->

    <script>
        // Enhanced JavaScript with animations and micro-interactions
        document.addEventListener('DOMContentLoaded', function() {
            // Initialize the store
            init();
            
            // Add scroll animations
            initScrollAnimations();
            
            // Add header scroll effect
            initHeaderScroll();
            
            // Add hover effects
            initHoverEffects();
            
            // Add loading states
            initLoadingStates();
        });

        function initScrollAnimations() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, { threshold: 0.1 });

            document.querySelectorAll('.fade-in').forEach(el => {
                observer.observe(el);
            });
        }

        function initHeaderScroll() {
            const header = document.getElementById('mainHeader');
            let lastScroll = 0;

            window.addEventListener('scroll', () => {
                const currentScroll = window.pageYOffset;
                
                if (currentScroll > 100) {
                    header.classList.add('scrolled');
                } else {
                    header.classList.remove('scrolled');
                }
                
                lastScroll = currentScroll;
            });
        }

        function initHoverEffects() {
            // Add ripple effect to buttons
            document.addEventListener('click', function(e) {
                if (e.target.closest('.btn')) {
                    const btn = e.target.closest('.btn');
                    const ripple = document.createElement('span');
                    const rect = btn.getBoundingClientRect();
                    const size = Math.max(rect.width, rect.height);
                    const x = e.clientX - rect.left - size / 2;
                    const y = e.clientY - rect.top - size / 2;
                    
                    ripple.style.cssText = `
                        position: absolute;
                        border-radius: 50%;
                        background: rgba(255, 255, 255, 0.6);
                        transform: scale(0);
                        animation: ripple 0.6s linear;
                        width: ${size}px;
                        height: ${size}px;
                        left: ${x}px;
                        top: ${y}px;
                    `;
                    
                    btn.style.position = 'relative';
                    btn.style.overflow = 'hidden';
                    btn.appendChild(ripple);
                    
                    setTimeout(() => ripple.remove(), 600);
                }
            });

            // Add CSS for ripple animation
            const style = document.createElement('style');
            style.textContent = `
                @keyframes ripple {
                    to {
                        transform: scale(4);
                        opacity: 0;
                    }
                }
            `;
            document.head.appendChild(style);
        }

        function initLoadingStates() {
            // Enhanced loading states for buttons
            document.addEventListener('submit', function(e) {
                const form = e.target;
                const submitBtn = form.querySelector('button[type="submit"]');
                
                if (submitBtn) {
                    submitBtn.classList.add('btn-loading');
                    submitBtn.disabled = true;
                    
                    // Simulate loading completion
                    setTimeout(() => {
                        submitBtn.classList.remove('btn-loading');
                        submitBtn.disabled = false;
                    }, 2000);
                }
            });
        }

        // Enhanced add to cart with animation
        function addToCartWithAnimation(id, name, price) {
            const cartIcon = document.querySelector('.cart-icon');
            const productCard = document.querySelector(`[data-id="${id}"]`).closest('.product-card');
            const productImage = productCard.querySelector('.product-image');
            
            // Create flying product animation
            const flyingProduct = productImage.cloneNode(true);
            flyingProduct.style.cssText = `
                position: fixed;
                z-index: 10000;
                pointer-events: none;
                transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
                transform-origin: center;
            `;
            
            const productRect = productImage.getBoundingClientRect();
            const cartRect = cartIcon.getBoundingClientRect();
            
            flyingProduct.style.left = `${productRect.left}px`;
            flyingProduct.style.top = `${productRect.top}px`;
            flyingProduct.style.width = `${productRect.width}px`;
            flyingProduct.style.height = `${productRect.height}px`;
            flyingProduct.style.fontSize = '3rem';
            
            document.body.appendChild(flyingProduct);
            
            // Animate to cart
            setTimeout(() => {
                flyingProduct.style.left = `${cartRect.left}px`;
                flyingProduct.style.top = `${cartRect.top}px`;
                flyingProduct.style.width = '20px';
                flyingProduct.style.height = '20px';
                flyingProduct.style.opacity = '0.5';
                flyingProduct.style.transform = 'scale(0.5)';
            }, 50);
            
            // Remove element and add to cart
            setTimeout(() => {
                flyingProduct.remove();
                addToCart(id, name, price);
                
                // Pulse cart icon
                cartIcon.style.animation = 'pulse 0.6s ease-in-out';
                setTimeout(() => {
                    cartIcon.style.animation = '';
                }, 600);
                
                showToast('🎉 Added to cart!', 'success');
            }, 800);
        }

        // Enhanced product rendering with staggered animation
        function renderProductsWithAnimation(products, container) {
            container.innerHTML = '';
            
            products.forEach((product, index) => {
                const productCard = createProductCard(product);
                productCard.style.animationDelay = `${index * 0.1}s`;
                container.appendChild(productCard);
            });
        }

        // Enhanced toast with better animations
        function showEnhancedToast(message, type = 'success') {
            const toast = document.getElementById('toast');
            const toastMessage = document.getElementById('toastMessage');
            
            toastMessage.textContent = message;
            toast.className = `toast ${type}`;
            
            // Add icon based on type
            let icon = 'fas fa-check-circle';
            if (type === 'error') icon = 'fas fa-exclamation-circle';
            if (type === 'warning') icon = 'fas fa-exclamation-triangle';
            
            toast.innerHTML = `<i class="${icon}"></i><span id="toastMessage">${message}</span>`;
            
            toast.classList.add('show');
            
            // Auto-hide with better timing
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }

        // Enhanced page transitions
        function showPageWithTransition(page) {
            const currentPage = document.querySelector('main > section:not([style*="display: none"])');
            const nextPage = document.getElementById(`${page}Page`);
            
            if (currentPage) {
                currentPage.style.opacity = '0';
                currentPage.style.transform = 'translateY(20px)';
                currentPage.style.transition = 'all 0.4s ease';
                
                setTimeout(() => {
                    currentPage.style.display = 'none';
                    nextPage.style.display = 'block';
                    
                    setTimeout(() => {
                        nextPage.style.opacity = '1';
                        nextPage.style.transform = 'translateY(0)';
                    }, 50);
                }, 400);
            } else {
                nextPage.style.display = 'block';
                nextPage.style.opacity = '1';
            }
            
            // Update active nav
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });
            document.querySelector(`.nav-link[data-page="${page}"]`).classList.add('active');
            
            // Scroll to top with smooth behavior
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Replace original functions with enhanced versions
        // In your existing code, replace:
        // - addToCart → addToCartWithAnimation
        // - renderProducts → renderProductsWithAnimation
        // - showToast → showEnhancedToast
        // - showPage → showPageWithTransition

        // ... [Rest of your existing JavaScript with these enhanced functions integrated] ...
    </script>
</body>
</html>
