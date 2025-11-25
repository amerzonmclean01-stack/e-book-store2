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
            --focus-ring: 0 0 0 3px rgba(212, 175, 55, 0.5);
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
            font-size: 16px;
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
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            display: none;
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
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
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
        }

        .btn-accessibility.active {
            background: var(--gold);
            color: var(--prophetic-blue);
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
            padding: 0.5rem;
            border-radius: 4px;
        }

        nav a:hover, nav a:focus {
            color: var(--gold);
            background: rgba(255,255,255,0.1);
            outline: none;
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

        nav a:hover::after, nav a:focus::after {
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
            font-size: 1rem;
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
            background: var(--red);
            color: var(--white);
        }

        .btn-primary:hover, .btn-primary:focus {
            background: #9c1a1a;
            transform: translateY(-2px);
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

        .cart-icon {
            position: relative;
            margin-left: 1rem;
            font-size: 1.5rem;
            cursor: pointer;
            transition: transform 0.3s;
            padding: 0.5rem;
            border-radius: 4px;
        }

        .cart-icon:hover, .cart-icon:focus {
            transform: scale(1.1);
            background: rgba(255,255,255,0.1);
            outline: none;
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

        /* Quick Actions */
        .quick-actions {
            background: var(--light-blue);
            padding: 1rem 0;
            border-bottom: 1px solid #ddd;
        }

        .quick-actions-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
        }

        .quick-action {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.8rem;
            background: var(--white);
            border-radius: 8px;
            text-decoration: none;
            color: var(--dark-blue);
            transition: all 0.3s;
            border: 1px solid transparent;
        }

        .quick-action:hover, .quick-action:focus {
            border-color: var(--gold);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            outline: none;
        }

        .quick-action i {
            color: var(--gold);
            font-size: 1.2rem;
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

        @media (prefers-reduced-motion: reduce) {
            .hero {
                background-attachment: scroll;
            }
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

        .btn-gold:hover, .btn-gold:focus {
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
            border: 1px solid transparent;
        }

        .product-card:hover, .product-card:focus-within {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
            border-color: var(--gold);
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

        /* Wishlist */
        .wishlist-btn {
            position: absolute;
            top: 10px;
            left: 10px;
            background: rgba(255,255,255,0.9);
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            color: var(--dark-gray);
            transition: all 0.3s;
            z-index: 2;
        }

        .wishlist-btn:hover, .wishlist-btn:focus {
            background: var(--white);
            color: var(--red);
            transform: scale(1.1);
            outline: none;
        }

        .wishlist-btn.active {
            color: var(--red);
        }

        /* Quick View */
        .quick-view-btn {
            position: absolute;
            bottom: 10px;
            right: 10px;
            background: rgba(255,255,255,0.9);
            border: none;
            border-radius: 4px;
            padding: 0.5rem;
            cursor: pointer;
            color: var(--dark-blue);
            transition: all 0.3s;
            z-index: 2;
            font-size: 0.8rem;
        }

        .quick-view-btn:hover, .quick-view-btn:focus {
            background: var(--white);
            color: var(--prophetic-blue);
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

        .dashboard-nav a:hover, .dashboard-nav a:focus, .dashboard-nav a.active {
            background: var(--prophetic-blue);
            color: var(--white);
            outline: none;
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

        .feature-card:hover, .feature-card:focus-within {
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
            width: 36px;
            height: 36px;
            background: var(--prophetic-blue);
            border-radius: 50%;
            transition: all 0.3s;
        }

        .social-icons a:hover, .social-icons a:focus {
            background: var(--gold);
            transform: translateY(-3px);
            outline: none;
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

        .close-modal:hover, .close-modal:focus {
            color: var(--red);
            background: var(--gray);
            outline: none;
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

        .form-footer a:hover, .form-footer a:focus {
            text-decoration: underline;
            outline: none;
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
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            display: none;
            max-width: 300px;
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
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
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

            .keyboard-shortcuts {
                left: 10px;
                right: 10px;
                max-width: none;
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
        // Enhanced store with accessibility and convenience features
        // ... [Previous JavaScript code remains the same, but enhanced with new features below]

        // New Accessibility Features
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
            showToast('Reading guide ' + (document.body.classList.contains('reading-guide') ? 'enabled' : 'disabled'));
        }

        function toggleDyslexiaFont() {
            document.body.classList.toggle('dyslexia-font');
            // This would apply a dyslexia-friendly font
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
                    // Focus search (if implemented)
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

        // Enhanced convenience features
        function initConvenienceFeatures() {
            // Quick actions
            document.querySelectorAll('.quick-action').forEach(action => {
                action.addEventListener('click', function(e) {
                    e.preventDefault();
                    const page = this.getAttribute('data-page');
                    const category = this.getAttribute('data-category');
                    showPage(page);
                    
                    // If category is specified, filter products
                    if (category) {
                        setTimeout(() => filterProductsByCategory(category), 100);
                    }
                });
            });

            // Wishlist functionality
            initWishlist();

            // Quick view
            initQuickView();

            // Load saved preferences
            loadSavedPreferences();
        }

        function initWishlist() {
            let wishlist = JSON.parse(localStorage.getItem('wishlist')) || [];

            // Add wishlist buttons to products
            document.addEventListener('click', function(e) {
                if (e.target.closest('.wishlist-btn')) {
                    const btn = e.target.closest('.wishlist-btn');
                    const productId = btn.getAttribute('data-id');
                    
                    if (btn.classList.contains('active')) {
                        // Remove from wishlist
                        wishlist = wishlist.filter(id => id !== productId);
                        btn.classList.remove('active');
                        showToast('Removed from wishlist');
                    } else {
                        // Add to wishlist
                        wishlist.push(productId);
                        btn.classList.add('active');
                        showToast('Added to wishlist');
                    }
                    
                    localStorage.setItem('wishlist', JSON.stringify(wishlist));
                }
            });

            // Update wishlist buttons when products are rendered
            const originalRenderProducts = window.renderProducts;
            window.renderProducts = function(products, container) {
                originalRenderProducts(products, container);
                
                // Add wishlist buttons
                container.querySelectorAll('.product-card').forEach(card => {
                    const productId = card.querySelector('.add-to-cart').getAttribute('data-id');
                    const wishlistBtn = document.createElement('button');
                    wishlistBtn.className = 'wishlist-btn' + (wishlist.includes(productId) ? ' active' : '');
                    wishlistBtn.setAttribute('data-id', productId);
                    wishlistBtn.setAttribute('aria-label', 'Add to wishlist');
                    wishlistBtn.innerHTML = '<i class="fas fa-heart"></i>';
                    card.appendChild(wishlistBtn);
                });
            };
        }

        function initQuickView() {
            // Add quick view buttons to products
            const originalRenderProducts = window.renderProducts;
            window.renderProducts = function(products, container) {
                originalRenderProducts(products, container);
                
                // Add quick view buttons
                container.querySelectorAll('.product-card').forEach(card => {
                    const productId = card.querySelector('.add-to-cart').getAttribute('data-id');
                    const quickViewBtn = document.createElement('button');
                    quickViewBtn.className = 'quick-view-btn';
                    quickViewBtn.setAttribute('data-id', productId);
                    quickViewBtn.setAttribute('aria-label', 'Quick view');
                    quickViewBtn.innerHTML = '<i class="fas fa-eye"></i> Quick View';
                    card.appendChild(quickViewBtn);

                    quickViewBtn.addEventListener('click', function() {
                        showProductPreview(productId);
                    });
                });
            };
        }

        function filterProductsByCategory(category) {
            const products = sampleProducts.filter(product => product.category === category);
            renderProducts(products, allProductsContainer);
            showToast(`Showing ${category} products`);
        }

        function loadSavedPreferences() {
            // Load text size
            const savedSize = localStorage.getItem('textSize');
            if (savedSize) {
                document.body.style.fontSize = savedSize + 'px';
            }

            // Load contrast mode
            if (localStorage.getItem('highContrast') === 'true') {
                document.body.classList.add('high-contrast');
            }

            // Load currency
            const savedCurrency = localStorage.getItem('currency');
            if (savedCurrency) {
                currentCurrency = savedCurrency;
                currencySelector.value = savedCurrency;
            }
        }

        // Enhanced product rendering with accessibility
        const originalRenderProducts = window.renderProducts;
        window.renderProducts = function(products, container) {
            container.innerHTML = '';
            
            if (products.length === 0) {
                container.innerHTML = '<p role="alert">No products found.</p>';
                return;
            }
            
            products.forEach(product => {
                const productCard = document.createElement('article');
                productCard.className = 'product-card';
                productCard.setAttribute('aria-labelledby', `product-title-${product.id}`);
                
                productCard.innerHTML = `
                    ${product.badge ? `<div class="product-badge" aria-label="${product.badge} product">${product.badge}</div>` : ''}
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
        };

        // Initialize enhanced features
        document.addEventListener('DOMContentLoaded', function() {
            init();
            initAccessibility();
            initConvenienceFeatures();
        });

        // ... [Rest of the existing JavaScript code remains the same]
    </script>
</body>
</html>
