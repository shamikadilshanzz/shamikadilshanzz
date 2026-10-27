<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>iOS Modern · Shamika Dilshan</title>
    <!-- Fonts: SF Pro-like & modern -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <style>
        /* RESET + BASE — iOS Clean Canvas */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #f2f2f7;  /* iOS light gray background */
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            display: flex;
            justify-content: center;
            padding: 2rem 1.5rem;
            line-height: 1.5;
            color: #1c1c1e;
            min-height: 100vh;
        }

        /* main card – frosted glass iOS style, rounded, subtle shadow */
        .ios-card {
            max-width: 1000px;
            width: 100%;
            background: rgba(255, 255, 255, 0.75);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-radius: 44px;
            padding: 2.5rem 2.2rem;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25), 0 0 0 1px rgba(255, 255, 255, 0.8) inset;
            border: 1px solid rgba(255, 255, 255, 0.5);
            transition: all 0.3s ease;
            animation: cardAppear 0.8s cubic-bezier(0.23, 1, 0.32, 1);
        }

        @keyframes cardAppear {
            0% { opacity: 0; transform: scale(0.98) translateY(12px); }
            100% { opacity: 1; transform: scale(1) translateY(0); }
        }

        /* Typography – iOS weights and colors */
        h1, h2, h3 {
            font-weight: 700;
            letter-spacing: -0.022em;
            color: #1c1c1e;
        }

        h2 {
            font-size: 1.9rem;
            margin: 2.2rem 0 1.2rem 0;
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 700;
            letter-spacing: -0.03em;
            border-bottom: 1px solid rgba(60, 60, 67, 0.08);
            padding-bottom: 0.6rem;
        }

        h3 {
            font-size: 1.3rem;
            font-weight: 600;
            margin: 1.5rem 0 0.75rem 0;
            color: #2c2c2e;
        }

        /* emoji + icon alignment */
        .section-emoji {
            font-size: 1.8rem;
            margin-right: 6px;
            filter: drop-shadow(0 2px 4px rgba(0,0,0,0.05));
        }

        /* ——— ANIMATED TYPING HEADER (replaced with smooth fade + shimmer) ——— */
        .typing-header {
            text-align: center;
            margin-bottom: 2rem;
            position: relative;
            animation: fadeSlide 0.9s ease-out;
        }

        @keyframes fadeSlide {
            0% { opacity: 0; transform: translateY(-8px); }
            100% { opacity: 1; transform: translateY(0); }
        }

        .typing-header h1 {
            font-size: 3.2rem;
            font-weight: 800;
            letter-spacing: -0.04em;
            background: linear-gradient(135deg, #0a84ff, #5e5ce6, #bf5af2);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            display: inline-block;
            line-height: 1.2;
            margin-bottom: 0.5rem;
        }

        .typing-header .wave {
            display: inline-block;
            animation: wave 2.5s infinite;
            transform-origin: 70% 70%;
        }

        @keyframes wave {
            0% { transform: rotate(0deg); }
            10% { transform: rotate(14deg); }
            20% { transform: rotate(-8deg); }
            30% { transform: rotate(14deg); }
            40% { transform: rotate(-4deg); }
            50% { transform: rotate(10deg); }
            60% { transform: rotate(0deg); }
            100% { transform: rotate(0deg); }
        }

        .subhead {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.75rem 1.5rem;
            margin-top: 0.8rem;
            font-size: 1.5rem;
            font-weight: 500;
            color: #3a3a3c;
        }

        .subhead span {
            background: rgba(120, 120, 128, 0.08);
            padding: 0.4rem 1.1rem;
            border-radius: 40px;
            backdrop-filter: blur(4px);
            font-weight: 500;
            font-size: 1.1rem;
            color: #1c1c1e;
            transition: all 0.25s ease;
            border: 1px solid rgba(255,255,255,0.6);
        }

        .subhead span:hover {
            background: rgba(10, 132, 255, 0.12);
            transform: scale(1.02);
            border-color: rgba(10, 132, 255, 0.3);
        }

        /* About me – iOS pill style */
        .about-text {
            font-size: 1.18rem;
            line-height: 1.6;
            color: #2c2c2e;
            background: rgba(255, 255, 255, 0.6);
            border-radius: 28px;
            padding: 1.6rem 1.8rem;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.9);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.02);
            margin-bottom: 1.2rem;
        }

        .about-text p {
            margin-bottom: 0.75rem;
            display: flex;
            align-items: center;
            gap: 10px;
            flex-wrap: wrap;
        }

        .about-text p:last-child {
            margin-bottom: 0;
        }

        .about-text i {
            font-style: normal;
            background: rgba(10, 132, 255, 0.08);
            padding: 0.25rem 0.7rem;
            border-radius: 40px;
            font-size: 1rem;
            font-weight: 500;
            color: #0a84ff;
        }

        /* CV button – iOS filled style */
        .cv-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            background: #0a84ff;
            color: white;
            font-weight: 600;
            font-size: 1.2rem;
            padding: 0.9rem 2.2rem;
            border-radius: 50px;
            text-decoration: none;
            transition: all 0.2s cubic-bezier(0.2, 0.9, 0.4, 1);
            box-shadow: 0 4px 14px rgba(10, 132, 255, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.2);
            margin: 0.5rem 0 1rem 0;
            width: fit-content;
        }

        .cv-button:hover {
            background: #0071e3;
            transform: scale(1.02);
            box-shadow: 0 6px 20px rgba(10, 132, 255, 0.45);
        }

        .cv-button:active {
            transform: scale(0.98);
        }

        /* badge grid – tech stack */
        .badge-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 10px 12px;
            margin: 0.5rem 0 1.2rem 0;
        }

        .badge-grid img {
            height: 34px;
            width: auto;
            border-radius: 8px;
            transition: transform 0.15s ease, box-shadow 0.2s;
            box-shadow: 0 2px 6px rgba(0,0,0,0.05);
        }

        .badge-grid img:hover {
            transform: translateY(-3px) scale(1.03);
            box-shadow: 0 8px 16px rgba(0,0,0,0.12);
        }

        /* stats & graph containers – full-width, rounded */
        .stats-container {
            background: rgba(255, 255, 255, 0.6);
            border-radius: 32px;
            padding: 1.2rem 1rem;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.9);
            margin: 1rem 0;
            display: flex;
            justify-content: center;
            transition: all 0.2s ease;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.02);
        }

        .stats-container img {
            max-width: 100%;
            height: auto;
            border-radius: 18px;
        }

        /* featured project card */
        .project-card {
            background: rgba(255, 255, 255, 0.7);
            border-radius: 32px;
            padding: 1.6rem 2rem;
            border: 1px solid rgba(255, 255, 255, 0.9);
            box-shadow: 0 8px 22px -8px rgba(0, 0, 0, 0.08);
            transition: all 0.25s ease;
            margin: 1.2rem 0;
        }

        .project-card:hover {
            background: rgba(255, 255, 255, 0.9);
            box-shadow: 0 16px 32px -12px rgba(0, 0, 0, 0.2);
            transform: translateY(-3px);
        }

        .project-card h3 {
            margin-top: 0;
            font-size: 1.7rem;
            font-weight: 700;
            letter-spacing: -0.02em;
            background: linear-gradient(135deg, #0a84ff, #5e5ce6);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            display: inline-block;
        }

        .project-card a {
            text-decoration: none;
            color: #0a84ff;
            font-weight: 600;
            font-size: 1.1rem;
            display: inline-flex;
            align-items: center;
            gap: 5px;
            margin-bottom: 0.75rem;
            transition: gap 0.2s;
        }

        .project-card a:hover {
            gap: 10px;
            text-decoration: underline;
        }

        .project-card ul {
            list-style: none;
            margin-top: 0.8rem;
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem 1.5rem;
        }

        .project-card li {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 1.05rem;
            background: rgba(120, 120, 128, 0.06);
            padding: 0.35rem 1rem 0.35rem 0.9rem;
            border-radius: 40px;
            backdrop-filter: blur(2px);
        }

        /* Social icons – iOS circular */
        .social-icons {
            display: flex;
            justify-content: center;
            gap: 1.2rem;
            flex-wrap: wrap;
            margin: 1.8rem 0 1rem;
        }

        .social-icons a {
            display: flex;
            align-items: center;
            gap: 10px;
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(10px);
            padding: 0.75rem 1.8rem;
            border-radius: 100px;
            text-decoration: none;
            font-weight: 600;
            color: #1c1c1e;
            border: 1px solid rgba(255, 255, 255, 0.9);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.04);
            transition: all 0.2s;
            font-size: 1.1rem;
        }

        .social-icons a:hover {
            background: white;
            transform: scale(1.03);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.12);
            border-color: #0a84ff40;
        }

        .social-icons img {
            height: 28px;
            width: auto;
        }

        /* Connect section link buttons (original badges) but keep them pretty */
        .connect-badges {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 14px;
            margin: 1.5rem 0 0.5rem;
        }

        .connect-badges a img {
            height: 48px;
            border-radius: 16px;
            transition: transform 0.15s ease, filter 0.2s;
            filter: drop-shadow(0 4px 8px rgba(0,0,0,0.05));
        }

        .connect-badges a img:hover {
            transform: translateY(-4px) scale(1.02);
            filter: drop-shadow(0 8px 16px rgba(10, 132, 255, 0.25));
        }

        /* Open for opportunities */
        .opportunity {
            background: rgba(10, 132, 255, 0.08);
            border-radius: 32px;
            padding: 1.2rem 1.8rem;
            border: 1px solid rgba(10, 132, 255, 0.15);
            text-align: center;
            font-size: 1.2rem;
            font-weight: 500;
            margin: 2rem 0 0.5rem;
            backdrop-filter: blur(6px);
            color: #1c1c1e;
        }

        hr {
            border: none;
            border-top: 1px solid rgba(60, 60, 67, 0.12);
            margin: 2rem 0 1rem;
        }

        /* Responsive */
        @media (max-width: 600px) {
            body { padding: 0.8rem; }
            .ios-card { padding: 1.6rem 1.2rem; border-radius: 32px; }
            .typing-header h1 { font-size: 2.2rem; }
            .subhead span { font-size: 0.9rem; }
            h2 { font-size: 1.6rem; }
            .about-text { padding: 1.2rem; font-size: 1rem; }
            .cv-button { font-size: 1rem; padding: 0.75rem 1.8rem; }
            .badge-grid img { height: 28px; }
            .project-card { padding: 1.2rem; }
        }
    </style>
