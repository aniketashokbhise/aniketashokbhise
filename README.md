<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Aniket Bhise — Full Stack Developer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600&family=Space+Grotesk:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: 'Space Grotesk', sans-serif;
      background: linear-gradient(135deg, #0d1117 0%, #161b22 60%, #0d1117 100%);
      min-height: 100vh;
      padding: 32px 24px;
      color: #e6edf3;
    }

    .card {
      max-width: 860px;
      margin: 0 auto;
      background: rgba(22,27,34,0.95);
      border: 1px solid #30363d;
      border-radius: 16px;
      overflow: hidden;
    }

    .hero {
      background: linear-gradient(120deg, #0d1117 0%, #161b22 40%, #1f2937 100%);
      padding: 40px 40px 32px;
      border-bottom: 1px solid #30363d;
      position: relative;
      overflow: hidden;
    }

    .hero::before {
      content: '';
      position: absolute;
      top: -60px; right: -60px;
      width: 260px; height: 260px;
      background: radial-gradient(circle, rgba(88,166,255,0.12) 0%, transparent 70%);
      border-radius: 50%;
    }

    .hero-top {
      display: flex;
      align-items: center;
      gap: 24px;
      margin-bottom: 20px;
    }

    .avatar {
      width: 80px; height: 80px;
      border-radius: 50%;
      background: linear-gradient(135deg, #58a6ff, #bc8cff);
      display: flex; align-items: center; justify-content: center;
      font-size: 28px; font-weight: 700;
      color: #fff;
      border: 3px solid #30363d;
      flex-shrink: 0;
    }

    .hero-text h1 {
      font-size: 26px;
      font-weight: 700;
      color: #e6edf3;
      margin-bottom: 4px;
    }

    .hero-text .tagline {
      font-size: 14px;
      color: #8b949e;
      font-family: 'Fira Code', monospace;
    }

    .hero-text .tagline span { color: #58a6ff; }

    .badges {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
      margin-top: 16px;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 5px 12px;
      border-radius: 20px;
      font-size: 12px;
      font-weight: 500;
      border: 1px solid;
    }

    .badge-blue { background: rgba(88,166,255,0.1); border-color: rgba(88,166,255,0.3); color: #58a6ff; }
    .badge-green { background: rgba(63,185,80,0.1); border-color: rgba(63,185,80,0.3); color: #3fb950; }
    .badge-purple { background: rgba(188,140,255,0.1); border-color: rgba(188,140,255,0.3); color: #bc8cff; }

    .dot { width: 7px; height: 7px; border-radius: 50%; display: inline-block; }
    .dot-blue { background: #58a6ff; }
    .dot-green { background: #3fb950; }
    .dot-purple { background: #bc8cff; }

    .body {
      padding: 32px 40px;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 28px;
    }

    .section-title {
      font-family: 'Fira Code', monospace;
      font-size: 11px;
      font-weight: 500;
      color: #58a6ff;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .section-title::after {
      content: '';
      flex: 1;
      height: 1px;
      background: #21262d;
    }

    .info-list { display: flex; flex-direction: column; gap: 10px; }

    .info-row {
      display: flex;
      align-items: flex-start;
      gap: 10px;
      font-size: 13.5px;
      color: #c9d1d9;
    }

    .info-icon { width: 18px; font-size: 14px; flex-shrink: 0; margin-top: 1px; }

    .info-row a { color: #58a6ff; text-decoration: none; font-size: 12px; word-break: break-all; }
    .info-row a:hover { text-decoration: underline; }

    .socials { display: flex; gap: 10px; flex-wrap: wrap; }

    .social-btn {
      display: flex;
      align-items: center;
      gap: 7px;
      padding: 7px 14px;
      border-radius: 8px;
      background: rgba(33,38,45,0.8);
      border: 1px solid #30363d;
      font-size: 12.5px;
      font-weight: 500;
      color: #c9d1d9;
      text-decoration: none;
      transition: border-color 0.2s, background 0.2s, color 0.2s;
    }

    .social-btn:hover { border-color: #58a6ff; background: rgba(88,166,255,0.08); color: #58a6ff; }
    .social-icon { width: 16px; height: 16px; }

    .full-width { grid-column: 1 / -1; }

    .skills-grid { display: flex; flex-wrap: wrap; gap: 8px; }

    .skill-chip {
      display: flex;
      align-items: center;
      gap: 6px;
      padding: 5px 12px;
      border-radius: 8px;
      background: #21262d;
      border: 1px solid #30363d;
      font-size: 12px;
      font-weight: 500;
      color: #c9d1d9;
      transition: border-color 0.2s, color 0.2s;
    }

    .skill-chip:hover { border-color: #58a6ff; color: #e6edf3; }

    .skill-dot { width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; }

    .streak-box {
      background: #21262d;
      border: 1px solid #30363d;
      border-radius: 10px;
      padding: 16px 20px;
      display: flex;
      justify-content: space-around;
      gap: 12px;
    }

    .streak-stat { text-align: center; }

    .streak-num {
      font-size: 22px;
      font-weight: 700;
      font-family: 'Fira Code', monospace;
    }

    .streak-label { font-size: 11px; color: #8b949e; margin-top: 3px; }

    .footer {
      padding: 18px 40px;
      border-top: 1px solid #21262d;
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: rgba(13,17,23,0.5);
    }

    .footer-text { font-family: 'Fira Code', monospace; font-size: 11px; color: #484f58; }

    .views-badge {
      display: flex;
      align-items: center;
      gap: 6px;
      background: rgba(88,166,255,0.08);
      border: 1px solid rgba(88,166,255,0.2);
      border-radius: 20px;
      padding: 4px 10px;
      font-size: 11px;
      color: #58a6ff;
      font-family: 'Fira Code', monospace;
    }

    @media (max-width: 600px) {
      .body { grid-template-columns: 1fr; }
      .hero { padding: 24px 20px 20px; }
      .body { padding: 20px; }
      .footer { padding: 14px 20px; flex-direction: column; gap: 8px; text-align: center; }
    }
  </style>
</head>
<body>
  <div class="card">
    <div class="hero">
      <div class="hero-top">
        <div class="avatar">AB</div>
        <div class="hero-text">
          <h1>Aniket Bhise</h1>
          <div class="tagline"><span>@aniketashokbhise</span> · Full Stack Developer</div>
        </div>
      </div>
      <div class="badges">
        <span class="badge badge-green"><span class="dot dot-green"></span>Open to work</span>
        <span class="badge badge-blue"><span class="dot dot-blue"></span>Currently building School LMS</span>
        <span class="badge badge-purple"><span class="dot dot-purple"></span>Learning something new every day</span>
      </div>
    </div>

    <div class="body">
      <div>
        <div class="section-title">About</div>
        <div class="info-list">
          <div class="info-row">
            <span class="info-icon">🔭</span>
            <span>Working on <strong style="color:#e6edf3;">School LMS</strong></span>
          </div>
          <div class="info-row">
            <span class="info-icon">💬</span>
            <span>Ask me about <strong style="color:#e6edf3;">Full Stack</strong> development</span>
          </div>
          <div class="info-row">
            <span class="info-icon">📫</span>
            <span><a href="mailto:aniketbhise449@gmail.com">aniketbhise449@gmail.com</a></span>
          </div>
          <div class="info-row">
            <span class="info-icon">👨‍💻</span>
            <a href="https://6964d9275d4ac6a0d8e79ca2--extraordinary-madeleine-6901e0.netlify.app/" target="_blank">View portfolio ↗</a>
          </div>
          <div class="info-row">
            <span class="info-icon">⚡</span>
            <span>Fun fact: I learn something new in tech every day</span>
          </div>
        </div>
      </div>

      <div>
        <div class="section-title">Connect</div>
        <div class="socials">
          <a class="social-btn" href="https://twitter.com/aniketbhise8204" target="_blank">
            <svg class="social-icon" viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.746l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
            Twitter
          </a>
          <a class="social-btn" href="https://linkedin.com/in/aniket-ashok-bhise-5bab61205" target="_blank">
            <svg class="social-icon" viewBox="0 0 24 24" fill="#0A66C2"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            LinkedIn
          </a>
          <a class="social-btn" href="https://instagram.com/aniketbhise8204" target="_blank">
            <svg class="social-icon" viewBox="0 0 24 24" fill="url(#ig)">
              <defs>
                <linearGradient id="ig" x1="0%" y1="100%" x2="100%" y2="0%">
                  <stop offset="0%" style="stop-color:#f09433"/>
                  <stop offset="25%" style="stop-color:#e6683c"/>
                  <stop offset="50%" style="stop-color:#dc2743"/>
                  <stop offset="75%" style="stop-color:#cc2366"/>
                  <stop offset="100%" style="stop-color:#bc1888"/>
                </linearGradient>
              </defs>
              <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/>
            </svg>
            Instagram
          </a>
        </div>
      </div>

      <div class="full-width">
        <div class="section-title">Languages &amp; Tools</div>
        <div class="skills-grid">
          <span class="skill-chip"><span class="skill-dot" style="background:#FF9900"></span>AWS</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#7952B3"></span>Bootstrap</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#1572B6"></span>CSS3</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#2496ED"></span>Docker</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#888"></span>Express.js</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#F24E1E"></span>Figma</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#FFCA28"></span>Firebase</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#F05032"></span>Git</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#E34F26"></span>HTML5</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#F7DF1E"></span>JavaScript</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#47A248"></span>MongoDB</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#4479A1"></span>MySQL</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#339933"></span>Node.js</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#5C3EE8"></span>OpenCV</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#F80000"></span>Oracle</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#FF6C37"></span>Postman</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#61DAFB"></span>React</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#61DAFB"></span>React Native</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#CC6699"></span>Sass</span>
          <span class="skill-chip"><span class="skill-dot" style="background:#06B6D4"></span>Tailwind CSS</span>
        </div>
      </div>

      <div class="full-width">
        <div class="section-title">GitHub Stats</div>
        <div class="streak-box">
          <div class="streak-stat">
            <div class="streak-num" style="color:#58a6ff;">∞</div>
            <div class="streak-label">Current Streak</div>
          </div>
          <div class="streak-stat">
            <div class="streak-num" style="color:#3fb950;">20+</div>
            <div class="streak-label">Projects</div>
          </div>
          <div class="streak-stat">
            <div class="streak-num" style="color:#bc8cff;">MERN</div>
            <div class="streak-label">Stack Focus</div>
          </div>
          <div class="streak-stat">
            <div class="streak-num" style="color:#f78166;">365</div>
            <div class="streak-label">Days Coding / Year</div>
          </div>
        </div>
      </div>
    </div>

    <div class="footer">
      <span class="footer-text">// aniketashokbhise · github.com</span>
      <span class="views-badge">
        <svg width="8" height="8" viewBox="0 0 8 8" fill="currentColor"><circle cx="4" cy="4" r="4"/></svg>
        profile views: live
      </span>
    </div>
  </div>
</body>
</html>
