
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Sora:wght@300;400;600;700&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .readme {
    font-family: 'Sora', sans-serif;
    background: linear-gradient(135deg, #0d0d1a 0%, #0a0a16 50%, #0d0d1a 100%);
    color: #e2e8f0;
    min-height: 100vh;
    padding: 0;
    position: relative;
    overflow: hidden;
  }

  .stars {
    position: absolute; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none;
    background-image:
      radial-gradient(1px 1px at 10% 15%, rgba(255,255,255,0.6) 0%, transparent 100%),
      radial-gradient(1px 1px at 25% 40%, rgba(255,255,255,0.4) 0%, transparent 100%),
      radial-gradient(1.5px 1.5px at 60% 10%, rgba(255,255,255,0.7) 0%, transparent 100%),
      radial-gradient(1px 1px at 80% 25%, rgba(255,255,255,0.5) 0%, transparent 100%),
      radial-gradient(1px 1px at 45% 70%, rgba(255,255,255,0.3) 0%, transparent 100%),
      radial-gradient(1.5px 1.5px at 90% 60%, rgba(255,255,255,0.6) 0%, transparent 100%),
      radial-gradient(1px 1px at 15% 85%, rgba(255,255,255,0.4) 0%, transparent 100%),
      radial-gradient(1px 1px at 70% 90%, rgba(255,255,255,0.5) 0%, transparent 100%),
      radial-gradient(1px 1px at 35% 55%, rgba(255,255,255,0.3) 0%, transparent 100%),
      radial-gradient(1.5px 1.5px at 55% 30%, rgba(255,255,255,0.6) 0%, transparent 100%);
  }

  .glow-orb {
    position: absolute; border-radius: 50%; filter: blur(80px); pointer-events: none;
  }
  .orb1 { width: 300px; height: 300px; background: rgba(0, 201, 255, 0.07); top: -100px; left: -100px; }
  .orb2 { width: 250px; height: 250px; background: rgba(255, 111, 216, 0.07); bottom: 100px; right: -80px; }
  .orb3 { width: 200px; height: 200px; background: rgba(120, 80, 255, 0.06); top: 40%; left: 50%; }

  .content { position: relative; z-index: 1; padding: 2rem 1.5rem; max-width: 680px; margin: 0 auto; }

  /* HEADER */
  .header { text-align: center; padding: 2.5rem 0 1.5rem; }

  .avatar-ring {
    width: 90px; height: 90px; border-radius: 50%; margin: 0 auto 1rem;
    background: linear-gradient(135deg, #00C9FF, #FF6FD8, #7B5FFF);
    padding: 3px; display: flex; align-items: center; justify-content: center;
    animation: spin-slow 8s linear infinite;
  }
  .avatar-inner {
    width: 100%; height: 100%; border-radius: 50%; background: #0d0d1a;
    display: flex; align-items: center; justify-content: center;
    font-family: 'Space Mono', monospace; font-size: 28px; font-weight: 700;
    background: linear-gradient(135deg, #00C9FF, #FF6FD8);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  @keyframes spin-slow {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }

  .name {
    font-family: 'Sora', sans-serif; font-size: 2rem; font-weight: 700;
    background: linear-gradient(90deg, #00C9FF 0%, #a78bfa 50%, #FF6FD8 100%);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
    margin-bottom: 0.4rem; letter-spacing: -0.5px;
  }

  .tagline {
    font-size: 0.8rem; color: #94a3b8; letter-spacing: 0.08em; text-transform: uppercase;
    font-weight: 400; margin-bottom: 1rem;
  }

  .gif-container {
    margin: 1.5rem auto; max-width: 300px; border-radius: 12px; overflow: hidden;
    border: 1px solid rgba(255,255,255,0.08);
    box-shadow: 0 0 30px rgba(0, 201, 255, 0.12);
  }
  .gif-container img { width: 100%; display: block; }

  .quote {
    font-size: 0.85rem; color: #64748b; font-style: italic; margin-top: 0.75rem;
    letter-spacing: 0.03em;
  }

  /* DIVIDER */
  .divider {
    height: 1px; margin: 2rem 0;
    background: linear-gradient(90deg, transparent, rgba(0, 201, 255, 0.3), rgba(255, 111, 216, 0.3), transparent);
  }

  /* SECTIONS */
  .section-label {
    font-family: 'Space Mono', monospace; font-size: 0.7rem; color: #00C9FF;
    letter-spacing: 0.15em; text-transform: uppercase; margin-bottom: 0.75rem;
    display: flex; align-items: center; gap: 8px;
  }
  .section-label::after {
    content: ''; flex: 1; height: 1px;
    background: linear-gradient(90deg, rgba(0,201,255,0.3), transparent);
  }

  .section-title {
    font-size: 1.1rem; font-weight: 600; color: #f1f5f9; margin-bottom: 1rem;
  }

  /* ABOUT CARDS */
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }

  .about-card {
    background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.07);
    border-radius: 10px; padding: 0.85rem 1rem; transition: border-color 0.2s, background 0.2s;
  }
  .about-card:hover { background: rgba(255,255,255,0.05); border-color: rgba(0,201,255,0.2); }

  .about-card .icon { font-size: 1.2rem; margin-bottom: 0.35rem; }
  .about-card .label { font-size: 0.7rem; color: #64748b; text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 0.2rem; }
  .about-card .value { font-size: 0.82rem; color: #cbd5e1; line-height: 1.4; }

  /* TECH PILLS */
  .tech-grid { display: flex; flex-wrap: wrap; gap: 8px; }

  .tech-pill {
    display: flex; align-items: center; gap: 7px;
    background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.08);
    border-radius: 8px; padding: 6px 12px; font-size: 0.78rem; color: #94a3b8;
    transition: all 0.2s;
  }
  .tech-pill:hover {
    background: rgba(0, 201, 255, 0.06); border-color: rgba(0, 201, 255, 0.25); color: #e2e8f0;
    transform: translateY(-1px);
  }
  .tech-pill img { width: 18px; height: 18px; }

  /* SOCIAL LINKS */
  .social-grid { display: flex; flex-wrap: wrap; gap: 10px; }

  .social-btn {
    display: flex; align-items: center; gap: 8px;
    border-radius: 8px; padding: 8px 16px; font-size: 0.8rem; font-weight: 600;
    text-decoration: none; transition: all 0.2s; letter-spacing: 0.03em;
    border: 1px solid transparent;
  }
  .social-btn:hover { transform: translateY(-2px); }
  .social-btn svg { width: 16px; height: 16px; flex-shrink: 0; }

  .btn-linkedin { background: rgba(10,102,194,0.15); border-color: rgba(10,102,194,0.35); color: #60a5fa; }
  .btn-linkedin:hover { background: rgba(10,102,194,0.25); }
  .btn-gmail { background: rgba(209,72,54,0.12); border-color: rgba(209,72,54,0.3); color: #f87171; }
  .btn-gmail:hover { background: rgba(209,72,54,0.22); }
  .btn-whatsapp { background: rgba(37,211,102,0.1); border-color: rgba(37,211,102,0.28); color: #4ade80; }
  .btn-whatsapp:hover { background: rgba(37,211,102,0.2); }
  .btn-instagram { background: rgba(228,64,95,0.1); border-color: rgba(228,64,95,0.28); color: #f472b6; }
  .btn-instagram:hover { background: rgba(228,64,95,0.2); }

  /* FOOTER WAVE */
  .footer {
    margin-top: 2.5rem; text-align: center; padding: 2rem 0;
    border-top: 1px solid rgba(255,255,255,0.05);
  }
  .footer-text {
    font-family: 'Space Mono', monospace; font-size: 0.75rem; color: #475569;
    letter-spacing: 0.08em;
  }
  .footer-gradient {
    font-size: 1rem; margin-top: 0.5rem;
    background: linear-gradient(90deg, #00C9FF, #FF6FD8);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  }

  /* TYPING ANIMATION */
  .cursor { display: inline-block; width: 2px; height: 1em; background: #00C9FF; margin-left: 2px; animation: blink 1s step-end infinite; vertical-align: text-bottom; }
  @keyframes blink { 0%,100% { opacity:1; } 50% { opacity:0; } }

  /* FADE IN */
  .fade-in { animation: fadeIn 0.6s ease both; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: none; } }
  .delay-1 { animation-delay: 0.1s; }
  .delay-2 { animation-delay: 0.2s; }
  .delay-3 { animation-delay: 0.3s; }
  .delay-4 { animation-delay: 0.4s; }
  .delay-5 { animation-delay: 0.5s; }
</style>

<div class="readme">
  <div class="stars"></div>
  <div class="glow-orb orb1"></div>
  <div class="glow-orb orb2"></div>
  <div class="glow-orb orb3"></div>

  <div class="content">

    <!-- HEADER -->
    <div class="header fade-in">
      <div class="avatar-ring">
        <div class="avatar-inner">JA</div>
      </div>
      <div class="name">João Augusto</div>
      <div class="tagline">Front-End &amp; Mobile Developer &nbsp;·&nbsp; Passionate Learner &nbsp;·&nbsp; Gamer by Nature</div>
      <div class="gif-container">
        <img src="https://img1.picmix.com/output/stamp/normal/6/5/5/1/2621556_3a7b1.gif" alt="Cool animation" />
      </div>
      <div class="quote">"Where creativity meets code." ⚡</div>
    </div>

    <div class="divider"></div>

    <!-- ABOUT -->
    <div class="fade-in delay-1">
      <div class="section-label">// about me</div>
      <div class="about-grid">
        <div class="about-card">
          <div class="icon">🧠</div>
          <div class="label">Currently exploring</div>
          <div class="value">React · Flutter · C#</div>
        </div>
        <div class="about-card">
          <div class="icon">🎨</div>
          <div class="label">Passion</div>
          <div class="value">UI/UX design &amp; smooth animations</div>
        </div>
        <div class="about-card">
          <div class="icon">🚀</div>
          <div class="label">Focus</div>
          <div class="value">Intuitive, modern &amp; visually appealing digital experiences</div>
        </div>
        <div class="about-card">
          <div class="icon">🎮</div>
          <div class="label">Outside coding</div>
          <div class="value">Games &amp; analyzing their mechanics as mini-simulations</div>
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <!-- TECH -->
    <div class="fade-in delay-2">
      <div class="section-label">// tech & tools</div>
      <div class="tech-grid">
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JS" />
          JavaScript
        </div>
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React" />
          React
        </div>
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg" alt="C#" />
          C#
        </div>
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt="Node" />
          Node.js
        </div>
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python" />
          Python
        </div>
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git" />
          Git
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <!-- FRONT-END -->
    <div class="fade-in delay-3">
      <div class="section-label">// front-end & design</div>
      <div class="tech-grid">
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5" />
          HTML5
        </div>
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3" />
          CSS3
        </div>
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg" alt="Bootstrap" />
          Bootstrap
        </div>
        <div class="tech-pill">
          <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg" alt="Figma" />
          Figma
        </div>
      </div>
    </div>

    <div class="divider"></div>

    <!-- CONNECT -->
    <div class="fade-in delay-4">
      <div class="section-label">// connect with me</div>
      <div class="social-grid">
        <a href="https://www.linkedin.com/in/joão-augusto-silva-martins-2b523a1a8" target="_blank" class="social-btn btn-linkedin">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 0 1-2.063-2.065 2.064 2.064 0 1 1 2.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
        <a href="mailto:joaoaugustosm1103@gmail.com" target="_blank" class="social-btn btn-gmail">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L12 9.641l8.073-6.148C21.69 2.28 24 3.434 24 5.457z"/></svg>
          Gmail
        </a>
        <a href="https://wa.me/17992459258" target="_blank" class="social-btn btn-whatsapp">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 0 1-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 0 1-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 0 1 2.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0 0 12.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 0 0 5.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 0 0-3.48-8.413Z"/></svg>
          WhatsApp
        </a>
        <a href="https://www.instagram.com/joao_augustosm" target="_blank" class="social-btn btn-instagram">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/></svg>
          Instagram
        </a>
      </div>
    </div>

    <!-- FOOTER -->
    <div class="footer fade-in delay-5">
      <div class="footer-text">// thanks for visiting</div>
      <div class="footer-gradient">✦ keep building, keep creating ✦</div>
    </div>

  </div>
</div>