</head>
<body>
    <div class="ios-card">

        <!-- ——— ANIMATED HEADER (iOS style) ——— -->
        <div class="typing-header">
            <h1>
                Hi there! <span class="wave">👋</span><br>
                I'm SHAMIKA DILSHAN
            </h1>
            <div class="subhead">
                <span>Full Stack Developer</span>
                <span>Graphic Designer</span>
                <span>Video Editor</span>
                <span>Always Learning</span>
            </div>
        </div>

        <!-- 🚀 About Me -->
        <h2>
            <span class="section-emoji">🚀</span> About Me
        </h2>
        <div class="about-text">
            <p>
                <i>✨</i> I'm a passionate <strong>Full Stack Developer</strong> who loves building scalable web applications and exploring new technologies.
            </p>
            <p>
                <i>💡</i> I turn ideas into elegant, functional solutions with clean code and creative thinking.
            </p>
            <p><i>🔭</i> Currently working on exciting web projects &nbsp;·&nbsp; <i>🌱</i> Always learning</p>
            <p><i>🎯</i> Goal: Create impactful solutions that make a difference &nbsp;·&nbsp; <i>⚡</i> Fun fact: I debug with coffee ☕</p>
        </div>

        <!-- 📄 My CV button -->
        <div>
            <a href="./Shamika%20DIlshan.pdf" download class="cv-button">
                <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="margin-right: 4px;">
                    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4" />
                    <polyline points="7 10 12 15 17 10" />
                    <line x1="12" y1="15" x2="12" y2="3" />
                </svg>
                Download CV
            </a>
        </div>

        <!-- 🛠️ Tech Stack -->
        <h2>
            <span class="section-emoji">🛠️</span> Tech Stack
        </h2>

        <h3>Languages</h3>
        <div class="badge-grid">
            <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
            <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript">
            <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java">
            <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5">
            <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3">
        </div>

        <h3>Frontend</h3>
        <div class="badge-grid">
            <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React">
            <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js">
            <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="TailwindCSS">
        </div>

        <h3>Backend</h3>
        <div class="badge-grid">
            <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js">
            <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express.js">
        </div>

        <h3>Database</h3>
        <div class="badge-grid">
            <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB">
            <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL">
        </div>

        <h3>Tools & Others</h3>
        <div class="badge-grid">
            <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git">
            <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
            <img src="https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white" alt="VS Code">
            <img src="https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white" alt="Postman">
        </div>

        <!-- 📊 GitHub Stats -->
        <h2>
            <span class="section-emoji">📊</span> GitHub Stats
        </h2>
        <div class="stats-container">
            <img src="https://github-readme-streak-stats.herokuapp.com/?user=shamikadilshanzz&theme=tokyonight&hide_border=true" alt="GitHub Streak" height="170" style="max-width: 100%;">
        </div>

        <!-- 📈 Contribution Graph -->
        <h2>
            <span class="section-emoji">📈</span> Contribution Graph
        </h2>
        <div class="stats-container">
            <img src="https://github-readme-activity-graph.vercel.app/graph?username=shamikadilshanzz&theme=tokyo-night&hide_border=true" alt="Contribution Graph" style="width: 100%; border-radius: 18px;">
        </div>

        <!-- 🔥 Featured Projects -->
        <h2>
            <span class="section-emoji">🔥</span> Featured Projects
        </h2>

        <div class="project-card">
            <h3>🌟 Zayra-Project</h3>
            <a href="https://github.com/shamikadilshanzz/Zayra-Project" target="_blank">
                github.com/shamikadilshanzz/Zayra-Project
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
            </a>
            <p style="font-size: 1.1rem; margin-bottom: 0.5rem;">This is my first full-stack project 🦑🌟</p>
            <ul>
                <li>🛠️ React, Node.js, TypeScript, MongoDB</li>
                <li>⚡ Real-time updates, Authentication, Responsive design</li>
            </ul>
        </div>

        <!-- 🤝 Connect with Me -->
        <h2>
            <span class="section-emoji">🤝</span> Connect with Me
        </h2>
        <div class="connect-badges">
            <a href="https://www.linkedin.com/in/shamika-dilshan-193a4b268" target="_blank">
                <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
            </a>
            <a href="mailto:shamikadilshan1562@gmail.com">
                <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email">
            </a>
        </div>

        <!-- 💼 Open for Opportunities -->
        <div class="opportunity">
            💼 Open for Opportunities · I'm always interested in collaborating on innovative projects. Feel free to reach out!
        </div>

        <hr>

        <!-- subtle closing -->
        <div style="text-align: center; font-size: 0.9rem; color: #8e8e93; padding: 0.5rem 0 0.2rem;">
            ⚡ Designed with iOS modern vibes · Shamika Dilshan
        </div>

    </div> <!-- end ios-card -->
</body>
</html>
