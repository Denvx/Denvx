<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Denver – GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;600&family=Outfit:wght@300;400;600;700;900&display=swap" rel="stylesheet"/>
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg: #03070f;
  --bg2: #060d1a;
  --panel: #08111f;
  --border: #0e2040;
  --border2: #1a3a6a;
  --blue: #1466ff;
  --cyan: #00d4ff;
  --white: #eaf2ff;
  --dim: #3d5a80;
  --mono: 'IBM Plex Mono', monospace;
  --sans: 'Outfit', sans-serif;
}

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--white);
  font-family: var(--sans);
  min-height: 100vh;
  overflow-x: hidden;
}

/* === BACKGROUND FX === */
.bg-fx {
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
  overflow: hidden;
}

.bg-fx::before {
  content: '';
  position: absolute;
  top: -30%;
  left: 50%;
  transform: translateX(-50%);
  width: 900px;
  height: 900px;
  background: radial-gradient(ellipse, rgba(20,102,255,0.08) 0%, transparent 65%);
  animation: pulse 8s ease-in-out infinite;
}

.bg-fx::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(20,102,255,0.035) 1px, transparent 1px),
    linear-gradient(90deg, rgba(20,102,255,0.035) 1px, transparent 1px);
  background-size: 52px 52px;
}

@keyframes pulse {
  0%, 100% { opacity: 1; transform: translateX(-50%) scale(1); }
  50% { opacity: 0.6; transform: translateX(-50%) scale(1.12); }
}

/* === LAYOUT === */
.page {
  position: relative;
  z-index: 1;
  max-width: 820px;
  margin: 0 auto;
  padding: 80px 32px 100px;
}

/* === HERO === */
.hero {
  margin-bottom: 80px;
  animation: rise 0.9s cubic-bezier(.16,1,.3,1) both;
}

.hero-eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-family: var(--mono);
  font-size: 11px;
  letter-spacing: 0.22em;
  color: var(--cyan);
  text-transform: uppercase;
  margin-bottom: 28px;
}

.hero-eyebrow::before {
  content: '';
  width: 24px;
  height: 1px;
  background: var(--cyan);
}

.hero-name {
  font-size: clamp(52px, 10vw, 96px);
  font-weight: 900;
  letter-spacing: -0.04em;
  line-height: 0.92;
  margin-bottom: 24px;
}

.hero-name .line1 { display: block; color: var(--white); }
.hero-name .line2 {
  display: block;
  background: linear-gradient(90deg, var(--blue), var(--cyan));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-desc {
  font-size: 16px;
  font-weight: 300;
  color: var(--dim);
  max-width: 480px;
  line-height: 1.7;
  margin-bottom: 36px;
}

.hero-desc strong {
  color: #7da8d0;
  font-weight: 600;
}

.hero-pills {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.pill {
  font-family: var(--mono);
  font-size: 11px;
  letter-spacing: 0.1em;
  color: var(--cyan);
  background: rgba(0, 212, 255, 0.06);
  border: 1px solid rgba(0, 212, 255, 0.2);
  padding: 5px 14px;
  border-radius: 100px;
}

/* === SECTION === */
.section {
  margin-bottom: 64px;
}

.section-head {
  display: flex;
  align-items: center;
  gap: 14px;
  margin-bottom: 24px;
}

.section-head .num {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--blue);
  letter-spacing: 0.1em;
}

.section-head h2 {
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--white);
}

.section-head::after {
  content: '';
  flex: 1;
  height: 1px;
  background: linear-gradient(90deg, var(--border2), transparent);
}

/* === ABOUT TERMINAL === */
.terminal {
  background: var(--panel);
  border: 1px solid var(--border2);
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 24px 64px rgba(0,0,0,0.5), 0 0 0 1px rgba(20,102,255,0.06) inset;
}

.terminal-bar {
  background: #0d1a2e;
  padding: 10px 16px;
  display: flex;
  align-items: center;
  gap: 7px;
  border-bottom: 1px solid var(--border);
}

.dot { width: 11px; height: 11px; border-radius: 50%; }
.dot.r { background: #ff5f57; }
.dot.y { background: #febc2e; }
.dot.g { background: #28c840; }

.terminal-title {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--dim);
  margin-left: 8px;
}

.terminal-body {
  padding: 24px 28px;
  font-family: var(--mono);
  font-size: 13px;
  line-height: 2;
}

.t-line { display: flex; gap: 0; }
.t-prompt { color: var(--blue); white-space: nowrap; }
.t-cmd { color: var(--cyan); }
.t-out { color: #7da8d0; padding-left: 20px; }
.t-out b { color: var(--white); font-weight: 600; }
.t-blank { height: 8px; }
.t-cursor {
  display: inline-block;
  width: 8px;
  height: 14px;
  background: var(--cyan);
  vertical-align: middle;
  margin-left: 4px;
  animation: blink 1s step-end infinite;
  border-radius: 1px;
}

/* === TECH === */
.tech-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  gap: 10px;
}

.tech-card {
  background: var(--panel);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 18px 12px 14px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  transition: all 0.3s cubic-bezier(.16,1,.3,1);
  cursor: default;
  position: relative;
  overflow: hidden;
}

.tech-card::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--blue), var(--cyan));
  transform: scaleX(0);
  transition: transform 0.3s ease;
  transform-origin: left;
}

