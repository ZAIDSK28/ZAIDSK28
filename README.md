<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zaid Shaikh - Frontend Developer</title>
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
            color: white;
        }

        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .floating-shapes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .shape {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            animation: float 20s infinite linear;
        }

        .shape:nth-child(1) {
            width: 80px;
            height: 80px;
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .shape:nth-child(2) {
            width: 120px;
            height: 120px;
            top: 60%;
            left: 80%;
            animation-delay: 5s;
        }

        .shape:nth-child(3) {
            width: 60px;
            height: 60px;
            top: 80%;
            left: 20%;
            animation-delay: 10s;
        }

        @keyframes float {
            0% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
            100% { transform: translateY(0px) rotate(360deg); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            position: relative;
            z-index: 1;
        }

        .hero-section {
            text-align: center;
            padding: 4rem 0;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            margin-bottom: 3rem;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            animation: slideUp 1s ease-out;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .profile-avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4);
            background-size: 300% 300%;
            animation: gradientRotate 3s ease infinite;
            margin: 0 auto 2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
        }

        @keyframes gradientRotate {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .hero-title {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ffffff, #f0f0f0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: titleGlow 2s ease-in-out infinite alternate;
        }

        @keyframes titleGlow {
            from { text-shadow: 0 0 20px rgba(255, 255, 255, 0.5); }
            to { text-shadow: 0 0 30px rgba(255, 255, 255, 0.8); }
        }

        .hero-subtitle {
            font-size: 1.5rem;
            opacity: 0.9;
            margin-bottom: 2rem;
            animation: fadeIn 1.5s ease-out 0.5s both;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .stats-container {
            display: inline-flex;
            align-items: center;
            background: rgba(255, 255, 255, 0.15);
            padding: 1rem 2rem;
            border-radius: 50px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .stats-icon {
            width: 20px;
            height: 20px;
            margin-right: 0.5rem;
            fill: currentColor;
        }

        .section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 25px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            padding: 2.5rem;
            margin-bottom: 2rem;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            animation: slideUp 1s ease-out;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .section:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.2);
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 2rem;
            text-align: center;
            background: linear-gradient(45deg, #ffffff, #f0f0f0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .tech-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 1.5rem;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            animation: techItemFloat 3s ease-in-out infinite;
        }

        .tech-item:nth-child(even) {
            animation-delay: 1.5s;
        }

        @keyframes techItemFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .tech-item:hover {
            transform: translateY(-15px) scale(1.1);
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        .tech-icon {
            width: 50px;
            height: 50px;
            margin-bottom: 1rem;
            border-radius: 12px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            animation: iconSpin 4s linear infinite;
        }

        @keyframes iconSpin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .tech-item:hover .tech-icon {
            animation-play-state: paused;
        }

        .tech-name {
            font-weight: 600;
            text-align: center;
            font-size: 0.9rem;
        }

        .stats-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            animation: cardFloat 4s ease-in-out infinite;
        }

        .stat-card:nth-child(2) {
            animation-delay: 1.3s;
        }

        .stat-card:nth-child(3) {
            animation-delay: 2.6s;
        }

        @keyframes cardFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-8px); }
        }

        .stat-card:hover {
            transform: translateY(-15px) scale(1.05);
            background: rgba(255, 255, 255, 0.15);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .stat-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            border-radius: 15px;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            animation: statGlow 3s ease-in-out infinite alternate;
        }

        @keyframes statGlow {
            from { box-shadow: 0 5px 20px rgba(102, 126, 234, 0.4); }
            to { box-shadow: 0 10px 40px rgba(118, 75, 162, 0.6); }
        }

        .connect-section {
            text-align: center;
            padding: 3rem 0;
        }

        .connect-text {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            flex-wrap: wrap;
        }

        .social-link {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            background-size: 200% 200%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            color: white;
            font-size: 1.5rem;
            transition: all 0.3s ease;
            animation: socialFloat 3s ease-in-out infinite;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .social-link:nth-child(even) {
            animation-delay: 1s;
        }

        @keyframes socialFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .social-link:hover {
            transform: scale(1.2) translateY(-5px);
            background-position: 100% 100%;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero-title {
                font-size: 2.5rem;
            }
            
            .hero-subtitle {
                font-size: 1.2rem;
            }
            
            .section {
                padding: 1.5rem;
            }
            
            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
                gap: 1rem;
            }
            
            .stats-section {
                grid-template-columns: 1fr;
            }
            
            .container {
                padding: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="animated-bg"></div>
    <div class="floating-shapes">
        <div class="shape"></div>
        <div class="shape"></div>
        <div class="shape"></div>
    </div>

    <div class="container">
        <!-- Hero Section -->
        <div class="hero-section">
            <div class="profile-avatar">👋</div>
            <h1 class="hero-title">Hi, I'm Zaid Shaikh</h1>
            <p class="hero-subtitle">A passionate frontend developer from India</p>
            <div class="stats-container">
                <svg class="stats-icon" viewBox="0 0 24 24">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                </svg>
                <span>Profile Views: Loading...</span>
            </div>
        </div>

        <!-- Technologies Section -->
        <div class="section">
            <h2 class="section-title">🛠️ Languages and Tools</h2>
            <div class="tech-grid">
                <div class="tech-item">
                    <div class="tech-icon">🎨</div>
                    <div class="tech-name">CSS3</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🔥</div>
                    <div class="tech-name">Firebase</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">📝</div>
                    <div class="tech-name">Git</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🌐</div>
                    <div class="tech-name">HTML5</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">☕</div>
                    <div class="tech-name">Java</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">⚡</div>
                    <div class="tech-name">JavaScript</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🐧</div>
                    <div class="tech-name">Linux</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🗄️</div>
                    <div class="tech-name">MySQL</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">📮</div>
                    <div class="tech-name">Postman</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">⚛️</div>
                    <div class="tech-name">React</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🌱</div>
                    <div class="tech-name">Spring</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🎯</div>
                    <div class="tech-name">Tailwind</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">📘</div>
                    <div class="tech-name">TypeScript</div>
                </div>
            </div>
        </div>

        <!-- GitHub Stats Section -->
        <div class="section">
            <h2 class="section-title">📊 GitHub Statistics</h2>
            <div class="stats-section">
                <div class="stat-card">
                    <div class="stat-image">📈</div>
                    <h3>Most Used Languages</h3>
                    <p>Dynamic breakdown of my coding languages and their usage patterns across repositories.</p>
                </div>
                <div class="stat-card">
                    <div class="stat-image">⭐</div>
                    <h3>GitHub Stats</h3>
                    <p>Comprehensive overview of contributions, stars, and repository activity metrics.</p>
                </div>
                <div class="stat-card">
                    <div class="stat-image">🔥</div>
                    <h3>Contribution Streak</h3>
                    <p>Visualization of consistent coding habits and daily contribution patterns.</p>
                </div>
            </div>
        </div>

        <!-- Connect Section -->
        <div class="section connect-section">
            <h2 class="section-title">🤝 Let's Connect</h2>
            <p class="connect-text">Feel free to reach out for collaborations, discussions, or just to say hello!</p>
            <div class="social-links">
                <a href="#" class="social-link" title="LinkedIn">💼</a>
                <a href="#" class="social-link" title="GitHub">🐱</a>
                <a href="#" class="social-link" title="Twitter">🐦</a>
                <a href="#" class="social-link" title="Email">📧</a>
                <a href="#" class="social-link" title="Portfolio">🌐</a>
            </div>
        </div>
    </div>

    <script>
        // Simulate profile view counter animation
        let viewCount = 0;
        const targetViews = 1337;
        const counter = document.querySelector('.stats-container span');
        
        const countAnimation = setInterval(() => {
            viewCount += Math.floor(Math.random() * 50) + 10;
            if (viewCount >= targetViews) {
                viewCount = targetViews;
                clearInterval(countAnimation);
            }
            counter.textContent = `Profile Views: ${viewCount.toLocaleString()}`;
        }, 100);

        // Add dynamic interaction effects
        document.querySelectorAll('.tech-item').forEach(item => {
            item.addEventListener('mouseenter', () => {
                item.style.background = 'rgba(255, 255, 255, 0.25)';
            });
            
            item.addEventListener('mouseleave', () => {
                item.style.background = 'rgba(255, 255, 255, 0.1)';
            });
        });

        // Add scroll-triggered animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.section').forEach(section => {
            section.style.opacity = '0';
            section.style.transform = 'translateY(30px)';
            section.style.transition = 'all 0.6s ease';
            observer.observe(section);
        });

        // Add particle effect on hover
        document.addEventListener('mousemove', (e) => {
            if (Math.random() > 0.95) {
                const particle = document.createElement('div');
                particle.style.position = 'fixed';
                particle.style.left = e.clientX + 'px';
                particle.style.top = e.clientY + 'px';
                particle.style.width = '4px';
                particle.style.height = '4px';
                particle.style.background = 'rgba(255, 255, 255, 0.6)';
                particle.style.borderRadius = '50%';
                particle.style.pointerEvents = 'none';
                particle.style.zIndex = '1000';
                particle.style.animation = 'particleFade 1s ease-out forwards';
                
                document.body.appendChild(particle);
                
                setTimeout(() => {
                    particle.remove();
                }, 1000);
            }
        });

        // Add particle fade animation
        const style = document.createElement('style');
        style.textContent = `
            @keyframes particleFade {
                0% {
                    opacity: 1;
                    transform: scale(1);
                }
                100% {
                    opacity: 0;
                    transform: scale(0) translateY(-20px);
                }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>