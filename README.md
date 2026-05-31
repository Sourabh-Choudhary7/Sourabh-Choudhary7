<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Sourabh Choudhary · Full Stack Developer Portfolio</title>
    <!-- Google Fonts & subtle font smoothing -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 (free icons) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #f8fafc 0%, #eef2f5 100%);
            font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif;
            padding: 2rem 1.5rem;
            color: #0a1e2f;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
        }

        /* card style & soft shadows */
        .card {
            background: rgba(255, 255, 255, 0.98);
            backdrop-filter: blur(0px);
            border-radius: 2rem;
            box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.08), 0 1px 2px rgba(0, 0, 0, 0.02);
            padding: 1.8rem 2rem;
            margin-bottom: 2rem;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .card:hover {
            transform: translateY(-3px);
            box-shadow: 0 25px 40px -14px rgba(0, 0, 0, 0.12);
        }

        /* header area animation + gradient */
        .profile-header {
            text-align: center;
            animation: fadeSlideUp 0.7s cubic-bezier(0.2, 0.9, 0.4, 1.1) forwards;
        }

        h1 {
            font-size: 2.6rem;
            font-weight: 700;
            background: linear-gradient(135deg, #1F2B3C, #2C3E50, #1A2A3F);
            background-size: 200% auto;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: shimmerMove 6s linear infinite;
            letter-spacing: -0.01em;
        }

        @keyframes shimmerMove {
            0% { background-position: 0% 50%; }
            100% { background-position: 200% 50%; }
        }

        .subtitle {
            font-size: 1.2rem;
            font-weight: 500;
            color: #2c5368;
            border-bottom: 2px solid rgba(44, 83, 104, 0.2);
            display: inline-block;
            padding-bottom: 6px;
            margin-top: 8px;
        }

        .view-count {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: #eef2ff;
            padding: 6px 16px;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            color: #1e4a6e;
            margin-top: 18px;
            backdrop-filter: blur(2px);
            transition: all 0.2s;
        }

        .view-count i {
            font-size: 1rem;
        }

        .info-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            margin-top: 1rem;
            justify-content: center;
        }

        .info-item {
            background: #f1f5f9;
            border-radius: 60px;
            padding: 0.5rem 1.3rem;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            font-weight: 500;
            font-size: 0.9rem;
            color: #0f3b5c;
            transition: 0.2s;
        }

        .info-item i {
            font-size: 1.1rem;
            color: #2c7da0;
        }

        .social-links {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            margin: 1.8rem 0 0.5rem 0;
        }

        .social-icon {
            background: #ffffff;
            border-radius: 50%;
            width: 48px;
            height: 48px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-size: 1.6rem;
            box-shadow: 0 5px 12px rgba(0,0,0,0.05);
            transition: all 0.25s ease;
            color: #1f4e6e;
            text-decoration: none;
        }

        .social-icon:hover {
            transform: translateY(-6px) scale(1.02);
            background: #1f4e6e;
            color: white;
            box-shadow: 0 15px 22px -12px rgba(31,78,110,0.4);
        }

        /* tech stack animation (icons pulse softly) */
        .tech-icons {
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            align-items: center;
            justify-content: center;
            margin-top: 1rem;
        }

        .tech-icons a, .tech-icons span {
            transition: all 0.2s ease;
            display: inline-block;
            animation: floatSoft 3s infinite ease-in-out;
        }

        .tech-icons a:hover, .tech-icons span:hover {
            transform: scale(1.1) rotate(2deg);
            filter: drop-shadow(0 8px 12px rgba(0,0,0,0.1));
            animation: none;
        }

        @keyframes floatSoft {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-5px); }
            100% { transform: translateY(0px); }
        }

        /* stats row - original untouched layout but with subtle fade-in */
        .stats-row {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: space-between;
            align-items: flex-start;
            margin-top: 1rem;
        }

        .stats-left {
            flex: 1;
            min-width: 240px;
        }

        .stats-center {
            flex: 1;
            min-width: 280px;
            text-align: center;
        }

        .stats-right {
            flex: 1;
            min-width: 280px;
            text-align: center;
        }

        img.stats-img {
            max-width: 100%;
            height: auto;
            border-radius: 18px;
            background: #fff;
            box-shadow: 0 8px 18px rgba(0,0,0,0.05);
            transition: all 0.3s;
        }

        img.stats-img:hover {
            transform: scale(1.01);
            box-shadow: 0 14px 28px rgba(0,0,0,0.1);
        }

        hr {
            margin: 1.5rem 0;
            border: 0;
            height: 1px;
            background: linear-gradient(90deg, transparent, #9bb6c5, transparent);
        }

        .bio-section {
            line-height: 1.55;
            color: #1e2f3e;
        }

        .bio-highlight {
            background: #e6f0f7;
            border-left: 5px solid #2c7da0;
            padding: 1rem 1.5rem;
            border-radius: 1rem;
            margin: 1.2rem 0;
            font-weight: 500;
        }

        @keyframes fadeSlideUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* responsiveness */
        @media (max-width: 780px) {
            .card {
                padding: 1.3rem;
            }
            h1 {
                font-size: 1.9rem;
            }
            .stats-row {
                flex-direction: column;
                align-items: center;
            }
            .tech-icons {
                gap: 0.8rem;
            }
        }

        footer {
            text-align: center;
            font-size: 0.75rem;
            color: #5a7e9a;
            margin-top: 2rem;
        }
    </style>
</head>
<body>
<div class="container">
    <!-- MAIN PROFILE CARD (with animations) -->
    <div class="card profile-header">
        <h1>👋 Hi, I'm Sourabh Choudhary</h1>
        <div class="subtitle">Full Stack Engineer · Scalable Systems · Clean Code</div>
        
        <!-- animated view counter (still same image but animated container) -->
        <div class="view-count">
            <i class="fas fa-eye"></i>
            <span>Profile visits: </span>
            <img src="https://komarev.com/ghpvc/?username=Sourabh-Choudhary7&label=views&color=0e75b6&style=flat" alt="Sourabh view counter" style="display: inline-block; vertical-align: middle; height: 20px;">
        </div>

        <!-- New bio summary (based on LinkedIn content) -->
        <div class="bio-section" style="margin-top: 1.5rem;">
            <p style="font-size: 1.02rem; font-weight: 500;">🚀 <strong>Full Stack Software Engineer</strong> with 2+ years of experience building scalable, high-performance web and mobile applications.</p>
            <div class="info-grid">
                <span class="info-item"><i class="fab fa-react"></i> React.js · Next.js · React Native</span>
                <span class="info-item"><i class="fab fa-node-js"></i> Node.js · Express.js</span>
                <span class="info-item"><i class="fas fa-database"></i> MongoDB · PostgreSQL</span>
                <span class="info-item"><i class="fas fa-cloud-upload-alt"></i> RESTful APIs · Auth systems</span>
            </div>
            <div class="bio-highlight">
                <i class="fas fa-bolt" style="margin-right: 8px; color:#2c7da0;"></i> 
                Focused on clean code, performance optimization, and scalable application architecture. 
                Passionate about solving real-world problems and delivering reliable, user-centric digital solutions.
            </div>
        </div>

        <!-- ask me about & learning snippet -->
        <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; margin: 20px 0 10px 0;">
            <span style="background:#eef2ff; border-radius:30px; padding:6px 18px;"><i class="fas fa-code"></i> 💬 Ask me about: React.js, Node.js, MongoDB, Express.js</span>
            <span style="background:#eef2ff; border-radius:30px; padding:6px 18px;"><i class="fas fa-seedling"></i> 🌱 Currently deepening Backend with Express, Node & Databases</span>
        </div>

        <!-- Connect section with animations / hover effects -->
        <div class="social-links">
            <a href="https://www.linkedin.com/in/sourabh-choudhary-286281256/" target="_blank" class="social-icon" aria-label="LinkedIn">
                <i class="fab fa-linkedin-in"></i>
            </a>
            <a href="https://www.geeksforgeeks.org/user/saurabhb78q1" target="_blank" class="social-icon" aria-label="GeeksforGeeks">
                <i class="fas fa-code"></i>
            </a>
            <a href="mailto:saurabh.bwn2001@gmail.com" class="social-icon" aria-label="Email">
                <i class="far fa-envelope"></i>
            </a>
        </div>
    </div>

    <!-- Languages and Tools (animated icons) -->
    <div class="card">
        <h3 style="display: flex; align-items: center; gap: 10px; margin-bottom: 20px;">
            <i class="fas fa-cogs" style="color: #2c7da0;"></i> 
            Languages & Tools
        </h3>
        <div class="tech-icons">
            <!-- HTML5 -->
            <a href="#" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="45" height="45"/></a>
            <!-- JavaScript -->
            <a href="#" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="45" height="45"/></a>
            <!-- React -->
            <a href="#" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="react" width="45" height="45"/></a>
            <!-- TypeScript -->
            <a href="#" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="typescript" width="45" height="45"/></a>
            <!-- Java -->
            <a href="#" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" width="45" height="45"/></a>
            <!-- MongoDB -->
            <a href="#" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="mongodb" width="45" height="45"/></a>
            <!-- NodeJS -->
            <a href="#" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="nodejs" width="50" height="50"/></a>
            <!-- ExpressJS (custom white bg friendly) -->
            <a href="#" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original-wordmark.svg" alt="expressjs" width="50" height="50" style="background: #1e2f3e; border-radius: 8px; padding: 4px;"/></a>
            <!-- PostgreSQL -->
            <a href="#" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="postgresql" width="45" height="45"/></a>
            <!-- Next.js (extra, to reflect bio) but still consistent -->
            <span><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nextjs/nextjs-original-wordmark.svg" alt="nextjs" width="45" height="45" style="filter: drop-shadow(0 1px 1px rgba(0,0,0,0.1));"/></span>
            <!-- React Native -->
            <span><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" alt="react-native" width="43" height="43"/></span>
        </div>
        <p style="font-size: 0.75rem; text-align: center; margin-top: 1.2rem; opacity: 0.7;"><i class="fas fa-magic"></i> Hover over any icon — soft floating animation ✨</p>
    </div>

    <!-- STATS SECTION - exactly preserved from original (top-langs, github stats, streak stats) 
         but wrapped with fade animation to respect original but no content change -->
    <div class="card" style="padding-bottom: 1.5rem;">
        <div class="stats-row">
            <!-- Left: Top Languages (exact original) -->
            <div class="stats-left">
                <p><img class="stats-img" align="left" src="https://github-readme-stats.vercel.app/api/top-langs?username=Sourabh-Choudhary7&show_icons=true&locale=en&layout=compact" alt="Sourabh-Choudhary7" style="margin-right: 0; width: 100%; max-width: 320px;" /></p>
            </div>
            <!-- Center: GitHub Stats (exact original) -->
            <div class="stats-center">
                <p><img class="stats-img" align="center" src="https://github-readme-stats.vercel.app/api?username=Sourabh-Choudhary7&show_icons=true&locale=en" alt="Sourabh-Choudhary7" style="width: 100%; max-width: 400px;" /></p>
            </div>
            <!-- Right: Streak Stats (exact original) -->
            <div class="stats-right">
                <p><img class="stats-img" align="center" src="https://github-readme-streak-stats.herokuapp.com/?user=Sourabh-Choudhary7" alt="GitHub Streak" style="width: 100%; max-width: 400px;" /></p>
            </div>
        </div>
        <hr />
        <p style="text-align: center; font-size: 0.85rem; margin-top: 0.5rem;"><i class="fas fa-chart-line"></i> GitHub analytics — realtime stats from your profile</p>
    </div>

    <!-- Extra animated pulse section about philosophy / optional -->
    <div class="card" style="background: linear-gradient(115deg, #ffffff, #f9fafb); text-align: center;">
        <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 2rem;">
            <div style="animation: fadeSlideUp 0.5s ease;">
                <i class="fas fa-layer-group" style="font-size: 2rem; color: #2c7da0;"></i>
                <h4 style="margin-top: 8px;">End-to-End Solutions</h4>
                <p style="font-size: 0.85rem;">Frontend architecture + secure backend APIs</p>
            </div>
            <div style="animation: fadeSlideUp 0.5s ease; animation-delay: 0.1s;">
                <i class="fas fa-shield-alt" style="font-size: 2rem; color: #2c7da0;"></i>
                <h4 style="margin-top: 8px;">Authentication & Security</h4>
                <p style="font-size: 0.85rem;">JWT, OAuth, role-based access systems</p>
            </div>
            <div style="animation: fadeSlideUp 0.5s ease; animation-delay: 0.2s;">
                <i class="fas fa-rocket" style="font-size: 2rem; color: #2c7da0;"></i>
                <h4 style="margin-top: 8px;">Performance Driven</h4>
                <p style="font-size: 0.85rem;">Optimized queries, caching & clean code</p>
            </div>
        </div>
        <div style="margin-top: 1.2rem; font-size: 0.9rem;">
            <i class="fas fa-map-marker-alt"></i> India · Open to collaborations
        </div>
    </div>
    <footer>
        <i class="far fa-copyright"></i> Sourabh Choudhary — Full Stack Developer | Built with 💙 & animated GitHub stats
    </footer>
</div>

<!-- optional small script to preserve original link behavior and smoothness - no stats modifications -->
</body>
</html>
