---
layout: none
title: Home
---

<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
:root {
  --font-stack: "Trebuchet MS", "Segoe UI", sans-serif;
  --radius-card: 1rem;
  --shadow-card: 0 24px 48px rgba(0,0,0,0.8);
  --text-main: #ffffff;

  /* Background gradient matching banner colours */
  --bg-grad: radial-gradient(circle at 20% 30%, #0077ff 0%, #8b00ff 35%, #ff8800 70%, #00d4ff 100%);

  /* Tile gradients */
  --electronics-grad: linear-gradient(135deg,#34d399 0%,#065f46 100%);
  --engineering-grad: linear-gradient(135deg,#fb923c 0%,#c2410c 100%);
}

/* PAGE BASE */
body {
  margin: 0;
  background: var(--bg-grad);
  background-attachment: fixed;
  color: var(--text-main);
  font-family: var(--font-stack);
  -webkit-font-smoothing: antialiased;
  line-height: 1.5;
  overflow-x: hidden;
  min-height: 100vh;
  transition: background 10s ease-in-out;
}

/* BANNER */
.banner-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
  box-shadow: 0 6px 15px rgba(0,0,0,0.6);
}
.banner {
  width: 100%;
  height: auto;
  max-height: 420px;
  object-fit: cover;
  object-position: center;
  display: block;
  opacity: 0;
  animation: fadeIn 1.2s ease forwards;
}
@keyframes fadeIn { to { opacity: 1; } }
@media (max-width: 768px) {.banner { max-height: 300px; }}

/* Animated tint overlay */
.banner-tint {
  position: absolute;
  inset: 0;
  background: linear-gradient(120deg, rgba(0,119,255,0.45), rgba(139,0,255,0.35), rgba(255,136,0,0.35));
  mix-blend-mode: multiply;
  animation: tintShift 12s ease-in-out infinite alternate;
  pointer-events: none;
}
@keyframes tintShift {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}

/* FADE SEPARATOR BELOW BANNER */
.banner-separator {
  width: 100%;
  height: 70px;
  background: linear-gradient(to bottom, rgba(0,0,0,0.35), rgba(0,0,0,0));
  filter: blur(4px);
  margin-top: -3px;
  position: relative;
  z-index: 1;
}

/* MENU BUTTON */
.menu-btn {
  position: fixed;
  top: 15px;
  right: 20px;
  font-size: 1.6rem;
  background: none;
  border: none;
  color: #fff;
  cursor: pointer;
  z-index: 200;
  transition: transform 0.2s ease;
  text-shadow: 0 4px 10px rgba(0,0,0,0.8);
}
.menu-btn:hover, .menu-btn:focus {
  transform: scale(1.1);
  outline: none;
}

/* DRAWER MENU */
.menu-overlay {
  position: fixed; top:0; left:0; width:100%; height:100%;
  background: rgba(0,0,0,0.5);
  display:none; z-index:99;
}
.side-menu {
  position: fixed; top:0; right:-270px;
  height:100%; width:270px;
  background: rgba(15,23,42,0.92);
  backdrop-filter: blur(12px) saturate(160%);
  box-shadow:-4px 0 25px rgba(0,0,0,0.6);
  transition:right 0.3s ease;
  z-index:150;
  display:flex; flex-direction:column;
  padding-top:4rem;
}
.side-menu.open { right:0; }
.menu-overlay.show { display:block; }
.side-menu a {
  color:#fff;
  text-decoration:none;
  font-size:1.1rem;
  padding:0.9rem 1.5rem;
  display:flex;
  align-items:center;
  gap:0.8rem;
  transition:background 0.2s ease;
}
.side-menu a:hover { background:rgba(255,255,255,0.12); }

/* PAGE WRAP */
.page-wrap {
  width:100%;
  max-width:1200px;
  margin:2rem auto 4rem;
  padding:0 1rem;
  position:relative;
  z-index:1;
}

/* GRID */
.tile-grid {
  display:grid;
  gap:1rem;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  margin-top:1rem;
}
@media (max-width:900px){.tile-grid{grid-template-columns:1fr;}}

/* ACCESSIBILITY HELPERS */
.visually-hidden {
  position:absolute;
  width:1px;
  height:1px;
  padding:0;
  margin:-1px;
  overflow:hidden;
  clip:rect(0 0 0 0);
  white-space:nowrap;
  border:0;
}

/* TILE BASE */
.class-tile {
  display:block;
  border-radius:var(--radius-card);
  min-height:140px;
  box-shadow:var(--shadow-card);
  border:2px solid rgba(0,0,0,0.4);
  outline:2px solid rgba(255,255,255,0.07);
  outline-offset:-4px;
  position:relative;
  overflow:hidden;
  transition:transform 0.18s ease,box-shadow 0.18s ease,filter 0.2s ease;
  cursor:pointer;
}
.class-tile:hover, .class-tile:focus {
  transform:translateY(-4px) scale(1.02);
  box-shadow:0 30px 60px rgba(0,0,0,0.9);
  filter:brightness(1.08);
  outline:3px solid #fff;
  outline-offset:3px;
}

/* IMAGE TILES */
.tile-science {
  background:url("/assets/sciencebanner.png") center/cover no-repeat;
}
.tile-physics {
  background:url("/assets/physicsbanner.png") center/cover no-repeat;
}

/* GRADIENT TILES */
.tile-electronics { background:var(--electronics-grad); color:#fff; }
.tile-engineering { background:var(--engineering-grad); color:#fff; }

.class-inner {
  display:flex;
  flex-direction:column;
  height:100%;
  justify-content:flex-end;
  align-items:flex-start;
  padding:1.5rem 1rem;
  color:#fff;
}
.class-emoji {font-size:1.8rem; margin-bottom:0.5rem;}
.class-name {font-size:1.3rem; font-weight:700;}
</style>

<!-- NAV BUTTON + BANNER -->
<button class="menu-btn" onclick="toggleMenu()" aria-label="Open menu">☰</button>
<div class="banner-wrap">
  <img src="/assets/homepagebanner2.png" alt="Mr Stewart’s Physics, Electronics and Engineering" class="banner">
  <div class="banner-tint"></div>
</div>

<!-- Soft fade separator -->
<div class="banner-separator"></div>

<div class="page-wrap">
  <section class="tile-grid">
    <a class="class-tile tile-science" href="/classes/science.html" aria-label="Science">
      <span class="visually-hidden">Science</span>
    </a>

    <a class="class-tile tile-physics" href="/classes/physics.html" aria-label="Physics">
      <span class="visually-hidden">Physics</span>
    </a>

    <a class="class-tile tile-electronics" href="/classes/electronics.html" aria-label="Electronics">
      <div class="class-inner">
        <div class="class-emoji">💡</div>
        <h2 class="class-name">Electronics</h2>
      </div>
    </a>

    <a class="class-tile tile-engineering" href="/classes/engineering.html" aria-label="Engineering">
      <div class="class-inner">
        <div class="class-emoji">🧰</div>
        <h2 class="class-name">Engineering</h2>
      </div>
    </a>
  </section>
</div>

<!-- DRAWER MENU -->
<div class="menu-overlay" id="menuOverlay" onclick="toggleMenu()"></div>
<nav class="side-menu" id="sideMenu">
  <a href="/">🏠 Home</a>
  <a href="/classes/science.html">🧪 Science</a>
  <a href="/classes/physics.html">⚡ Physics</a>
  <a href="/classes/electronics.html">💡 Electronics</a>
  <a href="/classes/engineering.html">🧰 Engineering</a>
</nav>

<script>
function toggleMenu(){
  const menu=document.getElementById('sideMenu');
  const overlay=document.getElementById('menuOverlay');
  const isOpen=menu.classList.contains('open');
  if(isOpen){
    menu.classList.remove('open');
    overlay.classList.remove('show');
  } else {
    menu.classList.add('open');
    overlay.classList.add('show');
  }
}

// ESC to close
document.addEventListener('keydown', (e) => {
  if (e.key === 'Escape') {
    document.getElementById('sideMenu').classList.remove('open');
    document.getElementById('menuOverlay').classList.remove('show');
  }
});
</script>
