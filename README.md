<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DRZ — Comunidad, Fotos, Juegos & Discord</title>
<meta name="description" content="DRZ — Galería de fotos, enlaces a juegos y servidores de Discord.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
/* ============ BASE ============ */
:root{
  --bg:#05060a;
  --card:rgba(255,255,255,.045);
  --card-hi:rgba(255,255,255,.075);
  --border:rgba(255,255,255,.09);
  --border-hi:rgba(255,255,255,.2);
  --text:#e9edf6;
  --muted:#8b93a7;
  --c1:#7c3aed;
  --c2:#22d3ee;
  --c3:#f472b6;
  --radius:20px;
  --max:1200px;
}
*{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{
  font-family:'Inter',system-ui,-apple-system,sans-serif;
  background:var(--bg);
  color:var(--text);
  overflow-x:hidden;
  line-height:1.6;
  -webkit-font-smoothing:antialiased;
}
body.no-scroll{overflow:hidden}
h1,h2,h3,.font-display{font-family:'Space Grotesk',sans-serif;letter-spacing:-.02em;line-height:1.15}
a{color:inherit;text-decoration:none}
img{display:block;max-width:100%}
::selection{background:var(--c1);color:#fff}

/* Scrollbar */
::-webkit-scrollbar{width:10px}
::-webkit-scrollbar-track{background:#080a10}
::-webkit-scrollbar-thumb{background:linear-gradient(var(--c1),var(--c2));border-radius:10px;border:2px solid #080a10}

/* ============ FONDO ANIMADO ============ */
.bg-wrap{position:fixed;inset:0;z-index:-3;overflow:hidden;background:
  radial-gradient(1200px 800px at 15% -10%, #140b2e 0%, transparent 60%),
  radial-gradient(1000px 700px at 90% 10%, #062730 0%, transparent 55%),
  radial-gradient(900px 900px at 50% 110%, #1a0a26 0%, transparent 60%),
  #05060a;}
.blob{
  position:absolute;border-radius:50%;filter:blur(90px);opacity:.55;
  mix-blend-mode:screen;will-change:transform;
}
.blob.b1{width:520px;height:520px;background:var(--c1);top:-120px;left:-80px;animation:float1 22s ease-in-out infinite}
.blob.b2{width:460px;height:460px;background:var(--c2);top:20%;right:-120px;animation:float2 26s ease-in-out infinite}
.blob.b3{width:600px;height:600px;background:var(--c3);bottom:-200px;left:30%;opacity:.35;animation:float3 30s ease-in-out infinite}
@keyframes float1{0%,100%{transform:translate(0,0) scale(1)}33%{transform:translate(160px,120px) scale(1.15)}66%{transform:translate(60px,260px) scale(.92)}}
@keyframes float2{0%,100%{transform:translate(0,0) scale(1)}50%{transform:translate(-180px,160px) scale(1.2)}}
@keyframes float3{0%,100%{transform:translate(0,0) scale(1)}40%{transform:translate(-220px,-140px) scale(1.1)}70%{transform:translate(140px,-60px) scale(.95)}}

/* Rejilla sutil en movimiento */
.grid-overlay{
  position:fixed;inset:-50%;z-index:-2;pointer-events:none;opacity:.35;
  background-image:linear-gradient(rgba(255,255,255,.045) 1px,transparent 1px),
                   linear-gradient(90deg,rgba(255,255,255,.045) 1px,transparent 1px);
  background-size:64px 64px;
  transform:perspective(500px) rotateX(0deg);
  animation:gridMove 24s linear infinite;
  mask-image:radial-gradient(ellipse 80% 60% at 50% 40%,#000 30%,transparent 100%);
  -webkit-mask-image:radial-gradient(ellipse 80% 60% at 50% 40%,#000 30%,transparent 100%);
}
@keyframes gridMove{from{background-position:0 0}to{background-position:64px 64px}}

#particles{position:fixed;inset:0;z-index:-1;pointer-events:none}

/* ============ NAV ============ */
header{
  position:fixed;top:0;left:0;right:0;z-index:100;
  transition:background .4s,backdrop-filter .4s,border-color .4s,padding .4s;
  border-bottom:1px solid transparent;padding:18px 0;
}
header.scrolled{
  background:rgba(5,6,10,.72);
  backdrop-filter:blur(18px) saturate(160%);
  -webkit-backdrop-filter:blur(18px) saturate(160%);
  border-bottom-color:var(--border);padding:10px 0;
}
.nav{max-width:var(--max);margin:0 auto;padding:0 24px;display:flex;align-items:center;justify-content:space-between;gap:20px}
.logo{display:flex;align-items:center;gap:11px;font-family:'Space Grotesk';font-weight:700;font-size:1.45rem;letter-spacing:.08em}
.logo-mark{
  width:38px;height:38px;border-radius:12px;display:grid;place-items:center;
  background:linear-gradient(135deg,var(--c1),var(--c2));
  box-shadow:0 0 26px rgba(124,58,237,.55);font-size:.95rem;color:#fff;font-weight:700;
  animation:pulseGlow 3.5s ease-in-out infinite;
}
@keyframes pulseGlow{0%,100%{box-shadow:0 0 22px rgba(124,58,237,.45)}50%{box-shadow:0 0 38px rgba(34,211,238,.6)}}
.logo span{background:linear-gradient(90deg,#fff,#b9c2d6);-webkit-background-clip:text;background-clip:text;color:transparent}
.nav-links{display:flex;align-items:center;gap:6px;list-style:none}
.nav-links a{
  padding:9px 16px;border-radius:999px;font-size:.92rem;font-weight:500;color:var(--muted);
  transition:.25s;position:relative;
}
.nav-links a:hover{color:#fff;background:rgba(255,255,255,.06)}
.nav-cta{
  padding:10px 20px !important;border-radius:999px;font-weight:600 !important;color:#fff !important;
  background:linear-gradient(135deg,var(--c1),#4f46e5);
  box-shadow:0 8px 26px -8px rgba(124,58,237,.9);transition:.3s;
}
.nav-cta:hover{transform:translateY(-2px);box-shadow:0 14px 34px -8px rgba(124,58,237,1)}
.burger{display:none;background:none;border:0;cursor:pointer;padding:8px;color:#fff}
.burger span{display:block;width:24px;height:2px;background:#fff;margin:5px 0;border-radius:2px;transition:.3s}
.burger.open span:nth-child(1){transform:translateY(7px) rotate(45deg)}
.burger.open span:nth-child(2){opacity:0}
.burger.open span:nth-child(3){transform:translateY(-7px) rotate(-45deg)}

/* ============ HERO ============ */
.hero{
  min-height:100svh;display:flex;align-items:center;justify-content:center;
  text-align:center;padding:130px 24px 80px;position:relative;
}
.hero-inner{max-width:900px;position:relative;z-index:2}
.badge{
  display:inline-flex;align-items:center;gap:9px;padding:8px 18px;border-radius:999px;
  background:rgba(255,255,255,.05);border:1px solid var(--border);
  font-size:.8rem;letter-spacing:.14em;text-transform:uppercase;color:#c3cada;
  backdrop-filter:blur(10px);margin-bottom:28px;
}
.dot{width:7px;height:7px;border-radius:50%;background:#22c55e;box-shadow:0 0 10px #22c55e;animation:blink 2s infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.25}}

.hero h1{
  font-size:clamp(3.2rem,11vw,7.5rem);font-weight:700;letter-spacing:-.04em;margin-bottom:6px;
  background:linear-gradient(100deg,#fff 0%,#c4b5fd 30%,#67e8f9 55%,#f9a8d4 80%,#fff 100%);
  background-size:250% auto;-webkit-background-clip:text;background-clip:text;color:transparent;
  animation:shine 7s linear infinite;
  filter:drop-shadow(0 0 44px rgba(124,58,237,.4));
}
@keyframes shine{to{background-position:250% center}}
.hero .sub{
  font-size:clamp(1rem,2.4vw,1.3rem);color:#a8b0c4;max-width:620px;margin:18px auto 40px;font-weight:300;
}
.hero-actions{display:flex;gap:14px;justify-content:center;flex-wrap:wrap}
.btn{
  display:inline-flex;align-items:center;gap:10px;padding:15px 30px;border-radius:999px;
  font-weight:600;font-size:.95rem;border:1px solid transparent;cursor:pointer;transition:.3s;
  font-family:'Inter',sans-serif;
}
.btn-primary{
  background:linear-gradient(135deg,var(--c1),var(--c2));color:#fff;
  box-shadow:0 14px 40px -12px rgba(124,58,237,.95);
  background-size:200% auto;
}
.btn-primary:hover{transform:translateY(-3px) scale(1.02);background-position:right center;box-shadow:0 20px 50px -12px rgba(34,211,238,.9)}
.btn-ghost{background:rgba(255,255,255,.05);border-color:var(--border);color:#dfe4ef;backdrop-filter:blur(10px)}
.btn-ghost:hover{background:rgba(255,255,255,.1);border-color:var(--border-hi);transform:translateY(-3px)}

.hero-stats{display:flex;gap:44px;justify-content:center;flex-wrap:wrap;margin-top:64px}
.stat b{display:block;font-family:'Space Grotesk';font-size:2rem;font-weight:700;
  background:linear-gradient(135deg,#fff,var(--c2));-webkit-background-clip:text;background-clip:text;color:transparent}
.stat span{font-size:.78rem;text-transform:uppercase;letter-spacing:.16em;color:var(--muted)}

.scroll-hint{position:absolute;bottom:34px;left:50%;transform:translateX(-50%);color:var(--muted);font-size:.75rem;letter-spacing:.2em;text-transform:uppercase;animation:bob 2.4s ease-in-out infinite}
@keyframes bob{0%,100%{transform:translate(-50%,0);opacity:.5}50%{transform:translate(-50%,10px);opacity:1}}

/* ============ SECCIONES ============ */
section{padding:110px 24px;position:relative}
.container{max-width:var(--max);margin:0 auto}
.sec-head{text-align:center;margin-bottom:60px}
.sec-tag{
  display:inline-block;font-size:.75rem;letter-spacing:.24em;text-transform:uppercase;
  color:var(--c2);margin-bottom:14px;font-weight:600;
}
.sec-head h2{font-size:clamp(2rem,5vw,3.1rem);font-weight:700;margin-bottom:14px}
.sec-head p{color:var(--muted);max-width:560px;margin:0 auto;font-size:1.02rem}

/* ============ GALERÍA ============ */
.gallery{display:grid;grid-template-columns:repeat(auto-fill,minmax(230px,1fr));grid-auto-rows:190px;gap:16px}
.g-item{
  position:relative;overflow:hidden;border-radius:var(--radius);cursor:pointer;
  border:1px solid var(--border);background:#0c0e17;
  transition:transform .5s cubic-bezier(.2,.8,.2,1),box-shadow .5s,border-color .5s;
}
.g-item:nth-child(1){grid-column:span 2;grid-row:span 2}
.g-item:nth-child(6){grid-column:span 2}
.g-item img{width:100%;height:100%;object-fit:cover;transition:transform .8s cubic-bezier(.2,.8,.2,1),filter .5s;filter:grayscale(.25) brightness(.85)}
.g-item:hover{transform:translateY(-6px);border-color:var(--border-hi);box-shadow:0 26px 60px -22px rgba(124,58,237,.85)}
.g-item:hover img{transform:scale(1.1);filter:grayscale(0) brightness(1)}
.g-overlay{
  position:absolute;inset:0;display:flex;align-items:flex-end;padding:20px;
  background:linear-gradient(to top,rgba(5,6,10,.92) 0%,transparent 60%);
  opacity:0;transition:.4s;
}
.g-item:hover .g-overlay{opacity:1}
.g-overlay h4{font-size:1rem;font-weight:600}
.g-overlay small{color:var(--muted);font-size:.78rem}
.g-zoom{
  position:absolute;top:16px;right:16px;width:36px;height:36px;border-radius:50%;
  background:rgba(255,255,255,.12);backdrop-filter:blur(8px);display:grid;place-items:center;
  transform:scale(.5);opacity:0;transition:.35s;border:1px solid var(--border-hi);font-size:1rem;
}
.g-item:hover .g-zoom{transform:scale(1);opacity:1}

/* ============ CARDS GRID ============ */
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(290px,1fr));gap:22px}
.card{
  position:relative;border-radius:var(--radius);padding:28px;overflow:hidden;
  background:var(--card);border:1px solid var(--border);
  backdrop-filter:blur(14px);-webkit-backdrop-filter:blur(14px);
  transition:transform .45s cubic-bezier(.2,.8,.2,1),border-color .45s,background .45s,box-shadow .45s;
}
.card::before{
  content:'';position:absolute;inset:0;border-radius:inherit;opacity:0;transition:.45s;
  background:radial-gradient(600px circle at var(--mx,50%) var(--my,50%),rgba(124,58,237,.16),transparent 42%);
  pointer-events:none;
}
.card:hover{transform:translateY(-8px);border-color:var(--border-hi);background:var(--card-hi);box-shadow:0 30px 70px -30px rgba(0,0,0,.95)}
.card:hover::before{opacity:1}
.card-top{display:flex;align-items:center;gap:16px;margin-bottom:18px}
.card-icon{
  width:62px;height:62px;border-radius:17px;display:grid;place-items:center;font-size:1.7rem;flex-shrink:0;
  background:linear-gradient(135deg,rgba(124,58,237,.28),rgba(34,211,238,.18));
  border:1px solid var(--border);position:relative;overflow:hidden;
}
.card-icon img{width:100%;height:100%;object-fit:cover}
.card h3{font-size:1.22rem;font-weight:600;margin-bottom:3px}
.card .meta{font-size:.8rem;color:var(--muted);display:flex;align-items:center;gap:7px}
.card .meta .dot{width:6px;height:6px;height:6px}
.card p{color:var(--muted);font-size:.93rem;margin-bottom:20px}
.tags{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:22px}
.tag{
  font-size:.72rem;padding:5px 11px;border-radius:999px;background:rgba(255,255,255,.06);
  border:1px solid var(--border);color:#b7bfd2;letter-spacing:.03em;
}
.card-btn{
  display:flex;align-items:center;justify-content:center;gap:9px;width:100%;
  padding:13px;border-radius:13px;font-weight:600;font-size:.9rem;transition:.3s;
  background:rgba(255,255,255,.06);border:1px solid var(--border);color:#e9edf6;
}
.card-btn:hover{background:linear-gradient(135deg,var(--c1),var(--c2));border-color:transparent;color:#fff;box-shadow:0 12px 30px -12px rgba(124,58,237,.9)}
.card-btn.discord:hover{background:linear-gradient(135deg,#5865F2,#8b5cf6);box-shadow:0 12px 30px -12px rgba(88,101,242,.95)}
.card-btn svg{width:17px;height:17px;fill:currentColor}

/* ============ CTA FINAL ============ */
.cta-box{
  position:relative;border-radius:28px;padding:70px 40px;text-align:center;overflow:hidden;
  border:1px solid var(--border);background:rgba(255,255,255,.035);backdrop-filter:blur(16px);
}
.cta-box::before{
  content:'';position:absolute;inset:-2px;border-radius:inherit;padding:1px;
  background:linear-gradient(120deg,var(--c1),var(--c2),var(--c3),var(--c1));
  background-size:300% 300%;animation:shine 8s linear infinite;
  -webkit-mask:linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);
  -webkit-mask-composite:xor;mask-composite:exclude;opacity:.6;pointer-events:none;
}
.cta-box h2{font-size:clamp(1.8rem,4.5vw,2.8rem);margin-bottom:16px}
.cta-box p{color:var(--muted);max-width:520px;margin:0 auto 34px}

/* ============ FOOTER ============ */
footer{border-top:1px solid var(--border);padding:52px 24px 34px;background:rgba(5,6,10,.6)}
.foot{max-width:var(--max);margin:0 auto;display:flex;justify-content:space-between;align-items:center;gap:26px;flex-wrap:wrap}
.foot p{color:var(--muted);font-size:.87rem}
.socials{display:flex;gap:12px}
.socials a{
  width:42px;height:42px;border-radius:12px;display:grid;place-items:center;
  background:rgba(255,255,255,.05);border:1px solid var(--border);transition:.3s;color:#c3cada;
}
.socials a:hover{background:linear-gradient(135deg,var(--c1),var(--c2));color:#fff;transform:translateY(-4px);border-color:transparent}
.socials svg{width:19px;height:19px;fill:currentColor}

/* ============ LIGHTBOX ============ */
.lightbox{
  position:fixed;inset:0;z-index:1000;display:grid;place-items:center;padding:24px;
  background:rgba(3,4,8,.9);backdrop-filter:blur(14px);
  opacity:0;visibility:hidden;transition:.35s;
}
.lightbox.active{opacity:1;visibility:visible}
.lightbox img{max-width:92vw;max-height:82vh;border-radius:16px;border:1px solid var(--border-hi);
  box-shadow:0 40px 100px -30px rgba(0,0,0,1);transform:scale(.92);transition:.4s cubic-bezier(.2,.8,.2,1)}
.lightbox.active img{transform:scale(1)}
.lb-close{
  position:absolute;top:26px;right:26px;width:46px;height:46px;border-radius:50%;
  background:rgba(255,255,255,.08);border:1px solid var(--border);color:#fff;font-size:1.4rem;
  cursor:pointer;transition:.3s;display:grid;place-items:center;
}
.lb-close:hover{background:var(--c3);transform:rotate(90deg)}

/* ============ REVEAL ============ */
[data-reveal]{opacity:0;transform:translateY(38px);transition:opacity .9s cubic-bezier(.2,.8,.2,1),transform .9s cubic-bezier(.2,.8,.2,1)}
[data-reveal].visible{opacity:1;transform:none}

/* ============ RESPONSIVE ============ */
@media(max-width:860px){
  .nav-links{
    position:fixed;top:0;right:0;height:100vh;width:min(300px,82vw);
    flex-direction:column;justify-content:center;gap:10px;
    background:rgba(8,10,18,.96);backdrop-filter:blur(24px);
    border-left:1px solid var(--border);transform:translateX(105%);transition:transform .45s cubic-bezier(.2,.8,.2,1);
    padding:40px 26px;
  }
  .nav-links.open{transform:translateX(0)}
  .nav-links a{width:100%;text-align:center;font-size:1.05rem;padding:14px}
  .burger{display:block;z-index:101}
  .gallery{grid-template-columns:repeat(auto-fill,minmax(150px,1fr));grid-auto-rows:150px;gap:12px}
  .g-item:nth-child(1),.g-item:nth-child(6){grid-column:span 1;grid-row:span 1}
  .hero-stats{gap:30px}
  .stat b{font-size:1.55rem}
  section{padding:80px 20px}
  .cta-box{padding:52px 24px}
}
@media(max-width:420px){
  .gallery{grid-template-columns:1fr 1fr;grid-auto-rows:130px}
  .btn{padding:13px 22px;font-size:.88rem}
}
@media(prefers-reduced-motion:reduce){
  *{animation:none !important;transition-duration:.01ms !important}
  [data-reveal]{opacity:1;transform:none}
}
</style>
</head>
<body>

<!-- ===== FONDO ANIMADO ===== -->
<div class="bg-wrap">
  <div class="blob b1"></div>
  <div class="blob b2"></div>
  <div class="blob b3"></div>
</div>
<div class="grid-overlay"></div>
<canvas id="particles"></canvas>

<!-- ===== HEADER ===== -->
<header id="header">
  <nav class="nav">
    <a href="#inicio" class="logo">
      <div class="logo-mark">DRZ</div>
      <span>DRZ</span>
    </a>
    <ul class="nav-links" id="navLinks">
      <li><a href="#inicio">Inicio</a></li>
      <li><a href="#galeria">Galería</a></li>
      <li><a href="#juegos">Juegos</a></li>
      <li><a href="#discord">Discord</a></li>
      <li><a href="#discord" class="nav-cta">Unirse</a></li>
    </ul>
    <button class="burger" id="burger" aria-label="Menú">
      <span></span><span></span><span></span>
    </button>
  </nav>
</header>

<!-- ===== HERO ===== -->
<section class="hero" id="inicio">
  <div class="hero-inner">
    <div class="badge"><span class="dot"></span> Comunidad activa 24/7</div>
    <h1>DRZ</h1>
    <p class="sub">Fotos, juegos y servidores de Discord en un solo lugar. Únete a la comunidad y comparte tus mejores momentos.</p>
    <div class="hero-actions">
      <a href="#discord" class="btn btn-primary">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M20.317 4.37a19.79 19.79 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994a.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128c.126-.094.252-.192.372-.291a.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.3 12.3 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.84 19.84 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z"/></svg>
        Entrar a Discord
      </a>
      <a href="#galeria" class="btn btn-ghost">Ver galería</a>
    </div>

    <div class="hero-stats">
      <div class="stat"><b data-count="1250">0</b><span>Miembros</span></div>
      <div class="stat"><b data-count="340">0</b><span>Fotos</span></div>
      <div class="stat"><b data-count="18">0</b><span>Juegos</span></div>
    </div>
  </div>
  <div class="scroll-hint">Scroll ↓</div>
</section>

<!-- ===== GALERÍA ===== -->
<section id="galeria">
  <div class="container">
    <div class="sec-head" data-reveal>
      <span class="sec-tag">// Galería</span>
      <h2>Momentos de la comunidad</h2>
      <p>Capturas, clips y recuerdos compartidos por los miembros de DRZ. Haz clic en cualquier imagen para ampliarla.</p>
    </div>
    <div class="gallery" id="gallery" data-reveal></div>
  </div>
</section>

<!-- ===== JUEGOS ===== -->
<section id="juegos">
  <div class="container">
    <div class="sec-head" data-reveal>
      <span class="sec-tag">// Juegos</span>
      <h2>Nuestros juegos</h2>
      <p>Accede directamente a los juegos donde la comunidad DRZ se reúne cada noche.</p>
    </div>
    <div class="cards" id="gamesGrid" data-reveal></div>
  </div>
</section>

<!-- ===== DISCORD ===== -->
<section id="discord">
  <div class="container">
    <div class="sec-head" data-reveal>
      <span class="sec-tag">// Discord</span>
      <h2>Servidores recomendados</h2>
      <p>Únete a nuestros servidores asociados y encuentra gente para jugar en segundos.</p>
    </div>
    <div class="cards" id="discordGrid" data-reveal></div>

    <div class="cta-box" data-reveal style="margin-top:70px">
      <h2>¿Listo para unirte a DRZ?</h2>
      <p>Entra al servidor principal, preséntate y empieza a jugar con nosotros hoy mismo.</p>
      <a href="#" class="btn btn-primary" id="mainDiscord">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M20.317 4.37a19.79 19.79 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994a.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128c.126-.094.252-.192.372-.291a.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.3 12.3 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.84 19.84 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z"/></svg>
        Unirse al servidor DRZ
      </a>
    </div>
  </div>
</section>

<!-- ===== FOOTER ===== -->
<footer>
  <div class="foot">
    <div class="logo" style="font-size:1.2rem">
      <div class="logo-mark" style="width:32px;height:32px;border-radius:10px;font-size:.8rem">DRZ</div>
      <span>DRZ</span>
    </div>
    <p>© <span id="year"></span> DRZ — Todos los derechos reservados.</p>
    <div class="socials">
      <a href="#" aria-label="Discord"><svg viewBox="0 0 24 24"><path d="M20.317 4.37a19.79 19.79 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994a.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128c.126-.094.252-.192.372-.291a.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.3 12.3 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.84 19.84 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z"/></svg></a>
      <a href="#" aria-label="YouTube"><svg viewBox="0 0 24 24"><path d="M23.5 6.2a3 3 0 0 0-2.1-2.1C19.5 3.6 12 3.6 12 3.6s-7.5 0-9.4.5A3 3 0 0 0 .5 6.2 31.3 31.3 0 0 0 0 12a31.3 31.3 0 0 0 .5 5.8 3 3 0 0 0 2.1 2.1c1.9.5 9.4.5 9.4.5s7.5 0 9.4-.5a3 3 0 0 0 2.1-2.1A31.3 31.3 0 0 0 24 12a31.3 31.3 0 0 0-.5-5.8zM9.6 15.6V8.4l6.2 3.6-6.2 3.6z"/></svg></a>
      <a href="#" aria-label="X"><svg viewBox="0 0 24 24"><path d="M18.9 2H22l-7 8 8.2 12h-6.4l-5-7.3L5.9 22H2.8l7.5-8.6L2.4 2h6.6l4.5 6.6L18.9 2zm-1.1 18h1.7L7.3 3.8H5.5L17.8 20z"/></svg></a>
    </div>
  </div>
</footer>

<!-- ===== LIGHTBOX ===== -->
<div class="lightbox" id="lightbox">
  <button class="lb-close" id="lbClose" aria-label="Cerrar">✕</button>
  <img src="" alt="Vista ampliada" id="lbImg">
</div>

<script>
/* ============ DATOS (edita aquí) ============ */
const FOTOS = [
  { src:'https://picsum.photos/seed/drz1/900/900', titulo:'Sesión nocturna', cat:'Gameplay' },
  { src:'https://picsum.photos/seed/drz2/800/600', titulo:'Escuadrón DRZ',   cat:'Squad' },
  { src:'https://picsum.photos/seed/drz3/800/600', titulo:'Victoria épica',  cat:'Highlights' },
  { src:'https://picsum.photos/seed/drz4/800/600', titulo:'Base construida', cat:'Survival' },
  { src:'https://picsum.photos/seed/drz5/800/600', titulo:'Momentos random', cat:'Comunidad' },
  { src:'https://picsum.photos/seed/drz6/1200/700',titulo:'Evento semanal',  cat:'Eventos' },
  { src:'https://picsum.photos/seed/drz7/800/600', titulo:'Clutch 1v4',      cat:'Clips' },
  { src:'https://picsum.photos/seed/drz8/800/600', titulo:'Squad goals',     cat:'Comunidad' }
];

const JUEGOS = [
  { icon:'🎯', nombre:'Valorant', desc:'Partidas competitivas y customs internas con la comunidad.', tags:['FPS','Competitivo','5v5'], url:'#' },
  { icon:'🪂', nombre:'Fortnite', desc:'Squads, torneos y eventos especiales cada semana.', tags:['Battle Royale','Cross-platform'], url:'#' },
  { icon:'⛏️', nombre:'Minecraft', desc:'Servidor survival, minijuegos y construcciones en grupo.', tags:['Survival','Creative','SMP'], url:'#' },
  { icon:'🔫', nombre:'Call of Duty', desc:'Warzone y multijugador con escuadrones DRZ.', tags:['FPS','Warzone'], url:'#' },
  { icon:'🏎️', nombre:'Rocket League', desc:'Rankeds y torneos 2v2 / 3v3 dentro del server.', tags:['Deportes','Torneos'], url:'#' },
  { icon:'👑', nombre:'League of Legends', desc:'Flex, ARAM y scrims internas de la comunidad.', tags:['MOBA','5v5','Ranked'], url:'#' }
];

const SERVIDORES = [
  { icon:'💜', nombre:'DRZ Official', desc:'Servidor principal de la comunidad DRZ. Eventos, sorteos y canales de voz siempre activos.', tags:['Principal','Eventos','24/7'], url:'#', miembros:'1.2k' },
  { icon:'🎮', nombre:'DRZ Gaming Hub', desc:'Busca duo, squad o compañeros para cualquier juego en minutos.', tags:['LFG','Duo','Squad'], url:'#', miembros:'860' },
  { icon:'🎨', nombre:'DRZ Creators', desc:'Espacio para editores, streamers y creadores de contenido de la comunidad.', tags:['Streamers','Edición'], url:'#', miembros:'430' }
];

/* ============ RENDER GALERÍA ============ */
const gallery = document.getElementById('gallery');
FOTOS.forEach(f => {
  const d = document.createElement('div');
  d.className = 'g-item';
  d.innerHTML = `
    <img src="${f.src}" alt="${f.titulo}" loading="lazy">
    <div class="g-zoom">⤢</div>
    <div class="g-overlay"><div><h4>${f.titulo}</h4><small>${f.cat}</small></div></div>`;
  d.addEventListener('click', () => openLightbox(f.src));
  gallery.appendChild(d);
});

/* ============ RENDER JUEGOS ============ */
const gamesGrid = document.getElementById('gamesGrid');
JUEGOS.forEach(j => {
  const c = document.createElement('article');
  c.className = 'card';
  c.innerHTML = `
    <div class="card-top">
      <div class="card-icon">${j.icon}</div>
      <div>
        <h3>${j.nombre}</h3>
        <div class="meta"><span class="dot"></span> Disponible ahora</div>
      </div>
    </div>
    <p>${j.desc}</p>
    <div class="tags">${j.tags.map(t=>`<span class="tag">${t}</span>`).join('')}</div>
    <a href="${j.url}" class="card-btn" target="_blank" rel="noopener">
      <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg> Jugar ahora
    </a>`;
  gamesGrid.appendChild(c);
});

/* ============ RENDER DISCORD ============ */
const discordGrid = document.getElementById('discordGrid');
SERVIDORES.forEach(s => {
  const c = document.createElement('article');
  c.className = 'card';
  c.innerHTML = `
    <div class="card-top">
      <div class="card-icon">${s.icon}</div>
      <div>
        <h3>${s.nombre}</h3>
        <div class="meta"><span class="dot"></span> ${s.miembros} miembros</div>
      </div>
    </div>
    <p>${s.desc}</p>
    <div class="tags">${s.tags.map(t=>`<span class="tag">${t}</span>`).join('')}</div>
    <a href="${s.url}" class="card-btn discord" target="_blank" rel="noopener">
      <svg viewBox="0 0 24 24"><path d="M20.317 4.37a19.79 19.79 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994a.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128c.126-.094.252-.192.372-.291a.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.3 12.3 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.84 19.84 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03zM8.02 15.33c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.956-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.956 2.418-2.157 2.418zm7.975 0c-1.183 0-2.157-1.085-2.157-2.419 0-1.333.955-2.419 2.157-2.419 1.21 0 2.176 1.096 2.157 2.42 0 1.333-.946 2.418-2.157 2.418z"/></svg>
      Unirse al servidor
    </a>`;
  discordGrid.appendChild(c);
});

/* ============ HEADER SCROLL ============ */
const header = document.getElementById('header');
window.addEventListener('scroll', () => {
  header.classList.toggle('scrolled', window.scrollY > 40);
}, { passive:true });

/* ============ MENÚ MÓVIL ============ */
const burger = document.getElementById('burger');
const navLinks = document.getElementById('navLinks');
burger.addEventListener('click', () => {
  burger.classList.toggle('open');
  navLinks.classList.toggle('open');
  document.body.classList.toggle('no-scroll');
});
navLinks.querySelectorAll('a').forEach(a => a.addEventListener('click', () => {
  burger.classList.remove('open');
  navLinks.classList.remove('open');
  document.body.classList.remove('no-scroll');
}));

/* ============ LIGHTBOX ============ */
const lb = document.getElementById('lightbox');
const lbImg = document.getElementById('lbImg');
function openLightbox(src){
  lbImg.src = src;
  lb.classList.add('active');
  document.body.classList.add('no-scroll');
}
function closeLightbox(){
  lb.classList.remove('active');
  document.body.classList.remove('no-scroll');
}
document.getElementById('lbClose').addEventListener('click', closeLightbox);
lb.addEventListener('click', e => { if(e.target === lb) closeLightbox(); });
document.addEventListener('keydown', e => { if(e.key === 'Escape') closeLightbox(); });

/* ============ REVEAL ON SCROLL ============ */
const io = new IntersectionObserver((entries) => {
  entries.forEach(en => {
    if(en.isIntersecting){ en.target.classList.add('visible'); io.unobserve(en.target); }
  });
}, { threshold:.12 });
document.querySelectorAll('[data-reveal]').forEach(el => io.observe(el));

/* ============ CONTADORES ============ */
const counters = document.querySelectorAll('[data-count]');
const cio = new IntersectionObserver((entries) => {
  entries.forEach(en => {
    if(!en.isIntersecting) return;
    const el = en.target;
    const target = +el.dataset.count;
    const dur = 1600;
    const start = performance.now();
    const tick = (now) => {
      const p = Math.min((now - start) / dur, 1);
      const eased = 1 - Math.pow(1 - p, 3);
      el.textContent = Math.floor(target * eased).toLocaleString('es-ES') + (p === 1 && target > 999 ? '+' : '');
      if(p < 1) requestAnimationFrame(tick);
    };
    requestAnimationFrame(tick);
    cio.unobserve(el);
  });
}, { threshold:.5 });
counters.forEach(c => cio.observe(c));

/* ============ EFECTO LUZ EN CARDS ============ */
document.addEventListener('mousemove', e => {
  document.querySelectorAll('.card').forEach(card => {
    const r = card.getBoundingClientRect();
    if(e.clientX < r.left - 200 || e.clientX > r.right + 200) return;
    card.style.setProperty('--mx', (e.clientX - r.left) + 'px');
    card.style.setProperty('--my', (e.clientY - r.top) + 'px');
  });
}, { passive:true });

/* ============ AÑO FOOTER ============ */
document.getElementById('year').textContent = new Date().getFullYear();

/* ============ PARTÍCULAS ============ */
(function(){
  const canvas = document.getElementById('particles');
  const ctx = canvas.getContext('2d');
  let w, h, particles = [];
  const COUNT = window.innerWidth < 768 ? 35 : 70;

  function resize(){
    w = canvas.width = window.innerWidth;
    h = canvas.height = window.innerHeight;
  }
  resize();
  window.addEventListener('resize', resize);

  class P {
    constructor(){ this.reset(); }
    reset(){
      this.x = Math.random() * w;
      this.y = Math.random() * h;
      this.r = Math.random() * 1.8 + .5;
      this.vx = (Math.random() - .5) * .35;
      this.vy = (Math.random() - .5) * .35;
      this.a = Math.random() * .5 + .15;
      this.c = Math.random() > .5 ? '124,58,237' : '34,211,238';
    }
    update(){
      this.x += this.vx; this.y += this.vy;
      if(this.x < 0 || this.x > w) this.vx *= -1;
      if(this.y < 0 || this.y > h) this.vy *= -1;
    }
    draw(){
      ctx.beginPath();
      ctx.arc(this.x, this.y, this.r, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(${this.c},${this.a})`;
      ctx.fill();
    }
  }

  for(let i = 0; i < COUNT; i++) particles.push(new P());

  const mouse = { x:null, y:null };
  window.addEventListener('mousemove', e => { mouse.x = e.clientX; mouse.y = e.clientY; }, { passive:true });
  window.addEventListener('mouseout', () => { mouse.x = mouse.y = null; });

  function loop(){
    ctx.clearRect(0, 0, w, h);

    // conexiones
    for(let i = 0; i < particles.length; i++){
      for(let j = i + 1; j < particles.length; j++){
        const dx = particles[i].x - particles[j].x;
        const dy = particles[i].y - particles[j].y;
        const dist = Math.hypot(dx, dy);
        if(dist < 130){
          ctx.beginPath();
          ctx.moveTo(particles[i].x, particles[i].y);
          ctx.lineTo(particles[j].x, particles[j].y);
          ctx.strokeStyle = `rgba(124,58,237,${(1 - dist / 130) * .13})`;
          ctx.lineWidth = .7;
          ctx.stroke();
        }
      }
      // línea hacia el cursor
      if(mouse.x !== null){
        const dx = particles[i].x - mouse.x;
        const dy = particles[i].y - mouse.y;
        const d = Math.hypot(dx, dy);
        if(d < 170){
          ctx.beginPath();
          ctx.moveTo(particles[i].x, particles[i].y);
          ctx.lineTo(mouse.x, mouse.y);
          ctx.strokeStyle = `rgba(34,211,238,${(1 - d / 170) * .22})`;
          ctx.lineWidth = .8;
          ctx.stroke();
        }
      }
      particles[i].update();
      particles[i].draw();
    }
    requestAnimationFrame(loop);
  }
  loop();
})();
</script>
</body>
</html>
