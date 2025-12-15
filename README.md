<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AG Sneaker Hub - Premium Sneakers</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            color: #333;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            width: 100%;
            background: rgba(0, 0, 0, 0.95);
            padding: 1rem 2rem;
            z-index: 1000;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.3);
        }

        .logo-nav {
            height: 60px;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .logo-nav:hover {
            transform: scale(1.05);
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 2rem;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 1px;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        nav a:hover {
            background: #e63946;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(230, 57, 70, 0.4);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, #1a1a1a 0%, #e63946 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
            padding-top: 80px;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.05) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: moveGrid 20s linear infinite;
        }

        @keyframes moveGrid {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .logo-container {
            position: relative;
            z-index: 1;
            margin-bottom: 2rem;
            animation: fadeIn 1s ease;
        }

        .hero-logo {
            width: 350px;
            height: 350px;
            filter: drop-shadow(0 10px 30px rgba(0,0,0,0.5));
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
            animation: fadeInUp 1s ease 0.3s backwards;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.5);
            letter-spacing: 2px;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

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

        .cta-button {
            display: inline-block;
            padding: 1rem 3rem;
            background: white;
            color: #e63946;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.2rem;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .cta-button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.5);
            background: #e63946;
            color: white;
        }

        /* Sections */
        section {
            padding: 5rem 2rem;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        h2 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 3rem;
            color: #1a1a1a;
            position: relative;
            padding-bottom: 15px;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: #e63946;
            border-radius: 2px;
        }

        /* Featured Section */
        #featured {
            background: #f8f9fa;
        }

        .sneaker-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .sneaker-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 3px solid transparent;
        }

        .sneaker-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(230, 57, 70, 0.3);
            border-color: #e63946;
        }

        .sneaker-img {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, #1a1a1a 0%, #e63946 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 5rem;
            position: relative;
            overflow: hidden;
        }

        .sneaker-img::before {
            content: '👟';
            position: absolute;
            font-size: 8rem;
            opacity: 0.1;
            transform: rotate(-15deg);
        }

        .sneaker-info {
            padding: 2rem;
        }

        .sneaker-info h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: #1a1a1a;
        }

        .sneaker-info p {
            color: #666;
            margin-bottom: 1rem;
        }

        .price {
            font-size: 2rem;
            color: #e63946;
            font-weight: bold;
        }

        /* About Section */
        #about {
            background: white;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text p {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 1.5rem;
            color: #555;
        }

        .about-logo {
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 2rem;
        }

        .about-logo img {
            width: 100%;
            max-width: 400px;
            filter: drop-shadow(0 10px 30px rgba(230, 57, 70, 0.3));
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        /* Features Section */
        #features {
            background: #1a1a1a;
            color: white;
        }

        #features h2 {
            color: white;
        }

        #features h2::after {
            background: white;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .feature-box {
            background: rgba(255, 255, 255, 0.05);
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            border: 2px solid rgba(230, 57, 70, 0.3);
            transition: all 0.3s ease;
        }

        .feature-box:hover {
            background: rgba(230, 57, 70, 0.1);
            border-color: #e63946;
            transform: translateY(-10px);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .feature-box h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #e63946;
        }

        /* Contact Section */
        #contact {
            background: linear-gradient(135deg, #e63946 0%, #1a1a1a 100%);
            color: white;
        }

        #contact h2 {
            color: white;
        }

        #contact h2::after {
            background: white;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: none;
            border-radius: 10px;
            font-size: 1rem;
            background: rgba(255, 255, 255, 0.95);
        }

        .submit-btn {
            width: 100%;
            padding: 1rem;
            background: white;
            color: #e63946;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .submit-btn:hover {
            background: #1a1a1a;
            color: white;
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        /* Footer */
        footer {
            background: #0a0a0a;
            color: white;
            text-align: center;
            padding: 3rem 2rem;
        }

        .footer-logo {
            width: 150px;
            margin-bottom: 1rem;
        }

        footer p {
            margin: 0.5rem 0;
        }

        footer a {
            color: #e63946;
            text-decoration: none;
            margin: 0 10px;
        }

        footer a:hover {
            text-decoration: underline;
        }

        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-logo {
                width: 250px;
                height: 250px;
            }

            .about-content {
                grid-template-columns: 1fr;
            }

            nav {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                gap: 1rem;
            }
        }
    </style>
