<!DOCTYPE html>

<html lang="pt-BR" style="background:#09080F !important; background-color:#09080F !important;">
<head>
<meta charset="UTF-8">
<meta name="theme-color" content="#09080F">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Decida Ai — A IA que decide por você</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Lora:ital,wght@0,400;0,500;1,400;1,500&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html, body { background: #09080F !important; }
:root {
–bg:      #09080F;
–bg2:     #13101F;
–surface: #1C1729;
–border:  rgba(255,255,255,.12);
–p1:      #A855F7;
–p2:      #7C3AED;
–p3:      #F0D9FF;
–gold:    #F59E0B;
–green:   #10B981;
–text:    #FFFFFF;
–muted:   #E2DCEF;
–soft:    #4D4568;
}

html { scroll-behavior: smooth; }

body {
font-family: ‘Inter’, sans-serif;
background: #09080F !important;
background-color: #09080F !important;
color: #FFFFFF !important;
overflow-x: hidden;
line-height: 1.6;
}

/* ── GRAIN ── */
body::after {
content: ‘’;
position: fixed; inset: 0;
background-image: url(“data:image/svg+xml,%3Csvg viewBox=‘0 0 200 200’ xmlns=‘http://www.w3.org/2000/svg’%3E%3Cfilter id=‘n’%3E%3CfeTurbulence type=‘fractalNoise’ baseFrequency=‘0.75’ numOctaves=‘4’ stitchTiles=‘stitch’/%3E%3C/filter%3E%3Crect width=‘100%25’ height=‘100%25’ filter=‘url(%23n)’ opacity=‘0.03’/%3E%3C/svg%3E”);
pointer-events: none; z-index: 9999; opacity: .4;
}

/* ── GLOW ORBS ── */
.orb { display: none; }

/* ── NAV ── */
nav {
position: fixed; top: 0; left: 0; right: 0; z-index: 100;
padding: 20px clamp(20px, 6vw, 80px);
display: flex; justify-content: space-between; align-items: center;
background: rgba(12,10,20,.8);
backdrop-filter: blur(12px);
border-bottom: 1px solid var(–border);
}

.nav-logo {
font-family: ‘Syne’, sans-serif;
font-weight: 800; font-size: 1.1rem;
text-decoration: none;
display: flex;
align-items: center;
gap: 12px;
}

.nav-link {
font-size: .8rem; font-weight: 500; color: rgba(255,255,255,.9);
text-decoration: none; letter-spacing: .06em; text-transform: uppercase;
transition: color .2s;
}
.nav-link:hover { color: var(–p3); }

/* ── SECTIONS ── */
section { position: relative; z-index: 1; background: #09080F; }

/* ── HERO ── */
.hero {
background: #09080F;
min-height: 100vh;
padding: 140px clamp(20px, 8vw, 100px) 80px;
display: flex; flex-direction: column;
justify-content: center;
max-width: 860px; margin: 0 auto;
}

.hero-tag {
display: inline-flex; align-items: center; gap: 8px;
background: rgba(255,255,255,.1);
border: 1px solid rgba(255,255,255,.25);
border-radius: 100px; padding: 6px 16px;
font-size: .75rem; font-weight: 500;
color: #F0DCFF; letter-spacing: .06em; text-transform: uppercase;
margin-bottom: 32px;
animation: fadeUp .6s ease both;
}
.hero-tag-dot {
width: 6px; height: 6px; border-radius: 50%;
background: var(–green);
box-shadow: 0 0 8px var(–green);
animation: pulse 2s infinite;
}

@keyframes pulse {
0%, 100% { opacity: 1; } 50% { opacity: .4; }
}

h1 {
font-family: ‘Syne’, sans-serif;
font-size: clamp(2.6rem, 6vw, 4.8rem);
font-weight: 800; line-height: 1.06;
margin-bottom: 28px;
animation: fadeUp .7s ease .1s both;
}

h1 .line-normal { color: var(–text); display: block; }
h1 .line-purple {
display: block;
background: linear-gradient(135deg, #C084FC 0%, #7C3AED 60%, #A855F7 100%);
-webkit-background-clip: text; -webkit-text-fill-color: transparent;
}
h1 .line-italic {
font-family: ‘Lora’, serif;
font-style: italic; font-weight: 500;
color: rgba(255,255,255,.85);
font-size: .72em; display: block;
}

.hero-body {
font-family: ‘Lora’, serif;
font-size: clamp(1.05rem, 2vw, 1.22rem);
line-height: 1.8; color: rgba(255,255,255,.95);
max-width: 580px; margin-bottom: 52px;
animation: fadeUp .7s ease .2s both;
}

.hero-body strong { color: var(–text); font-weight: 500; }

/* ── FORM HERO ── */
.hero-form {
background: var(–surface);
border: 1px solid var(–border);
border-radius: 24px;
padding: clamp(28px, 5vw, 44px);
max-width: 540px;
animation: fadeUp .7s ease .3s both;
position: relative;
overflow: hidden;
}

.hero-form::before {
content: ‘’;
position: absolute; top: 0; left: 0; right: 0; height: 1px;
background: linear-gradient(90deg, transparent, rgba(168,85,247,.5), transparent);
}

.form-title {
font-family: ‘Syne’, sans-serif;
font-size: 1.1rem; font-weight: 700;
color: var(–text); margin-bottom: 6px;
}

.form-subtitle {
font-size: .85rem; color: rgba(255,255,255,.92);
margin-bottom: 24px; line-height: 1.5;
}

.form-subtitle strong { color: #F5E8FF; }

.input-row {
display: flex; gap: 10px; margin-bottom: 14px;
}

@media (max-width: 480px) { .input-row { flex-direction: column; } }

.email-input {
flex: 1;
background: rgba(255,255,255,.05);
border: 1px solid var(–border);
border-radius: 14px; padding: 14px 18px;
font-size: .9rem; color: var(–text);
font-family: ‘Inter’, sans-serif;
outline: none; transition: border-color .2s;
}
.email-input::placeholder { color: var(–muted); }
.email-input:focus { border-color: var(–p1); }

.submit-btn {
background: linear-gradient(135deg, #A855F7, #7C3AED);
color: #fff; border: none; border-radius: 14px;
padding: 14px 24px; font-size: .88rem; font-weight: 600;
font-family: ‘Inter’, sans-serif; cursor: pointer;
white-space: nowrap; transition: opacity .2s, transform .1s;
letter-spacing: .01em;
}
.submit-btn:hover { opacity: .9; }
.submit-btn:active { transform: scale(.98); }

.form-badge {
display: inline-flex; align-items: center; gap: 6px;
background: rgba(16,185,129,.1);
border: 1px solid rgba(16,185,129,.25);
border-radius: 8px; padding: 8px 14px;
font-size: .8rem; color: #6EE7B7;
line-height: 1.4;
}
.form-badge-icon { font-size: 1rem; }

/* ── NUMBERS ── */
.numbers {
background: #09080F;
padding: 0 clamp(20px, 8vw, 100px) 100px;
max-width: 860px; margin: 0 auto;
}

.numbers-grid {
display: grid; grid-template-columns: repeat(3, 1fr);
gap: 1px; background: var(–border);
border-radius: 20px; overflow: hidden;
border: 1px solid var(–border);
}

@media (max-width: 600px) {
.numbers-grid { grid-template-columns: 1fr; }
}

.number-item {
background: var(–surface);
padding: 32px 28px; text-align: center;
}

.number-val {
font-family: ‘Syne’, sans-serif;
font-size: 2.6rem; font-weight: 800;
background: linear-gradient(135deg, #C084FC, #7C3AED);
-webkit-background-clip: text; -webkit-text-fill-color: transparent;
display: block; line-height: 1; margin-bottom: 8px;
}

.number-label-old { color: #C4BAD8;
font-size: .82rem; color: var(–muted);
line-height: 1.4;
}

/* ── CHAT DEMO ── */
.chat-section {
padding: 100px clamp(20px, 8vw, 100px);
max-width: 860px; margin: 0 auto;
}

.section-eyebrow {
font-size: .72rem; font-weight: 600;
letter-spacing: .14em; text-transform: uppercase;
color: #F0DCFF; margin-bottom: 16px;
display: flex; align-items: center; gap: 10px;
}
.section-eyebrow::after {
content: ‘’; flex: 1; height: 1px;
background: linear-gradient(90deg, var(–border), transparent);
}

.chat-heading {
font-family: ‘Syne’, sans-serif;
font-size: clamp(1.8rem, 3.5vw, 2.8rem);
font-weight: 700; margin-bottom: 48px;
line-height: 1.2;
}

.chat-heading em {
font-family: ‘Lora’, serif;
font-style: italic; font-weight: 400;
color: rgba(255,255,255,.8);
}

.chats {
display: flex; flex-direction: column; gap: 40px;
}

.chat-block { display: flex; flex-direction: column; gap: 12px; }

.chat-label {
font-size: .72rem; font-weight: 600;
letter-spacing: .1em; text-transform: uppercase;
color: #E0D8F4; padding-left: 4px;
}

.msg {
display: flex; gap: 12px; align-items: flex-start;
}

.msg-user { flex-direction: row-reverse; }

.msg-avatar {
width: 36px; height: 36px; border-radius: 50%;
flex-shrink: 0; display: flex; align-items: center;
justify-content: center; font-size: .85rem;
font-weight: 700; letter-spacing: -.02em;
}

.avatar-user {
background: var(–soft);
color: #F5E8FF; font-family: ‘Syne’, sans-serif;
}

.avatar-ai {
background: linear-gradient(135deg, #A855F7, #7C3AED);
color: #fff; font-size: .65rem; letter-spacing: .02em;
font-family: ‘Inter’, sans-serif; font-weight: 600;
}

.bubble {
border-radius: 18px; padding: 14px 18px;
font-size: .9rem; line-height: 1.6; max-width: 420px;
}

.bubble-user {
background: var(–soft);
color: rgba(255,255,255,.96);
border-radius: 18px 4px 18px 18px;
}

.bubble-ai {
background: var(–surface);
border: 1px solid var(–border);
color: var(–text);
border-radius: 4px 18px 18px 18px;
}

.bubble-ai strong { color: #F5E8FF; }

/* ── FEATURES ── */
.features {
padding: 100px clamp(20px, 8vw, 100px);
background: #0F0D1A;
}

.features-inner { max-width: 860px; margin: 0 auto; }

.features-grid {
display: grid; grid-template-columns: 1fr 1fr;
gap: 16px; margin-top: 48px;
}

@media (max-width: 640px) { .features-grid { grid-template-columns: 1fr; } }

.feat-card {
background: var(–surface);
border: 1px solid var(–border);
border-radius: 20px; padding: 28px 24px;
transition: border-color .3s, transform .3s;
}
.feat-card:hover { border-color: rgba(168,85,247,.3); transform: translateY(-2px); }

.feat-icon { font-size: 1.6rem; margin-bottom: 14px; display: block; }

.feat-title {
font-family: ‘Syne’, sans-serif;
font-size: 1rem; font-weight: 700;
color: var(–text); margin-bottom: 8px;
}

.feat-text-old { color: #C4BAD8;
font-size: .83rem; color: var(–muted);
line-height: 1.6;
}

/* ── CTA FINAL ── */
.cta-section {
padding: 120px clamp(20px, 8vw, 100px);
max-width: 700px; margin: 0 auto; text-align: center;
}

.cta-heading {
font-family: ‘Syne’, sans-serif;
font-size: clamp(2rem, 4vw, 3.2rem);
font-weight: 800; line-height: 1.1;
margin-bottom: 20px;
}

.cta-heading span {
background: linear-gradient(135deg, #C084FC, #7C3AED);
-webkit-background-clip: text; -webkit-text-fill-color: transparent;
}

.cta-sub {
font-family: ‘Lora’, serif;
font-size: 1.05rem; color: rgba(255,255,255,.92);
line-height: 1.7; margin-bottom: 48px;
}

.cta-form {
background: var(–surface);
border: 1px solid var(–border);
border-radius: 24px; padding: 36px;
position: relative; overflow: hidden;
}

.cta-form::before {
content: ‘’;
position: absolute; top: 0; left: 0; right: 0; height: 1px;
background: linear-gradient(90deg, transparent, rgba(168,85,247,.5), transparent);
}

/* ── SUCCESS ── */
.success { display: none; text-align: center; padding: 20px 0; }
.success.show { display: block; }
.success-big { font-size: 2.8rem; margin-bottom: 16px; }
.success-title {
font-family: ‘Syne’, sans-serif;
font-size: 1.5rem; font-weight: 700; color: var(–text);
margin-bottom: 10px;
}
.success-msg { font-size: .9rem; color: var(–muted); line-height: 1.6; }
.success-msg strong { color: #F5E8FF; }

/* ── FOOTER ── */
footer {
border-top: 1px solid var(–border);
padding: 28px clamp(20px, 8vw, 100px);
display: flex; justify-content: space-between;
align-items: center; flex-wrap: wrap; gap: 12px;
}

.footer-logo {
font-family: ‘Syne’, sans-serif; font-weight: 800;
font-size: .9rem;
background: linear-gradient(135deg, #C084FC, #7C3AED);
-webkit-background-clip: text; -webkit-text-fill-color: transparent;
}

.footer-note { font-size: .72rem; color: var(–muted); }
.footer-note a { color: var(–muted); text-decoration: none; }
.footer-note a:hover { color: var(–p3); }

/* ── ANIMATIONS ── */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(20px); }
to   { opacity: 1; transform: translateY(0); }
}

.reveal {
opacity: 0; transform: translateY(24px);
transition: opacity .7s ease, transform .7s ease;
}
.reveal.visible { opacity: 1; transform: none; }
/* ── CONTRAST FIXES ── */
.number-label { color: #C8BEE0; }
.feat-text { color: #C8BEE0; }
.chat-label { color: #A899C8; }
.bubble-user { color: rgba(255,255,255,.96); }
.section-eyebrow { color: #FFFFFF; -webkit-text-fill-color: #FFFFFF; }
.mode-desc { color: #C0B4D8; }
.footer-note { color: rgba(255,255,255,.8); }
.footer-note a { color: rgba(255,255,255,.8); }
.cta-sub { color: rgba(255,255,255,.92); }
/* ── CONTRAST FINAL — todas as cores de texto ── */
.number-label    { color: #EDE8F8 !important; }
.feat-text       { color: #EDE8F8 !important; }
.chat-label      { color: #D8D0EE !important; }
.bubble-user     { color: #FFFFFF !important; }
.bubble-ai       { color: #FFFFFF !important; }
.section-eyebrow { color: #EDE8F8 !important; }
.how-intro       { color: #EDE8F8 !important; }
.mode-desc       { color: #DDD6F0 !important; }
.mode-type       { color: #DDD6F0 !important; }
.mode-example    { color: #EDE8F8 !important; }
.footer-note     { color: rgba(255,255,255,.85) !important; }
.footer-note a   { color: rgba(255,255,255,.85) !important; }
.cta-sub         { color: #EDE8F8 !important; }
.pricing-sub     { color: #EDE8F8 !important; }
.price-plan      { color: #D8D0EE !important; }
.price-period    { color: #D8D0EE !important; }
.price-features li { color: #EDE8F8 !important; }
.form-subtitle   { color: #EDE8F8 !important; }
.form-guarantee  { color: #D8D0EE !important; }
.nav-link        { color: rgba(255,255,255,.85) !important; }
.hero-body       { color: #F0EBF8 !important; -webkit-text-fill-color: #F0EBF8 !important; }
.tagline-dark    { color: rgba(255,255,255,.85) !important; }
h1 .line-italic  { color: rgba(255,255,255,.95) !important; -webkit-text-fill-color: rgba(255,255,255,.95) !important; }

/* ══ CONTRAST NUCLEAR OVERRIDE ══ */
body { color: #FFFFFF !important; }
p, span, li, label, .feat-text, .number-label, .chat-label,
.how-intro, .mode-desc, .mode-type, .cta-sub, .pricing-sub,
.form-subtitle, .price-plan, .price-period, .footer-note,
.footer-note a, .hero-tag, .form-guarantee {
color: #E8E2F5 !important;
-webkit-text-fill-color: #E8E2F5 !important;
}
h1, h2, h3, h4, .form-title, .feat-title, .chat-heading,
.success-title, .cta-heading, .mode-title, .price-value {
color: #FFFFFF !important;
}
.hero-body {
color: #EDE8F8 !important;
-webkit-text-fill-color: #EDE8F8 !important;
}
.bubble-user { color: #FFFFFF !important; -webkit-text-fill-color: #FFFFFF !important; }
.bubble-ai   { color: #FFFFFF !important; -webkit-text-fill-color: #FFFFFF !important; }
.bubble-ai strong { color: #E8D4FF !important; -webkit-text-fill-color: #E8D4FF !important; }
/* Keep gradient texts working */
h1 .line-purple, .cta-heading span,
.word-ai, .footer-logo { -webkit-text-fill-color: transparent !important; }

</style>
</head>

<div style="position:fixed;inset:0;background:#09080F;z-index:-999;pointer-events:none;"></div>
<body bgcolor="#09080F" style="background:#09080F !important; background-color:#09080F !important; min-height:100vh; margin:0; padding:0;">

<div class="orb orb-1"></div>
<div class="orb orb-2"></div>

<!-- NAV -->

<nav>
  <a href="#" class="nav-logo">
    <!-- Símbolo -->
    <svg width="30" height="30" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="navg" x1="10" y1="10" x2="90" y2="90" gradientUnits="userSpaceOnUse">
          <stop offset="0%" stop-color="#E040A0"/>
          <stop offset="60%" stop-color="#9B4DB8"/>
          <stop offset="100%" stop-color="#4A7CC7"/>
        </linearGradient>
      </defs>
      <circle cx="46" cy="46" r="36" stroke="url(#navg)" stroke-width="1.8" stroke-dasharray="4.5 3.5" opacity=".6"/>
      <path d="M46 12 A34 34 0 1 1 12 46" stroke="url(#navg)" stroke-width="3.5" stroke-linecap="round"/>
      <path d="M57 57 L74 74 M74 74 L74 62 M74 74 L62 74" stroke="url(#navg)" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
      <circle cx="46" cy="46" r="5.5" fill="url(#navg)"/>
      <circle cx="74" cy="74" r="6" fill="#FF6B35"/>
    </svg>
    <!-- Wordmark: Decida em branco, Ai em gradiente, ponto laranja -->
    <span style="font-family:'Syne',sans-serif; font-weight:800; font-size:1.15rem; color:#FFFFFF; -webkit-text-fill-color:#FFFFFF; letter-spacing:-.02em; line-height:1;">Decida</span><span style="font-family:'Syne',sans-serif; font-weight:800; font-size:1.15rem; background:linear-gradient(135deg,#E040A0,#9B4DB8); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; letter-spacing:-.02em; line-height:1;">Ai</span><span style="font-family:'Syne',sans-serif; font-weight:800; font-size:1.15rem; color:#FF6B35; -webkit-text-fill-color:#FF6B35; line-height:1;">.</span>
  </a>
  <a href="#inscrever" class="nav-link">Quero entrar</a>
</nav>

<!-- HERO -->

<section class="hero">
  <!-- Logo em destaque no hero -->
  <div style="margin-bottom:40px; display:flex; flex-direction:column; align-items:flex-start; gap:16px;">
    <svg width="72" height="72" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="hlg" x1="10" y1="10" x2="90" y2="90" gradientUnits="userSpaceOnUse">
          <stop offset="0%" stop-color="#E040A0"/>
          <stop offset="60%" stop-color="#9B4DB8"/>
          <stop offset="100%" stop-color="#4A7CC7"/>
        </linearGradient>
        <filter id="hglow">
          <feGaussianBlur stdDeviation="2" result="blur"/>
          <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
        </filter>
      </defs>
      <circle cx="46" cy="46" r="36" stroke="url(#hlg)" stroke-width="1.8" stroke-dasharray="4.5 3.5" opacity=".55"/>
      <path d="M46 12 A34 34 0 1 1 12 46" stroke="url(#hlg)" stroke-width="3.5" stroke-linecap="round" filter="url(#hglow)"/>
      <path d="M57 57 L74 74 M74 74 L74 62 M74 74 L62 74" stroke="url(#hlg)" stroke-width="3" stroke-linecap="round" stroke-linejoin="round" filter="url(#hglow)"/>
      <circle cx="46" cy="46" r="5.5" fill="url(#hlg)" filter="url(#hglow)"/>
      <circle cx="74" cy="74" r="6.5" fill="#FF6B35" filter="url(#hglow)">
        <animate attributeName="r" values="6.5;8;6.5" dur="2s" repeatCount="indefinite"/>
        <animate attributeName="opacity" values="1;0.7;1" dur="2s" repeatCount="indefinite"/>
      </circle>
    </svg>
    <div style="line-height:1;">
      <span style="font-family:'Syne',sans-serif; font-weight:800; font-size:clamp(2.2rem,7vw,3rem); color:#FFFFFF; -webkit-text-fill-color:#FFFFFF; letter-spacing:-.04em;">Decida</span><span style="font-family:'Syne',sans-serif; font-weight:800; font-size:clamp(2.2rem,7vw,3rem); background:linear-gradient(135deg,#E040A0,#9B4DB8); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; letter-spacing:-.04em;">Ai</span><span style="font-family:'Syne',sans-serif; font-weight:800; font-size:clamp(2.2rem,7vw,3rem); color:#FF6B35; -webkit-text-fill-color:#FF6B35; letter-spacing:-.04em;">.</span>
      <div style="font-family:'Inter',sans-serif; font-size:.7rem; font-weight:400; letter-spacing:.2em; text-transform:uppercase; color:rgba(255,255,255,.55); -webkit-text-fill-color:rgba(255,255,255,.55); margin-top:6px;">A IA que decide por você</div>
    </div>
  </div>

  <div class="hero-tag">
    <span class="hero-tag-dot"></span>
    Em construção · Acesso antecipado aberto
  </div>

  <h1>
    <span class="line-normal">Você está cansada</span>
    <span class="line-purple">de decidir tudo.</span>
    <span class="line-italic">E tá tudo bem.</span>
  </h1>

  <p class="hero-body">
    Você toma <strong>35 mil decisões por dia</strong>. Do que vestir ao que fazer com sua vida.<br>
    Seu cérebro foi feito pra sentir, criar, conectar — não pra ficar escolhendo restaurante às 20h com a cabeça cheia.<br><br>
    <strong>Decida Ai</strong> é a IA que aprende quem você é de verdade — e decide por você.
    Direta. Sem lista de opções. Sem "depende".
  </p>

  <div class="hero-form" id="inscrever">
    <p class="form-title">Quero entrar na lista</p>
    <p class="form-subtitle">
      Se inscreva agora e garanta <strong>50% de desconto</strong> para sempre quando lançarmos.
    </p>

```
<div id="form-area">
  <div class="input-row">
    <input class="email-input" type="email" id="hero-email" placeholder="seu@email.com" autocomplete="email">
    <input type="hidden" name="b_6579168fbbad838300efbc466_07919f9758" value="">
    <button class="submit-btn" onclick="submitForm('hero')">Quero entrar →</button>
  </div>
  <div class="form-badge">
    <span class="form-badge-icon">✦</span>
    Gratuito. Sem cartão. Sem compromisso. Só o seu e-mail e o desconto garantido para sempre.
  </div>
</div>

<div class="success" id="hero-success">
  <div class="success-big">✦</div>
  <p class="success-title">Você está dentro.</p>
  <p class="success-msg">Vamos te avisar assim que lançar — e o seu <strong>desconto de 50% está garantido para sempre</strong>. Obrigada por acreditar antes de todo mundo.</p>
</div>
```

  </div>
</section>

<!-- NUMBERS -->

<div class="numbers reveal">
  <div class="numbers-grid">
    <div class="number-item">
      <span class="number-val">35k</span>
      <span class="number-label">decisões que você toma todo dia — queira ou não</span>
    </div>
    <div class="number-item">
      <span class="number-val">71%</span>
      <span class="number-label">das pessoas sentem queda de produtividade por excesso de escolhas</span>
    </div>
    <div class="number-item">
      <span class="number-val">0</span>
      <span class="number-label">apps que decidem por você de verdade. Até agora.</span>
    </div>
  </div>
</div>

<!-- CHAT DEMO -->

<section class="chat-section reveal">
  <p class="section-eyebrow">Como funciona</p>
  <h2 class="chat-heading">
    Você pergunta.<br>
    Ela decide. <em>Sem enrolação.</em>
  </h2>

  <div class="chats">

```
<div class="chat-block">
  <p class="chat-label">Decisão trivial · Modo Rápido</p>
  <div class="msg msg-user">
    <div class="msg-avatar avatar-user">Vc</div>
    <div class="bubble bubble-user">que roupa eu coloco pra hoje? tenho reunião de manhã e jantar com amigas à noite</div>
  </div>
  <div class="msg">
    <div class="msg-avatar avatar-ai">AI</div>
    <div class="bubble bubble-ai">O blazer verde com a calça preta. <strong>Funciona nos dois momentos</strong> — só troca os brincos entre um e outro. Você não usou essa combinação nas últimas duas semanas.</div>
  </div>
</div>

<div class="chat-block">
  <p class="chat-label">Decisão média · Planos do fim de semana</p>
  <div class="msg msg-user">
    <div class="msg-avatar avatar-user">Vc</div>
    <div class="bubble bubble-user">decide aí — vou a um jantar que não tenho muito afim ou fico em casa esse sábado</div>
  </div>
  <div class="msg">
    <div class="msg-avatar avatar-ai">AI</div>
    <div class="bubble bubble-ai"><strong>Fica em casa.</strong> Você saiu quatro vezes essa semana e dormiu mal nas últimas três noites. Seu padrão mostra que você fica de mau humor quando força programa cansada. Descanse.</div>
  </div>
</div>

<div class="chat-block">
  <p class="chat-label">Decisão de vida · Modo Profundo</p>
  <div class="msg msg-user">
    <div class="msg-avatar avatar-user">Vc</div>
    <div class="bubble bubble-user">recebi uma proposta de emprego muito boa mas teria que mudar de cidade. não consigo decidir há semanas</div>
  </div>
  <div class="msg">
    <div class="msg-avatar avatar-ai">AI</div>
    <div class="bubble bubble-ai">Você não está travada na decisão — <strong>você está travada no medo de decepcionar alguém</strong>. Nas últimas semanas você me perguntou três vezes sobre isso e nunca mencionou o que você quer. Só o que os outros vão achar. O que você quer?</div>
  </div>
</div>
```

  </div>
</section>

<!-- FEATURES -->

<section class="features reveal">
  <div class="features-inner">
    <p class="section-eyebrow">O que ela decide por você</p>
    <h2 class="chat-heading">
      Não é só o jantar.<br>
      <em>É tudo que trava sua cabeça.</em>
    </h2>

```
<div class="features-grid">
  <div class="feat-card">
    <span class="feat-icon">⚡</span>
    <h3 class="feat-title">O que comer, vestir, assistir</h3>
    <p class="feat-text">As decisões do dia a dia que drenam sua energia sem te dar nada em troca. Ela responde em segundos. Você segue em frente.</p>
  </div>
  <div class="feat-card">
    <span class="feat-icon">🍽️</span>
    <h3 class="feat-title">Onde jantar ou o que cozinhar</h3>
    <p class="feat-text">Com base no seu humor, orçamento e onde você está. Uma sugestão. Direta. Já com horário e endereço se precisar.</p>
  </div>
  <div class="feat-card">
    <span class="feat-icon">🔔</span>
    <h3 class="feat-title">Ela avisa antes de você perguntar</h3>
    <p class="feat-text">"Sexta chegando e você ainda sem planos — posso sugerir algo?" Aparece no momento certo, antes de você chegar cansada demais pra pensar.</p>
  </div>
  <div class="feat-card">
    <span class="feat-icon">🧠</span>
    <h3 class="feat-title">Espelho honesto das suas escolhas</h3>
    <p class="feat-text">Com o tempo ela percebe seus padrões — e te conta o que está vendo. Sem julgamento. Só clareza.</p>
  </div>
  <div class="feat-card">
    <span class="feat-icon">🎉</span>
    <h3 class="feat-title">Baladas, eventos e experiências</h3>
    <p class="feat-text">Ela sabe o que você curte e o que você evita. Vai sugerir o lugar certo, na hora certa, sem você precisar pesquisar nada.</p>
  </div>
  <div class="feat-card">
    <span class="feat-icon">✦</span>
    <h3 class="feat-title">Aprende e melhora toda semana</h3>
    <p class="feat-text">Quanto mais você usa, mais ela acerta. No mês 1 ela é boa. No mês 6 ela é você.</p>
  </div>
</div>
```

  </div>
</section>

<!-- CTA FINAL -->

<section class="cta-section reveal">
  <h2 class="cta-heading">
    Pronta pra <span>delegar</span><br>algumas decisões?
  </h2>
  <p class="cta-sub">
    Entre na lista agora. É gratuito.<br>
    Quando lançarmos, você paga metade do preço — para sempre.
  </p>

  <div class="cta-form">
    <div id="cta-form-area">
      <p class="form-title" style="margin-bottom:20px;">Garantir meu desconto de 50%</p>
      <div class="input-row">
        <input class="email-input" type="email" id="cta-email" placeholder="seu@email.com" autocomplete="email">
        <button class="submit-btn" onclick="submitForm('cta')">Quero entrar →</button>
      </div>
      <div class="form-badge" style="margin-top:14px;">
        <span class="form-badge-icon">✦</span>
        Zero cartão. Zero cobrança. Só o desconto garantido quando lançar.
      </div>
    </div>
    <div class="success" id="cta-success">
      <div class="success-big">✦</div>
      <p class="success-title">Você está dentro.</p>
      <p class="success-msg">Desconto de <strong>50% garantido para sempre</strong>. A gente te avisa quando lançar.</p>
    </div>
  </div>
</section>

<!-- FOOTER -->

<footer>
  <span class="footer-logo">decidaai.app</span>
  <span class="footer-note">
    © 2026 · Em construção com cuidado ·
    <a href="/cdn-cgi/l/email-protection#036a6d656c436766606a6762626a2d606c6e2d6171"><span class="__cf_email__" data-cfemail="a7cec9c1c8e7c3c2c4cec3c6c6ce89c4c8ca89c5d5">[email&#160;protected]</span></a>
  </span>
</footer>

<script>
// ── Mailchimp action URL ──
const MC_ACTION = 'https://decidaai.us6.list-manage.com/subscribe/post?u=6579168fbbad838300efbc466&id=07919f9758&f_id=00412fe3f0';

function submitForm(id) {
  const input = document.getElementById(id === 'hero' ? 'hero-email' : 'cta-email');
  const email = input.value.trim();

  if (!email || !email.includes('@') || !email.includes('.')) {
    input.style.borderColor = '#EF4444';
    input.focus();
    setTimeout(() => input.style.borderColor = '', 1800);
    return;
  }

  const btn = input.nextElementSibling;
  btn.textContent = '...';
  btn.disabled = true;

  // Envia para o Mailchimp via JSONP (evita erro de CORS)
  const script = document.createElement('script');
  const callbackName = 'mc_callback_' + Date.now();

  window[callbackName] = function(data) {
    delete window[callbackName];
    document.body.removeChild(script);

    const formArea = document.getElementById(id === 'hero' ? 'form-area' : 'cta-form-area');
    const success  = document.getElementById(id === 'hero' ? 'hero-success' : 'cta-success');

    formArea.style.opacity = '0';
    formArea.style.transform = 'translateY(-10px)';
    formArea.style.transition = 'all .3s ease';

    setTimeout(() => {
      formArea.style.display = 'none';
      success.classList.add('show');
      success.style.animation = 'fadeUp .5s ease';
    }, 300);
  };

  const jsonpUrl = MC_ACTION.replace('/post?', '/post-json?') +
    '&EMAIL=' + encodeURIComponent(email) +
    '&b_6579168fbbad838300efbc466_07919f9758=' +
    '&c=' + callbackName;

  script.src = jsonpUrl;
  document.body.appendChild(script);

  // Fallback: se o Mailchimp não responder em 4s, mostra sucesso de qualquer forma
  setTimeout(() => {
    if (window[callbackName]) {
      window[callbackName]({});
    }
  }, 4000);
}

// Enter key
document.querySelectorAll('.email-i
