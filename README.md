<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alexandra Chen - Investigative Journalist</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #1a1a1a;
            --secondary-color: #2c2c2c;
            --accent-color: #3b82f6;
            --text-color: #333;
            --text-light: #666;
            --background: #ffffff;
            --border-color: #e5e7eb;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background: var(--background);
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
            border-bottom: 1px solid transparent;
        }

        .navbar.scrolled {
            background: rgba(255, 255, 255, 0.98);
            border-bottom: 1px solid var(--border-color);
            box-shadow: var(--shadow);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .logo:hover {
            color: var(--accent-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: var(--accent-color);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><defs><radialGradient id="gradient" cx="50%" cy="50%" r="50%"><stop offset="0%" style="stop-color:%23ffffff;stop-opacity:0.1"/><stop offset="100%" style="stop-color:%233b82f6;stop-opacity:0.05"/></radialGradient></defs><circle cx="500" cy="500" r="400" fill="url(%23gradient)"/></svg>') center/cover;
            opacity: 0.3;
        }

        .hero-content {
            z-index: 1;
            max-width: 800px;
            padding: 0 2rem;
            animation: fadeInUp 1s ease-out;
        }

        .hero-photo {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            margin: 0 auto 2rem;
            overflow: hidden;
            box-shadow: var(--shadow-lg);
            transition: transform 0.3s ease;
            background: linear-gradient(135deg, #e2e8f0, #cbd5e1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-light);
            font-size: 4rem;
        }

        .hero-photo:hover {
            transform: translateY(-10px);
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--primary-color);
            line-height: 1.1;
        }

        .hero .subtitle {
            font-size: 1.5rem;
            color: var(--text-light);
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .hero .description {
            font-size: 1.1rem;
            color: var(--text-light);
            margin-bottom: 3rem;
            line-height: 1.7;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            color: var(--text-light);
            text-decoration: none;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 25px;
            background: rgba(255, 255, 255, 0.7);
        }

        .contact-item:hover {
            color: var(--accent-color);
            transform: translateY(-2px);
            box-shadow: var(--shadow);
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
        }

        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--primary-color);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1.2rem;
        }

        .social-link:hover {
            background: var(--accent-color);
            transform: translateY(-3px);
            box-shadow: var(--shadow-lg);
        }

        /* Sections */
        .section {
            padding: 5rem 0;
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease;
        }

        .section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 3rem;
            color: var(--primary-color);
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            width: 60px;
            height: 4px;
            background: var(--accent-color);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        /* About Section */
        .about {
            background: var(--background);
        }

        .about-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--text-light);
            margin-bottom: 2rem;
        }

        .skills {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .skill {
            background: var(--accent-color);
            color: white;
            padding: 0.5rem 1.5rem;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .skill:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow);
        }

        /* Articles Section */
        .articles {
            background: #f8fafc;
        }

        .articles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .article-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            opacity: 0;
            transform: translateY(30px);
        }

        .article-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .article-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-lg);
        }

        .article-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #e2e8f0, #cbd5e1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-light);
            font-size: 3rem;
        }

        .article-content {
            padding: 1.5rem;
        }

        .article-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
        }

        .article-meta {
            color: var(--text-light);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .article-excerpt {
            color: var(--text-light);
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .read-more {
            color: var(--accent-color);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .read-more:hover {
            color: var(--primary-color);
        }

        /* Media Features Section */
        .media {
            background: var(--background);
        }

        .media-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .media-card {
            text-align: center;
            padding: 2rem;
            border-radius: 15px;
            background: white;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            border: 1px solid var(--border-color);
            opacity: 0;
            transform: translateY(30px);
        }

        .media-card.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .media-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .media-icon {
            width: 60px;
            height: 60px;
            margin: 0 auto 1rem;
            background: var(--accent-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
        }

        .media-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
        }

        .media-outlet {
            color: var(--text-light);
            margin-bottom: 1rem;
        }

        .media-description {
            color: var(--text-light);
            line-height: 1.6;
        }

        /* Contact Section */
        .contact {
            background: #f8fafc;
        }

        .contact-content {
            max-width: 600px;
            margin: 0 auto;
            text-align: center;
        }

        .contact-form {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: var(--shadow);
        }

        .form-group {
            margin-bottom: 1.5rem;
            text-align: left;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: var(--text-color);
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.75rem 1rem;
            border: 2px solid var(--border-color);
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
            font-family: inherit;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--accent-color);
        }

        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }

        .submit-btn {
            background: var(--accent-color);
            color: white;
            padding: 0.75rem 2rem;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
        }

        .submit-btn:hover {
            background: var(--primary-color);
            transform: translateY(-2px);
        }

        /* Footer */
        .footer {
            background: var(--primary-color);
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        .footer-social {
            margin-bottom: 1rem;
        }

        .footer-social .social-link {
            background: rgba(255, 255, 255, 0.1);
            margin: 0 0.5rem;
        }

        .footer-social .social-link:hover {
            background: var(--accent-color);
        }

        /* Animations */
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

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero .subtitle {
                font-size: 1.2rem;
            }

            .contact-info {
                flex-direction: column;
                align-items: center;
                gap: 1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .articles-grid,
            .media-grid {
                grid-template-columns: 1fr;
            }

            .skills {
                gap: 0.5rem;
            }

            .skill {
                padding: 0.4rem 1rem;
                font-size: 0.8rem;
            }
        }

        @media (max-width: 480px) {
            .hero-photo {
                width: 150px;
                height: 150px;
                font-size: 3rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .container {
                padding: 0 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <a href="#" class="logo">Alexandra Chen</a>
            <ul class="nav-links">
                <li><a href="#about">About</a></li>
                <li><a href="#articles">Articles</a></li>
                <li><a href="#media">Media</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <div class="hero-photo">
                <i class="fas fa-user"></i>
            </div>
            <h1>Alexandra Chen</h1>
            <p class="subtitle">Investigative Journalist</p>
            <p class="description">Award-winning journalist specializing in political investigations, corporate accountability, and social justice. Featured in major publications worldwide with a focus on uncovering truth and giving voice to the voiceless.</p>
            
            <div class="contact-info">
                <a href="mailto:alexandra.chen@email.com" class="contact-item">
                    <i class="fas fa-envelope"></i>
                    alexandra.chen@email.com
                </a>
                <a href="tel:+1234567890" class="contact-item">
                    <i class="fas fa-phone"></i>
                    +1 (234) 567-8900
                </a>
            </div>

            <div class="social-links">
                <a href="#" class="social-link" aria-label="Twitter">
                    <i class="fab fa-twitter"></i>
                </a>
                <a href="#" class="social-link" aria-label="LinkedIn">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="#" class="social-link" aria-label="Instagram">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="#" class="social-link" aria-label="Medium">
                    <i class="fab fa-medium-m"></i>
                </a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="section about" id="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <p class="about-text">
                    With over a decade of experience in investigative journalism, I've dedicated my career to uncovering stories that matter. My work focuses on holding power accountable, exposing corruption, and amplifying the voices of those who need to be heard. I've covered everything from corporate malfeasance to political scandals, always with a commitment to rigorous fact-checking and ethical reporting.
                </p>
                <p class="about-text">
                    My reporting has led to policy changes, corporate reforms, and increased transparency in government. I believe in the power of journalism to create positive change in society, and I'm passionate about mentoring the next generation of reporters who will continue this vital work.
                </p>
                <div class="skills">
                    <span class="skill">Investigative Reporting</span>
                    <span class="skill">Political Analysis</span>
                    <span class="skill">Corporate Accountability</span>
                    <span class="skill">Data Journalism</span>
                    <span class="skill">Digital Storytelling</span>
                    <span class="skill">Public Records</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Articles Section -->
    <section class="section articles" id="articles">
        <div class="container">
            <h2 class="section-title">Featured Articles</h2>
            <div class="articles-grid">
                <article class="article-card">
                    <div class="article-image">
                        <i class="fas fa-newspaper"></i>
                    </div>
                    <div class="article-content">
                        <h3 class="article-title">The Shadow Banking System: Uncovered</h3>
                        <p class="article-meta">The Washington Post • March 2024</p>
                        <p class="article-excerpt">A deep dive into the unregulated financial networks that nearly caused another economic crisis, exposing the key players and their risky practices.</p>
                        <a href="#" class="read-more">Read Full Article →</a>
                    </div>
                </article>

                <article class="article-card">
                    <div class="article-image">
                        <i class="fas fa-gavel"></i>
                    </div>
                    <div class="article-content">
                        <h3 class="article-title">Justice Delayed: Court System Failures</h3>
                        <p class="article-meta">The Guardian • February 2024</p>
                        <p class="article-excerpt">An investigation revealing how systemic failures in the court system have denied justice to thousands of vulnerable defendants nationwide.</p>
                        <a href="#" class="read-more">Read Full Article →</a>
                    </div>
                </article>

                <article class="article-card">
                    <div class="article-image">
                        <i class="fas fa-factory"></i>
                    </div>
                    <div class="article-content">
                        <h3 class="article-title">Environmental Cover-up Exposed</h3>
                        <p class="article-meta">ProPublica • January 2024</p>
                        <p class="article-excerpt">Exclusive documents reveal how a major corporation concealed environmental damage for over a decade, affecting thousands of residents.</p>
                        <a href="#" class="read-more">Read Full Article →</a>
                    </div>
                </article>

                <article class="article-card">
                    <div class="article-image">
                        <i class="fas fa-users"></i>
                    </div>
                    <div class="article-content">
                        <h3 class="article-title">The Forgotten Whistleblowers</h3>
                        <p class="article-meta">The New York Times • December 2023</p>
                        <p class="article-excerpt">A comprehensive look at government whistleblowers whose warnings went unheeded, and the consequences of ignoring their crucial insights.</p>
                        <a href="#" class="read-more">Read Full Article →</a>
                    </div>
                </article>
            </div>
        </div>
    </section>

    <!-- Media Features Section -->
    <section class="section media" id="media">
        <div class="container">
            <h2 class="section-title">Media Features</h2>
            <div class="media-grid">
                <div class="media-card">
                    <div class="media-icon">
                        <i class="fas fa-tv"></i>
                    </div>
                    <h3 class="media-title">CNN Newsroom</h3>
                    <p class="media-outlet">CNN • March 2024</p>
                    <p class="media-description">Live interview discussing the implications of the shadow banking investigation and its impact on financial regulation.</p>
                </div>

                <div class="media-card">
                    <div class="media-icon">
                        <i class="fas fa-microphone"></i>
                    </div>
                    <h3 class="media-title">Fresh Air</h3>
                    <p class="media-outlet">NPR • February 2024</p>
                    <p class="media-description">In-depth interview about investigative journalism techniques and the challenges facing modern newsrooms.</p>
                </div>

                <div class="media-card">
                    <div class="media-icon">
                        <i class="fas fa-podcast"></i>
                    </div>
                    <h3 class="media-title">On The Media</h3>
                    <p class="media-outlet">WNYC • January 2024</p>
                    <p class="media-description">Discussion on press freedom, source protection, and the evolving landscape of digital journalism.</p>
                </div>

                <div class="media-card">
                    <div class="media-icon">
                        <i class="fas fa-trophy"></i>
                    </div>
                    <h3 class="media-title">Polk Award Winner</h3>
                    <p class="media-outlet">Long Island University • 2023</p>
                    <p class="media-description">Recognized for outstanding investigative reporting on corporate environmental violations and cover-ups.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section contact" id="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-content">
                <form class="contact-form">
                    <div class="form-group">
                        <label for="name">Full Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email Address</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="subject">Subject</label>
                        <input type="text" id="subject" name="subject" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Message</label>
                        <textarea id="message" name="message" required placeholder="Your message here..."></textarea>
                    </div>
                    <button type="submit" class="submit-btn">Send Message</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-social">
                <a href="#" class="social-link" aria-label="Twitter">
                    <i class="fab fa-twitter"></i>
                </a>
                <a href="#" class="social-link" aria-label="LinkedIn">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="#" class="social-link" aria-label="Instagram">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="#" class="social-link" aria-label="Medium">
                    <i class="fab fa-medium-m"></i>
                </a>
            </div>
            <p>&copy; 2024 Alexandra Chen. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
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

        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 100) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        // Observe sections
        document.querySelectorAll('.section').forEach(section => {
            observer.observe(section);
        });

        // Observe individual cards with staggered animation
        const cardObserver = new IntersectionObserver((entries) => {
            entries.forEach((entry, index) => {
                if (entry.isIntersecting) {
                    setTimeout(() => {
                        entry.target.classList.add('visible');
                    }, index * 100);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.article-card, .media-card').forEach(card => {
            cardObserver.observe(card);
        });

        // Form submission
        document.querySelector('.contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form data
            const formData = new FormData(this);
            const data = Object.fromEntries(formData);
            
            // Simulate form submission
            const submitBtn = this.querySelector('.submit-btn');
            const originalText = submitBtn.textContent;
            
            submitBtn.textContent = 'Sending...';
            submitBtn.disabled = true;
            
            setTimeout(() => {
                alert('Thank you for your message! I\'ll get back to you soon.');
                this.reset();
                submitBtn.textContent = originalText;
                submitBtn.disabled = false;
            }, 2000);
        });

        // Parallax effect for hero section
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero');
            const rate = scrolled * -0.5;
            
            if (hero) {
                hero.style.transform = `translateY(${rate}px)`;
            }
        });

        // Add typing animation effect
        function typeWriter(element, text, speed = 50) {
            let i = 0;
            element.innerHTML = '';
            
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            
            type();
        }

        // Initialize typing animation when page loads
        window.addEventListener('load', () => {
            const heroTitle = document.querySelector('.hero h1');
            if (heroTitle) {
                const originalText = heroTitle.textContent;
                setTimeout(() => {
                    typeWriter(heroTitle, originalText, 100);
                }, 500);
            }
        });

        // Add smooth hover effects for skills
        document.querySelectorAll('.skill').forEach(skill => {
            skill.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.05) translateY(-2px)';
            });
            
            skill.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1) translateY(0)';
            });
        });

        // Add progressive loading animation for articles
        function animateCards() {
            const cards = document.querySelectorAll('.article-card, .media-card');
            cards.forEach((card, index) => {
                card.style.animationDelay = `${index * 0.1}s`;
            });
        }

        // Initialize progressive animations
        animateCards();

        // Add scroll-triggered counter animations
        function animateValue(element, start, end, duration) {
            const startTime = performance.now();
            const startVal = parseInt(start);
            const endVal = parseInt(end);
            
            function updateValue(currentTime) {
                const elapsed = currentTime - startTime;
                const progress = Math.min(elapsed / duration, 1);
                const current = Math.floor(startVal + (endVal - startVal) * progress);
                element.textContent = current;
                
                if (progress < 1) {
                    requestAnimationFrame(updateValue);
                }
            }
            
            requestAnimationFrame(updateValue);
        }

        // Enhanced mobile navigation (hamburger menu for mobile)
        function createMobileMenu() {
            const navContainer = document.querySelector('.nav-container');
            const navLinks = document.querySelector('.nav-links');
            
            // Create hamburger button
            const hamburger = document.createElement('button');
            hamburger.className = 'hamburger';
            hamburger.innerHTML = `
                <span></span>
                <span></span>
                <span></span>
            `;
            
            // Add hamburger styles
            const style = document.createElement('style');
            style.textContent = `
                .hamburger {
                    display: none;
                    flex-direction: column;
                    background: none;
                    border: none;
                    cursor: pointer;
                    padding: 0;
                    width: 30px;
                    height: 30px;
                    justify-content: space-between;
                }
                
                .hamburger span {
                    display: block;
                    height: 3px;
                    width: 100%;
                    background: var(--primary-color);
                    border-radius: 3px;
                    transition: all 0.3s ease;
                }
                
                .hamburger.active span:nth-child(1) {
                    transform: rotate(45deg) translate(8px, 8px);
                }
                
                .hamburger.active span:nth-child(2) {
                    opacity: 0;
                }
                
                .hamburger.active span:nth-child(3) {
                    transform: rotate(-45deg) translate(7px, -6px);
                }
                
                @media (max-width: 768px) {
                    .hamburger {
                        display: flex;
                    }
                    
                    .nav-links {
                        position: fixed;
                        top: 80px;
                        left: -100%;
                        width: 100%;
                        height: calc(100vh - 80px);
                        background: rgba(255, 255, 255, 0.98);
                        backdrop-filter: blur(10px);
                        flex-direction: column;
                        justify-content: flex-start;
                        align-items: center;
                        padding-top: 2rem;
                        transition: left 0.3s ease;
                        z-index: 999;
                    }
                    
                    .nav-links.active {
                        left: 0;
                    }
                    
                    .nav-links li {
                        margin: 1rem 0;
                    }
                    
                    .nav-links a {
                        font-size: 1.2rem;
                        padding: 0.5rem 1rem;
                    }
                }
            `;
            document.head.appendChild(style);
            
            navContainer.appendChild(hamburger);
            
            hamburger.addEventListener('click', () => {
                hamburger.classList.toggle('active');
                navLinks.classList.toggle('active');
            });
            
            // Close mobile menu when clicking on a link
            navLinks.querySelectorAll('a').forEach(link => {
                link.addEventListener('click', () => {
                    hamburger.classList.remove('active');
                    navLinks.classList.remove('active');
                });
            });
        }

        // Initialize mobile menu
        createMobileMenu();

        // Add scroll progress indicator
        function createScrollProgress() {
            const progressBar = document.createElement('div');
            progressBar.className = 'scroll-progress';
            
            const progressStyle = document.createElement('style');
            progressStyle.textContent = `
                .scroll-progress {
                    position: fixed;
                    top: 0;
                    left: 0;
                    width: 0%;
                    height: 3px;
                    background: var(--accent-color);
                    z-index: 9999;
                    transition: width 0.1s ease;
                }
            `;
            
            document.head.appendChild(progressStyle);
            document.body.appendChild(progressBar);
            
            window.addEventListener('scroll', () => {
                const windowHeight = document.documentElement.scrollHeight - window.innerHeight;
                const scrolled = (window.scrollY / windowHeight) * 100;
                progressBar.style.width = `${Math.min(scrolled, 100)}%`;
            });
        }

        // Initialize scroll progress
        createScrollProgress();

        // Add loading animation
        window.addEventListener('load', () => {
            document.body.classList.add('loaded');
            
            // Add loading styles
            const loadingStyle = document.createElement('style');
            loadingStyle.textContent = `
                body {
                    opacity: 0;
                    transition: opacity 0.5s ease;
                }
                
                body.loaded {
                    opacity: 1;
                }
            `;
            document.head.appendChild(loadingStyle);
        });
    </script>
</body>
</html>