</head>
<body>
    <nav>
        <a href="#home">
            <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 200'%3E%3Ccircle cx='100' cy='100' r='95' fill='white' stroke='black' stroke-width='5'/%3E%3Ctext x='100' y='70' font-size='35' font-weight='bold' text-anchor='middle' fill='black'%3EAG SNEAKER%3C/text%3E%3Ctext x='100' y='110' font-size='35' font-weight='bold' text-anchor='middle' fill='black'%3EHUB%3C/text%3E%3Ctext x='100' y='150' font-size='60' text-anchor='middle'%3E👟%3C/text%3E%3C/svg%3E" alt="AG Sneaker Hub Logo" class="logo-nav">
        </a>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#featured">Shop</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#features">Features</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section id="home" class="hero">
        <div class="logo-container">
            <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 400 400'%3E%3Ccircle cx='200' cy='200' r='190' fill='white' stroke='black' stroke-width='8'/%3E%3Ccircle cx='200' cy='200' r='160' fill='%23e63946'/%3E%3Cpath d='M 150 180 Q 200 160 250 180 L 240 240 Q 200 260 160 240 Z' fill='white' stroke='black' stroke-width='3'/%3E%3Cpath d='M 165 200 L 175 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 180 195 L 190 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 195 192 L 205 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 210 195 L 220 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 225 200 L 235 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 190 180 Q 200 175 210 180' fill='%23e63946'/%3E%3Cpath d='M 220 190 Q 235 185 245 195' fill='black'/%3E%3Ctext x='200' y='80' font-size='45' font-weight='bold' text-anchor='middle' fill='black' transform='rotate(-10 200 80)'%3EAG SNEAKER%3C/text%3E%3Ctext x='200' y='340' font-size='45' font-weight='bold' text-anchor='middle' fill='black' transform='rotate(10 200 340)'%3EHUB%3C/text%3E%3C/svg%3E" alt="AG Sneaker Hub Logo" class="hero-logo">
        </div>
        <div class="hero-content">
            <h1>AG SNEAKER HUB</h1>
            <p>Where Passion Meets Sole</p>
            <a href="#featured" class="cta-button">Shop Collection</a>
        </div>
    </section>

    <section id="featured">
        <div class="container">
            <h2>Featured Collection</h2>
            <div class="sneaker-grid">
                <div class="sneaker-card">
                    <div class="sneaker-img">
                        <span style="font-size: 6rem; z-index: 1;">👟</span>
                    </div>
                    <div class="sneaker-info">
                        <h3>Nike Air Jordan 1</h3>
                        <p>Classic high-top design with premium leather and iconic colorway</p>
                        <div class="price">$179.99</div>
                    </div>
                </div>
                <div class="sneaker-card">
                    <div class="sneaker-img">
                        <span style="font-size: 6rem; z-index: 1;">👟</span>
                    </div>
                    <div class="sneaker-info">
                        <h3>Adidas Yeezy Boost</h3>
                        <p>Luxury comfort with cutting-edge design and premium materials</p>
                        <div class="price">$249.99</div>
                    </div>
                </div>
                <div class="sneaker-card">
                    <div class="sneaker-img">
                        <span style="font-size: 6rem; z-index: 1;">👟</span>
                    </div>
                    <div class="sneaker-info">
                        <h3>Nike Dunk Low</h3>
                        <p>Versatile street style with bold colors and comfortable fit</p>
                        <div class="price">$129.99</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="about">
        <div class="container">
            <h2>About AG Sneaker Hub</h2>
            <div class="about-content">
                <div class="about-text">
                    <p><strong>AG Sneaker Hub</strong> is your ultimate destination for authentic, premium sneakers from the world's most iconic brands.</p>
                    <p>We curate only the finest selection of Nike, Adidas, Jordan, and limited-edition releases that sneaker enthusiasts crave. Every pair is verified for authenticity and delivered with passion.</p>
                    <p>Whether you're building your collection, hunting for rare drops, or just stepping up your style game, we've got you covered. Join our community and experience sneaker culture at its finest.</p>
                </div>
                <div class="about-logo">
                    <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 400 400'%3E%3Ccircle cx='200' cy='200' r='190' fill='white' stroke='black' stroke-width='8'/%3E%3Ccircle cx='200' cy='200' r='160' fill='%23e63946'/%3E%3Cpath d='M 150 180 Q 200 160 250 180 L 240 240 Q 200 260 160 240 Z' fill='white' stroke='black' stroke-width='3'/%3E%3Cpath d='M 165 200 L 175 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 180 195 L 190 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 195 192 L 205 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 210 195 L 220 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 225 200 L 235 230' stroke='black' stroke-width='2'/%3E%3Cpath d='M 190 180 Q 200 175 210 180' fill='%23e63946'/%3E%3Cpath d='M 220 190 Q 235 185 245 195' fill='black'/%3E%3Ctext x='200' y='80' font-size='45' font-weight='bold' text-anchor='middle' fill='black' transform='rotate(-10 200 80)'%3EAG SNEAKER%3C/text%3E%3Ctext x='200' y='340' font-size='45' font-weight='bold' text-anchor='middle' fill='black' transform='rotate(10 200 340)'%3EHUB%3C/text%3E%3C/svg%3E" alt="AG Sneaker Hub">
                </div>
            </div>
        </div>
    </section>

    <section id="features">
        <div class="container">
            <h2>Why Choose Us</h2>
            <div class="features-grid">
                <div class="feature-box">
                    <div class="feature-icon">✓</div>
                    <h3>100% Authentic</h3>
                    <p>Every sneaker verified and guaranteed genuine with certificates of authenticity</p>
                </div>
                <div class="feature-box">
                    <div class="feature-icon">🚀</div>
                    <h3>Fast Shipping</h3>
                    <p>Free express delivery on orders over $150 with tracking</p>
                </div>
                <div class="feature-box">
                    <div class="feature-icon">🔥</div>
                    <h3>Exclusive Drops</h3>
                    <p>Early access to limited releases and rare collaborations</p>
                </div>
                <div class="feature-box">
                    <div class="feature-icon">💎</div>
                    <h3>Premium Selection</h3>
                    <p>Curated collection of the hottest and most sought-after sneakers</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container">
            <h2>Get In Touch</h2>
            <form class="contact-form">
                <div class="form-group">
                    <label for="name">Name</label>
                    <input type="text" id="name" required>
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="email" id="email" required>
                </div>
                <div class="form-group">
                    <label for="message">Message</label>
                    <textarea id="message" rows="5" required></textarea>
                </div>
                <button type="submit" class="submit-btn">Send Message</button>
            </form>
        </div>
    </section>

    <footer>
        <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 200'%3E%3Ccircle cx='100' cy='100' r='95' fill='white' stroke='black' stroke-width='5'/%3E%3Ctext x='100' y='70' font-size='35' font-weight='bold' text-anchor='middle' fill='black'%3EAG SNEAKER%3C/text%3E%3Ctext x='100' y='110' font-size='35' font-weight='bold' text-anchor='middle' fill='black'%3EHUB%3C/text%3E%3Ctext x='100' y='150' font-size='60' text-anchor='middle'%3E👟%3C/text%3E%3C/svg%3E" alt="AG Sneaker Hub" class="footer-logo">
        <p>&copy; 2024 AG Sneaker Hub. All rights reserved.</p>
        <p>
            <a href="#privacy">Privacy Policy</a> | 
            <a href="#terms">Terms of Service</a>
        </p>
        <p style="margin-top: 1rem;">Email: info@agsneakerhub.com | Phone: (123) 456-7890</p>
    </footer>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission
        document.querySelector('.contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thanks for reaching out! We\'ll get back to you soon.');
            this.reset();
        });
    </script>
</body>
</html>