.tech-card:hover {
  border-color: rgba(20,102,255,0.5);
  transform: translateY(-4px);
  box-shadow: 0 12px 32px rgba(20,102,255,0.15);
  background: #0b1827;
}

.tech-card:hover::after { transform: scaleX(1); }

.tech-card img {
  width: 38px;
  height: 38px;
  object-fit: contain;
  transition: transform 0.3s ease;
}

.tech-card:hover img { transform: scale(1.12); }

.tech-label {
  font-family: var(--mono);
  font-size: 10px;
  color: var(--dim);
  letter-spacing: 0.1em;
  transition: color 0.3s;
}

.tech-card:hover .tech-label { color: var(--cyan); }

/* === STATS === */
.stats-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 12px;
}

.stat-frame {
  background: var(--panel);
  border: 1px solid var(--border);
  border-radius: 8px;
  overflow: hidden;
  padding: 12px;
  transition: border-color 0.3s, box-shadow 0.3s;
}

.stat-frame:hover {
  border-color: rgba(20,102,255,0.4);
  box-shadow: 0 8px 24px rgba(20,102,255,0.1);
}

.stat-frame img { width: 100%; display: block; border-radius: 4px; }

.contrib-frame {
  background: var(--panel);
  border: 1px solid var(--border);
  border-radius: 8px;
  overflow: hidden;
  padding: 16px 10px 10px;
  transition: border-color 0.3s;
}

.contrib-frame:hover { border-color: rgba(20,102,255,0.4); }
.contrib-frame img { width: 100%; display: block; }

/* === CONTACT === */
.contact-row {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.contact-link {
  display: inline-flex;
  align-items: center;
  gap: 11px;
  padding: 13px 22px;
  background: var(--panel);
  border: 1px solid var(--border2);
  border-radius: 8px;
  text-decoration: none;
  color: var(--white);
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 0.04em;
  transition: all 0.3s cubic-bezier(.16,1,.3,1);
  position: relative;
  overflow: hidden;
}

.contact-link::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(20,102,255,0.12), transparent);
  opacity: 0;
  transition: opacity 0.3s;
}

.contact-link:hover {
  border-color: var(--blue);
  transform: translateY(-3px);
  box-shadow: 0 10px 28px rgba(20,102,255,0.2);
  color: var(--cyan);
}

.contact-link:hover::before { opacity: 1; }

.contact-link img {
  width: 20px;
  height: 20px;
  position: relative;
  z-index: 1;
}

.contact-link span { position: relative; z-index: 1; }

.contact-link .arrow {
  font-size: 16px;
  color: var(--dim);
  transition: color 0.3s, transform 0.3s;
  position: relative;
  z-index: 1;
}

.contact-link:hover .arrow {
  color: var(--cyan);
  transform: translate(3px, -3px);
}

/* === STATUS BAR === */
.status-bar {
  margin-top: 80px;
  padding-top: 24px;
  border-top: 1px solid var(--border);
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 12px;
}

.status-left {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--dim);
  letter-spacing: 0.12em;
}

.status-right {
  display: flex;
  align-items: center;
  gap: 7px;
  font-family: var(--mono);
  font-size: 11px;
  color: #28c840;
  letter-spacing: 0.1em;
}

.status-dot {
  width: 7px;
  height: 7px;
  background: #28c840;
  border-radius: 50%;
  animation: pulse-dot 2s ease-in-out infinite;
}

@keyframes pulse-dot {
  0%, 100% { box-shadow: 0 0 0 0 rgba(40,200,64,0.4); }
  50% { box-shadow: 0 0 0 5px rgba(40,200,64,0); }
}

/* === ANIMATIONS === */
@keyframes rise {
  from { opacity: 0; transform: translateY(32px); }
  to   { opacity: 1; transform: translateY(0); }
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0; }
}

.s1 { animation: rise 0.9s cubic-bezier(.16,1,.3,1) 0.1s both; }
.s2 { animation: rise 0.9s cubic-bezier(.16,1,.3,1) 0.2s both; }
.s3 { animation: rise 0.9s cubic-bezier(.16,1,.3,1) 0.3s both; }
.s4 { animation: rise 0.9s cubic-bezier(.16,1,.3,1) 0.4s both; }
.s5 { animation: rise 0.9s cubic-bezier(.16,1,.3,1) 0.5s both; }

/* === RESPONSIVE === */
@media (max-width: 580px) {
  .stats-row { grid-template-columns: 1fr; }
  .page { padding: 48px 20px 72px; }
  .hero-name { font-size: clamp(42px, 12vw, 72px); }
}
</style>
</head>
<body>

<div class="bg-fx"></div>

