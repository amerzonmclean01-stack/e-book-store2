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

        .btn-admin {
            background: var(--gold);
            color: var(--prophetic-blue);
            font-weight: 700;
        }

        .btn-admin:hover {
            background: #c19b2e;
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

        /* Admin Panel Styles */
        .admin-panel {
            background: var(--white);
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
        }

        .admin-actions {
            display: flex;
            gap: 1rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .admin-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
        }

        .admin-table th, .admin-table td {
            padding: 0.8rem;
            text-align: left;
            border-bottom: 1px solid #eee;
        }

        .admin-table th {
            background: var(--prophetic-blue);
            color: var(--white);
        }

        .admin-table tr:hover {
            background: var(--gray);
        }

        .action-buttons {
            display: flex;
            gap: 0.5rem;
        }

        .btn-edit {
            background: var(--warning);
            color: white;
            padding: 0.3rem 0.6rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        .btn-delete {
            background: var(--red);
            color: white;
            padding: 0.3rem 0.6rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        /* Preview Modal Styles */
        .preview-modal {
            max-width: 900px;
        }

        .preview-content {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .preview-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }

        .preview-body {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
        }

        .preview-cover {
            background: var(--light-blue);
            height: 300px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 8px;
            font-size: 4rem;
            color: var(--prophetic-blue);
        }

        .preview-details {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .preview-sample {
            background: var(--gray);
            padding: 1.5rem;
            border-radius: 8px;
            max-height: 300px;
            overflow-y: auto;
        }

        .preview-actions {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
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

            .preview-body {
                grid-template-columns: 1fr;
            }

            .admin-actions {
                flex-direction: column;
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
                    <button class="btn btn-admin btn-small" id="adminBtn" style="display: none;">
                        <i class="fas fa-cog"></i>Admin
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
                <span id="cartTotal">$0.00</span>
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
                    <label for="productPrice">Price ($)</label>
                    <input type="number" id="productPrice" class="form-control" step="0.01" min="0" required>
                </div>
                <div class="form-group">
                    <label for="productOriginalPrice">Original Price ($) - Leave empty if no discount</label>
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
        // Supabase Configuration
        const SUPABASE_URL = 'https://your-project.supabase.co';
        const SUPABASE_ANON_KEY = 'your-anon-key';
        
        // Initialize Supabase client
        const supabase = window.supabase.createClient(SUPABASE_URL, SUPABASE_ANON_KEY);

        // Sample Data (In a real app, this would come from Supabase)
        let sampleProducts = [
            {
                id: 1,
                name: "The Path to Enlightenment",
                description: "A comprehensive guide to spiritual growth and personal transformation. This ebook takes you on a journey through ancient wisdom and modern practices to help you find inner peace and purpose.",
                price: 24.99,
                originalPrice: 29.99,
                category: "Ebook",
                type: "ebook",
                badge: "Bestseller",
                featured: true,
                sample: "In the quiet moments of our lives, we often find ourselves searching for meaning. This journey of self-discovery is not about finding answers outside of ourselves, but rather uncovering the truth that has always been within. The path to enlightenment begins with a single step - the decision to look inward and listen to the quiet whispers of your soul..."
            },
            {
                id: 2,
                name: "Manifesting Your Destiny",
                description: "A 5-part video series on creating the life you desire through manifestation. Learn practical techniques to align your thoughts, emotions, and actions with your deepest desires.",
                price: 49.99,
                category: "Workshop",
                type: "video",
                badge: "New",
                featured: true,
                sample: "Welcome to Manifesting Your Destiny. In this first module, we'll explore the fundamental principles of manifestation. Many people misunderstand manifestation as simply 'wishing for things to happen.' In reality, it's a sophisticated process of aligning your energy, beliefs, and actions with your desired outcomes. The universe responds not to what we want, but to who we become in the process of pursuing our desires..."
            },
            {
                id: 3,
                name: "Daily Reflection Journal",
                description: "Printable journal with prompts for daily self-reflection and growth tracking. This resource helps you develop consistency in your personal development practice.",
                price: 12.99,
                category: "Resource",
                type: "pdf",
                featured: true,
                sample: "Morning Reflection: What am I grateful for today? What intention will I set for this day? How can I show up as my best self? Evening Reflection: What went well today? What challenges did I face and how did I handle them? What did I learn about myself? What can I improve tomorrow?"
            },
            {
                id: 4,
                name: "Meditation Series",
                description: "Guided meditation sessions for stress relief, focus, and inner peace. Perfect for beginners and experienced practitioners alike.",
                price: 19.99,
                category: "Audio",
                type: "audio",
                badge: "Popular",
                featured: true,
                sample: "Find a comfortable position, either sitting or lying down. Close your eyes and bring your awareness to your breath. Notice the natural rhythm of your breathing without trying to change it. As you breathe in, imagine you're breathing in peace and calm. As you breathe out, imagine you're releasing any tension or stress. Continue to follow your breath, allowing your body to relax more with each exhale..."
            },
            {
                id: 5,
                name: "Financial Freedom Blueprint",
                description: "Step-by-step guide to achieving financial independence and security. Learn proven strategies for budgeting, investing, and wealth building.",
                price: 34.99,
                category: "Ebook",
                type: "ebook",
                featured: false,
                sample: "Financial freedom isn't about being rich - it's about having choices. It's the ability to make decisions based on what you want, not what you can afford. This blueprint will guide you through the fundamental principles of wealth building, starting with mindset shifts that are essential for long-term financial success. We'll debunk common myths about money and replace them with practical, actionable strategies..."
            },
            {
                id: 6,
                name: "Relationship Mastery",
                description: "Workshop on building healthy, fulfilling relationships in all areas of life. Transform your connections with practical communication tools.",
                price: 39.99,
                category: "Workshop",
                type: "video",
                featured: false,
                sample: "Healthy relationships are the foundation of a fulfilling life. In this workshop, we'll explore the key elements that make relationships thrive. Communication is often cited as the most important factor, but what does effective communication really look like? It's not just about speaking clearly - it's about listening deeply, understanding non-verbal cues, and creating emotional safety for authentic expression..."
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
        const previewModal = document.getElementById('previewModal');
        const productModal = document.getElementById('productModal');
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
        const productForm = document.getElementById('productForm');
        const loginSubmitBtn = document.getElementById('loginSubmitBtn');
        const signupSubmitBtn = document.getElementById('signupSubmitBtn');
        const productSubmitBtn = document.getElementById('productSubmitBtn');
        const toast = document.getElementById('toast');
        const toastMessage = document.getElementById('toastMessage');
        const authButtons = document.getElementById('authButtons');
        const userMenu = document.getElementById('userMenu');
        const userAvatar = document.getElementById('userAvatar');
        const userName = document.getElementById('userName');
        const dashboardBtn = document.getElementById('dashboardBtn');
        const adminBtn = document.getElementById('adminBtn');
        const logoutBtn = document.getElementById('logoutBtn');
        const exploreProductsBtn = document.getElementById('exploreProductsBtn');
        const joinCommunityBtn = document.getElementById('joinCommunityBtn');
        const featuredProductsContainer = document.getElementById('featuredProducts');
        const allProductsContainer = document.getElementById('allProducts');
        const userPurchasesContainer = document.getElementById('userPurchases');
        const adminProductsTable = document.getElementById('adminProductsTable');
        const addProductBtn = document.getElementById('addProductBtn');
        const refreshProductsBtn = document.getElementById('refreshProductsBtn');
        const navLinks = document.querySelectorAll('.nav-link');
        const dashboardNavLinks = document.querySelectorAll('.dashboard-nav-link');
        const dashboardTabs = document.querySelectorAll('.dashboard-tab');
        const homePage = document.getElementById('homePage');
        const productsPage = document.getElementById('productsPage');
        const dashboardPage = document.getElementById('dashboardPage');
        const adminPage = document.getElementById('adminPage');
        const aboutPage = document.getElementById('aboutPage');
        const dashboardUserName = document.getElementById('dashboardUserName');
        const settingsForm = document.getElementById('settingsForm');
        const previewContent = document.getElementById('previewContent');
        const productModalTitle = document.getElementById('productModalTitle');

        // App State
        let currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;
        let cart = JSON.parse(localStorage.getItem('cart')) || [];
        let isAdmin = false;

        // Initialize the application
        function init() {
            updateCartUI();
            setupEventListeners();
            loadProducts();
            checkAuthState();
            
            // Check if user is admin (in a real app, this would check user role from Supabase)
            const urlParams = new URLSearchParams(window.location.search);
            if (urlParams.get('admin') === 'true' || localStorage.getItem('isAdmin') === 'true') {
                isAdmin = true;
                localStorage.setItem('isAdmin', 'true');
                if (currentUser) {
                    adminBtn.style.display = 'inline-flex';
                }
            }
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
            productForm.addEventListener('submit', handleProductSave);

            // Auth buttons
            dashboardBtn.addEventListener('click', () => showPage('dashboard'));
            adminBtn.addEventListener('click', () => showPage('admin'));
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

            // Admin buttons
            addProductBtn.addEventListener('click', () => openProductModal());
            refreshProductsBtn.addEventListener('click', loadProducts);
        }

        // Check authentication state and update UI
        function checkAuthState() {
            if (currentUser) {
                authButtons.style.display = 'none';
                userMenu.style.display = 'flex';
                userName.textContent = currentUser.name;
                dashboardUserName.textContent = currentUser.name;
                userAvatar.textContent = currentUser.name.charAt(0).toUpperCase();
                
                if (isAdmin) {
                    adminBtn.style.display = 'inline-flex';
                }
                
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
            adminPage.style.display = 'none';
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
                case 'admin':
                    if (currentUser && isAdmin) {
                        adminPage.style.display = 'block';
                        loadAdminProducts();
                    } else {
                        showToast('Admin access required', 'error');
                        showPage('home');
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
            
            if (isAdmin && adminPage.style.display !== 'none') {
                loadAdminProducts();
            }
        }

        // Render products to the DOM
        function renderProducts(products, container) {
            container.innerHTML = '';
            
            if (products.length === 0) {
                container.innerHTML = '<p>No products found.</p>';
                return;
            }
            
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
                    showProductPreview(id);
                });
            });
        }

        // Show product preview
        function showProductPreview(productId) {
            const product = sampleProducts.find(p => p.id == productId);
            if (!product) {
                showToast('Product not found', 'error');
                return;
            }
            
            previewContent.innerHTML = `
                <div class="preview-header">
                    <h3>Preview: ${product.name}</h3>
                    <span class="product-category">${product.category}</span>
                </div>
                <div class="preview-body">
                    <div class="preview-cover">
                        <i class="fas ${getProductIcon(product.type)}"></i>
                    </div>
                    <div class="preview-details">
                        <h4>About This ${product.category}</h4>
                        <p>${product.description}</p>
                        <div class="product-price">
                            ${product.originalPrice ? `<span class="original-price">$${product.originalPrice.toFixed(2)}</span>` : ''}
                            $${product.price.toFixed(2)}
                        </div>
                        <div class="preview-sample">
                            <h5>Sample Content</h5>
                            <p>${product.sample}</p>
                        </div>
                        <div class="preview-actions">
                            <button class="btn btn-primary add-to-cart-preview" data-id="${product.id}" data-name="${product.name}" data-price="${product.price}">
                                <i class="fas fa-cart-plus"></i>Add to Cart
                            </button>
                            <button class="btn btn-outline" onclick="closeModal(previewModal)">
                                Continue Browsing
                            </button>
                        </div>
                    </div>
                </div>
            `;
            
            // Add event listener to preview add to cart button
            previewContent.querySelector('.add-to-cart-preview').addEventListener('click', function() {
                const id = this.getAttribute('data-id');
                const name = this.getAttribute('data-name');
                const price = this.getAttribute('data-price');
                
                addToCart(id, name, price);
                showToast('Product added to cart!', 'success');
                closeModal(previewModal);
            });
            
            openModal(previewModal);
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

        // Load admin products table
        function loadAdminProducts() {
            adminProductsTable.innerHTML = '';
            
            if (sampleProducts.length === 0) {
                adminProductsTable.innerHTML = '<tr><td colspan="6">No products found.</td></tr>';
                return;
            }
            
            sampleProducts.forEach(product => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${product.id}</td>
                    <td>${product.name}</td>
                    <td>${product.category}</td>
                    <td>$${product.price.toFixed(2)}</td>
                    <td>${product.featured ? 'Featured' : 'Standard'}</td>
                    <td class="action-buttons">
                        <button class="btn-edit" data-id="${product.id}">
                            <i class="fas fa-edit"></i> Edit
                        </button>
                        <button class="btn-delete" data-id="${product.id}">
                            <i class="fas fa-trash"></i> Delete
                        </button>
                    </td>
                `;
                
                adminProductsTable.appendChild(row);
            });
            
            // Add event listeners to admin action buttons
            adminProductsTable.querySelectorAll('.btn-edit').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    openProductModal(id);
                });
            });
            
            adminProductsTable.querySelectorAll('.btn-delete').forEach(button => {
                button.addEventListener('click', function() {
                    const id = this.getAttribute('data-id');
                    deleteProduct(id);
                });
            });
        }

        // Open product modal for adding/editing
        function openProductModal(productId = null) {
            // Reset form
            productForm.reset();
            productModalTitle.textContent = productId ? 'Edit Product' : 'Add New Product';
            
            if (productId) {
                // Edit existing product
                const product = sampleProducts.find(p => p.id == productId);
                if (product) {
                    document.getElementById('productId').value = product.id;
                    document.getElementById('productName').value = product.name;
                    document.getElementById('productDescription').value = product.description;
                    document.getElementById('productCategory').value = product.category;
                    document.getElementById('productType').value = product.type;
                    document.getElementById('productPrice').value = product.price;
                    document.getElementById('productOriginalPrice').value = product.originalPrice || '';
                    document.getElementById('productBadge').value = product.badge || '';
                    document.getElementById('productFeatured').checked = product.featured;
                    document.getElementById('productSample').value = product.sample || '';
                }
            } else {
                // Add new product
                document.getElementById('productId').value = '';
            }
            
            openModal(productModal);
        }

        // Handle product save (add or update)
        function handleProductSave(e) {
            e.preventDefault();
            
            const productId = document.getElementById('productId').value;
            const name = document.getElementById('productName').value;
            const description = document.getElementById('productDescription').value;
            const category = document.getElementById('productCategory').value;
            const type = document.getElementById('productType').value;
            const price = parseFloat(document.getElementById('productPrice').value);
            const originalPrice = document.getElementById('productOriginalPrice').value ? 
                parseFloat(document.getElementById('productOriginalPrice').value) : null;
            const badge = document.getElementById('productBadge').value || null;
            const featured = document.getElementById('productFeatured').checked;
            const sample = document.getElementById('productSample').value;
            
            if (productId) {
                // Update existing product
                const index = sampleProducts.findIndex(p => p.id == productId);
                if (index !== -1) {
                    sampleProducts[index] = {
                        ...sampleProducts[index],
                        name,
                        description,
                        category,
                        type,
                        price,
                        originalPrice,
                        badge,
                        featured,
                        sample
                    };
                }
            } else {
                // Add new product
                const newId = Math.max(...sampleProducts.map(p => p.id)) + 1;
                sampleProducts.push({
                    id: newId,
                    name,
                    description,
                    category,
                    type,
                    price,
                    originalPrice,
                    badge,
                    featured,
                    sample
                });
            }
            
            showToast(`Product ${productId ? 'updated' : 'added'} successfully!`, 'success');
            closeModal(productModal);
            loadProducts();
        }

        // Delete product
        function deleteProduct(productId) {
            if (confirm('Are you sure you want to delete this product?')) {
                sampleProducts = sampleProducts.filter(p => p.id != productId);
                showToast('Product deleted successfully!', 'success');
                loadProducts();
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
                const product = sampleProducts.find(p => p.id === purchase.productId);
                if (!product) return;
                
                const purchaseCard = document.createElement('div');
                purchaseCard.className = 'purchase-card';
                
                purchaseCard.innerHTML = `
                    <div class="purchase-image">
                        <i class="fas ${getProductIcon(product.type)}"></i>
                    </div>
                    <div class="purchase-details">
                        <h4>${product.name}</h4>
                        <p>Purchased on: ${new Date(purchase.purchaseDate).toLocaleDateString()}</p>
                        <p>Price: $${purchase.price.toFixed(2)}</p>
                        <div class="progress-bar">
                            <div class="progress-fill" style="width: ${purchase.progress}%"></div>
                        </div>
                        <small>Progress: ${purchase.progress}%</small>
                        <div style="margin-top: 1rem;">
                            <button class="btn btn-outline btn-small" onclick="accessProduct(${product.id})">
                                <i class="fas fa-play"></i> Access Content
                            </button>
                        </div>
                    </div>
                `;
                
                userPurchasesContainer.appendChild(purchaseCard);
            });
        }

        // Access purchased product
        function accessProduct(productId) {
            const product = sampleProducts.find(p => p.id === productId);
            if (product) {
                showToast(`Opening ${product.name}...`, 'success');
                // In a real app, this would redirect to the product content page
                // or open the PDF/video/audio content
            }
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
            isAdmin = false;
            localStorage.removeItem('currentUser');
            localStorage.removeItem('isAdmin');
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
