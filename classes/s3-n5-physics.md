---
layout: none
title: National 5 Physics
---

<meta name="viewport" content="width=device-width, initial-scale=1">

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
  min-height: 100vh;
}

/* BANNER */
.banner-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
  box-shadow: 0 6px 15px rgba(0,0,0,0.4);
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

.banner-tint {
  position: absolute;
  inset: 0;
  background: linear-gradient(120deg, rgba(255,79,154,0.45), rgba(192,18,116,0.45));
  mix-blend-mode: multiply;
  animation: tintShift 10s ease-in-out infinite alternate;
}
@keyframes tintShift {
  from {background-position: 0% 50%;}
  to {background-position: 100% 50%;}
}

/* Translucent info bar across banner */
.banner-overlay-text {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  background: rgba(0,0,0,0.45);
  backdrop-filter: blur(8px);
  color: #fff;
  text-align: center;
  padding: 1rem 0.5rem;
  font-family: var(--font-stack);
  font-size: 1.2rem;
  font-weight: 600;
  text-shadow: 0 2px 6px rgba(0,0,0,0.6);
  border-top: 1px solid rgba(255,255,255,0.2);
  z-index: 2;
}
@media (max-width: 768px){
  .banner-overlay-text h1{
    font-size:1rem;
    padding:0.8rem 0.5rem;
  }
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
  -webkit-backdrop-filter: blur(12px) saturate(160%);
  box-shadow:-4px 0 25px rgba(0,0,0,0.6);
  transition:right 0.3s ease;
  z-index:150;
  display:flex; flex-direction:column;
  padding-top:4rem;
}
.side-menu.open { right:0; }
.menu-overlay.show { display:block; }
.side-menu a {
  color:#fff; text-decoration:none; font-size:1.1rem;
  padding:0.9rem 1.5rem; display:flex; align-items:center; gap:0.8rem;
  transition:background 0.2s ease;
}
.side-menu a:hover, .side-menu a:focus {
  background:rgba(255,255,255,0.12);
  outline:none;
}

/* GRID */
.page-wrap {
  width: 100%;
  max-width: 1200px;
  margin: 2rem auto 4rem;
  padding: 0 1rem;
  position: relative;
}
.tile-grid {
  display:grid;
  gap:1rem;
  margin-top:1.5rem;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
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
.class-tile:hover, .class-tile:focus {
  transform:translateY(-4px) scale(1.02);
  box-shadow:0 28px 60px rgba(0,0,0,0.55);
  outline:3px solid #fff;
  outline-offset:3px;
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
<button class="menu-btn" onclick="toggleMenu()" aria-label="Open menu">☰</button>

<div class="banner-wrap">
  <img src="/assets/n5physicsbanner.png" alt="National 5 Physics Banner" class="banner">
  <div class="banner-tint"></div>
  <div class="banner-overlay-text"><h1>Learn, revise and explore National 5 Physics</h1></div>
</div>

<!-- PAGE CONTENT -->
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
  if(isOpen){
    menu.classList.remove('open');
    overlay.classList.remove('show');
  } else {
    menu.classList.add('open');
    overlay.classList.add('show');
  }
}

// ESC closes drawer
document.addEventListener('keydown',(e)=>{
  if(e.key==='Escape'){
    document.getElementById('sideMenu').classList.remove('open');
    document.getElementById('menuOverlay').classList.remove('show');
  }
});
</script>
