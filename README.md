<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shadrack Abely - Legendary Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated background particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 1; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 0.5; }
        }

        /* Main container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
            z-index: 1;
        }

        /* Hero section */
        .hero {
            text-align: center;
            padding: 4rem 0;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            margin-bottom: 3rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 4s ease-in-out infinite;
            margin-bottom: 1rem;
            text-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
        }

        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .hero .subtitle {
            font-size: 1.5rem;
            color: rgba(255, 255, 255, 0.9);
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .hero .tagline {
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.8);
            max-width: 800px;
            margin: 0 auto;
            line-height: 1.6;
        }

        /* Tech stack showcase */
        .tech-stack {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .tech-card {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .tech-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .tech-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #ff6b6b, #4ecdc4, #45b7d1);
            animation: colorFlow 3s linear infinite;
        }

        @keyframes colorFlow {
            0% { background-position: 0% 50%; }
            100% { background-position: 200% 50%; }
        }

        .tech-card h3 {
            font-size: 1.5rem;
            color: white;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .tech-card p {
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.6;
            margin-bottom: 1.5rem;
        }

        .tech-icons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .tech-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-icon:hover {
            transform: scale(1.2) rotate(5deg);
        }

        .tech-icon.java { background: linear-gradient(135deg, #f89820, #ed8b00); }
        .tech-icon.dart { background: linear-gradient(135deg, #0175c2, #13b9fd); }
        .tech-icon.flutter { background: linear-gradient(135deg, #02569b, #0468d7); }
        .tech-icon.react { background: linear-gradient(135deg, #61dafb, #21759b); }
        .tech-icon.javascript { background: linear-gradient(135deg, #f7df1e, #f0db4f); }
        .tech-icon.html { background: linear-gradient(135deg, #e34f26, #f06529); }
        .tech-icon.css { background: linear-gradient(135deg, #1572b6, #33a9dc); }
        .tech-icon.tailwind { background: linear-gradient(135deg, #06b6d4, #0891b2); }

        /* Stats section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 900;
            color: #4ecdc4;
            margin-bottom: 0.5rem;
            text-shadow: 0 0 20px rgba(78, 205, 196, 0.5);
        }

        .stat-label {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
            font-weight: 500;
        }

        /* Contact section */
        .contact {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 3rem;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            margin: 3rem 0;
        }

        .contact h2 {
            font-size: 2.5rem;
            color: white;
            margin-bottom: 2rem;
            font-weight: 700;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 2rem 0;
        }

        .social-link {
            width: 80px;
            height: 80px;
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            font-size: 2rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s;
        }

        .social-link:hover::before {
            transform: translateX(100%);
        }

        .social-link:hover {
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }

        .social-link.twitter { background: linear-gradient(135deg, #1da1f2, #0d8bd9); }
        .social-link.linkedin { background: linear-gradient(135deg, #0077b5, #005885); }
        .social-link.github { background: linear-gradient(135deg, #333, #24292e); }
        .social-link.email { background: linear-gradient(135deg, #ea4335, #d33b2c); }

        .email-display {
            display: inline-block;
            background: rgba(255, 255, 255, 0.1);
            padding: 1rem 2rem;
            border-radius: 15px;
            color: white;
            font-size: 1.2rem;
            margin-top: 1rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .email-display:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: scale(1.05);
        }

        /* Fun fact section */
        .fun-fact {
            background: linear-gradient(135deg, rgba(255, 107, 107, 0.2), rgba(78, 205, 196, 0.2));
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 3rem;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            margin: 3rem 0;
            position: relative;
            overflow: hidden;
        }

        .fun-fact::before {
            content: '⚡';
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 3rem;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        .fun-fact h2 {
            font-size: 2rem;
            color: white;
            margin-bottom: 1.5rem;
            font-weight: 700;
        }

        .fun-fact p {
            color: rgba(255, 255, 255, 0.9);
            font-size: 1.1rem;
            line-height: 1.8;
            max-width: 800px;
            margin: 0 auto;
        }

        /* GitHub stats */
        .github-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .github-stat {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .github-stat:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        .github-stat img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            filter: brightness(1.1) saturate(1.2);
        }

        /* Responsive design */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero .subtitle {
                font-size: 1.2rem;
            }
            
            .hero .tagline {
                font-size: 1rem;
            }
            
            .tech-stack {
                grid-template-columns: 1fr;
            }
            
            .stats {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .social-links {
                flex-wrap: wrap;
                gap: 1rem;
            }
            
            .github-stats {
                grid-template-columns: 1fr;
            }
        }

        /* Loading animation */
        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            animation: fadeOut 2s ease-in-out 1s forwards;
        }

        .loading-text {
            font-size: 3rem;
            color: white;
            font-weight: 900;
            animation: pulse 1s infinite;
        }

        @keyframes fadeOut {
            to {
                opacity: 0;
                visibility: hidden;
            }
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.8s ease-out forwards;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <!-- Loading screen -->
    <div class="loading-overlay">
        <div class="loading-text">Loading Excellence...</div>
    </div>

    <!-- Animated background -->
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Hero Section -->
        <section class="hero fade-in">
            <h1>Shadrack Abely Mwang'onda</h1>
            <p class="subtitle">🚀 Legendary Full Stack Developer</p>
            <p class="tagline">
                Crafting digital experiences that transcend boundaries. Master of Java, Dart, Flutter, React.js, and the entire modern web ecosystem. 
                Building tomorrow's applications with today's cutting-edge technologies.
            </p>
        </section>

        <!-- Tech Stack Showcase -->
        <section class="tech-stack">
            <div class="tech-card fade-in">
                <h3>🏗️ Backend Mastery</h3>
                <p>Robust, scalable server-side solutions that power enterprise applications with unmatched performance and reliability.</p>
                <div class="tech-icons">
                    <div class="tech-icon java">☕</div>
                    <div class="tech-icon dart">🎯</div>
                </div>
            </div>

            <div class="tech-card fade-in">
                <h3>📱 Mobile Innovation</h3>
                <p>Cross-platform mobile applications that deliver native performance with Flutter's revolutionary framework.</p>
                <div class="tech-icons">
                    <div class="tech-icon flutter">🦋</div>
                    <div class="tech-icon dart">🎯</div>
                </div>
            </div>

            <div class="tech-card fade-in">
                <h3>🌐 Frontend Excellence</h3>
                <p>Interactive, responsive web applications that captivate users and drive engagement through modern frameworks.</p>
                <div class="tech-icons">
                    <div class="tech-icon react">⚛️</div>
                    <div class="tech-icon javascript">📜</div>
                </div>
            </div>

            <div class="tech-card fade-in">
                <h3>🎨 Design Systems</h3>
                <p>Pixel-perfect interfaces with modern CSS frameworks that ensure consistency and beauty across all platforms.</p>
                <div class="tech-icons">
                    <div class="tech-icon html">🏗️</div>
                    <div class="tech-icon css">🎨</div>
                    <div class="tech-icon tailwind">💨</div>
                </div>
            </div>
        </section>

        <!-- Stats Section -->
        <section class="stats">
            <div class="stat-card fade-in">
                <div class="stat-number">∞</div>
                <div class="stat-label">Lines of Code</div>
            </div>
            <div class="stat-card fade-in">
                <div class="stat-number">24/7</div>
                <div class="stat-label">Dedication</div>
            </div>
            <div class="stat-card fade-in">
                <div class="stat-number">100%</div>
                <div class="stat-label">Passion</div>
            </div>
            <div class="stat-card fade-in">
                <div class="stat-number">∞</div>
                <div class="stat-label">Possibilities</div>
            </div>
        </section>

        <!-- GitHub Stats -->
        <section class="github-stats">
            <div class="github-stat fade-in">
                <img src="https://github-readme-stats.vercel.app/api?username=shadythedecipher&show_icons=true&theme=radical&hide_border=true&bg_color=0D1117&title_color=F85D7F&icon_color=F8D866&text_color=FFFFFF" alt="GitHub Stats" />
            </div>
            <div class="github-stat fade-in">
                <img src="https://github-readme-stats.vercel.app/api/top-langs?username=shadythedecipher&show_icons=true&theme=radical&layout=compact&hide_border=true&bg_color=0D1117&title_color=F85D7F&text_color=FFFFFF" alt="Top Languages" />
            </div>
        </section>

        <!-- Fun Fact -->
        <section class="fun-fact fade-in">
            <h2>⚡ The Legend Behind the Code</h2>
            <p>
                I don't just write code—I architect digital dreams. My journey through diverse programming languages and technologies 
                isn't just about versatility; it's about pushing the boundaries of what's possible. Every line of code I write is 
                a step toward revolutionizing how we interact with technology. From mobile apps that feel magical to web applications 
                that redefine user experience, I'm not just keeping up with the evolution of software development—I'm leading it.
            </p>
        </section>

        <!-- Contact Section -->
        <section class="contact fade-in">
            <h2>🌟 Let's Build Something Legendary</h2>
            <p style="color: rgba(255, 255, 255, 0.8); font-size: 1.2rem; margin-bottom: 2rem;">
                Ready to turn your vision into reality? Let's collaborate on something extraordinary.
            </p>
            
            <div class="social-links">
                <a href="https://twitter.com/shedyixc" class="social-link twitter" target="_blank" rel="noopener noreferrer">
                    🐦
                </a>
                <a href="https://linkedin.com/in/shadrack-abely-2222841b9" class="social-link linkedin" target="_blank" rel="noopener noreferrer">
                    💼
                </a>
                <a href="https://github.com/shadythedecipher" class="social-link github" target="_blank" rel="noopener noreferrer">
                    🐙
                </a>
                <a href="mailto:shadrack.abely321@gmail.com" class="social-link email">
                    ✉️
                </a>
            </div>
            
            <div class="email-display">
                📧 shadrack.abely321@gmail.com
            </div>
        </section>
    </div>

    <script>
        // Create floating particles
        function createParticles() {
            const particles = document.getElementById('particles');
            const particleCount = 50;

            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particles.appendChild(particle);
            }
        }

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animationDelay = '0s';
                    entry.target.classList.add('fade-in');
                }
            });
        }, observerOptions);

        // Initialize everything when page loads
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            
            // Observe all elements with fade-in class
            document.querySelectorAll('.fade-in').forEach(el => {
                observer.observe(el);
            });

            // Add smooth scrolling for any anchor links
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

            // Add interactive tech icons
            document.querySelectorAll('.tech-icon').forEach(icon => {
                icon.addEventListener('click', function() {
                    this.style.transform = 'scale(1.3) rotate(360deg)';
                    setTimeout(() => {
                        this.style.transform = '';
                    }, 600);
                });
            });

            // Add dynamic background color change
            let hue = 0;
            setInterval(() => {
                hue = (hue + 1) % 360;
                document.body.style.background = `linear-gradient(135deg, hsl(${hue}, 70%, 60%) 0%, hsl(${(hue + 30) % 360}, 70%, 60%) 100%)`;
            }, 100);
        });

        // Add particle trail effect on mouse move
        document.addEventListener('mousemove', function(e) {
            const trail = document.createElement('div');
            trail.className = 'particle';
            trail.style.left = e.clientX + 'px';
            trail.style.top = e.clientY + 'px';
            trail.style.position = 'fixed';
            trail.style.pointerEvents = 'none';
            trail.style.zIndex = '1000';
            trail.style.opacity = '0.6';
            document.body.appendChild(trail);

            setTimeout(() => {
                trail.remove();
            }, 2000);
        });

        // Add keyboard interactions
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Enter' || e.key === ' ') {
                // Add a burst of particles
                for (let i = 0; i < 10; i++) {
                    setTimeout(() => {
                        const burst = document.createElement('div');
                        burst.className = 'particle';
                        burst.style.left = Math.random() * 100 + '%';
                        burst.style.top = Math.random() * 100 + '%';
                        burst.style.position = 'fixed';
                        burst.style.zIndex = '1000';
                        burst.style.background = `hsl(${Math.random() * 360}, 70%, 60%)`;
                        document.body.appendChild(burst);

                        setTimeout(() => {
                            burst.remove();
                        }, 3000);
                    }, i * 100);
                }
            }
        });
    </script>
</body>
</html>
