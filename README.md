<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BAKU - GitHub Profile</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 50%, #16213e 100%);
            color: #fff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
        }

        .baku-banner {
            position: relative;
            background: linear-gradient(45deg, #ff006e, #8338ec, #3a86ff);
            border-radius: 20px;
            padding: 60px 40px;
            margin-bottom: 30px;
            overflow: hidden;
        }

        .baku-banner::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><radialGradient id="g" cx="50%" cy="50%" r="50%"><stop offset="0%" stop-color="rgba(255,255,255,0.1)"/><stop offset="100%" stop-color="rgba(255,255,255,0)"/></radialGradient></defs><circle cx="20" cy="20" r="3" fill="url(%23g)"/><circle cx="80" cy="30" r="2" fill="url(%23g)"/><circle cx="40" cy="70" r="2.5" fill="url(%23g)"/><circle cx="90" cy="80" r="1.5" fill="url(%23g)"/></svg>') repeat;
            animation: float 6s ease-in-out infinite;
        }

        .baku-title {
            font-size: 4rem;
            font-weight: 900;
            text-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
            letter-spacing: 0.2em;
            position: relative;
            z-index: 2;
        }

        .greeting {
            font-size: 2.5rem;
            margin: 30px 0;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
        }

        .wave {
            animation: wave 2s infinite;
            transform-origin: 70% 70%;
        }

        .typing-text {
            border-right: 3px solid #ff006e;
            animation: blink 1s infinite;
        }

        .subtitle {
            font-size: 1.5rem;
            color: #00f5ff;
            font-weight: 600;
            margin-bottom: 20px;
            text-shadow: 0 0 20px rgba(0, 245, 255, 0.5);
        }

        .profile-stats {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            display: inline-block;
        }

        .social-section {
            margin: 40px 0;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 25px;
            text-align: center;
            background: linear-gradient(45deg, #ff006e, #8338ec);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .social-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-bottom: 30px;
        }

        .social-btn {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            position: relative;
            overflow: hidden;
        }

        .social-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .social-btn:hover::before {
            left: 100%;
        }

        .instagram {
            background: linear-gradient(45deg, #405de6, #5851db, #833ab4, #c13584, #e1306c, #fd1d1d);
            color: white;
        }

        .discord {
            background: #5865F2;
            color: white;
        }

        .tiktok {
            background: linear-gradient(45deg, #ff0050, #00f2ea);
            color: white;
        }

        .support-btn {
            background: linear-gradient(45deg, #ff6b6b, #ee5a52);
            color: white;
            font-size: 1.1rem;
            padding: 15px 30px;
            animation: pulse 2s infinite;
        }

        .support-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255, 107, 107, 0.4);
        }

        .skills-section {
            margin: 40px 0;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(60px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .skill-icon {
            width: 60px;
            height: 60px;
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
        }

        .skill-icon:hover {
            transform: translateY(-10px) rotate(5deg);
            filter: brightness(1.2);
        }

        .projects-section {
            margin: 40px 0;
        }

        .project-list {
            list-style: none;
            padding: 0;
        }

        .project-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 20px;
            margin: 15px 0;
            transition: all 0.3s ease;
        }

        .project-item:hover {
            transform: translateX(10px);
            border-color: #ff006e;
            box-shadow: 0 10px 30px rgba(255, 0, 110, 0.3);
        }

        .project-link {
            color: #00f5ff;
            text-decoration: none;
            font-weight: 600;
        }

        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(20deg); }
            75% { transform: rotate(-10deg); }
        }

        @keyframes blink {
            0%, 50% { border-color: #ff006e; }
            51%, 100% { border-color: transparent; }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(255, 107, 107, 0.7); }
            70% { box-shadow: 0 0 0 10px rgba(255, 107, 107, 0); }
            100% { box-shadow: 0 0 0 0 rgba(255, 107, 107, 0); }
        }

        @media (max-width: 768px) {
            .baku-title { font-size: 2.5rem; }
            .greeting { font-size: 1.8rem; }
            .social-buttons { flex-direction: column; align-items: center; }
            .skills-grid { grid-template-columns: repeat(auto-fit, minmax(50px, 1fr)); }
        }
    </style>
</head>
<body>
    <canvas class="matrix-bg" id="matrix"></canvas>
    
    <div class="container">
        <div class="header">
            <div class="baku-banner">
                <div class="baku-title">BAKU</div>
            </div>
            
            <div class="greeting">
                <span>Hi</span>
                <span class="wave">👋</span>
                <span>, I'm</span>
                <span id="typing-name" class="typing-text"></span>
            </div>
            
            <div class="subtitle" id="typing-subtitle"></div>
            
            <div class="profile-stats">
                <strong>Profile views:</strong> <span style="color: #00f5ff;">721</span>
            </div>
        </div>

        <div class="social-section">
            <h2 class="section-title">🌐 Connect With Me</h2>
            <div class="social-buttons">
                <a href="#" class="social-btn instagram">
                    <span>📷</span>
                    <span>Instagram</span>
                </a>
                <a href="#" class="social-btn discord">
                    <span>🎮</span>
                    <span>Discord</span>
                </a>
                <a href="#" class="social-btn tiktok">
                    <span>🎵</span>
                    <span>TikTok</span>
                </a>
            </div>
            
            <div style="text-align: center;">
                <a href="https://saweria.co/Kuzuroken" class="social-btn support-btn" target="_blank">
                    <span>☕</span>
                    <span>Support Me on Saweria</span>
                </a>
            </div>
        </div>

        <div class="projects-section">
            <h2 class="section-title">🚀 What I Do</h2>
            <ul class="project-list">
                <li class="project-item">
                    <span>🔐</span> <strong>Kesukaan SayaCrack</strong> - Cybersecurity enthusiast
                </li>
                <li class="project-item">
                    <span>🛡️</span> <strong>Proses Cyber</strong> - Digital security processes
                </li>
                <li class="project-item">
                    <span>💼</span> <strong>Project:</strong> 
                    <a href="https://portofolio-baku.netlify.app/" class="project-link" target="_blank">
                        Portfolio Website
                    </a>
                </li>
                <li class="project-item">
                    <span>📧</span> <strong>Contact:</strong> 
                    <a href="mailto:bakuff793@gmail.com" class="project-link">
                        bakuff793@gmail.com
                    </a>
                </li>
            </ul>
        </div>

        <div class="skills-section">
            <h2 class="section-title">💻 Languages & Tools</h2>
            <div class="skills-grid">
                <div class="skill-icon" style="background: linear-gradient(45deg, #00599C, #004482);" title="C++">C++</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #F7931E, #FFCA28);" title="Crypto">🔐</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #E34F26, #F16529);" title="HTML5">🌐</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #1572B6, #33A9DC);" title="CSS3">🎨</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #0078D4, #40E0D0);" title="Docker">🐳</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #FFCA28, #F7DF1E);" title="JavaScript">JS</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #FF6B35, #F7931E);" title="Git">📝</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #FF5722, #E64A19);" title="Firebase">🔥</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #4CAF50, #66BB6A);" title="Linux">🐧</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #FF6B6B, #EE5A52);" title="AI">🤖</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #61DAFB, #21D4FD);" title="React">⚛️</div>
                <div class="skill-icon" style="background: linear-gradient(45deg, #4FC08D, #42B883);" title="Vue">💚</div>
            </div>
        </div>
    </div>

    <script>
        // Matrix background effect
        const canvas = document.getElementById('matrix');
        const ctx = canvas.getContext('2d');

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        const matrix = "ABCDEFGHIJKLMNOPQRSTUVWXYZ123456789@#$%^&*()*&^%+-/~{[|`]}";
        const matrixArray = matrix.split("");

        const fontSize = 10;
        const columns = canvas.width / fontSize;

        const drops = [];
        for(let x = 0; x < columns; x++) {
            drops[x] = 1;
        }

        function draw() {
            ctx.fillStyle = 'rgba(15, 15, 35, 0.04)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            ctx.fillStyle = '#00ff00';
            ctx.font = fontSize + 'px monospace';

            for(let i = 0; i < drops.length; i++) {
                const text = matrixArray[Math.floor(Math.random() * matrixArray.length)];
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);

                if(drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }

        setInterval(draw, 35);

        // Typing animation
        function typeWriter(element, text, speed = 100) {
            let i = 0;
            element.innerHTML = '';
            
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                } else {
                    setTimeout(() => {
                        element.classList.remove('typing-text');
                        setTimeout(() => {
                            element.classList.add('typing-text');
                            typeWriter(element, text, speed);
                        }, 2000);
                    }, 1000);
                }
            }
            type();
        }

        // Start typing animations
        window.addEventListener('load', () => {
            const nameElement = document.getElementById('typing-name');
            const subtitleElement = document.getElementById('typing-subtitle');
            
            setTimeout(() => {
                typeWriter(nameElement, 'Faiz Fauzan', 150);
            }, 1000);
            
            setTimeout(() => {
                typeWriter(subtitleElement, 'Cyber Pemula Form Indonesia', 120);
            }, 3000);
        });

        // Resize canvas on window resize
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });

        // Add floating animation to skill icons
        document.querySelectorAll('.skill-icon').forEach((icon, index) => {
            icon.style.animationDelay = `${index * 0.1}s`;
            icon.style.animation = `float 3s ease-in-out infinite`;
        });
    </script>
</body>
</html>
