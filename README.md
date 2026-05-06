# lolokkabeats.github.io
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Lolokka Beats — Escolha o seu</title>
  <link href="https://fonts.googleapis.com/css2?family=Anton&family=Syne:wght@400;500;700;800&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
 
    :root {
      --bg:        #060a06;
      --bg2:       #0b100b;
      --bg3:       #0f160f;
      --green:     #2dff6e;
      --green2:    #00c44a;
      --green-dim: #0d3d1e;
      --green-glow:rgba(45,255,110,.18);
      --white:     #eef5ee;
      --gray:      #7a917a;
      --border:    rgba(45,255,110,.14);
      --font-head: 'Anton', sans-serif;
      --font-body: 'Syne', sans-serif;
    }
 
    html { scroll-behavior: smooth; }
 
    body {
      background: var(--bg);
      color: var(--white);
      font-family: var(--font-body);
      font-size: 16px;
      line-height: 1.65;
      overflow-x: hidden;
      cursor: default;
    }
 
    /* grain */
    body::after {
      content: '';
      position: fixed; inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='g'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23g)' opacity='0.035'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 999;
    }
 
    /* ═══ SCROLLBAR ═══ */
    ::-webkit-scrollbar { width: 4px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: var(--green-dim); border-radius: 99px; }
 
    /* ═══ NAV ═══ */
    nav {
      position: fixed; top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 20px 32px;
      background: rgba(6,10,6,.85);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }
 
    .nav-logo {
      font-family: var(--font-head);
      font-size: 1.5rem;
      letter-spacing: .06em;
      color: var(--green);
    }
 
    .nav-cta {
      background: var(--green);
      color: #030d06;
      font-family: var(--font-body);
      font-weight: 800;
      font-size: .78rem;
      letter-spacing: .08em;
      text-transform: uppercase;
      padding: 10px 22px;
      border-radius: 999px;
      text-decoration: none;
      transition: transform .2s, box-shadow .2s;
      box-shadow: 0 0 20px rgba(45,255,110,.3);
    }
    .nav-cta:hover { transform: scale(1.05); box-shadow: 0 0 35px rgba(45,255,110,.5); }
 
    /* ═══ HERO ═══ */
    .hero {
      min-height: 100svh;
      display: grid;
      place-items: center;
      text-align: center;
      padding: 140px 24px 80px;
      position: relative;
      overflow: hidden;
    }
 
    /* big glow orb */
    .hero::before {
      content: '';
      position: absolute;
      width: 800px; height: 800px;
      background: radial-gradient(circle, rgba(45,255,110,.13) 0%, transparent 65%);
      top: 50%; left: 50%;
      transform: translate(-50%,-52%);
      pointer-events: none;
      animation: orb 6s ease-in-out infinite;
    }
 
    /* grid lines */
    .hero::after {
      content: '';
      position: absolute; inset: 0;
      background-image:
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 80px 80px;
      mask-image: radial-gradient(ellipse 60% 60% at 50% 50%, black 20%, transparent 100%);
      pointer-events: none;
    }
 
    @keyframes orb {
      0%,100% { transform: translate(-50%,-52%) scale(1); opacity:.8; }
      50%      { transform: translate(-50%,-50%) scale(1.12); opacity:1; }
    }
 
    .hero-inner { position: relative; z-index: 1; }
 
    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: rgba(45,255,110,.07);
      border: 1px solid rgba(45,255,110,.25);
      color: var(--green);
      font-size: .72rem;
      font-weight: 700;
      letter-spacing: .18em;
      text-transform: uppercase;
      padding: 8px 20px;
      border-radius: 999px;
      margin-bottom: 36px;
      animation: fadeUp .5s ease both;
    }
 
    .live-dot {
      width: 7px; height: 7px;
      background: var(--green);
      border-radius: 50%;
      box-shadow: 0 0 8px var(--green);
      animation: blink 1.8s ease-in-out infinite;
    }
    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:.2} }
 
    .hero-title {
      font-family: var(--font-head);
      font-size: clamp(3.8rem, 14vw, 10rem);
      line-height: .92;
      letter-spacing: .02em;
      animation: fadeUp .55s .08s ease both;
    }
 
    .hero-title .outline {
      -webkit-text-stroke: 2px var(--green);
      color: transparent;
    }
 
    .hero-title .solid { color: var(--green); }
 
    .hero-by {
      font-size: clamp(1rem, 2.5vw, 1.25rem);
      color: var(--gray);
      font-weight: 500;
      margin-top: 20px;
      margin-bottom: 14px;
      animation: fadeUp .55s .16s ease both;
    }
 
    .hero-name {
      font-family: var(--font-head);
      font-size: clamp(1.8rem, 5vw, 3rem);
      letter-spacing: .08em;
      color: var(--white);
      animation: fadeUp .55s .22s ease both;
    }
 
    /* equalizer bars */
    .eq {
      display: flex;
      align-items: flex-end;
      gap: 5px;
      justify-content: center;
      margin: 56px auto 0;
      height: 60px;
      animation: fadeUp .55s .3s ease both;
    }
    .eq-bar {
      width: 6px;
      background: linear-gradient(to top, var(--green2), var(--green));
      border-radius: 3px 3px 0 0;
      animation: eq-anim 1s ease-in-out infinite alternate;
    }
    .eq-bar:nth-child(1)  { height:20%; animation-delay:.00s }
    .eq-bar:nth-child(2)  { height:55%; animation-delay:.07s }
    .eq-bar:nth-child(3)  { height:80%; animation-delay:.14s }
    .eq-bar:nth-child(4)  { height:45%; animation-delay:.21s }
    .eq-bar:nth-child(5)  { height:95%; animation-delay:.28s }
    .eq-bar:nth-child(6)  { height:65%; animation-delay:.35s }
    .eq-bar:nth-child(7)  { height:100%;animation-delay:.42s }
    .eq-bar:nth-child(8)  { height:55%; animation-delay:.49s }
    .eq-bar:nth-child(9)  { height:75%; animation-delay:.56s }
    .eq-bar:nth-child(10) { height:30%; animation-delay:.63s }
    .eq-bar:nth-child(11) { height:88%; animation-delay:.70s }
    .eq-bar:nth-child(12) { height:42%; animation-delay:.77s }
    .eq-bar:nth-child(13) { height:60%; animation-delay:.84s }
    .eq-bar:nth-child(14) { height:22%; animation-delay:.91s }
    @keyframes eq-anim {
      from { transform: scaleY(1); }
      to   { transform: scaleY(.2); }
    }
 
    /* ═══ SCROLL INDICATOR ═══ */
    .scroll-hint {
      position: absolute;
      bottom: 36px; left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      color: var(--gray);
      font-size: .72rem;
      font-weight: 600;
      letter-spacing: .12em;
      text-transform: uppercase;
      animation: fadeUp .6s .5s ease both;
    }
    .scroll-arrow {
      width: 24px; height: 40px;
      border: 2px solid var(--border);
      border-radius: 12px;
      display: flex;
      justify-content: center;
      padding-top: 6px;
    }
    .scroll-dot {
      width: 4px; height: 8px;
      background: var(--green);
      border-radius: 2px;
      animation: scroll-fall 1.5s ease-in-out infinite;
    }
    @keyframes scroll-fall {
      0%   { transform: translateY(0); opacity:1; }
      100% { transform: translateY(14px); opacity:0; }
    }
 
    /* ═══ GENERIC SECTION ═══ */
    .section {
      max-width: 1040px;
      margin: 0 auto;
      padding: 100px 24px;
    }
 
    .s-label {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      font-size: .72rem;
      font-weight: 700;
      letter-spacing: .18em;
      text-transform: uppercase;
      color: var(--green);
      margin-bottom: 16px;
    }
    .s-label::before {
      content: '';
      display: block;
      width: 28px; height: 2px;
      background: var(--green);
      border-radius: 99px;
    }
 
    .s-title {
      font-family: var(--font-head);
      font-size: clamp(2.4rem, 7vw, 5rem);
      line-height: .97;
      letter-spacing: .02em;
    }
 
    /* ═══ BENEFITS ═══ */
    .benefits { margin-top: 60px; display: flex; flex-direction: column; gap: 2px; }
 
    .benefit-row {
      display: grid;
      grid-template-columns: 80px 1fr;
      align-items: start;
      gap: 0 28px;
      padding: 28px 0;
      border-bottom: 1px solid var(--border);
      transition: background .25s;
      border-radius: 8px;
      padding-left: 12px;
      position: relative;
      overflow: hidden;
    }
    .benefit-row::before {
      content: '';
      position: absolute;
      left: 0; top: 0; bottom: 0;
      width: 3px;
      background: var(--green);
      transform: scaleY(0);
      transition: transform .3s;
      border-radius: 99px;
    }
    .benefit-row:hover::before { transform: scaleY(1); }
    .benefit-row:hover { background: rgba(45,255,110,.04); }
 
    .benefit-num {
      font-family: var(--font-head);
      font-size: 3.5rem;
      color: var(--green-dim);
      line-height: 1;
      padding-top: 4px;
      transition: color .3s;
    }
    .benefit-row:hover .benefit-num { color: rgba(45,255,110,.3); }
 
    .benefit-content { padding: 4px 0; }
    .benefit-title { font-weight: 800; font-size: 1.1rem; margin-bottom: 6px; }
    .benefit-desc  { color: var(--gray); font-size: .92rem; font-weight: 400; max-width: 560px; }
 
    /* ═══ GENRES STRIP ═══ */
    .genres-wrap {
      background: var(--bg2);
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      overflow: hidden;
      padding: 22px 0;
    }
    .genres-track {
      display: flex;
      gap: 40px;
      width: max-content;
      animation: marquee 18s linear infinite;
    }
    .genre-item {
      font-family: var(--font-head);
      font-size: 1.3rem;
      letter-spacing: .08em;
      white-space: nowrap;
      color: var(--gray);
      display: flex;
      align-items: center;
      gap: 20px;
    }
    .genre-item .dot { width:6px; height:6px; background:var(--green); border-radius:50%; }
    @keyframes marquee {
      from { transform: translateX(0); }
      to   { transform: translateX(-50%); }
    }
 
    /* ═══ TESTIMONIALS ═══ */
    .testi-grid {
      margin-top: 60px;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 16px;
    }
 
    .testi-card {
      background: var(--bg3);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 32px;
      position: relative;
      transition: border-color .3s, transform .3s;
    }
    .testi-card:hover {
      border-color: rgba(45,255,110,.35);
      transform: translateY(-5px);
    }
 
    .testi-card::after {
      content: '❝';
      position: absolute;
      top: 20px; right: 24px;
      font-size: 3rem;
      color: var(--green-dim);
      line-height: 1;
      font-family: Georgia, serif;
    }
 
    .stars {
      display: flex;
      gap: 3px;
      margin-bottom: 18px;
    }
    .star {
      width: 14px; height: 14px;
      background: var(--green);
      clip-path: polygon(50% 0%,61% 35%,98% 35%,68% 57%,79% 91%,50% 70%,21% 91%,32% 57%,2% 35%,39% 35%);
    }
 
    .testi-text {
      color: var(--gray);
      font-size: .94rem;
      font-weight: 400;
      margin-bottom: 24px;
      font-style: italic;
      line-height: 1.7;
    }
 
    .testi-bottom {
      display: flex;
      align-items: center;
      gap: 14px;
      padding-top: 20px;
      border-top: 1px solid var(--border);
    }
    .testi-avatar {
      width: 44px; height: 44px;
      background: var(--green-dim);
      border: 1.5px solid rgba(45,255,110,.4);
      border-radius: 50%;
      display: grid; place-items: center;
      font-weight: 800;
      font-size: .95rem;
      color: var(--green);
      flex-shrink: 0;
    }
    .testi-name { font-weight: 700; font-size: .95rem; margin-bottom: 2px; }
    .testi-role { color: var(--gray); font-size: .78rem; }
 
    /* ═══ CTA ═══ */
    .cta-section {
      position: relative;
      overflow: hidden;
    }
    .cta-section::before {
      content: '';
      position: absolute;
      width: 600px; height: 600px;
      background: radial-gradient(circle, rgba(45,255,110,.1) 0%, transparent 70%);
      bottom: -100px; left: 50%;
      transform: translateX(-50%);
      pointer-events: none;
    }
 
    .cta-inner {
      max-width: 720px;
      margin: 0 auto;
      padding: 100px 24px 120px;
      text-align: center;
      position: relative;
    }
 
    .urgency-pill {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: rgba(45,255,110,.07);
      border: 1px solid rgba(45,255,110,.3);
      color: var(--green);
      font-size: .75rem;
      font-weight: 700;
      letter-spacing: .14em;
      text-transform: uppercase;
      padding: 10px 22px;
      border-radius: 999px;
      margin-bottom: 36px;
      animation: pill-pulse 2.5s ease-in-out infinite;
    }
    @keyframes pill-pulse {
      0%,100% { box-shadow: 0 0 0 0 rgba(45,255,110,.2); }
      50%      { box-shadow: 0 0 0 8px rgba(45,255,110,0); }
    }
 
    .cta-title {
      font-family: var(--font-head);
      font-size: clamp(3rem, 9vw, 6.5rem);
      line-height: .93;
      letter-spacing: .02em;
      margin-bottom: 20px;
    }
    .cta-title span { color: var(--green); }
 
    .cta-sub {
      color: var(--gray);
      font-size: 1rem;
      max-width: 440px;
      margin: 0 auto 52px;
    }
 
    .btn-wa {
      display: inline-flex;
      align-items: center;
      gap: 14px;
      background: var(--green);
      color: #020d05;
      font-family: var(--font-body);
      font-weight: 800;
      font-size: 1rem;
      letter-spacing: .03em;
      padding: 22px 44px;
      border-radius: 999px;
      text-decoration: none;
      transition: transform .25s, box-shadow .25s;
      box-shadow: 0 0 40px rgba(45,255,110,.35), 0 4px 20px rgba(0,0,0,.4);
      position: relative;
      overflow: hidden;
    }
    .btn-wa::before {
      content: '';
      position: absolute; inset: 0;
      background: rgba(255,255,255,.12);
      transform: translateX(-100%) skewX(-12deg);
      transition: transform .35s;
    }
    .btn-wa:hover::before { transform: translateX(110%) skewX(-12deg); }
    .btn-wa:hover {
      transform: translateY(-4px) scale(1.03);
      box-shadow: 0 0 65px rgba(45,255,110,.55), 0 8px 30px rgba(0,0,0,.4);
    }
    .btn-wa svg { width: 24px; height: 24px; fill: #020d05; flex-shrink: 0; }
 
    .cta-note {
      margin-top: 28px;
      color: var(--gray);
      font-size: .8rem;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 16px;
      flex-wrap: wrap;
    }
    .cta-note span { display: flex; align-items: center; gap: 6px; }
    .cta-note em { color: var(--green); font-style: normal; }
 
    /* ═══ FOOTER ═══ */
    footer {
      border-top: 1px solid var(--border);
      padding: 44px 24px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 16px;
      text-align: center;
    }
 
    .footer-logo {
      font-family: var(--font-head);
      font-size: 2rem;
      letter-spacing: .1em;
      color: var(--green);
    }
 
    .footer-ig {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      color: var(--white);
      font-weight: 700;
      font-size: .9rem;
      text-decoration: none;
      padding: 10px 22px;
      border: 1px solid var(--border);
      border-radius: 999px;
      transition: border-color .25s, color .25s, background .25s;
    }
    .footer-ig:hover {
      border-color: var(--green);
      color: var(--green);
      background: rgba(45,255,110,.05);
    }
    .footer-ig svg { width: 16px; height: 16px; fill: currentColor; }
 
    footer small {
      color: var(--gray);
      font-size: .75rem;
      opacity: .5;
    }
 
    /* ═══ ANIMATIONS ═══ */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(22px); }
      to   { opacity: 1; transform: translateY(0); }
    }
 
    /* ═══ RESPONSIVE ═══ */
    @media (max-width: 640px) {
      nav { padding: 16px 20px; }
      .nav-cta { font-size: .7rem; padding: 9px 16px; }
      .benefit-row { grid-template-columns: 56px 1fr; }
      .benefit-num { font-size: 2.5rem; }
      .btn-wa { padding: 18px 28px; font-size: .9rem; }
    }
  </style>
