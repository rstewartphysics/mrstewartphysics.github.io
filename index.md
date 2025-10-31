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
  --bg-grad: radial-gradient(circle at 20% 30%, #0077ff 0%, #8b00ff 35%, #ff8800 70%, #00d4ff 100%);
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
  transform: translateY(0);
  animation: fadeIn 1.2s ease forwards;
}
@keyframes fadeIn { to { opacity: 1; } }
@media (max-width: 768px) {.banner { max-height: 300px; }}

/* Animated tint overlay */
.banner-tint {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    120deg,
    rgba(0,119,255,0.45),
    rgba(139,0,255,0.35),
    rgba(255,136,0,0.35)
  );
  mix-blend-mode: multiply;
  animation: tintShift 12s ease-in-out infinite alternate;
  pointer-events: none;
}
@keyframes tintShift {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
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

/* Fade separator */
.banner-separator {
  width: 100%;
  height: 70px;
  background: linear-gradient(to bottom, rgba(0,0,0,0.35), rgba(0,0,0,0));
  position: relative;
  z-index: 1;
  margin-top: -3px;
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
  color:#fff;
  text-decoration:none;
  font-size:1.1rem;
  padding:0.9rem 1.5rem;
  display:flex; align-items:center; gap:0.8rem;
  transition:background 0.2s ease;
}
.side-menu a:hover, .side-menu a:focus {
  background:rgba(255,255,255,0.12);
  outline:none;
}

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
  transition:transform 0.18s ease, box-shadow 0.18s ease, filter 0.2s ease;
  cursor:pointer;
  background-size:cover;
  background-position:center;
  background-repeat:no-repeat;
  text-decoration:none;
}
.class-tile:hover, .class-tile:focus {
  transform:translateY(-4px) scale(1.02);
  box-shadow:0 30px 60px rgba(0,0,0,0.9);
  filter:brightness(1.08);
  outline:3px solid #fff;
  outline-offset:3px;
  text-decoration:none;
}

/* Tile label bar */
.tile-label {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  background: rgba(0,0,0,0.45);
  backdrop-filter: blur(6px);
  color: #fff;
  text-align: center;
  font-family: var(--font-stack);
  font-weight: 600;
  font-size: 1rem;
  padding: 0.6rem 0.4rem;
  border-top: 1px solid rgba(255,255,255,0.2);
  text-shadow: 0 2px 5px rgba(0,0,0,0.6);
  transition: background 0.3s ease;
  pointer-events: none;
}
.class-tile:hover .tile-label {
  background: rgba(0,0,0,0.6);
}

/* INDIVIDUAL TILE IMAGES */
.tile-science { background-image:url("/assets/sciencebanner.png"); }
.tile-physics { background-image:url("/assets/physicsbanner.png"); }
.tile-electronics { background-image:url("/assets/Electronicsbanner.png"); }
.tile-engineering { background-image:url("/assets/Engeneringbanner.png"); }
</style>

<!-- NAV BUTTON -->
<button class="menu-btn" type="button" onclick="toggleMenu()" aria-label="Open menu">☰</button>

<!-- HERO BANNER -->
<div class="banner-wrap">
  <img src="/assets/homelogo.png" alt="Mr Stewart’s Physics, Science, Electronics and Engineering" class="banner">
  <div class="banner-tint"></div>
  <div class="banner-overlay-text"><h1>Welcome — explore Physics, Science, Electronics & Engineering</h1></div>
</div>

<div class="banner-separator"></div>

<div class="page-wrap">
  <section class="tile-grid">
    <a class="class-tile tile-science" href="/classes/science.html"><div class="tile-label">Science</div></a>
    <a class="class-tile tile-physics" href="/classes/physics.html"><div class="tile-label">Physics</div></a>
    <a class="class-tile tile-electronics" href="/classes/electronics.html"><div class="tile-label">Electronics</div></a>
    <a class="class-tile tile-engineering" href="/classes/engineering.html"><div class="tile-label">Engineering</div></a>
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
  if(isOpen){menu.classList.remove('open');overlay.classList.remove('show');}
  else{menu.classList.add('open');overlay.classList.add('show');}
}
document.addEventListener('keydown',(e)=>{
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
