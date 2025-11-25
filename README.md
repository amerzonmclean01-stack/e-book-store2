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
        /* All previous CSS remains exactly the same */
        /* ... [All your existing CSS code] ... */

        /* Admin Quick Actions */
        .admin-quick-actions {
            position: fixed;
            top: 50%;
            right: 0;
            transform: translateY(-50%);
            z-index: 999;
            display: flex;
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

        /* Product Quick Edit */
        .product-quick-edit {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(30, 58, 138, 0.9);
            display: none;
            align-items: center;
            justify-content: center;
            border-radius: 12px;
            z-index: 5;
        }

        .quick-edit-form {
            background: white;
            padding: 20px;
            border-radius: 8px;
            width: 90%;
            max-width: 400px;
        }

        .quick-edit-actions {
            display: flex;
            gap: 10px;
            margin-top: 15px;
        }

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

    <!-- All existing modals remain the same -->
    <!-- ... [All your existing modals] ... -->

    <script>
        // Enhanced Admin Functionality
        let isAdminMode = false;
        let isQuickEditMode = false;
        let isBulkEditMode = false;
        let selectedProducts = new Set();
        let currentContextProduct = null;

        // Initialize Admin Features
        function initAdminFeatures() {
            // Check if current user is admin
            if (currentUser && currentUser.role === 'admin') {
                enableAdminMode();
            }

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

        // Enhanced Product Rendering with Admin Features
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
            
            // Add event listeners (same as before)
            // ... [Your existing event listener code] ...
            
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

        // Initialize admin features when DOM is loaded
        document.addEventListener('DOMContentLoaded', function() {
            // Your existing initialization code
            init();
            
            // Initialize admin features
            initAdminFeatures();
        });

        // Make functions globally available for inline event handlers
        window.handleProductSelection = handleProductSelection;
    </script>
</body>
</html>
