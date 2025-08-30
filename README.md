<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VONDO - VONDO Online Shopping</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f8f9fa;
            color: #333;
            line-height: 1.6;
            max-width: 100%;
            overflow-x: hidden;
        }

        .container {
            width: 100%;
            padding: 0 15px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(to right, #2c3e50, #4a6572);
            color: white;
            padding: 12px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
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
            color: white;
        }

        .logo-img {
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 18px;
            color: white;
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            border-radius: 8px;
        }

        .logo-text {
            font-size: 22px;
            font-weight: bold;
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .search-icon, .cart-icon {
            font-size: 20px;
            color: white;
        }

        .cart-icon {
            position: relative;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #ff4757;
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 11px;
            font-weight: bold;
        }

        .menu-toggle {
            display: block;
            font-size: 24px;
            background: none;
            border: none;
            color: white;
            cursor: pointer;
        }

        /* Mobile Menu */
        .mobile-menu {
            position: fixed;
            top: 0;
            left: -100%;
            width: 80%;
            height: 100%;
            background: white;
            z-index: 1000;
            padding: 20px;
            box-shadow: 2px 0 10px rgba(0, 0, 0, 0.1);
            transition: left 0.3s ease;
        }

        .mobile-menu.active {
            left: 0;
        }

        .mobile-menu ul {
            list-style: none;
            margin-top: 30px;
        }

        .mobile-menu ul li {
            margin-bottom: 15px;
        }

        .mobile-menu ul li a {
            color: #333;
            text-decoration: none;
            font-size: 18px;
            font-weight: 500;
            display: block;
            padding: 10px 0;
            border-bottom: 1px solid #eee;
        }

        .close-menu {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 24px;
            background: none;
            border: none;
            cursor: pointer;
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 999;
            display: none;
        }

        .overlay.active {
            display: block;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://i.ibb.co.com/0yVPc2kX/1756539704581.jpg');
            background-size: cover;
            background-position: center;
            color: white;
            text-align: center;
            padding: 60px 20px;
            margin-bottom: 25px;
        }

        .hero h1 {
            font-size: 28px;
            margin-bottom: 15px;
        }

        .hero p {
            font-size: 16px;
            margin: 0 auto 20px;
        }

        .btn {
            display: inline-block;
            background: #ff6b6b;
            color: white;
            padding: 12px 25px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
        }

        .btn:hover {
            background: #ff4757;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        /* Products Section */
        .section-title {
            text-align: center;
            margin-bottom: 25px;
            font-size: 22px;
            color: #333;
            position: relative;
        }

        .section-title:after {
            content: '';
            display: block;
            width: 50px;
            height: 3px;
            background: #4a6572;
            margin: 8px auto;
        }

        .products {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
            margin-bottom: 30px;
        }

        .product {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease;
        }

        .product:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.1);
        }

        .product-img {
            height: 280px;
            width: 100%;
            object-fit: cover;
        }

        .product-content {
            padding: 15px;
        }

        .product-title {
            font-size: 16px;
            margin-bottom: 8px;
        }

        .product-price {
            font-size: 18px;
            font-weight: bold;
            color: #4a6572;
            margin-bottom: 10px;
        }

        .product-rating {
            color: #ffc107;
            margin-bottom: 12px;
            font-size: 14px;
        }

        .add-to-cart {
            width: 100%;
            padding: 10px;
            background: #4a6572;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            transition: background 0.3s ease;
        }

        .add-to-cart:hover {
            background: #2c3e50;
        }

        /* Address Section */
        .address-section {
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            margin: 30px 0;
            text-align: center;
        }

        .address-section h2 {
            color: #2c3e50;
            margin-bottom: 15px;
            font-size: 20px;
        }

        .address-section p {
            font-size: 16px;
            margin-bottom: 8px;
        }

        /* Search Modal */
        .search-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 70px;
            background: white;
            z-index: 1000;
            padding: 15px;
            display: flex;
            align-items: center;
            transform: translateY(-100%);
            transition: transform 0.3s ease;
        }

        .search-modal.active {
            transform: translateY(0);
        }

        .search-modal input {
            flex: 1;
            border: 1px solid #ddd;
            border-radius: 30px;
            padding: 10px 15px;
            font-size: 16px;
            outline: none;
        }

        .close-search {
            margin-left: 10px;
            font-size: 20px;
            background: none;
            border: none;
            cursor: pointer;
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            padding: 30px 0 15px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 25px;
            margin-bottom: 20px;
        }

        .footer-column h3 {
            font-size: 18px;
            margin-bottom: 15px;
            position: relative;
        }

        .footer-column h3:after {
            content: '';
            display: block;
            width: 30px;
            height: 2px;
            background: #ff6b6b;
            margin-top: 8px;
        }

        .footer-column p, .footer-column a {
            margin-bottom: 8px;
            display: block;
            color: #ccc;
            text-decoration: none;
            font-size: 14px;
        }

        .footer-column a:hover {
            color: #ff6b6b;
        }

        .social-icons {
            display: flex;
            gap: 12px;
        }

        .social-icons a {
            color: white;
            font-size: 18px;
        }

        .copyright {
            text-align: center;
            padding-top: 15px;
            border-top: 1px solid #4a6572;
            color: #ccc;
            font-size: 14px;
        }

        /* Bottom Navigation Bar (Mobile) */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background: white;
            display: flex;
            justify-content: space-around;
            padding: 10px 0;
            box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.1);
            z-index: 90;
        }

        .bottom-nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-decoration: none;
            color: #777;
            font-size: 12px;
        }

        .bottom-nav-item i {
            font-size: 20px;
            margin-bottom: 4px;
        }

        .bottom-nav-item.active {
            color: #4a6572;
        }

        /* Responsive Design for Tablets */
        @media (min-width: 768px) {
            .container {
                max-width: 720px;
                margin: 0 auto;
                padding: 0 15px;
            }
            
            .products {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .footer-content {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
        }

        /* Responsive Design for Desktop */
        @media (min-width: 992px) {
            .container {
                max-width: 960px;
            }
            
            .products {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .footer-content {
                grid-template-columns: repeat(4, 1fr);
            }
            
            .menu-toggle {
                display: none;
            }
            
            .bottom-nav {
                display: none;
            }
            
            nav {
                display: block !important;
            }
            
            nav ul {
                display: flex;
                list-style: none;
            }
            
            nav ul li {
                margin-left: 20px;
            }
            
            nav ul li a {
                color: white;
                text-decoration: none;
                font-weight: 500;
                transition: all 0.3s ease;
            }
            
            nav ul li a:hover {
                color: #ffd700;
            }
        }

        /* Show navigation on desktop */
        @media (max-width: 991px) {
            nav {
                display: none;
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
                    <div class="logo-img">V</div>
                    <div class="logo-text">VONDO</div>
                </a>
                
                <button class="menu-toggle">
                    <i class="fas fa-bars"></i>
                </button>
                
                <nav>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#">Products</a></li>
                        <li><a href="#">Categories</a></li>
                        <li><a href="#">Deals</a></li>
                        <li><a href="#">About</a></li>
                    </ul>
                </nav>
                
                <div class="header-actions">
                    <a href="#" class="search-icon" id="searchToggle">
                        <i class="fas fa-search"></i>
                    </a>
                    <a href="#" class="cart-icon">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">3</span>
                    </a>
                </div>
            </div>
        </div>
    </header>

    <!-- Mobile Menu -->
    <div class="mobile-menu" id="mobileMenu">
        <button class="close-menu" id="closeMenu">
            <i class="fas fa-times"></i>
        </button>
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Products</a></li>
            <li><a href="#">Categories</a></li>
            <li><a href="#">Deals</a></li>
            <li><a href="#">About Us</a></li>
            <li><a href="#">Contact</a></li>
            <li><a href="#">My Account</a></li>
        </ul>
    </div>
    <div class="overlay" id="overlay"></div>

    <!-- Search Modal -->
    <div class="search-modal" id="searchModal">
        <input type="text" placeholder="Search products...">
        <button class="close-search" id="closeSearch">
            <i class="fas fa-times"></i>
        </button>
    </div>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Summer Sale Up To 50% Off</h1>
            <p>Discover the latest trends with our exclusive summer collection.</p>
            <a href="#" class="btn">Shop Now</a>
        </div>
    </section>

    <!-- Featured Products -->
    <section class="container">
        <h2 class="section-title">Featured Products</h2>
        <div class="products">
            <!-- Product 1 -->
            <div class="product">
                <img src="https://i.ibb.co.com/KxkMrhkJ/IMG-20250720-WA0067.jpg" alt="Sneakers" class="product-img">
                <div class="product-content">
                    <h3 class="product-title">BD Flag</h3>
                    <div class="product-price">$89.99</div>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                    </div>
                    <button class="add-to-cart">Add to Cart</button>
                </div>
            </div>

            <!-- Product 2 -->
            <div class="product">
                <img src="https://i.ibb.co.com/BKBKMmmy/20240917-121925.jpg" alt="Watch" class="product-img">
                <div class="product-content">
                    <h3 class="product-title">GODA From Tangail</h3>
                    <div class="product-price">$159.99</div>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                    </div>
                    <button class="add-to-cart">Add to Cart</button>
                </div>
            </div>

            <!-- Product 3 -->
            <div class="product">
                <img src="https://i.ibb.co.com/chDr90hW/PXL-20250630-162949271-PORTRAIT.jpg" alt="Headphones" class="product-img">
                <div class="product-content">
                    <h3 class="product-title">Play Boy</h3>
                    <div class="product-price">$129.99</div>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <button class="add-to-cart">Add to Cart</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Address Section -->
    <section class="container">
        <div class="address-section">
            <h2>Visit Our Store</h2>
            <p><i class="fas fa-map-marker-alt"></i> 123 Fashion Avenue, Downtown District</p>
            <p>New York, NY 10001, United States</p>
            <p><i class="fas fa-phone"></i> +1 (555) 123-4567</p>
            <p><i class="fas fa-envelope"></i> info@vondo.com</p>
        </div>
    </section>

    <!-- New Arrivals -->
    <section class="container">
        <h2 class="section-title">New Arrivals</h2>
        <div class="products">
            <!-- Product 4 -->
            <div class="product">
                <img src="https://images.unsplash.com/photo-1593642632823-8f785ba67e45?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1632&q=80" alt="Laptop" class="product-img">
                <div class="product-content">
                    <h3 class="product-title">Ultra-Thin Laptop</h3>
                    <div class="product-price">$999.99</div>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                    </div>
                    <button class="add-to-cart">Add to Cart</button>
                </div>
            </div>

            <!-- Product 5 -->
            <div class="product">
                <img src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1399&q=80" alt="Smart Watch" class="product-img">
                <div class="product-content">
                    <h3 class="product-title">Smart Watch Series 5</h3>
                    <div class="product-price">$249.99</div>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>
                    <button class="add-to-cart">Add to Cart</button>
                </div>
            </div>

            <!-- Product 6 -->
            <div class="product">
                <img src="https://images.unsplash.com/photo-1546868871-7041f2a55e12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1528&q=80" alt="Wireless Earbuds" class="product-img">
                <div class="product-content">
                    <h3 class="product-title">Wireless Earbuds Pro</h3>
                    <div class="product-price">$129.99</div>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                    </div>
                    <button class="add-to-cart">Add to Cart</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>VONDO</h3>
                    <p>Your one-stop destination for all your shopping needs. We offer quality products at affordable prices.</p>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <a href="#">Home</a>
                    <a href="#">Products</a>
                    <a href="#">Featured</a>
                    <a href="#">New Arrivals</a>
                    <a href="#">Sale</a>
                </div>
                <div class="footer-column">
                    <h3>Customer Service</h3>
                    <a href="#">Contact Us</a>
                    <a href="#">FAQs</a>
                    <a href="#">Returns & Refunds</a>
                    <a href="#">Shipping Policy</a>
                    <a href="#">Privacy Policy</a>
                </div>
                <div class="footer-column">
                    <h3>Connect With Us</h3>
                    <p>Follow us on social media for updates and promotions.</p>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-facebook"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-pinterest"></i></a>
                    </div>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 VONDO. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Bottom Navigation (Mobile) -->
    <div class="bottom-nav">
        <a href="#" class="bottom-nav-item active">
            <i class="fas fa-home"></i>
            <span>Home</span>
        </a>
        <a href="#" class="bottom-nav-item">
            <i class="fas fa-search"></i>
            <span>Search</span>
        </a>
        <a href="#" class="bottom-nav-item">
            <i class="fas fa-shopping-cart"></i>
            <span>Cart</span>
        </a>
        <a href="#" class="bottom-nav-item">
            <i class="fas fa-user"></i>
            <span>Account</span>
        </a>
    </div>

    <script>
        // Mobile menu functionality
        const menuToggle = document.querySelector('.menu-toggle');
        const mobileMenu = document.querySelector('#mobileMenu');
        const closeMenu = document.querySelector('#closeMenu');
        const overlay = document.querySelector('#overlay');
        
        menuToggle.addEventListener('click', function() {
            mobileMenu.classList.add('active');
            overlay.classList.add('active');
            document.body.style.overflow = 'hidden';
        });
        
        closeMenu.addEventListener('click', function() {
            mobileMenu.classList.remove('active');
            overlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        });
        
        overlay.addEventListener('click', function() {
            mobileMenu.classList.remove('active');
            overlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        });

        // Search functionality
        const searchToggle = document.querySelector('#searchToggle');
        const searchModal = document.querySelector('#searchModal');
        const closeSearch = document.querySelector('#closeSearch');
        
        searchToggle.addEventListener('click', function(e) {
            e.preventDefault();
            searchModal.classList.add('active');
        });
        
        closeSearch.addEventListener('click', function() {
            searchModal.classList.remove('active');
        });

        // Simple cart functionality
        document.querySelectorAll('.add-to-cart').forEach(button => {
            button.addEventListener('click', function() {
                const product = this.closest('.product');
                const title = product.querySelector('.product-title').textContent;
                
                // Update cart count
                const cartCount = document.querySelector('.cart-count');
                cartCount.textContent = parseInt(cartCount.textContent) + 1;
                
                // Show confirmation
                alert(`Added ${title} to your cart!`);
            });
        });
    </script>
</body>
</html>
