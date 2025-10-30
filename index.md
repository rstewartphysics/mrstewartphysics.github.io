---
layout: none
title: Home
---

<style>
:root {
  --bg-page: #0f172a;
  --text-main: #f8fafc;
  --radius-card: 1rem;
  --shadow-card: 0 24px 48px rgba(0,0,0,0.8);
  --font-stack: "Trebuchet MS","Segoe UI",sans-serif;

  /* gradients */
  --science-grad: linear-gradient(135deg,#06b6d4 0%,#0e7490 100%);
  --physics-grad: linear-gradient(135deg,#3b82f6 0%,#1e3a8a 100%);
  --electronics-grad: linear-gradient(135deg,#34d399 0%,#065f46 100%);
  --engineering-grad: linear-gradient(135deg,#fb923c 0%,#c2410c 100%);
}

/* PAGE BASE */
body {
  margin: 0;
  background: var(--bg-page);
  color: var(--text-main);
  font-family: var(--font-stack);
  -webkit-font-smoothing: antialiased;
  line-height: 1.5;
}

.page-wrap {
  max-width: 1200px;
  margin: 3.5rem auto 4rem; /* more breathing room below banner */
  padding: 0 1rem;
}

/* BANNER */
.banner {
  width: 100%;
  height: auto;
  max-height: 340px; /* improved banner height */
  object-fit: cover;
  display: block;
  opacity: 0;
  animation: fadeIn 1.2s ease forwards;
  box-shadow: 0 6px 15px rgba(0,0,0,0.6);
}
@media (max-width: 768px) {
  .banner { max-height: 240px; }
}
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(-10px); }
  to { opacity: 1; transform: translateY(0); }
}

/* MENU BUTTON */
.menu-btn {
  position: absolute;
  top: 15px;
  right: 20px;
  font-size: 1.6rem;
  background: none;
  border: none;
  color: #fff;
  cursor: pointer;
  z-index: 10;
  transition: transform 0.2s ease;
}
.menu-btn:hover { transform: scale(1.1); }

/* OVERLAY + DRAWER */
.menu-overlay {
  position: fixed; top:0; left:0; width:100%; height:100%;
  background: rgba(0,0,0,0.5);
  display:none; z-index:99;
}
.side-menu {
  position: fixed; top:0; right:-270px;
  height:100%; width:270px;
  background: rgba(15,23,42,0.92);
  backdrop-filter: blur(8px);
  box-shadow:-4px 0 20px rgba(0,0,0,0.5);
  transition:right 0.3s ease;
  z-index:100;
  display:flex; flex-direction:column;
  padding-top:4rem;
}
.side-menu.open { right:0; }
.menu-overlay.show { display:block; }
.side-menu a {
  color: var(--text-main);
  text-decoration:none;
  font-size:1.1rem;
  padding:0.9rem 1.5rem;
  display:flex; align-items:center;
  gap:0.8rem;
  transition:background 0.2s ease;
}
.side-menu a:hover { background:rgba(255,255,255,0.1); }

/* GRID */
.tile-grid {
  display:grid;
  gap:1rem;
  margin-top:1.5rem;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
}
@media (max-width:900px){.tile-grid{grid-template-columns:1fr;}}

/* BUTTONS */
.class-tile {
  display:block;
  text-decoration:none;
  color:#fff;
  border-radius:var(--radius-card);
  box-shadow:var(--shadow-card);
  padding:1.5rem 1rem;
  min-height:120px;
  border:2px solid rgba(0,0,0,0.4);
  outline:2px solid rgba(255,255,255,0.07);
  outline-offset:-4px;
  transition:transform 0.18s ease,box-shadow 0.18s ease;
}
.class-tile:hover {
  transform:translateY(-4px) scale(1.02);
  box-shadow:0 30px 60px rgba(0,0,0,0.9);
}
.class-inner {
  display:flex;
  flex-direction:column;
  height:100%;
  justify-content:flex-end;
  align-items:flex-start;
}
.class-emoji {font-size:1.8rem; margin-bottom:0.5rem;}
.class-name {font-size:1.3rem; font-weight:700;}

/* SUBJECT COLOURS */
.tile-science     { background: var(--science-grad); }
.tile-physics     { background: var(--physics-grad); }
.tile-electronics { background: var(--electronics-grad); }
.tile-engineering { background: var(--engineering-grad); }
</style>

<!-- NAV BUTTON + BANNER -->
<button class="menu-btn" onclick="toggleMenu()">☰</button>
<img src="https://rstewartphysics.github.io/assets/homepagebanner.png" alt="Mr Stewart's Physics, Electronics and Engineering" class="banner">

<div class="page-wrap">
  <!-- MAIN MENU BUTTONS -->
  <section class="tile-grid">
    <a class="class-tile tile-science" href="/classes/science.html">
      <div class="class-inner"><div class="class-emoji">🧪</div><h2 class="class-name">Science</h2></div>
    </a>
    <a class="class-tile tile-physics" href="/classes/physics.html">
      <div class="class-inner"><div class="class-emoji">⚡</div><h2 class="class-name">Physics</h2></div>
    </a>
    <a class="class-tile tile-electronics" href="/classes/electronics.html">
      <div class="class-inner"><div class="class-emoji">💡</div><h2 class="class-name">Electronics</h2></div>
    </a>
    <a class="class-tile tile-engineering" href="/classes/engineering.html">
      <div class="class-inner"><div class="class-emoji">🧰</div><h2 class="class-name">Engineering</h2></div>
    </a>
  </section>
</div>

<!-- DRAWER NAVIGATION -->
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
  if(isOpen){menu.classList.remove('open');overlay.classList.remove('show');}
  else{menu.classList.add('open');overlay.classList.add('show');}
}
</script>