<div class="page">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-eyebrow">disponível para oportunidades</div>
    <h1 class="hero-name">
      <span class="line1">Olá, sou</span>
      <span class="line2">Denver.</span>
    </h1>
    <p class="hero-desc">
      Estudante de <strong>Desenvolvimento de Sistemas</strong> no SENAI, 3º semestre.
      Apaixonado por transformar lógica em soluções reais — do código de baixo nível à web.
    </p>
    <div class="hero-pills">
      <span class="pill">SENAI · 3º SEM</span>
      <span class="pill">C / C++ / Java</span>
      <span class="pill">HTML · CSS · PHP</span>
      <span class="pill">MySQL · Git</span>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section s1">
    <div class="section-head">
      <span class="num">01</span>
      <h2>Sobre mim</h2>
    </div>
    <div class="terminal">
      <div class="terminal-bar">
        <div class="dot r"></div>
        <div class="dot y"></div>
        <div class="dot g"></div>
        <span class="terminal-title">denver@senai ~ about.sh</span>
      </div>
      <div class="terminal-body">
        <div class="t-line">
          <span class="t-prompt">denver@dev</span>
          <span class="t-prompt" style="color:#1466ff">:~$ </span>
          <span class="t-cmd">cat sobre.txt</span>
        </div>
        <div class="t-blank"></div>
        <div class="t-line"><span class="t-out">🎓 Cursando <b>Desenvolvimento de Sistemas no SENAI</b> — 3º semestre</span></div>
        <div class="t-line"><span class="t-out">🔧 Pratico lógica com <b>C, C++, Java, HTML, CSS, PHP e MySQL</b></span></div>
        <div class="t-line"><span class="t-out">🚀 Apaixonado por <b>resolver problemas reais com código</b></span></div>
        <div class="t-line"><span class="t-out">🌱 Sempre aprendendo — <b>comprometido com evolução constante</b></span></div>
        <div class="t-blank"></div>
        <div class="t-line">
          <span class="t-prompt">denver@dev</span>
          <span class="t-prompt" style="color:#1466ff">:~$ </span>
          <span class="t-cursor"></span>
        </div>
      </div>
    </div>
  </div>

  <!-- TECH -->
  <div class="section s2">
    <div class="section-head">
      <span class="num">02</span>
      <h2>Tecnologias</h2>
    </div>
    <div class="tech-grid">
      <div class="tech-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="C"/>
        <span class="tech-label">C</span>
      </div>
      <div class="tech-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg" alt="C++"/>
        <span class="tech-label">C++</span>
      </div>
      <div class="tech-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="Java"/>
        <span class="tech-label">Java</span>
      </div>
      <div class="tech-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5"/>
        <span class="tech-label">HTML5</span>
      </div>
      <div class="tech-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3"/>
        <span class="tech-label">CSS3</span>
      </div>
      <div class="tech-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" alt="PHP"/>
        <span class="tech-label">PHP</span>
      </div>
      <div class="tech-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="MySQL"/>
        <span class="tech-label">MySQL</span>
      </div>
      <div class="tech-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git"/>
        <span class="tech-label">Git</span>
      </div>
      <div class="tech-card">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub" style="filter:invert(0.6) brightness(1.4)"/>
        <span class="tech-label">GitHub</span>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section s3">
    <div class="section-head">
      <span class="num">03</span>
      <h2>GitHub Stats</h2>
    </div>
    <div class="stats-row">
      <div class="stat-frame">
        <img src="https://github-readme-stats.vercel.app/api?username=Denvx&show_icons=true&theme=dark&hide_title=false&hide_border=true&icon_color=1466ff&text_color=eaf2ff&bg_color=08111f&cache_seconds=1800" alt="GitHub Stats"/>
      </div>
      <div class="stat-frame">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Denvx&layout=compact&theme=dark&hide_border=true&text_color=eaf2ff&bg_color=08111f&langs_count=10&cache_seconds=1800" alt="Top Langs"/>
      </div>
    </div>
    <div class="contrib-frame">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=Denvx&theme=github-compact&area=true&hide_border=true&line=1466ff&point=00d4ff&color=eaf2ff&bg_color=08111f" alt="Activity Graph"/>
    </div>
  </div>

  <!-- CONTACT -->
  <div class="section s4">
    <div class="section-head">
      <span class="num">04</span>
      <h2>Contato</h2>
    </div>
    <div class="contact-row">
      <a class="contact-link" href="mailto:denver.o.dev@gmail.com">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/google/google-original.svg" alt="Email"/>
        <span>denver.o.dev@gmail.com</span>
        <span class="arrow">↗</span>
      </a>
      <a class="contact-link" href="https://github.com/Denvx" target="_blank">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub" style="filter:invert(0.6) brightness(1.5)"/>
        <span>github.com/Denvx</span>
        <span class="arrow">↗</span>
      </a>
    </div>
  </div>

  <!-- STATUS -->
  <div class="status-bar s5">
    <span class="status-left">DENVER · DESENVOLVEDOR EM FORMAÇÃO · SENAI 2025</span>
    <span class="status-right"><span class="status-dot"></span>OPEN TO WORK</span>
  </div>

</div>
</body>
</html>
