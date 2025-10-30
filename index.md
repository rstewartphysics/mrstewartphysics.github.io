---
layout: none
title: Home
---

<style>
:root {
  --bg-page: #0f172a;            /* deep navy */
  --text-main: #f8fafc;          /* near-white */
  --radius-card: 1rem;
  --shadow-card: 0 24px 48px rgba(0,0,0,0.8);
  --font-stack: "Trebuchet MS","Segoe UI",sans-serif;

  /* subject gradients */
  --science-grad: linear-gradient(135deg,#06b6d4 0%,#0e7490 100%);    /* teal */
  --physics-grad: linear-gradient(135deg,#3b82f6 0%,#1e3a8a 100%);    /* blue */
  --electronics-grad: linear-gradient(135deg,#34d399 0%,#065f46 100%);/* green */
  --engineering-grad: linear-gradient(135deg,#fb923c 0%,#c2410c 100%);/* orange */

  --header-grad-1: #1e293b;
  --header-grad-2: #0f172a;
  --header-grad-3: #1e3a8a;
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
  margin: 2rem auto 4rem;
  padding: 0 1rem;
}

/* HEADER */
.header-block {
  background: radial-gradient(circle at 20% 20%, rgba(59,130,246,0.4) 0%, rgba(15,23,42,0) 60%),
              linear-gradient(270deg, var(--header-grad-1), var(--header-grad-2), var(--header-grad-3));
  background-size: 400% 400%;
  animation: headerPulse 10s ease infinite;
  border-radius: var(--radius-card);
  box-shadow: 0 30px 60px rgba(0,0,0,0.8);
  border: 2px solid rgba(148,163,184,0.2);
  padding: 1rem 1rem 0.8rem;
  margin-bottom: 1rem;
  text-align: center;
}
@keyframes headerPulse {
  0% {background-position: 0% 50%;}
  50% {background-position: 100% 50%;}
  100% {background-position: 0% 50%;}
}
.header-title {
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--text-main);
  margin: 0;
  line-height: 1.3;
}
@media (min-width: 768px) {
  .header-title { font-size: 1.8rem; }
}

/* GRID LAYOUT */
.tile-grid {
  display: grid;
  gap: 1rem;
  margin-top: 1rem;
  grid-template-columns: repeat(auto-fit, minmax(260px,1fr));
}
@media (max-width: 900px) {
  .tile-grid { grid-template-columns: 1fr; }
}

/* BUTTONS */
.class-tile {
  display: block;
  text-decoration: none;
  color: #fff;
  border-radius: var(--radius-card);
  box-shadow: var(--shadow-card);
  padding: 1.5rem 1rem;
  min-height: 120px;
  border: 2px solid rgba(0,0,0,0.4);
  outline: 2px solid rgba(255,255,255,0.07);
  outline-offset: -4px;
  transition: transform 0.18s ease, box-shadow 0.18s ease;
}
.class-tile:hover {
  transform: translateY(-4px) scale(1.02);
  box-shadow: 0 30px 60px rgba(0,0,0,0.9);
}

/* BUTTON CONTENT */
.class-inner {
  display: flex;
  flex-direction: column;
  height: 100%;
  justify-content: flex-end;
  align-items: flex-start;
}
.class-emoji {
  font-size: 1.8rem;
  margin-bottom: 0.5rem;
}
.class-name {
  font-size: 1.3rem;
  font-weight: 700;
}

/* SUBJECT COLOURS */
.tile-science     { background: var(--science-grad); }
.tile-physics     { background: var(--physics-grad); }
.tile-electronics { background: var(--electronics-grad); }
.tile-engineering { background: var(--engineering-grad); }

</style>

<div class="page-wrap">
  <!-- HEADER -->
  <section class="header-block">
    <h1 class="header-title">
      Mr Stewart’s Physics, Electronics and Engineering
    </h1>
  </section>

  <!-- MAIN MENU -->
  <section class="tile-grid">

    <a class="class-tile tile-science" href="/classes/science.html">
      <div class="class-inner">
        <div class="class-emoji">🧪</div>
        <h2 class="class-name">Science</h2>
      </div>
    </a>

    <a class="class-tile tile-physics" href="/classes/physics.html">
      <div class="class-inner">
        <div class="class-emoji">⚡</div>
        <h2 class="class-name">Physics</h2>
      </div>
    </a>

    <a class="class-tile tile-electronics" href="/classes/electronics.html">
      <div class="class-inner">
        <div class="class-emoji">💡</div>
        <h2 class="class-name">Electronics</h2>
      </div>
    </a>

    <a class="class-tile tile-engineering" href="/classes/engineering.html">
      <div class="class-inner">
        <div class="class-emoji">🧰</div>
        <h2 class="class-name">Engineering</h2>
      </div>
    </a>

  </section>
</div>