</head>
<body>
 
  <!-- ═══ NAV ═══ -->
  <nav>
    <div class="nav-logo">LOLOKKA</div>
    <a class="nav-cta" href="https://wa.me/5511968812053?text=Oi%20Lolokka!%20Quero%20comprar%20um%20beat%20seu%20🎧" target="_blank" rel="noopener">
      Comprar Beat
    </a>
  </nav>
 
  <!-- ═══ HERO ═══ -->
  <section class="hero">
    <div class="hero-inner">
      <div class="hero-tag">
        <div class="live-dot"></div>
        Beats disponíveis agora
      </div>
 
      <h1 class="hero-title">
        <span class="outline">BEAT</span><br>
        <span class="solid">DO SEU</span><br>
        <span class="outline">JEITO</span>
      </h1>
 
      <p class="hero-by">Produzido por</p>
      <div class="hero-name">LOLOKKA</div>
 
      <div class="eq">
        <div class="eq-bar"></div><div class="eq-bar"></div>
        <div class="eq-bar"></div><div class="eq-bar"></div>
        <div class="eq-bar"></div><div class="eq-bar"></div>
        <div class="eq-bar"></div><div class="eq-bar"></div>
        <div class="eq-bar"></div><div class="eq-bar"></div>
        <div class="eq-bar"></div><div class="eq-bar"></div>
        <div class="eq-bar"></div><div class="eq-bar"></div>
      </div>
    </div>
 
    <div class="scroll-hint">
      <div class="scroll-arrow"><div class="scroll-dot"></div></div>
      role pra baixo
    </div>
  </section>
 
  <!-- ═══ GENRES STRIP ═══ -->
  <div class="genres-wrap">
    <div class="genres-track">
      <div class="genre-item">Trap<span class="dot"></span></div>
      <div class="genre-item">Drill<span class="dot"></span></div>
      <div class="genre-item">Funk<span class="dot"></span></div>
      <div class="genre-item">Hip-Hop<span class="dot"></span></div>
      <div class="genre-item">RnB<span class="dot"></span></div>
      <div class="genre-item">Afrobeat<span class="dot"></span></div>
      <div class="genre-item">Phonk<span class="dot"></span></div>
      <div class="genre-item">Cloud Rap<span class="dot"></span></div>
      <!-- duplicate for seamless loop -->
      <div class="genre-item">Trap<span class="dot"></span></div>
      <div class="genre-item">Drill<span class="dot"></span></div>
      <div class="genre-item">Funk<span class="dot"></span></div>
      <div class="genre-item">Hip-Hop<span class="dot"></span></div>
      <div class="genre-item">RnB<span class="dot"></span></div>
      <div class="genre-item">Afrobeat<span class="dot"></span></div>
      <div class="genre-item">Phonk<span class="dot"></span></div>
      <div class="genre-item">Cloud Rap<span class="dot"></span></div>
    </div>
  </div>
 
  <!-- ═══ BENEFITS ═══ -->
  <div class="section">
    <div class="s-label">Por que escolher</div>
    <h2 class="s-title">5 RAZÕES<br>PRA FECHAR<br>COM LOLOKKA</h2>
 
    <div class="benefits">
 
      <div class="benefit-row">
        <div class="benefit-num">01</div>
        <div class="benefit-content">
          <div class="benefit-title">Você escolhe o beat que quiser</div>
          <p class="benefit-desc">Nada de pack genérico. Você ouve, escolhe o beat que combina com sua vibe e fecha só o que realmente vai usar.</p>
        </div>
      </div>
 
      <div class="benefit-row">
        <div class="benefit-num">02</div>
        <div class="benefit-content">
          <div class="benefit-title">Qualidade de estúdio profissional</div>
          <p class="benefit-desc">Cada beat é mixado e masterizado no nível certo para streaming. Spotify, YouTube, shows — soa bem em qualquer lugar.</p>
        </div>
      </div>
 
      <div class="benefit-row">
        <div class="benefit-num">03</div>
        <div class="benefit-content">
          <div class="benefit-title">Licença comercial inclusa</div>
          <p class="benefit-desc">Libera direto. Use em músicas comerciais, clipes e apresentações sem dor de cabeça com direitos autorais.</p>
        </div>
      </div>
 
      <div class="benefit-row">
        <div class="benefit-num">04</div>
        <div class="benefit-content">
          <div class="benefit-title">Entrega rápida — sem enrolação</div>
          <p class="benefit-desc">Você fecha no WhatsApp, confirma o pagamento e recebe os arquivos na hora. Sem espera, sem burocracia.</p>
        </div>
      </div>
 
      <div class="benefit-row">
        <div class="benefit-num">05</div>
        <div class="benefit-content">
          <div class="benefit-title">Suporte direto com o produtor</div>
          <p class="benefit-desc">Qualquer dúvida sobre o beat, mix ou uso — fala direto comigo no WhatsApp. Atendimento real, sem robô.</p>
        </div>
      </div>
 
    </div>
  </div>
 
  <!-- ═══ TESTIMONIALS ═══ -->
  <div style="background:var(--bg2); border-top:1px solid var(--border); border-bottom:1px solid var(--border);">
    <div class="section">
      <div class="s-label">Depoimentos</div>
      <h2 class="s-title">QUEM JÁ<br>COMPROU,<br>APROVOU</h2>
 
      <div class="testi-grid">
 
        <div class="testi-card">
          <div class="stars">
            <div class="star"></div><div class="star"></div><div class="star"></div>
            <div class="star"></div><div class="star"></div>
          </div>
          <p class="testi-text">Cara, comprei um beat do Lolokka sem esperar muito e tomei um susto positivo. A produção é absurda. Gravei a música, joguei no Spotify e as pessoas ficaram perguntando onde eu tinha feito. Já voltei pra comprar mais.</p>
          <div class="testi-bottom">
            <div class="testi-avatar">GV</div>
            <div>
              <div class="testi-name">Gui Valentim</div>
              <div class="testi-role">Cantor independente · São Paulo, SP</div>
            </div>
          </div>
        </div>
 
        <div class="testi-card">
          <div class="stars">
            <div class="star"></div><div class="star"></div><div class="star"></div>
            <div class="star"></div><div class="star"></div>
          </div>
          <p class="testi-text">Melhor investimento que fiz pra minha carreira esse ano. O beat chegou certinho, mixado, com tudo separado. A entrega foi rápida e o Lolokka ainda me ajudou com uma dúvida no mix. Atendimento nota 10.</p>
          <div class="testi-bottom">
            <div class="testi-avatar">MC</div>
            <div>
              <div class="testi-name">MC Cauê</div>
              <div class="testi-role">Artista de Trap · Campinas, SP</div>
            </div>
          </div>
        </div>
 
        <div class="testi-card">
          <div class="stars">
            <div class="star"></div><div class="star"></div><div class="star"></div>
            <div class="star"></div><div class="star"></div>
          </div>
          <p class="testi-text">Eu sou produtora e comprei um beat pra estudar a estrutura. Fiquei impressionada com o detalhamento — cada elemento no lugar certo. O processo foi fácil do começo ao fim. Com certeza vou recomendar pra galera.</p>
          <div class="testi-bottom">
            <div class="testi-avatar">NB</div>
            <div>
              <div class="testi-name">Nath Beats</div>
              <div class="testi-role">Produtora Musical · Rio de Janeiro, RJ</div>
            </div>
          </div>
        </div>
 
      </div>
    </div>
  </div>
 
  <!-- ═══ CTA ═══ -->
  <section class="cta-section">
    <div class="cta-inner">
      <div class="urgency-pill">
        <div class="live-dot"></div>
        Disponível agora — resposta imediata
      </div>
 
      <h2 class="cta-title">
        FALA<br>COMIGO<br>
        <span>AGORA</span>
      </h2>
 
      <p class="cta-sub">
        Me manda mensagem no WhatsApp, me conta sua vibe e eu te mostro os beats disponíveis. É rápido, sem enrolação.
      </p>
 
      <a class="btn-wa"
         href="https://wa.me/5511968812053?text=Oi%20Lolokka!%20Quero%20escolher%20um%20beat%20seu%20🎧%20Me%20mostra%20o%20que%20tem%20disponível!"
         target="_blank" rel="noopener">
        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
        </svg>
        Quero escolher meu beat agora
      </a>
 
      <div class="cta-note">
        <span>🔒 Pagamento seguro</span>
        <span>⚡ <em>Entrega imediata</em></span>
        <span>🎧 Suporte direto</span>
      </div>
    </div>
  </section>
 
  <!-- ═══ FOOTER ═══ -->
  <footer>
    <div class="footer-logo">LOLOKKA</div>
    <a class="footer-ig" href="https://instagram.com/lorenzoxsvb" target="_blank" rel="noopener">
      <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/>
      </svg>
      @lorenzoxsvb
    </a>
    <small>© 2025 Lolokka. Todos os direitos reservados.</small>
  </footer>
 
</body>
</html>
 
