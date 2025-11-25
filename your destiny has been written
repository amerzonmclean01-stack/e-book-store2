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

        /* High Contrast Mode */
        body.high-contrast {
            --white: #000000;
            --dark-blue: #FFFFFF;
            --gray: #1a1a1a;
            --light-blue: #2a2a2a;
            --prophetic-blue: #FFFFFF;
            color: #FFFFFF;
            background-color: #000000;
        }

        body.high-contrast .product-card,
        body.high-contrast .feature-card,
        body.high-contrast .dashboard-sidebar,
        body.high-contrast .dashboard-content,
        body.high-contrast .modal-content {
            background: #1a1a1a;
            border: 2px solid #FFFFFF;
        }

        /* Reduced Motion */
        @media (prefers-reduced-motion: reduce) {
            * {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
            }
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

        @keyframes ripple {
            to {
                transform: scale(4);
                opacity: 0;
            }
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Loading Animation */
        .loading-shimmer {
            animation: shimmer 1.5s infinite linear;
            background: linear-gradient(to right, #f6f7f8 8%, #edeef1 18%, #f6f7f8 33%);
            background-size: 800px 104px;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Skip to main content link */
        .skip-link {
            position: absolute;
            top: -40px;
            left: 6px;
            background: var(--gold);
            color: var(--prophetic-blue);
            padding: 8px;
            text-decoration: none;
            border-radius: 4px;
            z-index: 10000;
            font-weight: bold;
        }

        .skip-link:focus {
            top: 6px;
        }

        /* Accessibility Controls */
        .accessibility-controls {
            position: fixed;
            top: 80px;
            right: 20px;
            background: var(--white);
            border: 2px solid var(--gold);
            border-radius: 8px;
            padding: 1rem;
            z-index: 1000;
            box-shadow: var(--shadow-lg);
            display: none;
            animation: fadeInUp 0.3s ease-out;
        }

        .accessibility-controls.show {
            display: block;
        }

        .accessibility-toggle {
            position: fixed;
            top: 80px;
            right: 20px;
            background: var(--gold);
            color: var(--prophetic-blue);
            border: none;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            font-size: 1.5rem;
            cursor: pointer;
            z-index: 1001;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
        }

        .accessibility-toggle:hover {
            transform: scale(1.1);
        }

        .control-group {
            margin-bottom: 1rem;
        }

        .control-group h4 {
            margin-bottom: 0.5rem;
            color: var(--prophetic-blue);
        }

        .control-buttons {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
        }

        .btn-accessibility {
            padding: 0.5rem;
            border: 1px solid var(--gold);
            background: var(--white);
            color: var(--dark-blue);
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: var(--transition);
        }

        .btn-accessibility.active {
            background: var(--gold);
            color: var(--prophetic-blue);
        }

        .btn-accessibility:hover {
            transform: translateY(-2px);
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

        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
            font-family: 'Playfair Display', serif;
        }

        .logo span {
            color: var(--gold);
        }

        .currency-selector {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-left: 1rem;
            color: var(--white);
        }

        .currency-selector select {
            background: transparent;
            border: 1px solid var(--gold);
            color: var(--white);
            padding: 0.3rem;
            border-radius: 4px;
        }

        .currency-selector option {
            background: var(--prophetic-blue);
            color: var(--white);
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
            transition: var(--transition);
        }

        .user-avatar:hover {
            transform: scale(1.1);
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

        .btn:focus {
            outline: none;
            box-shadow: var(--focus-ring);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--gold);
            color: var(--gold);
        }

        .btn-outline:hover, .btn-outline:focus {
            background: var(--gold);
            color: var(--prophetic-blue);
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--red), #9c1a1a);
            color: var(--white);
        }

        .btn-primary:hover, .btn-primary:focus {
            background: linear-gradient(135deg, #9c1a1a, var(--red));
        }

        .btn-gold {
            background: linear-gradient(135deg, var(--gold), #b8941f);
            color: var(--prophetic-blue);
            font-weight: 700;
        }

        .btn-gold:hover, .btn-gold:focus {
            background: linear-gradient(135deg, #b8941f, var(--gold));
            transform: translateY(-3px) scale(1.05);
        }

        .btn-admin {
            background: var(--gold);
            color: var(--prophetic-blue);
            font-weight: 700;
        }

        .btn-admin:hover, .btn-admin:focus {
            background: #c19b2e;
            transform: translateY(-2px);
        }

        .btn-small {
            padding: 0.5rem 1rem;
            font-size: 0.9rem;
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

        /* Quick Actions */
        .quick-actions {
            background: var(--light-blue);
            padding: 1rem 0;
            border-bottom: 1px solid #ddd;
        }

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

        @media (prefers-reduced-motion: reduce) {
            .hero {
                background-attachment: scroll;
            }
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

        /* Products Section */
        .section-title {
            text-align: center;
            margin: 4rem 0 3rem;
            font-size: 2.5rem;
            color: var(--prophetic-blue);
            position: relative;
            font-family: 'Playfair Display', serif;
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

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        /* Enhanced Product Cards */
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
            font-family: 'Playfair Display', serif;
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
            outline: none;
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
            outline: none;
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
            box-shadow: var(--shadow-md);
            transition: var(--transition);
        }

        .dashboard-sidebar:hover {
            transform: translateY(-5px);
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
            transition: var(--transition);
        }

        .dashboard-nav a:hover, .dashboard-nav a:focus, .dashboard-nav a.active {
            background: var(--prophetic-blue);
            color: var(--white);
            outline: none;
            transform: translateX(5px);
        }

        .dashboard-content {
            background: var(--white);
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
        }

        .dashboard-content:hover {
            transform: translateY(-5px);
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
            transition: var(--transition);
        }

        .purchase-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-md);
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

        /* Admin Panel Styles */
        .admin-panel {
            background: var(--white);
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
        }

        .admin-panel:hover {
            transform: translateY(-5px);
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

        .admin-table tr {
            transition: var(--transition);
        }

        .admin-table tr:hover {
            background: var(--gray);
            transform: translateX(5px);
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
            transition: var(--transition);
        }

        .btn-edit:hover {
            transform: scale(1.05);
        }

        .btn-delete {
            background: var(--red);
            color: white;
            padding: 0.3rem 0.6rem;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: var(--transition);
        }

        .btn-delete:hover {
            transform: scale(1.05);
        }

        /* Enhanced Features Section */
        .features {
            background: var(--gray);
            padding: 4rem 0;
        }

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

        .feature-title {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--prophetic-blue);
            font-family: 'Playfair Display', serif;
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

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
            position: relative;
            z-index: 1;
        }

        .footer-column h3 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            color: var(--gold);
            position: relative;
            padding-bottom: 0.5rem;
            font-family: 'Playfair Display', serif;
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
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.2rem 0;
        }

        .footer-column a:hover, .footer-column a:focus {
            color: var(--gold);
            transform: translateX(5px);
            outline: none;
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
            outline: none;
        }

        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: var(--dark-gray);
            position: relative;
            z-index: 1;
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

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
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
            outline: none;
        }

        .modal-title {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--prophetic-blue);
            text-align: center;
            font-family: 'Playfair Display', serif;
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

        .form-footer {
            text-align: center;
            margin-top: 1.5rem;
        }

        .form-footer a {
            color: var(--prophetic-blue);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
        }

        .form-footer a:hover, .form-footer a:focus {
            text-decoration: underline;
            outline: none;
            color: var(--gold);
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
            transition: var(--transition);
        }

        .cart-item:hover {
            background: var(--gray);
            transform: translateX(5px);
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
            transition: var(--transition);
            padding: 0.5rem;
            border-radius: 4px;
        }

        .cart-item-remove:hover, .cart-item-remove:focus {
            transform: scale(1.1);
            background: rgba(185, 28, 28, 0.1);
            outline: none;
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

        /* Enhanced Toast Notification */
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

        /* Keyboard Shortcuts Help */
        .keyboard-shortcuts {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: var(--white);
            border: 2px solid var(--gold);
            border-radius: 8px;
            padding: 1rem;
            z-index: 1000;
            box-shadow: var(--shadow-lg);
            display: none;
            max-width: 300px;
            animation: fadeInUp 0.3s ease-out;
        }

        .keyboard-shortcuts.show {
            display: block;
        }

        .keyboard-toggle {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: var(--gold);
            color: var(--prophetic-blue);
            border: none;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            font-size: 1.2rem;
            cursor: pointer;
            z-index: 1001;
            box-shadow: var(--shadow-md);
            transition: var(--transition);
        }

        .keyboard-toggle:hover {
            transform: scale(1.1);
        }

        .shortcut-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
            padding-bottom: 0.5rem;
            border-bottom: 1px solid #eee;
        }

        .shortcut-key {
            background: var(--gray);
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            font-family: monospace;
            font-weight: bold;
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
            transition: var(--transition);
        }

        .preview-cover:hover {
            transform: scale(1.02);
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
            transition: var(--transition);
        }

        .preview-sample:hover {
            transform: translateY(-5px);
        }

        .preview-actions {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        /* Checkout Modal */
        #card-element {
            padding: 1rem;
            border: 2px solid #e5e7eb;
            border-radius: 8px;
            transition: var(--transition);
        }

        #card-element:focus {
            border-color: var(--prophetic-blue);
            box-shadow: 0 0 0 3px rgba(30, 58, 138, 0.1);
        }

        /* Pulse Animation for Special Elements */
        .pulse-gold {
            animation: pulse 2s infinite;
            box-shadow: 0 0 0 0 rgba(212, 175, 55, 0.7);
        }

        .pulse-gold:hover {
            animation: none;
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

        /* ===== ADMIN FEATURES ===== */
        
        /* Admin Mode Indicator */
        .admin-mode-indicator {
            position: fixed;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--gold);
            color: var(--prophetic-blue);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            z-index: 1001;
            display: none;
        }

        body.admin-mode .admin-mode-indicator {
            display: block;
        }

        /* Admin Quick Actions */
        .admin-quick-actions {
            position: fixed;
            top: 50%;
            right: 0;
            transform: translateY(-50%);
            z-index: 999;
            display: none;
            flex-direction: column;
            gap: 10px;
            padding: 10px;
            background: rgba(30, 58, 138, 0.9);
            border-radius: 10px 0 0 10px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .admin-quick-actions.collapsed {
            transform: translateY(-50%) translateX(90%);
        }

        .admin-toggle {
            position: absolute;
            left: -40px;
            top: 50%;
            transform: translateY(-50%);
            background: var(--gold);
            color: var(--prophetic-blue);
            border: none;
            border-radius: 5px 0 0 5px;
            padding: 10px 5px;
            cursor: pointer;
            font-size: 1.2rem;
            transition: all 0.3s ease;
        }

        .admin-quick-actions.collapsed .admin-toggle {
            left: -35px;
        }

        .admin-action-btn {
            background: var(--white);
            border: none;
            border-radius: 5px;
            padding: 10px;
            cursor: pointer;
            color: var(--prophetic-blue);
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1rem;
            position: relative;
        }

        .admin-action-btn:hover {
            background: var(--gold);
            transform: scale(1.1);
        }

        .admin-action-btn .tooltip {
            position: absolute;
            right: 100%;
            top: 50%;
            transform: translateY(-50%);
            background: var(--dark-blue);
            color: white;
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            white-space: nowrap;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease;
            margin-right: 10px;
        }

        .admin-action-btn:hover .tooltip {
            opacity: 1;
        }

        /* Quick Edit Mode */
        body.quick-edit-mode .product-card,
        body.quick-edit-mode .feature-card {
            position: relative;
            cursor: pointer;
        }

        body.quick-edit-mode .product-card::before,
        body.quick-edit-mode .feature-card::before {
            content: '✏️ Click to Edit';
            position: absolute;
            top: 10px;
            left: 10px;
            background: var(--gold);
            color: var(--prophetic-blue);
            padding: 5px 10px;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: bold;
            z-index: 10;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        body.quick-edit-mode .product-card:hover::before,
        body.quick-edit-mode .feature-card:hover::before {
            opacity: 1;
        }

        /* Admin Context Menu */
        .admin-context-menu {
            position: fixed;
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.15);
            z-index: 10000;
            padding: 10px 0;
            min-width: 150px;
            display: none;
        }

        .admin-context-menu button {
            width: 100%;
            border: none;
            background: none;
            padding: 10px 15px;
            text-align: left;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .admin-context-menu button:hover {
            background: var(--light-blue);
        }

        /* Quick Stats */
        .admin-quick-stats {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: var(--white);
            border: 2px solid var(--gold);
            border-radius: 10px;
            padding: 15px;
            z-index: 998;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
            display: none;
        }

        .admin-quick-stats.show {
            display: block;
        }

        .stats-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-size: 0.9rem;
        }

        .stats-item:last-child {
            margin-bottom: 0;
        }

        /* Enhanced Admin Panel */
        .admin-panel-quick-actions {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 20px;
        }

        .admin-quick-card {
            background: var(--white);
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .admin-quick-card:hover {
            border-color: var(--gold);
            transform: translateY(-5px);
        }

        .admin-quick-card i {
            font-size: 2rem;
            color: var(--gold);
            margin-bottom: 10px;
        }

        /* Bulk Actions */
        .bulk-actions {
            display: none;
            align-items: center;
            gap: 10px;
            margin-bottom: 20px;
            padding: 15px;
            background: var(--light-blue);
            border-radius: 8px;
        }

        .bulk-actions.show {
            display: flex;
        }

        /* Product Selection */
        .product-select-checkbox {
            position: absolute;
            top: 10px;
            left: 10px;
            z-index: 6;
            display: none;
        }

        body.bulk-edit-mode .product-select-checkbox {
            display: block;
        }

        /* Responsive Admin Controls */
        @media (max-width: 768px) {
            .admin-quick-actions {
                flex-direction: row;
                top: auto;
                bottom: 0;
                right: 50%;
                transform: translateX(50%);
                border-radius: 10px 10px 0 0;
                width: 90%;
            }

            .admin-quick-actions.collapsed {
                transform: translateX(50%) translateY(90%);
            }

            .admin-toggle {
                left: 50%;
                top: -35px;
                transform: translateX(-50%);
                border-radius: 5px 5px 0 0;
                padding: 5px 10px;
            }

            .admin-quick-actions.collapsed .admin-toggle {
                top: -30px;
            }
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

            .currency-selector {
                margin-left: 0;
                margin-top: 0.5rem;
            }

            .quick-actions-grid {
                grid-template-columns: 1fr;
            }

            .accessibility-controls {
                top: 120px;
                right: 10px;
                left: 10px;
            }

            .accessibility-toggle {
                top: 120px;
            }

            .keyboard-shortcuts {
                left: 10px;
                right: 10px;
                max-width: none;
            }
        }

        @media (max-width: 480px) {
            .hero h2 {
                font-size: 2rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .modal-content {
                padding: 1.5rem;
            }
        }

        /* Print Styles */
        @media print {
            .accessibility-toggle,
            .keyboard-toggle,
            .cart-icon,
            .auth-buttons,
            .user-menu,
            .quick-actions,
            footer {
                display: none !important;
            }

            .product-actions {
                display: none;
            }

            body {
                background: white !important;
                color: black !important;
                font-size: 12pt;
            }

            .product-card {
                break-inside: avoid;
                box-shadow: none !important;
                border: 1px solid #ddd !important;
            }
        }
    </style>
</head>
<body>
    <!-- Admin Mode Indicator -->
    <div class="admin-mode-indicator">
        <i class="fas fa-crown"></i> Admin Mode Active
    </div>

    <!-- Admin Quick Actions -->
    <div class="admin-quick-actions" id="adminQuickActions">
        <button class="admin-toggle" id="adminToggle">
            <i class="fas fa-cog"></i>
        </button>
        <button class="admin-action-btn" id="toggleEditMode" title="Toggle Quick Edit">
            <i class="fas fa-edit"></i>
            <span class="tooltip">Quick Edit Mode</span>
        </button>
        <button class="admin-action-btn" id="addNewProduct" title="Add New Product">
            <i class="fas fa-plus"></i>
            <span class="tooltip">Add Product</span>
        </button>
        <button class="admin-action-btn" id="viewStats" title="View Stats">
            <i class="fas fa-chart-bar"></i>
            <span class="tooltip">View Stats</span>
        </button>
        <button class="admin-action-btn" id="goToAdminPanel" title="Admin Panel">
            <i class="fas fa-tachometer-alt"></i>
            <span class="tooltip">Admin Panel</span>
        </button>
    </div>

    <!-- Admin Quick Stats -->
    <div class="admin-quick-stats" id="adminQuickStats">
        <h4>Store Stats</h4>
        <div class="stats-item">
            <span>Total Products:</span>
            <span id="statsTotalProducts">0</span>
        </div>
        <div class="stats-item">
            <span>Featured Products:</span>
            <span id="statsFeaturedProducts">0</span>
        </div>
        <div class="stats-item">
            <span>Total Sales:</span>
            <span id="statsTotalSales">R 0.00</span>
        </div>
        <div class="stats-item">
            <span>Active Users:</span>
            <span id="statsActiveUsers">0</span>
        </div>
    </div>

    <!-- Admin Context Menu -->
    <div class="admin-context-menu" id="adminContextMenu">
        <button data-action="edit"><i class="fas fa-edit"></i> Edit Product</button>
        <button data-action="toggle-featured"><i class="fas fa-star"></i> Toggle Featured</button>
        <button data-action="duplicate"><i class="fas fa-copy"></i> Duplicate</button>
        <button data-action="delete"><i class="fas fa-trash"></i> Delete</button>
    </div>

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
        <div class="shortcut-item" style="display: none;" id="adminShortcut">
            <span>Admin Mode</span>
            <kbd class="shortcut-key">Ctrl+E</kbd>
        </div>
    </div>

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

        <!-- Enhanced Admin Page -->
        <section id="adminPage" style="display: none;">
            <div class="dashboard">
                <div class="container">
                    <div class="dashboard-header">
                        <h2 class="section-title">Admin Panel</h2>
                        <div class="user-info">
                            <span>Manage your store content</span>
                        </div>
                    </div>
                    
                    <!-- Quick Actions Cards -->
                    <div class="admin-panel-quick-actions">
                        <div class="admin-quick-card" data-action="add-product">
                            <i class="fas fa-plus-circle"></i>
                            <h4>Add New Product</h4>
                            <p>Create a new product listing</p>
                        </div>
                        <div class="admin-quick-card" data-action="bulk-edit">
                            <i class="fas fa-edit"></i>
                            <h4>Bulk Edit</h4>
                            <p>Edit multiple products at once</p>
                        </div>
                        <div class="admin-quick-card" data-action="view-analytics">
                            <i class="fas fa-chart-line"></i>
                            <h4>View Analytics</h4>
                            <p>See store performance</p>
                        </div>
                        <div class="admin-quick-card" data-action="manage-users">
                            <i class="fas fa-users"></i>
                            <h4>Manage Users</h4>
                            <p>View and manage customers</p>
                        </div>
                    </div>

                    <!-- Bulk Actions Bar -->
                    <div class="bulk-actions" id="bulkActions">
                        <span id="selectedCount">0 products selected</span>
                        <button class="btn btn-outline btn-small" id="bulkFeatured">Toggle Featured</button>
                        <button class="btn btn-outline btn-small" id="bulkDelete">Delete Selected</button>
                        <button class="btn btn-outline btn-small" id="bulkCancel">Cancel</button>
                    </div>

                    <div class="admin-panel">
                        <div class="admin-actions">
                            <button class="btn btn-primary" id="addProductBtn">
                                <i class="fas fa-plus"></i>Add New Product
                            </button>
                            <button class="btn btn-outline" id="toggleBulkEdit">
                                <i class="fas fa-object-group"></i>Bulk Edit
                            </button>
                            <button class="btn btn-outline" id="refreshProductsBtn">
                                <i class="fas fa-sync"></i>Refresh Products
                            </button>
                        </div>
                        <h3>Product Management</h3>
                        <table class="admin-table">
                            <thead>
                                <tr>
                                    <th><input type="checkbox" id="selectAllProducts"></th>
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
        // Enhanced store with full functionality, animations, Stripe integration, and ADMIN FEATURES
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

        // ADMIN STATE
        let isAdminMode = false;
        let isQuickEditMode = false;
        let isBulkEditMode = false;
        let selectedProducts = new Set();
        let currentContextProduct = null;

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
                    enableAdminMode();
                }
            }
            
            // Load saved preferences
            loadSavedPreferences();
            
            // Initialize animations
            initScrollAnimations();
            initHeaderScroll();
            initHoverEffects();
        }

        // Set up all event listeners
        function setupEventListeners() {
            // Navigation
            document.querySelectorAll('.nav-link').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const page = this.getAttribute('data-page');
                    showPageWithTransition(page);
                });
            });

            // Auth buttons
            document.getElementById('loginBtn').addEventListener('click', () => openModal(loginModal));
            document.getElementById('signupBtn').addEventListener('click', () => openModal(signupModal));
            document.getElementById('logoutBtn').addEventListener('click', logout);
            document.getElementById('dashboardBtn').addEventListener('click', () => showPageWithTransition('dashboard'));
            document.getElementById('adminBtn').addEventListener('click', () => showPageWithTransition('admin'));

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
                    showPageWithTransition(page);
                    
                    if (category) {
                        setTimeout(() => {
                            categoryFilter.value = category;
                            filterProducts();
                        }, 100);
                    }
                });
            });

            // Hero buttons
            document.getElementById('exploreProductsBtn').addEventListener('click', () => showPageWithTransition('products'));
            document.getElementById('joinCommunityBtn').addEventListener('click', () => {
                if (currentUser) {
                    showPageWithTransition('dashboard');
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
                showEnhancedToast('Thank you for subscribing to our newsletter!', 'success');
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

            // Initialize ADMIN features
            initAdminFeatures();
        }

        // ===== ADMIN FEATURES =====
        function initAdminFeatures() {
            // Admin Quick Actions Event Listeners
            document.getElementById('adminToggle').addEventListener('click', toggleAdminPanel);
            document.getElementById('toggleEditMode').addEventListener('click', toggleQuickEditMode);
            document.getElementById('addNewProduct').addEventListener('click', () => openModal(productModal));
            document.getElementById('viewStats').addEventListener('click', toggleStatsPanel);
            document.getElementById('goToAdminPanel').addEventListener('click', () => showPageWithTransition('admin'));

            // Admin Panel Quick Cards
            document.querySelectorAll('.admin-quick-card').forEach(card => {
                card.addEventListener('click', function() {
                    const action = this.getAttribute('data-action');
                    handleQuickCardAction(action);
                });
            });

            // Bulk Edit Functionality
            document.getElementById('toggleBulkEdit').addEventListener('click', toggleBulkEditMode);
            document.getElementById('selectAllProducts').addEventListener('change', toggleSelectAllProducts);
            document.getElementById('bulkCancel').addEventListener('click', cancelBulkEdit);
            document.getElementById('bulkFeatured').addEventListener('click', bulkToggleFeatured);
            document.getElementById('bulkDelete').addEventListener('click', bulkDeleteProducts);

            // Context Menu
            document.addEventListener('click', closeContextMenu);
            document.addEventListener('contextmenu', handleRightClick);

            // Keyboard Shortcuts for Admin
            document.addEventListener('keydown', handleAdminKeyboardShortcuts);
        }

        function enableAdminMode() {
            isAdminMode = true;
            document.body.classList.add('admin-mode');
            document.getElementById('adminShortcut').style.display = 'flex';
            document.getElementById('adminBtn').style.display = 'inline-block';
            
            // Show admin quick actions
            document.getElementById('adminQuickActions').style.display = 'flex';
            
            // Update stats
            updateQuickStats();
        }

        function toggleAdminPanel() {
            const panel = document.getElementById('adminQuickActions');
            panel.classList.toggle('collapsed');
        }

        function toggleQuickEditMode() {
            isQuickEditMode = !isQuickEditMode;
            document.body.classList.toggle('quick-edit-mode', isQuickEditMode);
            
            // Add click handlers to products for quick editing
            if (isQuickEditMode) {
                enableQuickEditMode();
                showEnhancedToast('Quick Edit Mode Enabled - Click on any product to edit', 'success');
            } else {
                disableQuickEditMode();
                showEnhancedToast('Quick Edit Mode Disabled', 'info');
            }
        }

        function enableQuickEditMode() {
            // Add click event to all product cards
            document.querySelectorAll('.product-card').forEach(card => {
                card.addEventListener('click', handleProductQuickEdit);
            });
        }

        function disableQuickEditMode() {
            // Remove click event from all product cards
            document.querySelectorAll('.product-card').forEach(card => {
                card.removeEventListener('click', handleProductQuickEdit);
            });
        }

        function handleProductQuickEdit(event) {
            if (!isQuickEditMode) return;
            
            const productCard = event.currentTarget;
            const productId = productCard.querySelector('.add-to-cart').getAttribute('data-id');
            const product = products.find(p => p.id === productId);
            
            if (product) {
                editProduct(product.id);
            }
        }

        function toggleStatsPanel() {
            const statsPanel = document.getElementById('adminQuickStats');
            statsPanel.classList.toggle('show');
            updateQuickStats();
        }

        function updateQuickStats() {
            if (!isAdminMode) return;

            const totalProducts = products.length;
            const featuredProducts = products.filter(p => p.featured).length;
            const totalSales = products.reduce((sum, product) => {
                // Simulate sales data - in real app, this would come from your database
                const salesCount = Math.floor(Math.random() * 100);
                return sum + (product.price * salesCount);
            }, 0);
            const activeUsers = Math.floor(Math.random() * 1000) + 500; // Simulated data

            document.getElementById('statsTotalProducts').textContent = totalProducts;
            document.getElementById('statsFeaturedProducts').textContent = featuredProducts;
            document.getElementById('statsTotalSales').textContent = formatCurrency(totalSales);
            document.getElementById('statsActiveUsers').textContent = activeUsers.toLocaleString();
        }

        function handleQuickCardAction(action) {
            switch(action) {
                case 'add-product':
                    openModal(productModal);
                    break;
                case 'bulk-edit':
                    toggleBulkEditMode();
                    break;
                case 'view-analytics':
                    showEnhancedToast('Analytics dashboard coming soon!', 'info');
                    break;
                case 'manage-users':
                    showEnhancedToast('User management coming soon!', 'info');
                    break;
            }
        }

        function toggleBulkEditMode() {
            isBulkEditMode = !isBulkEditMode;
            document.body.classList.toggle('bulk-edit-mode', isBulkEditMode);
            document.getElementById('bulkActions').classList.toggle('show', isBulkEditMode);
            
            if (isBulkEditMode) {
                showEnhancedToast('Bulk Edit Mode Enabled - Select products to edit', 'success');
                renderAdminProducts(); // Re-render to show checkboxes
            } else {
                selectedProducts.clear();
                updateSelectedCount();
                showEnhancedToast('Bulk Edit Mode Disabled', 'info');
                renderAdminProducts(); // Re-render to hide checkboxes
            }
        }

        function toggleSelectAllProducts(event) {
            const checkboxes = document.querySelectorAll('.product-select-checkbox');
            checkboxes.forEach(checkbox => {
                checkbox.checked = event.target.checked;
                const productId = checkbox.getAttribute('data-id');
                if (event.target.checked) {
                    selectedProducts.add(productId);
                } else {
                    selectedProducts.delete(productId);
                }
            });
            updateSelectedCount();
        }

        function handleProductSelection(productId, isSelected) {
            if (isSelected) {
                selectedProducts.add(productId);
            } else {
                selectedProducts.delete(productId);
            }
            updateSelectedCount();
        }

        function updateSelectedCount() {
            document.getElementById('selectedCount').textContent = `${selectedProducts.size} products selected`;
        }

        function cancelBulkEdit() {
            toggleBulkEditMode();
        }

        function bulkToggleFeatured() {
            if (selectedProducts.size === 0) {
                showEnhancedToast('Please select products first', 'warning');
                return;
            }

            selectedProducts.forEach(productId => {
                const product = products.find(p => p.id === productId);
                if (product) {
                    product.featured = !product.featured;
                }
            });

            showEnhancedToast(`Toggled featured status for ${selectedProducts.size} products`, 'success');
            renderAdminProducts();
            renderFeaturedProducts();
            renderAllProducts();
            toggleBulkEditMode();
        }

        function bulkDeleteProducts() {
            if (selectedProducts.size === 0) {
                showEnhancedToast('Please select products first', 'warning');
                return;
            }

            if (confirm(`Are you sure you want to delete ${selectedProducts.size} products?`)) {
                products = products.filter(p => !selectedProducts.has(p.id));
                showEnhancedToast(`Deleted ${selectedProducts.size} products`, 'success');
                renderAdminProducts();
                renderFeaturedProducts();
                renderAllProducts();
                toggleBulkEditMode();
            }
        }

        function handleRightClick(event) {
            if (!isAdminMode) return;

            const productCard = event.target.closest('.product-card');
            if (productCard) {
                event.preventDefault();
                currentContextProduct = productCard.querySelector('.add-to-cart').getAttribute('data-id');
                showContextMenu(event.clientX, event.clientY);
            }
        }

        function showContextMenu(x, y) {
            const contextMenu = document.getElementById('adminContextMenu');
            contextMenu.style.display = 'block';
            contextMenu.style.left = x + 'px';
            contextMenu.style.top = y + 'px';

            // Add event listeners to context menu buttons
            contextMenu.querySelectorAll('button').forEach(button => {
                button.onclick = function() {
                    handleContextMenuAction(this.getAttribute('data-action'));
                };
            });
        }

        function closeContextMenu() {
            document.getElementById('adminContextMenu').style.display = 'none';
        }

        function handleContextMenuAction(action) {
            if (!currentContextProduct) return;

            const product = products.find(p => p.id === currentContextProduct);
            if (!product) return;

            switch(action) {
                case 'edit':
                    editProduct(product.id);
                    break;
                case 'toggle-featured':
                    product.featured = !product.featured;
                    showEnhancedToast(`${product.name} ${product.featured ? 'added to' : 'removed from'} featured`, 'success');
                    renderAdminProducts();
                    renderFeaturedProducts();
                    renderAllProducts();
                    break;
                case 'duplicate':
                    duplicateProduct(product.id);
                    break;
                case 'delete':
                    deleteProduct(product.id);
                    break;
            }

            closeContextMenu();
        }

        function duplicateProduct(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            const duplicatedProduct = {
                ...product,
                id: Date.now().toString(),
                name: `${product.name} (Copy)`,
                badge: null
            };

            products.push(duplicatedProduct);
            showEnhancedToast('Product duplicated successfully', 'success');
            renderAdminProducts();
            renderFeaturedProducts();
            renderAllProducts();
        }

        function handleAdminKeyboardShortcuts(e) {
            if (!isAdminMode) return;

            // Ctrl+E to toggle quick edit mode
            if (e.ctrlKey && e.key === 'e') {
                e.preventDefault();
                toggleQuickEditMode();
            }

            // Escape to exit modes
            if (e.key === 'Escape') {
                if (isQuickEditMode) {
                    toggleQuickEditMode();
                }
                if (isBulkEditMode) {
                    toggleBulkEditMode();
                }
                closeContextMenu();
            }
        }

        // ===== ORIGINAL STORE FUNCTIONS =====
        // ... [All your original store functions remain exactly the same] ...
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

        // Product rendering with animations
        function renderFeaturedProducts() {
            const featured = products.filter(product => product.featured);
            renderProductsWithAnimation(featured, featuredProductsContainer);
        }

        function renderAllProducts() {
            renderProductsWithAnimation(products, allProductsContainer);
        }

        function renderProductsWithAnimation(products, container) {
            container.innerHTML = '';
            
            if (products.length === 0) {
                container.innerHTML = '<p role="alert">No products found.</p>';
                return;
            }
            
            products.forEach((product, index) => {
                const productCard = createProductCard(product);
                productCard.style.animationDelay = `${index * 0.1}s`;
                container.appendChild(productCard);
            });
        }

        function createProductCard(product) {
            const productCard = document.createElement('article');
            productCard.className = 'product-card';
            productCard.setAttribute('aria-labelledby', `product-title-${product.id}`);
            
            // Check if product is in wishlist
            const isInWishlist = wishlist.includes(product.id);
            
            // Add selection checkbox for bulk edit
            const selectionCheckbox = isBulkEditMode ? `
                <input type="checkbox" class="product-select-checkbox" data-id="${product.id}" 
                       onchange="handleProductSelection('${product.id}', this.checked)">
            ` : '';
            
            productCard.innerHTML = `
                ${selectionCheckbox}
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
            
            // Add event listeners
            const addToCartBtn = productCard.querySelector('.add-to-cart');
            const previewBtn = productCard.querySelector('.preview-btn');
            const quickViewBtn = productCard.querySelector('.quick-view-btn');
            const wishlistBtn = productCard.querySelector('.wishlist-btn');
            
            addToCartBtn.addEventListener('click', function() {
                const id = this.getAttribute('data-id');
                const name = this.getAttribute('data-name');
                const price = this.getAttribute('data-price');
                
                addToCartWithAnimation(id, name, price);
            });
            
            previewBtn.addEventListener('click', function() {
                const id = this.getAttribute('data-id');
                showProductPreview(id);
            });
            
            quickViewBtn.addEventListener('click', function() {
                const id = this.getAttribute('data-id');
                showProductPreview(id);
            });
            
            wishlistBtn.addEventListener('click', function() {
                const id = this.getAttribute('data-id');
                toggleWishlist(id, this);
            });
            
            return productCard;
        }

        // Enhanced Admin Products Table
        function renderAdminProducts() {
            adminProductsTable.innerHTML = '';
            
            products.forEach(product => {
                const row = document.createElement('tr');
                const isSelected = selectedProducts.has(product.id);
                
                row.innerHTML = `
                    <td>
                        ${isBulkEditMode ? `
                            <input type="checkbox" class="product-select-checkbox" data-id="${product.id}" 
                                   ${isSelected ? 'checked' : ''} 
                                   onchange="handleProductSelection('${product.id}', this.checked)">
                        ` : ''}
                    </td>
                    <td>${product.id}</td>
                    <td>${product.name} ${product.featured ? '⭐' : ''}</td>
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
                    showPageWithTransition('products');
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
            
            renderProductsWithAnimation(filteredProducts, allProductsContainer);
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
                
                showEnhancedToast('🎉 Added to cart!', 'success');
            }, 800);
        }

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
                
                addToCartWithAnimation(id, name, price);
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
                showEnhancedToast('Removed from wishlist');
            } else {
                // Add to wishlist
                wishlist.push(id);
                button.classList.add('active');
                button.setAttribute('aria-label', 'Remove from wishlist');
                showEnhancedToast('Added to wishlist');
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
                    showEnhancedToast('Login successful!', 'success');
                    
                    // Reset form
                    document.getElementById('loginForm').reset();
                } else {
                    showEnhancedToast('Please enter both email and password', 'error');
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
                showEnhancedToast('Passwords do not match', 'error');
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
                showEnhancedToast('Account created successfully!', 'success');
                
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
            
            // Disable admin mode
            isAdminMode = false;
            document.body.classList.remove('admin-mode');
            document.getElementById('adminQuickActions').style.display = 'none';
            
            showPageWithTransition('home');
            showEnhancedToast('You have been logged out', 'success');
        }

        function showUserMenu() {
            authButtons.style.display = 'none';
            userMenu.style.display = 'flex';
            
            userName.textContent = currentUser.name;
            dashboardUserName.textContent = currentUser.name;
            userAvatar.textContent = currentUser.name.charAt(0).toUpperCase();
            
            if (currentUser.role === 'admin') {
                document.getElementById('adminBtn').style.display = 'inline-block';
                enableAdminMode();
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
                showEnhancedToast(`Product ${id ? 'updated' : 'added'} successfully!`, 'success');
                
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
                showEnhancedToast('Product deleted successfully!', 'success');
            }
        }

        // Payment handling with Stripe
        function handlePayment(e) {
            e.preventDefault();
            
            if (!currentUser) {
                showEnhancedToast('Please log in to complete your purchase', 'error');
                closeModal(checkoutModal);
                openModal(loginModal);
                return;
            }
            
            if (cart.length === 0) {
                showEnhancedToast('Your cart is empty', 'error');
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
            showEnhancedToast('Payment successful! Your products are now available in your dashboard.', 'success');
            
            // Redirect to dashboard
            showPageWithTransition('dashboard');
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
            
            showEnhancedToast('Settings updated successfully!', 'success');
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
            // This would typically add a reading line or highlight
            showEnhancedToast('Reading guide ' + (document.body.classList.contains('reading-guide') ? 'enabled' : 'disabled'));
        }

        function toggleDyslexiaFont() {
            document.body.classList.toggle('dyslexia-font');
            // This would apply a dyslexia-friendly font
            showEnhancedToast('Dyslexia-friendly font ' + (document.body.classList.contains('dyslexia-font') ? 'enabled' : 'disabled'));
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
                    // Focus search (if implemented)
                    showEnhancedToast('Press C for cart, A for accessibility controls');
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
                    showPageWithTransition('products');
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

        // Animation Functions
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
        }

        // Make functions globally available for inline event handlers
        window.handleProductSelection = handleProductSelection;

        // Initialize the application when DOM is loaded
        document.addEventListener('DOMContentLoaded', init);
    </script>
</body>
</html>
