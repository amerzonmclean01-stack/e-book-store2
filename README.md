<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Definitive Word - Your Destiny Has Been Written</title>
    <meta name="description" content="The Definitive Word Ministry - Your Destiny Has Been Written. Discover God's plan through prophetic teaching, life coaching, and transformative resources.">
    <meta name="keywords" content="prophetic teaching, life coaching, Christian resources, destiny, ministry, South Africa">
    <meta name="author" content="The Definitive Word Ministry">
    <meta property="og:title" content="The Definitive Word - Your Destiny Has Been Written">
    <meta property="og:description" content="Discover God's plan for your life through prophetic teaching and life coaching">
    <meta property="og:image" content="https://yourdomain.com/images/og-image.jpg">
    <meta property="og:url" content="https://yourdomain.com">
    <meta property="og:type" content="website">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="The Definitive Word - Your Destiny Has Been Written">
    <meta name="twitter:description" content="Discover God's plan for your life through prophetic teaching and life coaching">
    <meta name="csrf-token" content="csrf_token_placeholder">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://js.stripe.com/v3/"></script>
    
    <!-- Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());
        gtag('config', 'GA_MEASUREMENT_ID');
    </script>
    
    <style>
        :root {
            --prophetic-blue: #1e3a8a;
            --prophetic-red: #dc2626;
            --prophetic-gold: #d4af37;
            --white: #ffffff;
            --light-gray: #f3f4f6;
            --dark-gray: #374151;
            --success: #10b981;
            --warning: #f59e0b;
            --error: #ef4444;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f9fafb;
            color: var(--dark-gray);
            line-height: 1.6;
        }

        /* Header & Navigation */
        header {
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            color: var(--white);
            padding: 0.5rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 1.5rem;
        }

        .logo {
            display: flex;
            flex-direction: column;
        }

        .logo h1 {
            font-size: 1.6rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo p {
            font-size: 0.8rem;
            font-style: italic;
            opacity: 0.9;
        }

        .nav-container {
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 1.5rem;
            align-items: center;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            transition: opacity 0.3s;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.9rem;
            white-space: nowrap;
        }

        .nav-links a:hover {
            opacity: 0.8;
        }

        .user-actions {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .cart-icon, .wishlist-icon {
            position: relative;
            cursor: pointer;
        }

        .cart-count, .wishlist-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--prophetic-gold);
            color: var(--prophetic-blue);
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .auth-buttons {
            display: flex;
            gap: 0.5rem;
        }

        .btn {
            padding: 0.5rem 1rem;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.9rem;
        }

        .btn-outline {
            background: transparent;
            border: 1px solid var(--white);
            color: var(--white);
        }

        .btn-primary {
            background: var(--prophetic-gold);
            color: var(--prophetic-blue);
        }

        .btn-primary:hover {
            background: #e6b800;
        }

        .btn-outline:hover {
            background: rgba(255,255,255,0.1);
        }

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Search Container */
        .search-container {
            margin: 1rem 0;
            position: relative;
        }

        .search-results {
            position: absolute;
            top: 100%;
            left: 0;
            right: 0;
            background: white;
            border: 1px solid #e5e7eb;
            border-radius: 5px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            max-height: 300px;
            overflow-y: auto;
            z-index: 100;
            display: none;
        }

        .search-result-item {
            padding: 0.75rem 1rem;
            border-bottom: 1px solid #e5e7eb;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.75rem;
        }

        .search-result-item:hover {
            background: var(--light-gray);
        }

        .search-result-icon {
            font-size: 1.2rem;
            width: 30px;
            text-align: center;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(30, 58, 138, 0.9), rgba(220, 38, 38, 0.9)), url('https://images.unsplash.com/photo-1532629345422-7515f3d16bb6?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            color: var(--white);
            text-align: center;
            padding: 6rem 2rem;
            position: relative;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            font-style: italic;
        }

        /* Sections */
        section {
            max-width: 1200px;
            margin: 0 auto;
            padding: 3rem 1.5rem;
        }

        section h2 {
            color: var(--prophetic-blue);
            font-size: 2.2rem;
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
        }

        section h2:after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: var(--prophetic-gold);
            margin: 0.5rem auto;
            border-radius: 2px;
        }

        /* Products Grid */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .product-card {
            background: var(--white);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            display: flex;
            flex-direction: column;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }

        .product-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 3rem;
        }

        .wishlist-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: rgba(255,255,255,0.9);
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 1.2rem;
            color: var(--prophetic-red);
            transition: all 0.3s;
        }

        .wishlist-btn.active {
            color: var(--prophetic-red);
        }

        .product-content {
            padding: 1.5rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .product-content h3 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
        }

        .product-content p {
            margin-bottom: 1rem;
            color: var(--dark-gray);
            flex-grow: 1;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: auto;
        }

        .price {
            font-size: 1.5rem;
            color: var(--prophetic-red);
            font-weight: bold;
        }

        .in-stock {
            color: var(--success);
            font-size: 0.9rem;
            font-weight: bold;
        }

        .out-of-stock {
            color: var(--error);
            font-size: 0.9rem;
            font-weight: bold;
        }

        /* Cart Sidebar */
        .cart-sidebar, .wishlist-sidebar {
            position: fixed;
            top: 0;
            right: -400px;
            width: 400px;
            height: 100vh;
            background: var(--white);
            box-shadow: -5px 0 15px rgba(0,0,0,0.1);
            transition: right 0.3s ease;
            z-index: 1100;
            display: flex;
            flex-direction: column;
        }

        .cart-sidebar.active, .wishlist-sidebar.active {
            right: 0;
        }

        .cart-header, .wishlist-header {
            padding: 1.5rem;
            border-bottom: 1px solid #e5e7eb;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--prophetic-blue);
            color: var(--white);
        }

        .cart-header h3, .wishlist-header h3 {
            margin: 0;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .close-cart, .close-wishlist {
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        .cart-items, .wishlist-items {
            flex-grow: 1;
            overflow-y: auto;
            padding: 1rem;
        }

        .cart-item, .wishlist-item {
            display: flex;
            gap: 1rem;
            padding: 1rem 0;
            border-bottom: 1px solid #e5e7eb;
        }

        .cart-item-image, .wishlist-item-image {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red));
            border-radius: 5px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 1.5rem;
        }

        .cart-item-details, .wishlist-item-details {
            flex-grow: 1;
        }

        .cart-item-details h4, .wishlist-item-details h4 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
        }

        .cart-item-controls {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-top: 0.5rem;
        }

        .quantity-btn {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 1px solid #d1d5db;
            background: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }

        .quantity {
            margin: 0 0.5rem;
            font-weight: bold;
        }

        .remove-item {
            color: var(--prophetic-red);
            background: none;
            border: none;
            cursor: pointer;
            margin-left: auto;
        }

        .cart-footer, .wishlist-footer {
            padding: 1.5rem;
            border-top: 1px solid #e5e5e5;
            background: var(--light-gray);
        }

        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 1rem;
        }

        .checkout-btn {
            width: 100%;
            padding: 1rem;
            background: var(--prophetic-red);
            color: var(--white);
            border: none;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .checkout-btn:hover {
            background: #b91c1c;
        }

        .empty-cart, .empty-wishlist {
            text-align: center;
            padding: 2rem;
            color: #6b7280;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1200;
            align-items: center;
            justify-content: center;
            padding: 1rem;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: var(--white);
            padding: 2rem;
            border-radius: 10px;
            max-width: 800px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            position: relative;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            border-bottom: 1px solid #e5e7eb;
            padding-bottom: 1rem;
        }

        .modal-header h3 {
            color: var(--prophetic-blue);
            margin: 0;
        }

        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--dark-gray);
        }

        /* Auth Tabs */
        .auth-tabs {
            display: flex;
            margin-bottom: 1.5rem;
            border-bottom: 1px solid #e5e7eb;
            overflow-x: auto;
        }

        .auth-tab {
            padding: 0.75rem 1.5rem;
            background: none;
            border: none;
            cursor: pointer;
            font-weight: 600;
            color: var(--dark-gray);
            border-bottom: 3px solid transparent;
            white-space: nowrap;
        }

        .auth-tab.active {
            color: var(--prophetic-blue);
            border-bottom: 3px solid var(--prophetic-blue);
        }

        .auth-form {
            display: none;
        }

        .auth-form.active {
            display: block;
        }

        /* Admin Panel */
        .admin-panel {
            display: none;
            background: var(--light-gray);
            padding: 2rem;
            border-radius: 10px;
            margin-top: 2rem;
        }

        .admin-panel.active {
            display: block;
        }

        .admin-tabs {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
            overflow-x: auto;
        }

        .admin-tab {
            padding: 0.75rem 1.5rem;
            background: var(--white);
            border: 1px solid #d1d5db;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            color: var(--dark-gray);
            white-space: nowrap;
        }

        .admin-tab.active {
            background: var(--prophetic-blue);
            color: var(--white);
        }

        .admin-content {
            background: var(--white);
            padding: 1.5rem;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .admin-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
        }

        .admin-table th, .admin-table td {
            padding: 0.75rem;
            text-align: left;
            border-bottom: 1px solid #e5e7eb;
        }

        .admin-table th {
            background: var(--light-gray);
            color: var(--prophetic-blue);
        }

        .action-btn {
            padding: 0.5rem 0.75rem;
            border: none;
            border-radius: 3px;
            cursor: pointer;
            font-size: 0.8rem;
            margin-right: 0.5rem;
            display: inline-flex;
            align-items: center;
            gap: 0.3rem;
        }

        .edit-btn {
            background: var(--warning);
            color: var(--white);
        }

        .delete-btn {
            background: var(--error);
            color: var(--white);
        }

        .preview-btn {
            background: var(--prophetic-blue);
            color: var(--white);
        }

        /* Content Management */
        .content-management {
            margin-top: 2rem;
        }

        .content-type-tabs {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
            overflow-x: auto;
        }

        .content-type-tab {
            padding: 0.75rem 1.5rem;
            background: var(--white);
            border: 1px solid #d1d5db;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            color: var(--dark-gray);
            white-space: nowrap;
        }

        .content-type-tab.active {
            background: var(--prophetic-blue);
            color: var(--white);
        }

        .content-list {
            margin-top: 1.5rem;
        }

        .content-item {
            background: var(--light-gray);
            padding: 1.5rem;
            border-radius: 5px;
            margin-bottom: 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .content-item h4 {
            color: var(--prophetic-blue);
            margin-bottom: 0.5rem;
        }

        .content-item-actions {
            display: flex;
            gap: 0.5rem;
        }

        /* Preview Section */
        .preview-section {
            margin-top: 2rem;
            border-top: 1px solid #e5e7eb;
            padding-top: 1.5rem;
        }

        .preview-content {
            background: var(--light-gray);
            padding: 1.5rem;
            border-radius: 5px;
            margin-top: 1rem;
        }

        /* Social Share */
        .social-share {
            display: flex;
            gap: 0.5rem;
            margin: 1rem 0;
        }

        /* Footer */
        footer {
            background: var(--prophetic-blue);
            color: var(--white);
            text-align: center;
            padding: 3rem 2rem;
            margin-top: 4rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: left;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.5rem;
        }

        .footer-section a {
            color: var(--white);
            text-decoration: none;
            transition: opacity 0.3s;
        }

        .footer-section a:hover {
            opacity: 0.8;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            transition: background 0.3s;
        }

        .social-links a:hover {
            background: var(--prophetic-red);
        }

        .footer-bottom {
            margin-top: 2rem;
            padding-top: 1rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        /* Utility Classes */
        .alt-bg {
            background: var(--light-gray);
        }

        .text-center {
            text-align: center;
        }

        .hidden {
            display: none !important;
        }

        /* Form Styles */
        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--prophetic-blue);
            font-weight: bold;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #d1d5db;
            border-radius: 5px;
            font-family: inherit;
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        /* Cookie Consent */
        #cookieConsent {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: #333;
            color: white;
            padding: 1rem;
            z-index: 2000;
            display: none;
        }

        .cookie-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 1rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            .nav-container {
                flex-direction: column;
                align-items: flex-start;
                width: 100%;
                position: absolute;
                top: 100%;
                left: 0;
                background: var(--prophetic-blue);
                padding: 1rem;
                display: none;
            }

            .nav-container.active {
                display: flex;
            }

            .nav-links {
                flex-direction: column;
                width: 100%;
                gap: 1rem;
            }

            .user-actions {
                flex-direction: column;
                width: 100%;
                gap: 0.5rem;
            }

            .hero h2 {
                font-size: 2rem;
            }

            .cart-sidebar, .wishlist-sidebar {
                width: 100%;
                right: -100%;
            }

            .footer-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .social-links {
                justify-content: center;
            }

            .admin-tabs, .content-type-tabs {
                flex-direction: column;
            }

            .modal-content {
                padding: 1.5rem;
            }

            .cookie-content {
                flex-direction: column;
                text-align: center;
            }
        }

        /* Stripe Elements */
        .StripeElement {
            padding: 1rem;
            border: 1px solid #d1d5db;
            border-radius: 5px;
            margin: 1rem 0;
        }

        /* Loading Spinner */
        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid var(--prophetic-blue);
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 2s linear infinite;
            margin: 0 auto;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        @keyframes slideIn {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
    </style>
</head>
<body>
    <!-- Cookie Consent Banner -->
    <div id="cookieConsent">
        <div class="cookie-content">
            <p>We use cookies to enhance your experience. By continuing to visit this site you agree to our use of cookies.</p>
            <button onclick="acceptCookies()" class="btn btn-primary">Accept</button>
        </div>
    </div>

    <!-- Header -->
    <header>
        <nav>
            <div class="logo">
                <h1><i class="fas fa-cross"></i> The Definitive Word</h1>
                <p>Your Destiny Has Been Written</p>
            </div>
            
            <button class="menu-toggle" onclick="toggleMenu()">
                <i class="fas fa-bars"></i>
            </button>
            
            <div class="nav-container" id="navContainer">
                <ul class="nav-links">
                    <li><a href="#home"><i class="fas fa-home"></i> Home</a></li>
                    <li><a href="#products"><i class="fas fa-book"></i> Products</a></li>
                    <li><a href="#coaching"><i class="fas fa-hands-helping"></i> Coaching</a></li>
                    <li><a href="#blog"><i class="fas fa-blog"></i> Blog</a></li>
                    <li><a href="#workshops"><i class="fas fa-users"></i> Workshops</a></li>
                    <li><a href="#ministry"><i class="fas fa-church"></i> Ministry</a></li>
                    <li><a href="#contact"><i class="fas fa-envelope"></i> Contact</a></li>
                </ul>
                
                <div class="user-actions">
                    <div class="wishlist-icon" onclick="toggleWishlist()">
                        <i class="fas fa-heart"></i>
                        <span class="wishlist-count">0</span>
                    </div>
                    <div class="cart-icon" onclick="toggleCart()">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </div>
                    
                    <div class="auth-buttons">
                        <button class="btn btn-outline" onclick="openAuthModal()">
                            <i class="fas fa-user"></i> Login
                        </button>
                        <button class="btn btn-primary" onclick="openAuthModal('register')">
                            <i class="fas fa-user-plus"></i> Sign Up
                        </button>
                    </div>
                </div>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h2>Welcome to The Definitive Word</h2>
            <p>Your Destiny Has Been Written</p>
            <p>Discover God's plan for your life through prophetic teaching, life coaching, and transformative resources</p>
            <button class="btn btn-primary" onclick="scrollToSection('products')">
                <i class="fas fa-shopping-bag"></i> Explore Our Resources
            </button>
        </div>
    </section>

    <!-- Search Section -->
    <section class="alt-bg">
        <div class="search-container">
            <input type="text" id="searchInput" placeholder="Search products, blog posts, workshops..." 
                   style="width: 100%; padding: 0.8rem; border: 1px solid #d1d5db; border-radius: 5px;">
            <div class="search-results" id="searchResults"></div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products">
        <h2>Featured Products</h2>
        <p class="text-center" style="max-width: 800px; margin: 0 auto 2rem;">
            Dive deep into prophetic wisdom and biblical teaching with our collection of transformative resources.
        </p>
        
        <div class="products-grid" id="productsGrid">
            <!-- Product cards will be dynamically generated -->
        </div>
    </section>

    <!-- Coaching Section -->
    <section id="coaching" class="alt-bg">
        <h2>Life Coaching</h2>
        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: center;">
            <div>
                <h3 style="color: var(--prophetic-blue); margin-bottom: 1rem;">Transform Your Life Through Prophetic Coaching</h3>
                <p style="margin-bottom: 1.5rem;">Our life coaching program combines biblical principles with practical strategies to help you:</p>
                <ul style="margin-left: 1.5rem; margin-bottom: 2rem;">
                    <li style="margin-bottom: 0.8rem;">Discover your divine purpose and calling</li>
                    <li style="margin-bottom: 0.8rem;">Overcome obstacles and limiting beliefs</li>
                    <li style="margin-bottom: 0.8rem;">Develop spiritual disciplines and growth</li>
                    <li style="margin-bottom: 0.8rem;">Create actionable plans for your goals</li>
                    <li style="margin-bottom: 0.8rem;">Walk in the fullness of your destiny</li>
                </ul>
                <button class="btn btn-primary" onclick="addToCart('Life Coaching Session', 0, 'coaching')">
                    <i class="fas fa-calendar-check"></i> Book a Session
                </button>
            </div>
            <div>
                <div style="background: linear-gradient(135deg, var(--prophetic-blue), var(--prophetic-red)); height: 400px; border-radius: 10px; display: flex; align-items: center; justify-content: center; color: white; font-size: 4rem;">
                    <i class="fas fa-bullseye"></i>
                </div>
            </div>
        </div>
    </section>

    <!-- Blog Section -->
    <section id="blog">
        <h2>Latest from the Blog</h2>
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; margin-top: 2rem;" id="blogContainer">
            <!-- Blog posts will be dynamically generated -->
        </div>
    </section>

    <!-- Workshops Section -->
    <section id="workshops" class="alt-bg">
        <h2>Upcoming Workshops</h2>
        <div style="display: grid; gap: 2rem; margin-top: 2rem;" id="workshopsContainer">
            <!-- Workshop cards will be dynamically generated -->
        </div>
    </section>

    <!-- Ministry Section -->
    <section id="ministry">
        <h2>Our Ministry</h2>
        <div style="max-width: 800px; margin: 0 auto; text-align: center;">
            <p style="font-size: 1.2rem; margin-bottom: 2rem;">
                The Definitive Word Ministry is dedicated to helping believers understand that their destiny has already been written by God. Through prophetic teaching, life coaching, and biblical resources, we equip people to walk confidently in their divine calling.
            </p>
            
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 2rem; margin: 3rem 0;">
                <div>
                    <div style="font-size: 3rem; color: var(--prophetic-blue);">
                        <i class="fas fa-book-open"></i>
                    </div>
                    <h3 style="color: var(--prophetic-blue); margin: 1rem 0;">Teaching</h3>
                    <p>Biblical and prophetic instruction</p>
                </div>
                <div>
                    <div style="font-size: 3rem; color: var(--prophetic-red);">
                        <i class="fas fa-pray"></i>
                    </div>
                    <h3 style="color: var(--prophetic-red); margin: 1rem 0;">Prayer</h3>
                    <p>Intercessory and prophetic prayer</p>
                </div>
                <div>
                    <div style="font-size: 3rem; color: var(--prophetic-blue);">
                        <i class="fas fa-hands-helping"></i>
                    </div>
                    <h3 style="color: var(--prophetic-blue); margin: 1rem 0;">Coaching</h3>
                    <p>Personal transformation guidance</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="alt-bg">
        <h2>Get In Touch</h2>
        <div style="max-width: 600px; margin: 2rem auto; background: var(--white); padding: 2rem; border-radius: 10px;">
            <form id="contactForm">
                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="subject">Subject</label>
                    <select id="subject" name="subject" required>
                        <option value="">Select a topic...</option>
                        <option value="products">Products</option>
                        <option value="coaching">Life Coaching</option>
                        <option value="workshops">Workshops</option>
                        <option value="ministry">Ministry Inquiry</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" name="message" required></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%;">
                    <i class="fas fa-paper-plane"></i> Send Message
                </button>
            </form>
        </div>
    </section>

    <!-- Admin Panel (Hidden by default) -->
    <section id="admin" class="hidden">
        <h2>Admin Panel</h2>
        <div class="admin-panel">
            <div class="admin-tabs">
                <button class="admin-tab active" onclick="switchAdminTab('products')">Products</button>
                <button class="admin-tab" onclick="switchAdminTab('blog')">Blog Posts</button>
                <button class="admin-tab" onclick="switchAdminTab('workshops')">Workshops</button>
                <button class="admin-tab" onclick="switchAdminTab('ministry')">Ministry</button>
                <button class="admin-tab" onclick="switchAdminTab('users')">Users</button>
                <button class="admin-tab" onclick="switchAdminTab('orders')">Orders</button>
                <button class="admin-tab" onclick="switchAdminTab('settings')">Settings</button>
            </div>
            
            <div class="admin-content">
                <!-- Products Tab -->
                <div id="admin-products" class="admin-tab-content active">
                    <h3>Manage Products</h3>
                    <button class="btn btn-primary" onclick="openProductModal()">
                        <i class="fas fa-plus"></i> Add New Product
                    </button>
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Name</th>
                                <th>Price</th>
                                <th>Inventory</th>
                                <th>Category</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="admin-products-table">
                            <!-- Products will be populated here -->
                        </tbody>
                    </table>
                </div>
                
                <!-- Blog Posts Tab -->
                <div id="admin-blog" class="admin-tab-content">
                    <h3>Manage Blog Posts</h3>
                    <button class="btn btn-primary" onclick="openContentModal('blog')">
                        <i class="fas fa-plus"></i> Add New Blog Post
                    </button>
                    <div class="content-list" id="admin-blog-list">
                        <!-- Blog posts will be populated here -->
                    </div>
                </div>
                
                <!-- Workshops Tab -->
                <div id="admin-workshops" class="admin-tab-content">
                    <h3>Manage Workshops</h3>
                    <button class="btn btn-primary" onclick="openContentModal('workshop')">
                        <i class="fas fa-plus"></i> Add New Workshop
                    </button>
                    <div class="content-list" id="admin-workshops-list">
                        <!-- Workshops will be populated here -->
                    </div>
                </div>
                
                <!-- Ministry Tab -->
                <div id="admin-ministry" class="admin-tab-content">
                    <h3>Manage Ministry Content</h3>
                    <button class="btn btn-primary" onclick="openContentModal('ministry')">
                        <i class="fas fa-plus"></i> Add Ministry Content
                    </button>
                    <div class="content-list" id="admin-ministry-list">
                        <!-- Ministry content will be populated here -->
                    </div>
                </div>
                
                <!-- Users Tab -->
                <div id="admin-users" class="admin-tab-content">
                    <h3>Manage Users</h3>
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Name</th>
                                <th>Email</th>
                                <th>Role</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="admin-users-table">
                            <!-- Users will be populated here -->
                        </tbody>
                    </table>
                </div>
                
                <!-- Orders Tab -->
                <div id="admin-orders" class="admin-tab-content">
                    <h3>Manage Orders</h3>
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Order ID</th>
                                <th>Customer</th>
                                <th>Amount</th>
                                <th>Status</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="admin-orders-table">
                            <!-- Orders will be populated here -->
                        </tbody>
                    </table>
                </div>
                
                <!-- Settings Tab -->
                <div id="admin-settings" class="admin-tab-content">
                    <h3>Website Settings</h3>
                    <div class="form-group">
                        <label for="siteTitle">Site Title</label>
                        <input type="text" id="siteTitle" value="The Definitive Word">
                    </div>
                    <div class="form-group">
                        <label for="siteTagline">Site Tagline</label>
                        <input type="text" id="siteTagline" value="Your Destiny Has Been Written">
                    </div>
                    <div class="form-group">
                        <label for="primaryColor">Primary Color</label>
                        <input type="color" id="primaryColor" value="#1e3a8a">
                    </div>
                    <div class="form-group">
                        <label for="secondaryColor">Secondary Color</label>
                        <input type="color" id="secondaryColor" value="#dc2626">
                    </div>
                    <button class="btn btn-primary" onclick="saveSettings()">
                        <i class="fas fa-save"></i> Save Settings
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>The Definitive Word</h3>
                <p>Your Destiny Has Been Written. We are dedicated to helping you discover and walk in your God-given purpose through prophetic teaching and life coaching.</p>
                <div class="social-links">
                    <a href="#" onclick="shareOnFacebook()"><i class="fab fa-facebook-f"></i></a>
                    <a href="#" onclick="shareOnTwitter()"><i class="fab fa-twitter"></i></a>
                    <a href="#" onclick="shareOnLinkedIn()"><i class="fab fa-linkedin"></i></a>
                    <a href="#" onclick="shareOnWhatsApp()"><i class="fab fa-whatsapp"></i></a>
                </div>
            </div>
            
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#products">Products</a></li>
                    <li><a href="#coaching">Coaching</a></li>
                    <li><a href="#blog">Blog</a></li>
                    <li><a href="#workshops">Workshops</a></li>
                    <li><a href="#" onclick="openModal('privacyModal')">Privacy Policy</a></li>
                    <li><a href="#" onclick="openModal('termsModal')">Terms of Service</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Contact Us</h3>
                <ul>
                    <li><i class="fas fa-map-marker-alt"></i> Cape Town, South Africa</li>
                    <li><i class="fas fa-phone"></i> +27 21 123 4567</li>
                    <li><i class="fas fa-envelope"></i> info@definitiveword.org</li>
                </ul>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>&copy; 2025 The Definitive Word Ministry. Your Destiny Has Been Written.</p>
            <p style="margin-top: 0.5rem; font-size: 0.9rem;">Walking in prophetic purpose since 2025</p>
        </div>
    </footer>

    <!-- Shopping Cart Sidebar -->
    <div class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h3><i class="fas fa-shopping-cart"></i> Your Cart</h3>
            <button class="close-cart" onclick="toggleCart()">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="cart-items" id="cartItems">
            <!-- Cart items will be dynamically added here -->
        </div>
        <div class="cart-footer">
            <div class="cart-total">
                <span>Total:</span>
                <span id="cartTotal">R 0.00</span>
            </div>
            <button class="checkout-btn" id="checkoutBtn" onclick="checkout()">
                <i class="fas fa-lock"></i> Proceed to Checkout
            </button>
        </div>
    </div>

    <!-- Wishlist Sidebar -->
    <div class="wishlist-sidebar" id="wishlistSidebar">
        <div class="wishlist-header">
            <h3><i class="fas fa-heart"></i> Your Wishlist</h3>
            <button class="close-wishlist" onclick="toggleWishlist()">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="wishlist-items" id="wishlistItems">
            <!-- Wishlist items will be dynamically added here -->
        </div>
        <div class="wishlist-footer">
            <button class="checkout-btn" onclick="toggleWishlist()">
                Continue Shopping
            </button>
        </div>
    </div>

    <!-- Auth Modal -->
    <div class="modal" id="authModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 id="authModalTitle">Login to Your Account</h3>
                <button class="close-modal" onclick="closeAuthModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="auth-tabs">
                <button class="auth-tab active" onclick="switchAuthTab('login')">Login</button>
                <button class="auth-tab" onclick="switchAuthTab('register')">Register</button>
            </div>
            
            <form id="loginForm" class="auth-form active">
                <div class="form-group">
                    <label for="loginEmail">Email</label>
                    <input type="email" id="loginEmail" required>
                </div>
                <div class="form-group">
                    <label for="loginPassword">Password</label>
                    <input type="password" id="loginPassword" required>
                </div>
                <div class="form-footer">
                    <a href="#" class="forgot-password">Forgot Password?</a>
                    <button type="submit" class="btn btn-primary">Login</button>
                </div>
            </form>
            
            <form id="registerForm" class="auth-form">
                <div class="form-group">
                    <label for="registerName">Full Name</label>
                    <input type="text" id="registerName" required>
                </div>
                <div class="form-group">
                    <label for="registerEmail">Email</label>
                    <input type="email" id="registerEmail" required>
                </div>
                <div class="form-group">
                    <label for="registerPassword">Password</label>
                    <input type="password" id="registerPassword" required>
                </div>
                <div class="form-group">
                    <label for="registerConfirmPassword">Confirm Password</label>
                    <input type="password" id="registerConfirmPassword" required>
                </div>
                <div class="form-footer">
                    <button type="submit" class="btn btn-primary">Create Account</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Product Modal (for admin) -->
    <div class="modal" id="productModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 id="productModalTitle">Add New Product</h3>
                <button class="close-modal" onclick="closeProductModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <form id="productForm">
                <div class="form-group">
                    <label for="productName">Product Name</label>
                    <input type="text" id="productName" required>
                </div>
                <div class="form-group">
                    <label for="productDescription">Description</label>
                    <textarea id="productDescription" required></textarea>
                </div>
                <div class="form-group">
                    <label for="productPrice">Price (ZAR)</label>
                    <input type="number" id="productPrice" step="0.01" required>
                </div>
                <div class="form-group">
                    <label for="productInventory">Inventory</label>
                    <input type="number" id="productInventory" required>
                </div>
                <div class="form-group">
                    <label for="productSKU">SKU</label>
                    <input type="text" id="productSKU" required>
                </div>
                <div class="form-group">
                    <label for="productCategory">Category</label>
                    <select id="productCategory" required>
                        <option value="ebook">E-book</option>
                        <option value="workshop">Workshop</option>
                        <option value="coaching">Coaching</option>
                        <option value="other">Other</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="productImageUpload">Product Image</label>
                    <input type="file" id="productImageUpload" accept="image/*" onchange="handleImageUpload(event)">
                    <div id="imagePreview" style="margin-top: 0.5rem;"></div>
                </div>
                <input type="hidden" id="productImage">
                
                <!-- Preview Section -->
                <div class="preview-section">
                    <h4>Preview</h4>
                    <div class="preview-content" id="productPreview">
                        <p><strong>Product Preview:</strong> Your product will appear here as you type.</p>
                    </div>
                </div>
                
                <button type="submit" class="btn btn-primary" style="width: 100%; margin-top: 1rem;">Save Product</button>
            </form>
        </div>
    </div>

    <!-- Content Modal (for admin) -->
    <div class="modal" id="contentModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 id="contentModalTitle">Add New Content</h3>
                <button class="close-modal" onclick="closeContentModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <form id="contentForm">
                <div class="form-group">
                    <label for="contentTitle">Title</label>
                    <input type="text" id="contentTitle" required>
                </div>
                <div class="form-group">
                    <label for="contentDescription">Description</label>
                    <textarea id="contentDescription" required></textarea>
                </div>
                <div class="form-group" id="contentDateGroup">
                    <label for="contentDate">Date</label>
                    <input type="date" id="contentDate">
                </div>
                <div class="form-group" id="contentPriceGroup">
                    <label for="contentPrice">Price (ZAR)</label>
                    <input type="number" id="contentPrice" step="0.01">
                </div>
                <div class="form-group" id="contentLocationGroup">
                    <label for="contentLocation">Location</label>
                    <input type="text" id="contentLocation">
                </div>
                <div class="form-group" id="contentTimeGroup">
                    <label for="contentTime">Time</label>
                    <input type="text" id="contentTime" placeholder="e.g., 9:00 AM - 4:00 PM">
                </div>
                
                <!-- Preview Section -->
                <div class="preview-section">
                    <h4>Preview</h4>
                    <div class="preview-content" id="contentPreview">
                        <p><strong>Content Preview:</strong> Your content will appear here as you type.</p>
                    </div>
                </div>
                
                <button type="submit" class="btn btn-primary" style="width: 100%; margin-top: 1rem;">Save Content</button>
            </form>
        </div>
    </div>

    <!-- Payment Modal -->
    <div class="modal" id="paymentModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Complete Your Purchase</h3>
                <button class="close-modal" onclick="closePaymentModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div id="paymentContent">
                <!-- Payment content will be dynamically added here -->
            </div>
        </div>
    </div>

    <!-- Preview Modal -->
    <div class="modal" id="previewModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 id="previewModalTitle">Content Preview</h3>
                <button class="close-modal" onclick="closePreviewModal()">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div id="previewContent">
                <!-- Preview content will be dynamically added here -->
            </div>
        </div>
    </div>

    <!-- Legal Modals -->
    <div class="modal" id="privacyModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Privacy Policy</h3>
                <button class="close-modal" onclick="closeModal('privacyModal')">×</button>
            </div>
            <div style="max-height: 400px; overflow-y: auto;">
                <h4>Information We Collect</h4>
                <p>We collect information you provide directly to us, such as when you create an account, make a purchase, or contact us for support.</p>
                
                <h4>How We Use Your Information</h4>
                <p>We use the information we collect to provide, maintain, and improve our services, process transactions, and communicate with you.</p>
                
                <h4>Information Sharing</h4>
                <p>We do not sell your personal information to third parties. We may share information with service providers who assist us in operating our website.</p>
                
                <h4>Your Rights</h4>
                <p>You have the right to access, correct, or delete your personal information. Contact us at privacy@definitiveword.org for assistance.</p>
            </div>
        </div>
    </div>

    <div class="modal" id="termsModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Terms of Service</h3>
                <button class="close-modal" onclick="closeModal('termsModal')">×</button>
            </div>
            <div style="max-height: 400px; overflow-y: auto;">
                <h4>Acceptance of Terms</h4>
                <p>By accessing and using this website, you accept and agree to be bound by the terms and provision of this agreement.</p>
                
                <h4>Use License</h4>
                <p>Permission is granted to temporarily access the materials on our website for personal, non-commercial transitory viewing only.</p>
                
                <h4>Products and Services</h4>
                <p>All products and services are subject to availability. We reserve the right to discontinue any product at any time.</p>
                
                <h4>Limitations</h4>
                <p>In no event shall The Definitive Word Ministry or its suppliers be liable for any damages arising out of the use or inability to use the materials on our website.</p>
            </div>
        </div>
    </div>

    <!-- Structured Data -->
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Organization",
      "name": "The Definitive Word Ministry",
      "description": "Your Destiny Has Been Written",
      "url": "https://yourdomain.com",
      "logo": "https://yourdomain.com/images/logo.png",
      "contactPoint": {
        "@type": "ContactPoint",
        "telephone": "+27-21-123-4567",
        "contactType": "customer service"
      }
    }
    </script>

    <script>
        // Backend API integration
        const API_BASE_URL = 'https://your-api-domain.com/api';
        const stripe = Stripe('pk_test_your_publishable_key_here');

        // Application State
        const state = {
            user: null,
            cart: [],
            wishlist: [],
            products: [
                {
                    id: 1,
                    name: "Unveiling Your Destiny",
                    description: "A comprehensive guide to discovering and walking in your God-given purpose.",
                    price: 299.99,
                    category: "ebook",
                    image: "📖",
                    inventory: 100,
                    sku: "EBK-001"
                },
                {
                    id: 2,
                    name: "Prophetic Insights",
                    description: "Understanding the prophetic voice in the modern church and your personal life.",
                    price: 349.99,
                    category: "ebook",
                    image: "🕊️",
                    inventory: 50,
                    sku: "EBK-002"
                },
                {
                    id: 3,
                    name: "The Written Word",
                    description: "Exploring the power of God's promises and declarations over your life.",
                    price: 269.99,
                    category: "ebook",
                    image: "✝️",
                    inventory: 75,
                    sku: "EBK-003"
                },
                {
                    id: 4,
                    name: "Prayer & Fasting Guide",
                    description: "A 21-day guide to deepening your prayer life through biblical fasting.",
                    price: 199.99,
                    category: "ebook",
                    image: "🙏",
                    inventory: 0,
                    sku: "EBK-004"
                }
            ],
            blogPosts: [
                {
                    id: 1,
                    title: "Walking in Your Prophetic Purpose",
                    description: "Discovering how to align your daily life with the prophetic words spoken over you...",
                    date: "2025-11-20",
                    content: "Full blog post content would go here..."
                },
                {
                    id: 2,
                    title: "The Power of Declared Destiny",
                    description: "Understanding how God's written word over your life shapes your future...",
                    date: "2025-11-15",
                    content: "Full blog post content would go here..."
                },
                {
                    id: 3,
                    title: "Breaking Through Limitations",
                    description: "Practical steps to overcome the barriers standing between you and your destiny...",
                    date: "2025-11-10",
                    content: "Full blog post content would go here..."
                }
            ],
            workshops: [
                {
                    id: 1,
                    title: "Prophetic Activation Workshop",
                    description: "A powerful one-day intensive designed to activate and strengthen your prophetic gifting. Learn to hear God's voice clearly and minister prophetically with confidence.",
                    date: "2025-12-15",
                    price: 499.99,
                    location: "Virtual (Zoom)",
                    time: "9:00 AM - 4:00 PM",
                    inventory: 20
                },
                {
                    id: 2,
                    title: "Destiny Mapping Masterclass",
                    description: "Discover God's blueprint for your life and create a practical roadmap to walk in your divine purpose. Limited to 20 participants for personalized attention.",
                    date: "2026-01-22",
                    price: 799.99,
                    location: "Cape Town, South Africa",
                    time: "6:00 PM - 9:00 PM",
                    inventory: 20
                }
            ],
            ministryInfo: [
                {
                    id: 1,
                    title: "Our Mission",
                    description: "To help believers understand that their destiny has already been written by God and equip them to walk confidently in their divine calling."
                },
                {
                    id: 2,
                    title: "Our Vision",
                    description: "To see every believer living out their God-given purpose through prophetic teaching, life coaching, and biblical resources."
                }
            ],
            users: [
                {
                    id: 1,
                    name: "Admin User",
                    email: "admin@definitiveword.org",
                    role: "admin",
                    password: "admin123"
                }
            ],
            orders: [],
            settings: {
                siteTitle: "The Definitive Word",
                siteTagline: "Your Destiny Has Been Written",
                primaryColor: "#1e3a8a",
                secondaryColor: "#dc2626"
            }
        };

        // DOM Elements
        const elements = {
            cartSidebar: document.getElementById('cartSidebar'),
            wishlistSidebar: document.getElementById('wishlistSidebar'),
            cartItems: document.getElementById('cartItems'),
            wishlistItems: document.getElementById('wishlistItems'),
            cartTotal: document.getElementById('cartTotal'),
            cartCount: document.querySelector('.cart-count'),
            wishlistCount: document.querySelector('.wishlist-count'),
            authModal: document.getElementById('authModal'),
            productModal: document.getElementById('productModal'),
            contentModal: document.getElementById('contentModal'),
            paymentModal: document.getElementById('paymentModal'),
            previewModal: document.getElementById('previewModal'),
            productsGrid: document.getElementById('productsGrid'),
            blogContainer: document.getElementById('blogContainer'),
            workshopsContainer: document.getElementById('workshopsContainer'),
            adminSection: document.getElementById('admin'),
            checkoutBtn: document.getElementById('checkoutBtn'),
            navContainer: document.getElementById('navContainer'),
            searchInput: document.getElementById('searchInput'),
            searchResults: document.getElementById('searchResults')
        };

        // Backend API functions
        async function fetchProducts() {
            try {
                const response = await fetch(`${API_BASE_URL}/products`);
                return await response.json();
            } catch (error) {
                console.error('Error fetching products:', error);
                return state.products;
            }
        }

        async function saveProduct(product) {
            try {
                const response = await fetch(`${API_BASE_URL}/products`, {
                    method: 'POST',
                    headers: { 
                        'Content-Type': 'application/json',
                        'X-CSRF-Token': getCSRFToken()
                    },
                    body: JSON.stringify(product)
                });
                return await response.json();
            } catch (error) {
                console.error('Error saving product:', error);
                throw error;
            }
        }

        async function authenticateUser(email, password) {
            try {
                const response = await fetch(`${API_BASE_URL}/auth/login`, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({ email, password })
                });
                return await response.json();
            } catch (error) {
                console.error('Authentication error:', error);
                throw error;
            }
        }

        async function processOrder(orderData) {
            try {
                const response = await fetch(`${API_BASE_URL}/orders`, {
                    method: 'POST',
                    headers: { 
                        'Content-Type': 'application/json',
                        'Authorization': `Bearer ${state.user.token}`
                    },
                    body: JSON.stringify(orderData)
                });
                return await response.json();
            } catch (error) {
                console.error('Order processing error:', error);
                throw error;
            }
        }

        async function sendOrderConfirmation(order) {
            try {
                await fetch(`${API_BASE_URL}/send-confirmation`, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({
                        to: order.customerEmail,
                        subject: `Order Confirmation - #${order.id}`,
                        order: order
                    })
                });
            } catch (error) {
                console.error('Email sending failed:', error);
            }
        }

        async function sendContactForm(data) {
            try {
                const response = await fetch(`${API_BASE_URL}/contact`, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(data)
                });
                return response.ok;
            } catch (error) {
                console.error('Contact form submission failed:', error);
                return false;
            }
        }

        async function handleImageUpload(event) {
            const file = event.target.files[0];
            if (!file) return;

            // Show preview
            const reader = new FileReader();
            reader.onload = function(e) {
                document.getElementById('imagePreview').innerHTML = `
                    <img src="${e.target.result}" style="max-width: 200px; max-height: 200px; border-radius: 5px;">
                `;
            };
            reader.readAsDataURL(file);

            // Upload to server
            const formData = new FormData();
            formData.append('image', file);

            try {
                const response = await fetch(`${API_BASE_URL}/upload`, {
                    method: 'POST',
                    body: formData
                });
                const { imageUrl } = await response.json();
                document.getElementById('productImage').value = imageUrl;
            } catch (error) {
                console.error('Image upload failed:', error);
                showNotification('Image upload failed', 'error');
            }
        }

        // Security functions
        function sanitizeInput(input) {
            const div = document.createElement('div');
            div.textContent = input;
            return div.innerHTML;
        }

        function safeRenderContent(content) {
            return content.replace(/</g, '&lt;').replace(/>/g, '&gt;');
        }

        function getCSRFToken() {
            return document.querySelector('meta[name="csrf-token"]').getAttribute('content');
        }

        // Cookie consent
        function checkCookieConsent() {
            if (!localStorage.getItem('cookiesAccepted')) {
                document.getElementById('cookieConsent').style.display = 'block';
            }
        }

        function acceptCookies() {
            localStorage.setItem('cookiesAccepted', 'true');
            document.getElementById('cookieConsent').style.display = 'none';
        }

        // Initialize the application
        function init() {
            renderProducts();
            renderBlogPosts();
            renderWorkshops();
            updateCartUI();
            updateWishlistUI();
            checkAuthState();
            loadSettings();
            checkCookieConsent();
            
            // Set up event listeners
            document.getElementById('loginForm').addEventListener('submit', handleLogin);
            document.getElementById('registerForm').addEventListener('submit', handleRegister);
            document.getElementById('contactForm').addEventListener('submit', handleContact);
            document.getElementById('productForm').addEventListener('submit', handleProductSubmit);
            document.getElementById('contentForm').addEventListener('submit', handleContentSubmit);
            
            // Add preview functionality
            document.getElementById('productName').addEventListener('input', updateProductPreview);
            document.getElementById('productDescription').addEventListener('input', updateProductPreview);
            document.getElementById('productPrice').addEventListener('input', updateProductPreview);
            document.getElementById('productCategory').addEventListener('change', updateProductPreview);
            
            document.getElementById('contentTitle').addEventListener('input', updateContentPreview);
            document.getElementById('contentDescription').addEventListener('input', updateContentPreview);
            document.getElementById('contentDate').addEventListener('input', updateContentPreview);
            document.getElementById('contentPrice').addEventListener('input', updateContentPreview);
            document.getElementById('contentLocation').addEventListener('input', updateContentPreview);
            document.getElementById('contentTime').addEventListener('input', updateContentPreview);

            // Search functionality
            elements.searchInput.addEventListener('input', handleSearch);
            elements.searchInput.addEventListener('focus', handleSearch);
            
            document.addEventListener('click', function(e) {
                if (!elements.searchResults.contains(e.target) && e.target !== elements.searchInput) {
                    elements.searchResults.style.display = 'none';
                }
            });

            // Check if user is admin
            if (state.user && state.user.role === 'admin') {
                showAdminPanel();
                renderAdminData();
            }

            // Initialize service worker for PWA
            if ('serviceWorker' in navigator) {
                navigator.serviceWorker.register('/sw.js')
                .then(function(registration) {
                    console.log('Service Worker registered with scope:', registration.scope);
                })
                .catch(function(error) {
                    console.log('Service Worker registration failed:', error);
                });
            }
        }

        // Search functionality
        function handleSearch(e) {
            const searchTerm = e.target.value.toLowerCase().trim();
            
            if (searchTerm.length === 0) {
                elements.searchResults.style.display = 'none';
                return;
            }
            
            if (searchTerm.length < 2) {
                elements.searchResults.style.display = 'none';
                return;
            }
            
            const results = [
                ...state.products.filter(p => 
                    p.name.toLowerCase().includes(searchTerm) || 
                    p.description.toLowerCase().includes(searchTerm)
                ).map(p => ({ ...p, type: 'product' })),
                ...state.blogPosts.filter(b => 
                    b.title.toLowerCase().includes(searchTerm) || 
                    b.description.toLowerCase().includes(searchTerm)
                ).map(b => ({ ...b, type: 'blog' })),
                ...state.workshops.filter(w => 
                    w.title.toLowerCase().includes(searchTerm) || 
                    w.description.toLowerCase().includes(searchTerm)
                ).map(w => ({ ...w, type: 'workshop' }))
            ];
            
            displaySearchResults(results);
        }

        function displaySearchResults(results) {
            if (results.length === 0) {
                elements.searchResults.innerHTML = '<div class="search-result-item">No results found</div>';
                elements.searchResults.style.display = 'block';
                return;
            }
            
            elements.searchResults.innerHTML = results.map(item => `
                <div class="search-result-item" onclick="handleSearchResultClick('${item.type}', ${item.id})">
                    <div class="search-result-icon">
                        ${item.type === 'product' ? '📖' : item.type === 'blog' ? '📝' : '🎓'}
                    </div>
                    <div>
                        <div style="font-weight: bold;">${item.title}</div>
                        <div style="font-size: 0.8rem; color: #6b7280;">${item.type.charAt(0).toUpperCase() + item.type.slice(1)}</div>
                    </div>
                </div>
            `).join('');
            
            elements.searchResults.style.display = 'block';
        }

        function handleSearchResultClick(type, id) {
            elements.searchResults.style.display = 'none';
            elements.searchInput.value = '';
            
            switch(type) {
                case 'product':
                    scrollToSection('products');
                    break;
                case 'blog':
                    scrollToSection('blog');
                    break;
                case 'workshop':
                    scrollToSection('workshops');
                    break;
            }
        }

        // Social sharing
        function shareOnFacebook() {
            const url = encodeURIComponent(window.location.href);
            const text = encodeURIComponent('Check out The Definitive Word Ministry!');
            window.open(`https://www.facebook.com/sharer/sharer.php?u=${url}&quote=${text}`, '_blank');
        }

        function shareOnTwitter() {
            const url = encodeURIComponent(window.location.href);
            const text = encodeURIComponent('Check out The Definitive Word Ministry!');
            window.open(`https://twitter.com/intent/tweet?url=${url}&text=${text}`, '_blank');
        }

        function shareOnLinkedIn() {
            const url = encodeURIComponent(window.location.href);
            window.open(`https://www.linkedin.com/sharing/share-offsite/?url=${url}`, '_blank');
        }

        function shareOnWhatsApp() {
            const text = encodeURIComponent('Check out The Definitive Word Ministry! ' + window.location.href);
            window.open(`https://wa.me/?text=${text}`, '_blank');
        }

        // The rest of the functions remain the same as in the previous implementation
        // (Navigation, Cart, Wishlist, Admin, Auth, etc.)
        // ... [Previous JavaScript code continues here with all the same functions]

        // Initialize the application when DOM is loaded
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
