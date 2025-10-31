---
layout: none
title: National 5 Physics
---

<style>
:root {
  --bg-page: #fff1f8;
  --text-main: #2a0a18;
  --radius-card: 1rem;
  --shadow-card: 0 20px 44px rgba(0,0,0,0.28);
  --font-stack: "Trebuchet MS","Segoe UI",sans-serif;

  --accent-pink: linear-gradient(135deg,#ff4f9a 0%,#c01274 100%);
}

/* PAGE BASE */
body {
  margin: 0;
  background: var(--bg-page);
  color: var(--text-main);
  font-family: var(--font-stack);
  -webkit-font-smoothing: antialiased;
  line-height: 1.5;
  position: relative;
  overflow-x: hidden;
}

/* BANNER */
.banner-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
}
.banner {
  width: 100%;
  height: auto;
  max-height: 420px;
  object-fit: cover;
  object-position: center center;
  display: block;
  opacity: 0;
  animation: fadeIn 1.2s ease forwards;
  box-shadow: 0 6px 15px rgba(0,0,0,0.4);
}
@keyframes fadeIn { to { opacity: 1; } }
@media (max-width: 768px) {.banner { max-height: 300px; }}

.banner-tint {
  position: absolute;
  top:0; left:0; width:100%; height:100%;
  background: linear-gradient(120deg, rgba(255,79,154,0.4), rgba(192,18,116,0.45));
  mix-blend-mode: multiply;
  animation: tintShift 10s ease-in-out infinite alternate;
}
@keyframes tintShift {
  from {background-position: 0% 50%;}
  to {background-position: 100% 50%;}
}

/* NAV BUTTON */
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
  color: #fff;
  text-decoration:none;
  font-size:1.1rem;
  padding:0.9rem 1.5rem;
  display:flex; align-items:center;
  gap:0.8rem;
  transition:background 0.2s ease;
}
.side-menu a:hover { background:rgba(255,255,255,0.1); }

/* GRID */
.page-wrap { width: 100%; }
.tile-grid {
  display:grid;
  gap:1rem;
  margin-top:1.5rem;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  padding: 0 1rem 2rem;
}
@media (max-width:900px){.tile-grid{grid-template-columns:1fr;}}

/* BUTTONS / TILES */
.class-tile {
  display:block;
  text-decoration:none;
  color:#fff;
  border-radius:var(--radius-card);
  background: var(--accent-pink);
  box-shadow:var(--shadow-card);
  padding:1.5rem 1rem;
  min-height:120px;
  border:2px solid rgba(0,0,0,0.35);
  outline:2px solid rgba(255,255,255,0.08);
  outline-offset:-4px;
  transition:transform 0.18s ease,box-shadow 0.18s ease;
}
.class-tile:hover {
  transform:translateY(-4px) scale(1.02);
  box-shadow:0 28px 60px rgba(0,0,0,0.55);
}
.class-inner {
  display:flex;
  flex-direction:column;
  height:100%;
  justify-content:flex-end;
  align-items:flex-start;
}
.class-emoji {font-size:1.8rem; margin-bottom:0.5rem;}
.class-name {font-size:1.25rem; font-weight:700;}
</style>

<!-- NAV BUTTON + BANNER -->
<div class="banner-wrap">
  <button class="menu-btn" onclick="toggleMenu()">☰</button>
  <img src="/assets/n5physicsbanner.png" alt="National 5 Physics Banner" class="banner">
  <div class="banner-tint"></div>
</div>

<div class="page-wrap">
  <section class="tile-grid">
    <a class="class-tile" href="https://glowscotland-my.sharepoint.com/:b:/g/personal/gw20stewartrobert1_glow_sch_uk/EWFk37iHRGFBg4j0bTdCQZ4B2ywGu4aQBkdzXeWe1T00Lw?e=vK8KQX">
      <div class="class-inner"><div class="class-emoji">📂</div><h2 class="class-name">Mr Stewart Materials</h2></div>
    </a>

    <a class="class-tile" href="https://glowscotland-my.sharepoint.com/:f:/g/personal/gw20stewartrobert1_glow_sch_uk/EsrN6PPS0HtMkclmwJPrEiEBBbTgPcjZuWg-_m0yP25E5A?e=QnwV3L">
      <div class="class-inner"><div class="class-emoji">📘</div><h2 class="class-name">Past Papers</h2></div>
    </a>

    <a class="class-tile" href="https://physicsflashrepo.ovh/">
      <div class="class-inner"><div class="class-emoji">⚡</div><h2 class="class-name">Flash Physics</h2></div>
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
</script>