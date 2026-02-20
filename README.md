<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Vishwas Saxena — GitHub README</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600;700&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --surface2: #1c2128;
    --border: #30363d;
    --cyan: #00f5ff;
    --green: #39d353;
    --yellow: #f1e05a;
    --purple: #a371f7;
    --pink: #f778ba;
    --orange: #fe7434;
    --text: #e6edf3;
    --muted: #8b949e;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Fira Code', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Starfield */
  .stars {
    position: fixed; inset: 0; pointer-events: none; z-index: 0;
    background: 
      radial-gradient(1px 1px at 10% 20%, #fff 0%, transparent 100%),
      radial-gradient(1px 1px at 30% 50%, #fff8 0%, transparent 100%),
      radial-gradient(1px 1px at 60% 15%, #fff 0%, transparent 100%),
      radial-gradient(1px 1px at 80% 70%, #fff8 0%, transparent 100%),
      radial-gradient(1px 1px at 50% 90%, #fff 0%, transparent 100%),
      radial-gradient(1px 1px at 90% 40%, #fff8 0%, transparent 100%),
      radial-gradient(1px 1px at 15% 80%, #fff 0%, transparent 100%),
      radial-gradient(1px 1px at 70% 55%, #fff 0%, transparent 100%);
  }

  .container {
    position: relative; z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 40px 24px 80px;
  }

  /* Banner */
  .banner {
    background: linear-gradient(135deg, #0d1117 0%, #1a0a2e 50%, #0d1117 100%);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 40px;
    text-align: center;
    position: relative;
    overflow: hidden;
    margin-bottom: 24px;
    animation: fadeUp 0.8s ease;
  }
  .banner::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse at 50% 0%, rgba(0,245,255,0.08) 0%, transparent 70%);
    pointer-events: none;
  }

  .ascii-art {
    font-size: 10px;
    line-height: 1.2;
    color: var(--cyan);
    text-shadow: 0 0 20px var(--cyan);
    margin-bottom: 24px;
    letter-spacing: 1px;
    white-space: pre;
    overflow-x: auto;
  }

  .typing-line {
    color: var(--cyan);
    font-size: 18px;
    font-weight: 500;
    display: inline-block;
    border-right: 2px solid var(--cyan);
    white-space: nowrap;
    overflow: hidden;
    width: 0;
    animation: typing 2.5s steps(40) 0.5s forwards, blink 0.8s step-end infinite;
  }
  .typing-line-2 {
    color: var(--green);
    font-size: 14px;
    display: inline-block;
    border-right: 2px solid var(--green);
    white-space: nowrap;
    overflow: hidden;
    width: 0;
    animation: typing 2s steps(45) 3.5s forwards, blink 0.8s step-end 3.5s infinite;
    margin-top: 8px;
  }

  @keyframes typing { to { width: 100%; } }
  @keyframes blink { 50% { border-color: transparent; } }

  .badges-row {
    display: flex; gap: 8px; justify-content: center; flex-wrap: wrap;
    margin-top: 20px;
    animation: fadeUp 0.8s ease 1s both;
  }
  .badge {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 4px 14px;
    font-size: 12px;
    color: var(--muted);
  }

  /* Sections */
  .section {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px;
    margin-bottom: 20px;
    animation: fadeUp 0.6s ease both;
  }

  .section-title {
    font-size: 16px;
    font-weight: 700;
    color: var(--cyan);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, var(--border), transparent);
  }

  /* Code block */
  .code-block {
    background: #010409;
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
    position: relative;
    overflow: hidden;
  }
  .code-block::before {
    content: '● ● ●';
    position: absolute;
    top: 10px; left: 14px;
    font-size: 10px;
    color: #ff5f57;
    letter-spacing: 4px;
  }
  .code-inner {
    margin-top: 20px;
    font-size: 13px;
    line-height: 1.8;
  }
  .kw { color: var(--purple); }
  .fn { color: #d2a8ff; }
  .str { color: var(--green); }
  .prop { color: #79c0ff; }
  .arr { color: var(--yellow); }
  .cmt { color: var(--muted); font-style: italic; }
  .bool { color: var(--orange); }

  /* Skill grid */
  .skill-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
    gap: 10px;
  }
  .skill-chip {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 8px;
    text-align: center;
    font-size: 12px;
    color: var(--text);
    cursor: default;
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
  }
  .skill-chip:hover {
    border-color: var(--cyan);
    color: var(--cyan);
    transform: translateY(-3px);
    box-shadow: 0 8px 20px rgba(0,245,255,0.1);
  }
  .skill-icon { font-size: 22px; }

  /* Skill bars */
  .skill-bar-row { margin-bottom: 14px; }
  .skill-bar-label {
    display: flex; justify-content: space-between;
    font-size: 13px; color: var(--text); margin-bottom: 6px;
  }
  .skill-bar-track {
    background: var(--surface2);
    border-radius: 20px;
    height: 8px;
    overflow: hidden;
    border: 1px solid var(--border);
  }
  .skill-bar-fill {
    height: 100%;
    border-radius: 20px;
    width: 0;
    transition: width 1.5s cubic-bezier(0.22, 1, 0.36, 1);
  }
  .bar-cyan { background: linear-gradient(to right, #005f72, var(--cyan)); box-shadow: 0 0 8px var(--cyan)44; }
  .bar-green { background: linear-gradient(to right, #0a4a1a, var(--green)); }
  .bar-purple { background: linear-gradient(to right, #2a0a4a, var(--purple)); }
  .bar-yellow { background: linear-gradient(to right, #3a2a00, var(--yellow)); }
  .bar-pink { background: linear-gradient(to right, #3a0a2a, var(--pink)); }

  /* Stats grid */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 12px;
  }
  .stat-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
    text-align: center;
    transition: all 0.3s;
  }
  .stat-card:hover {
    border-color: var(--cyan);
    box-shadow: 0 0 20px rgba(0,245,255,0.08);
    transform: scale(1.02);
  }
  .stat-number {
    font-size: 32px; font-weight: 700;
    color: var(--cyan);
    text-shadow: 0 0 20px var(--cyan)66;
  }
  .stat-label { font-size: 11px; color: var(--muted); margin-top: 4px; }

  /* Activity graph fake */
  .contribution-grid {
    display: grid;
    grid-template-columns: repeat(52, 1fr);
    gap: 2px;
    padding: 10px 0;
  }
  .contrib-week { display: flex; flex-direction: column; gap: 2px; }
  .contrib-day {
    width: 100%; padding-bottom: 100%;
    border-radius: 2px;
    background: var(--surface2);
    transition: all 0.2s;
    cursor: pointer;
  }
  .contrib-day:hover { transform: scale(1.5); z-index: 10; position: relative; }
  .c0 { background: #161b22; }
  .c1 { background: #0e4429; }
  .c2 { background: #006d32; }
  .c3 { background: #26a641; }
  .c4 { background: #39d353; }

  /* Connect */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 12px;
  }
  .connect-card {
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px;
    text-align: center;
    font-size: 13px;
    text-decoration: none;
    color: var(--text);
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    background: var(--surface2);
  }
  .connect-card:hover { transform: translateY(-4px); }
  .connect-card.email:hover { border-color: #ea4335; color: #ea4335; box-shadow: 0 8px 20px #ea433522; }
  .connect-card.linkedin:hover { border-color: #0077b5; color: #0077b5; box-shadow: 0 8px 20px #0077b522; }
  .connect-card.whatsapp:hover { border-color: #25d366; color: #25d366; box-shadow: 0 8px 20px #25d36622; }
  .connect-card.github:hover { border-color: var(--cyan); color: var(--cyan); box-shadow: 0 8px 20px rgba(0,245,255,0.15); }
  .connect-icon { font-size: 28px; }

  /* Quote */
  .quote-block {
    background: linear-gradient(135deg, #1a0a2e, #0a1a2e);
    border-left: 3px solid var(--cyan);
    padding: 16px 20px;
    border-radius: 0 10px 10px 0;
    color: var(--muted);
    font-style: italic;
    font-size: 14px;
  }

  /* Footer */
  .footer-wave {
    height: 4px;
    background: linear-gradient(to right, var(--cyan), var(--purple), var(--pink), var(--cyan));
    border-radius: 4px;
    margin-top: 30px;
    animation: shimmer 3s linear infinite;
    background-size: 200% auto;
  }
  @keyframes shimmer { to { background-position: 200% center; } }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  /* Delay utilities */
  .d1 { animation-delay: 0.1s; }
  .d2 { animation-delay: 0.2s; }
  .d3 { animation-delay: 0.3s; }
  .d4 { animation-delay: 0.4s; }
  .d5 { animation-delay: 0.5s; }

  /* Tabs */
  .tab-bar { display: flex; gap: 4px; margin-bottom: 16px; flex-wrap: wrap; }
  .tab {
    padding: 6px 14px; border-radius: 6px; font-size: 12px; cursor: pointer;
    background: var(--surface2); border: 1px solid var(--border); color: var(--muted);
    transition: all 0.2s;
  }
  .tab.active, .tab:hover { background: #1a2a3a; border-color: var(--cyan); color: var(--cyan); }

  .tab-pane { display: none; }
  .tab-pane.active { display: block; }
</style>
</head>
<body>
<div class="stars"></div>
<div class="container">

  <!-- BANNER -->
  <div class="banner">
    <div class="ascii-art">██╗   ██╗██╗███████╗██╗  ██╗██╗    ██╗ █████╗ ███████╗
██║   ██║██║██╔════╝██║  ██║██║    ██║██╔══██╗██╔════╝
██║   ██║██║███████╗███████║██║ █╗ ██║███████║███████╗
╚██╗ ██╔╝██║╚════██║██╔══██║██║███╗██║██╔══██║╚════██║
 ╚████╔╝ ██║███████║██║  ██║╚███╔███╔╝██║  ██║███████║
  ╚═══╝  ╚═╝╚══════╝╚═╝  ╚═╝ ╚══╝╚══╝ ╚═╝  ╚═╝╚══════╝</div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:8px">
      <div class="typing-line">Hey there 👋, I'm Vishwas Saxena</div>
      <div class="typing-line-2">Full-Stack Dev · MERN Alchemist · Code Craftsman</div>
    </div>
    <div class="badges-row">
      <span class="badge">👀 1.2k profile views</span>
      <span class="badge">🔥 Open to collaborate</span>
      <span class="badge">📍 India</span>
    </div>
  </div>

  <!-- WHOAMI -->
  <div class="section d1">
    <div class="section-title">🧬 <code>$ whoami</code></div>
    <div class="code-block">
      <div class="code-inner">
        <span class="kw">const</span> <span class="fn">vishwas</span> = {<br/>
        &nbsp;&nbsp;<span class="prop">name</span>        : <span class="str">"Vishwas Saxena"</span>,<br/>
        &nbsp;&nbsp;<span class="prop">role</span>        : <span class="str">"Full-Stack Developer"</span>,<br/>
        &nbsp;&nbsp;<span class="prop">stack</span>       : <span class="arr">["MongoDB", "Express.js", "React.js", "Node.js"]</span>,<br/>
        &nbsp;&nbsp;<span class="prop">passions</span>    : <span class="arr">["Clean Code", "Scalable Systems", "Great UX"]</span>,<br/>
        &nbsp;&nbsp;<span class="prop">currentFocus</span>: <span class="str">"Building production-grade MERN apps"</span>,<br/>
        &nbsp;&nbsp;<span class="prop">funFact</span>     : <span class="str">"I refactor my code more than I sleep 😅"</span>,<br/>
        &nbsp;&nbsp;<span class="prop">available</span>   : <span class="bool">true</span>, <span class="cmt">// ← Open to collaborate!</span><br/>
        };
      </div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="section d2">
    <div class="section-title">⚡ Tech Arsenal</div>
    <div class="tab-bar">
      <div class="tab active" onclick="switchTab(this,'frontend')">🎨 Frontend</div>
      <div class="tab" onclick="switchTab(this,'backend')">⚙️ Backend</div>
      <div class="tab" onclick="switchTab(this,'tools')">🛠 Tools</div>
    </div>
    <div id="frontend" class="tab-pane active">
      <div class="skill-grid">
        <div class="skill-chip"><span class="skill-icon">⚛️</span>React.js</div>
        <div class="skill-chip"><span class="skill-icon">🟨</span>JavaScript</div>
        <div class="skill-chip"><span class="skill-icon">🎨</span>Tailwind</div>
        <div class="skill-chip"><span class="skill-icon">🟠</span>HTML5</div>
        <div class="skill-chip"><span class="skill-icon">🔵</span>CSS3</div>
        <div class="skill-chip"><span class="skill-icon">🖌️</span>Figma</div>
      </div>
    </div>
    <div id="backend" class="tab-pane">
      <div class="skill-grid">
        <div class="skill-chip"><span class="skill-icon">🟢</span>Node.js</div>
        <div class="skill-chip"><span class="skill-icon">🚂</span>Express.js</div>
        <div class="skill-chip"><span class="skill-icon">🍃</span>MongoDB</div>
        <div class="skill-chip"><span class="skill-icon">🔮</span>REST APIs</div>
        <div class="skill-chip"><span class="skill-icon">📮</span>Postman</div>
        <div class="skill-chip"><span class="skill-icon">🔐</span>JWT Auth</div>
      </div>
    </div>
    <div id="tools" class="tab-pane">
      <div class="skill-grid">
        <div class="skill-chip"><span class="skill-icon">🔀</span>Git</div>
        <div class="skill-chip"><span class="skill-icon">🐙</span>GitHub</div>
        <div class="skill-chip"><span class="skill-icon">💙</span>VSCode</div>
        <div class="skill-chip"><span class="skill-icon">▲</span>Vercel</div>
        <div class="skill-chip"><span class="skill-icon">🐳</span>Docker</div>
        <div class="skill-chip"><span class="skill-icon">🧠</span>AI Tools</div>
      </div>
    </div>

    <!-- Skill bars -->
    <div style="margin-top:24px">
      <div class="skill-bar-row">
        <div class="skill-bar-label"><span>⚛️ React.js</span><span>90%</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill bar-cyan" data-width="90"></div></div>
      </div>
      <div class="skill-bar-row">
        <div class="skill-bar-label"><span>🟢 Node.js + Express</span><span>82%</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill bar-green" data-width="82"></div></div>
      </div>
      <div class="skill-bar-row">
        <div class="skill-bar-label"><span>🍃 MongoDB</span><span>78%</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill bar-purple" data-width="78"></div></div>
      </div>
      <div class="skill-bar-row">
        <div class="skill-bar-label"><span>🟨 JavaScript</span><span>88%</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill bar-yellow" data-width="88"></div></div>
      </div>
      <div class="skill-bar-row">
        <div class="skill-bar-label"><span>🎨 Tailwind CSS</span><span>85%</span></div>
        <div class="skill-bar-track"><div class="skill-bar-fill bar-pink" data-width="85"></div></div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section d3">
    <div class="section-title">📊 GitHub Command Center</div>
    <div class="stats-grid">
      <div class="stat-card">
        <div class="stat-number" data-count="42">0</div>
        <div class="stat-label">Repositories</div>
      </div>
      <div class="stat-card">
        <div class="stat-number" data-count="1200">0</div>
        <div class="stat-label">Commits (2024)</div>
      </div>
      <div class="stat-card">
        <div class="stat-number" data-count="156">0</div>
        <div class="stat-label">Contributions</div>
      </div>
      <div class="stat-card">
        <div class="stat-number" data-count="18">0</div>
        <div class="stat-label">Stars Earned</div>
      </div>
    </div>

    <!-- Contribution Graph -->
    <div style="margin-top:24px">
      <div style="font-size:12px;color:var(--muted);margin-bottom:10px">Contribution Activity (past year)</div>
      <div class="contribution-grid" id="contrib-graph"></div>
      <div style="display:flex;align-items:center;gap:6px;margin-top:8px;font-size:11px;color:var(--muted);justify-content:flex-end">
        Less
        <div style="width:10px;height:10px;border-radius:2px;background:#161b22"></div>
        <div style="width:10px;height:10px;border-radius:2px;background:#0e4429"></div>
        <div style="width:10px;height:10px;border-radius:2px;background:#006d32"></div>
        <div style="width:10px;height:10px;border-radius:2px;background:#26a641"></div>
        <div style="width:10px;height:10px;border-radius:2px;background:#39d353"></div>
        More
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section d4">
    <div class="section-title">🌐 Let's Build Something Together</div>
    <div class="connect-grid">
      <a class="connect-card email" href="mailto:vvishwas221@gmail.com">
        <span class="connect-icon">📧</span>
        <span>Email</span>
        <span style="font-size:10px;color:var(--muted)">vvishwas221@gmail.com</span>
      </a>
      <a class="connect-card linkedin" href="https://linkedin.com/in/vishwas-saxena-aa985a321" target="_blank">
        <span class="connect-icon">💼</span>
        <span>LinkedIn</span>
        <span style="font-size:10px;color:var(--muted)">vishwas-saxena</span>
      </a>
      <a class="connect-card whatsapp" href="https://wa.me/919548033751" target="_blank">
        <span class="connect-icon">💬</span>
        <span>WhatsApp</span>
        <span style="font-size:10px;color:var(--muted)">+91 95480 33751</span>
      </a>
      <a class="connect-card github" href="https://github.com/vishuuu2813" target="_blank">
        <span class="connect-icon">🐙</span>
        <span>GitHub</span>
        <span style="font-size:10px;color:var(--muted)">@vishuuu2813</span>
      </a>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="section d5">
    <div class="section-title">💬 Dev Mantra</div>
    <div class="quote-block">
      "First, solve the problem. Then, write the code." — John Johnson
    </div>
    <div style="text-align:center;margin-top:20px;color:var(--muted);font-size:12px">
      ⭐ Drop a star if you vibe with my work — it means the world!
    </div>
  </div>

  <div class="footer-wave"></div>
</div>

<script>
  // Tab switching
  function switchTab(el, id) {
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    document.querySelectorAll('.tab-pane').forEach(p => p.classList.remove('active'));
    el.classList.add('active');
    document.getElementById(id).classList.add('active');
  }

  // Animate skill bars on load
  window.addEventListener('load', () => {
    setTimeout(() => {
      document.querySelectorAll('.skill-bar-fill').forEach(bar => {
        bar.style.width = bar.dataset.width + '%';
      });
    }, 400);
  });

  // Count-up animation
  function animateCount(el) {
    const target = parseInt(el.dataset.count);
    const duration = 1800;
    const step = target / (duration / 16);
    let current = 0;
    const timer = setInterval(() => {
      current = Math.min(current + step, target);
      el.textContent = Math.floor(current).toLocaleString();
      if (current >= target) clearInterval(timer);
    }, 16);
  }

  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.querySelectorAll('[data-count]').forEach(animateCount);
        observer.unobserve(e.target);
      }
    });
  });
  document.querySelectorAll('.stats-grid') .forEach(el => observer.observe(el));

  // Generate contribution graph
  const grid = document.getElementById('contrib-graph');
  const levels = [0,0,0,1,1,1,2,2,3,3,4];
  for (let w = 0; w < 52; w++) {
    const week = document.createElement('div');
    week.className = 'contrib-week';
    for (let d = 0; d < 7; d++) {
      const day = document.createElement('div');
      const rand = Math.random();
      const lvl = rand < 0.35 ? 0 : rand < 0.55 ? 1 : rand < 0.72 ? 2 : rand < 0.88 ? 3 : 4;
      day.className = `contrib-day c${lvl}`;
      day.title = `${lvl === 0 ? 'No' : lvl} contribution${lvl !== 1 ? 's' : ''}`;
      week.appendChild(day);
    }
    grid.appendChild(week);
  }
</script>
</body>
</html>
