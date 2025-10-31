---
layout: none
title: National 5 Physics
---

<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
:root {
  --font-stack: "Trebuchet MS","Segoe UI",sans-serif;
  --radius-card: 1rem;
  --shadow-card: 0 24px 48px rgba(0,0,0,0.8);
  --bg1: #4b0035;
  --bg2: #7d004f;
  --bg3: #0f0015;
  --tile-bg: rgba(255,105,180,0.35);
}

/* PAGE BASE */
body {
  margin: 0;
  background: radial-gradient(circle at 25% 30%, var(--bg1) 0%, var(--bg2) 45%, var(--bg3) 90%);
  background-attachment: fixed;
  color: #fff;
  font-family: var(--font-stack);
  -webkit-font-smoothing: antialiased;
  line-height: 1.5;
  overflow-x: hidden;
  min-height: 100vh;
  display:flex;
  flex-direction:column;
  animation: bgDrift 20s ease-in-out infinite alternate;
}
@keyframes bgDrift {
  0% {background: radial-gradient(circle at 25% 30%, var(--bg1), var(--bg2), var(--bg3));}
  100% {background: radial-gradient(circle at 70% 70%, #ff0066, #80004b, #24001c);}
}

/* BANNER */
.banner-wrap {
  position: relative;
  width: 100%;
  overflow: hidden;
  flex-shrink: 0;
  box-shadow: 0 6px 15px rgba(0,0,0,0.6);
}
.banner {
  width: 100%;
  height: auto;
  max-height: 360px;
  object-fit: cover;
  display: block;
  opacity: 0;
  animation: fadeIn 1.2s ease forwards;
}
@keyframes fadeIn { to { opacity: 1; } }
@media (max-width: 768px) {.banner { max-height: 260px; }}

/* Banner tint + overlay */
.banner-tint {
  position: absolute;
  inset: 0;
  background: linear-gradient(120deg, rgba(255,79,154,0.45), rgba(255,0,128,0.4), rgba(255,200,200,0.25));
  mix-blend-mode: multiply;
  animation: tintShift 20s ease-in-out infinite alternate;
}
@keyframes tintShift {0%{background-position:0% 50%;}100%{background-position:100% 50%;}}

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
  font-weight: 600;
  font-size: 1.2rem;
  border-top: 1px solid rgba(255,255,255,0.2);
  text-shadow: 0 2px 6px rgba(0,0,0,0.6);
}
.banner-overlay-text h1 {margin:0;}
@media(max-width:900px){
  .banner-overlay-text{font-size:1rem;}
  .banner-overlay-text h1{font-size:0.95rem;line-height:1.3;}
}

/* SEPARATOR */
.banner-separator {
  width:100%;
  height:60px;
  background:linear-gradient(to bottom, rgba(0,0,0,0.4), rgba(0,0,0,0));
  margin-top:-3px;
}

/* MENU BUTTON */
.menu-btn {
  position:fixed;
  top:15px; right:20px;
  font-size:1.6rem;
  background:none;
  border:none;
  color:#fff;
  cursor:pointer;
  z-index:200;
  transition:transform 0.2s ease;
  text-shadow:0 4px 10px rgba(0,0,0,0.8);
}
.menu-btn:hover,.menu-btn:focus{transform:scale(1.1);outline:none;}

/* DRAWER MENU */
.menu-overlay {
  position:fixed; top:0; left:0; width:100%; height:100%;
  background:rgba(0,0,0,0.5);
  display:none; z-index:99;
}
.side-menu {
  position:fixed; top:0; right:-270px;
  height:100%; width:270px;
  background:rgba(15,23,42,0.92);
  backdrop-filter:blur(12px) saturate(160%);
  box-shadow:-4px 0 25px rgba(0,0,0,0.6);
  transition:right 0.3s ease;
  z-index:150;
  display:flex; flex-direction:column;
  padding-top:4rem;
}
.side-menu.open{right:0;}
.menu-overlay.show{display:block;}
.side-menu a {
  color:#fff; text-decoration:none;
  font-size:1.1rem;
  padding:0.9rem 1.5rem;
  display:flex; align-items:center; gap:0.8rem;
  transition:background 0.2s ease;
}
.side-menu a:hover,.side-menu a:focus {
  background:rgba(255,255,255,0.12);
  outline:none;
}

/* PAGE WRAP */
.page-wrap {
  flex:1;
  width:100%;
  max-width:1200px;
  margin:2rem auto;
  padding:0 1rem 4rem;
}

/* TILE GRID */
.tile-grid {
  display:grid;
  gap:1.2rem;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  justify-items:center;
  align-items:stretch;
}
@media (max-width:700px){
  .tile-grid{gap:0.9rem;}
}

/* TILE STYLE */
.class-tile {
  display:block;
  position:relative;
  min-height:140px;
  border-radius:var(--radius-card);
  background: var(--tile-bg);
  backdrop-filter: blur(8px) saturate(160%);
  -webkit-backdrop-filter: blur(8px) saturate(160%);
  border:2px solid rgba(255,255,255,0.25);
  outline:2px solid rgba(255,255,255,0.1);
  outline-offset:-4px;
  box-shadow: var(--shadow-card);
  color:#fff;
  text-decoration:none;
  cursor:pointer;
  transition: transform 0.18s ease, box-shadow 0.18s ease, filter 0.2s ease;
}
.class-tile:hover, .class-tile:focus {
  transform:translateY(-4px) scale(1.02);
  box-shadow:0 30px 60px rgba(0,0,0,0.9);
  filter:brightness(1.1);
  outline:3px solid #fff;
  outline-offset:3px;
}

/* TILE CONTENT */
.class-inner {
  display:flex;
  flex-direction:column;
  justify-content:flex-end;
  align-items:flex-start;
  height:100%;
  padding:1rem 1rem 1.25rem;
  color:#fff;
  text-shadow:0 2px 4px rgba(0,0,0,0.7);
}
.class-emoji {
  font-size:1.8rem;
  margin-bottom:0.5rem;
}
.class-name {
  font-size:1.1rem;
  font-weight:700;
  line-height:1.3;
  margin:0;
}

/* FOOTER */
footer {
  text-align:center;
  color:#fff;
  padding:1rem 0.5rem;
  font-size:0.9rem;
  background:rgba(0,0,0,0.4);
  backdrop-filter:blur(8px);
  border-top:1px solid rgba(255,255,255,0.2);
  margin-top:auto;
  width:100%;
  box-shadow:0 -3px 10px rgba(0,0,0,0.4);
}
</style>

<!-- MENU BUTTON -->
<button class="menu-btn" onclick="toggleMenu()" aria-label="Open menu">☰</button>

<!-- BANNER -->
<div class="banner-wrap">
  <img src="/assets/n5physicsbanner.png" alt="National 5 Physics Banner" class="banner">
  <div class="banner-tint"></div>
  <div class="banner-overlay-text"><h1>Learn, revise and explore National 5 Physics</h1></div>
</div>
<div class="banner-separator"></div>

<!-- PAGE CONTENT -->
<main class="page-wrap">
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
</main>

<!-- FOOTER -->
<footer>© Mr R Stewart’s Science, Physics, Electronics & Engineering</footer>

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
  menu.classList.toggle('open');
  overlay.classList.toggle('show');
}
document.addEventListener('keydown',e=>{
  if(e.key==='Escape'){
    document.getElementById('sideMenu').classList.remove('open');
    document.getElementById('menuOverlay').classList.remove('show');
  }
});
window.addEventListener('scroll',()=>{
  const banner=document.querySelector('.banner');
  if(!banner)return;
  const offset=window.scrollY*0.25;
  banner.style.transform=`translateY(${offset}px)`;
});
</script>
