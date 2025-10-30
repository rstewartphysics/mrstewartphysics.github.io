---
layout: none
title: Home
---

<style>
:root {
  --bg-page: #0f172a;            /* deep navy/charcoal */
  --text-main: #f8fafc;          /* near-white */
  --text-dim: #94a3b8;           /* slate text */
  --radius-card: 1rem;
  --shadow-card: 0 24px 48px rgba(0,0,0,0.8);
  --font-stack: "Trebuchet MS","Segoe UI",sans-serif;

  /* subject gradients */
  --s1-grad: linear-gradient(135deg,#06b6d4 0%,#0e7490 100%);       /* cyan/teal */
  --s2-grad: linear-gradient(135deg,#7c3aed 0%,#4c1d95 100%);       /* purple */
  --n5-grad: linear-gradient(135deg,#ec4899 0%,#be185d 100%);       /* magenta/pink-ish (no hearts, still bold) */
  --higher-grad: linear-gradient(135deg,#3b82f6 0%,#1e3a8a 100%);   /* blue */
  --adv-grad: linear-gradient(135deg,#fde047 0%,#ca8a04 100%);      /* yellow/gold */
  --eng-grad: linear-gradient(135deg,#fb923c 0%,#c2410c 100%);      /* orange/amber */
  --elec-grad: linear-gradient(135deg,#34d399 0%,#065f46 100%);     /* green */

  --header-grad-1: #1e293b;
  --header-grad-2: #0f172a;
  --header-grad-3: #1e3a8a;
}

/* GLOBAL PAGE WRAPPER */
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
  color: var(--text-main);
  font-family: var(--font-stack);
}

/* HEADER / TITLE BAR */
.header-block {
  background: radial-gradient(circle at 20% 20%, rgba(59,130,246,0.4) 0%, rgba(15,23,42,0) 60%),
              linear-gradient(270deg, var(--header-grad-1), var(--header-grad-2), var(--header-grad-3));
  background-size: 400% 400%;
  animation: headerPulse 10s ease infinite;
  border-radius: var(--radius-card);
  box-shadow: 0 30px 60px rgba(0,0,0,0.8);
  border: 2px solid rgba(148,163,184,0.2);
  padding: 1.5rem 1rem 1.25rem;
  margin-bottom: 2rem;
  text-align: center;
}
@keyframes headerPulse {
  0%   {background-position: 0% 50%;}
  50%  {background-position: 100% 50%;}
  100% {background-position: 0% 50%;}
}

.header-title {
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--text-main);
  margin: 0;
  line-height: 1.3;
}
@media (min-width: 480px) {
  .header-title {
    font-size: 1.6rem;
  }
}
@media (min-width: 768px) {
  .header-title {
    font-size: 1.8rem;
  }
}

/* GRID OF CLASS BUTTONS */
.tile-grid {
  display: grid;
  gap: 1rem;
  margin-bottom: 2rem;
  grid-template-columns: repeat(auto-fit, minmax(260px,1fr));
}

/* FORCE 1-COLUMN ON SMALL PHONES */
@media (max-width: 500px) {
  .tile-grid {
    grid-template-columns: 1fr;
  }
}

/* BIG BUTTON TILE */
.class-tile {
  display: block;
  position: relative;
  text-decoration: none;
  color: #fff;
  border-radius: var(--radius-card);
  box-shadow: var(--shadow-card);
  padding: 1.25rem 1rem;
  min-height: 110px;
  border: 2px solid rgba(0,0,0,0.4);
  outline: 2px solid rgba(255,255,255,0.07);
  outline-offset: -4px;

  /* animation + hover */
  transition: transform 0.18s ease, box-shadow 0.18s ease;
}
.class-tile:hover {
  transform: translateY(-4px) scale(1.02);
  box-shadow: 0 30px 60px rgba(0,0,0,0.9);
}

/* TILE TEXT */
.class-inner {
  display: flex;
  flex-direction: column;
  height: 100%;
  justify-content: flex-end;
}
.class-name {
  font-size: 1.05rem;
  font-weight: 700;
  line-height: 1.4;
  margin: 0;
  text-shadow: 0 2px 4px rgba(0,0,0,0.6);
}
@media (min-width: 480px) {
  .class-name { font-size: 1.15rem; }
}
@media (min-width: 768px) {
  .class-name { font-size: 1.25rem; }
}

/* EMOJI BADGE IN TILE */
.class-emoji {
  font-size: 1.5rem;
  line-height: 1;
  margin-bottom: 0.5rem;
  text-shadow: 0 2px 4px rgba(0,0,0,0.6);
}
@media (min-width: 480px) {
  .class-emoji { font-size: 1.6rem; }
}
@media (min-width: 768px) {
  .class-emoji { font-size: 1.8rem; }
}

/* SUBJECT COLOURS */
.tile-s1   { background: var(--s1-grad); }
.tile-s2   { background: var(--s2-grad); }
.tile-n5   { background: var(--n5-grad); }
.tile-high { background: var(--higher-grad); }
.tile-adv  { background: var(--adv-grad); color:#000; text-shadow: 0 2px 4px rgba(0,0,0,0.15); }
.tile-eng  { background: var(--eng-grad); }
.tile-elec { background: var(--elec-grad); }

/* If tile uses light text vs dark text */
.tile-adv .class-emoji,
.tile-adv .class-name {
  color:#000;
  text-shadow: 0 2px 4px rgba(255,255,255,0.4);
}

/* QUICK LINKS CARD */
.quick-links-card {
  background: rgba(30,41,59,0.6);
  border-radius: var(--radius-card);
  border: 2px solid rgba(148,163,184,0.2);
  box-shadow: var(--shadow-card);
  padding: 1rem 1rem 1.25rem;
  margin-bottom: 2rem;
}
.quick-header {
  font-size: 1rem;
  font-weight: 700;
  color: var(--text-main);
  margin: 0 0 0.75rem;
  text-shadow: 0 2px 4px rgba(0,0,0,0.8);
  text-align: center;
  letter-spacing: 0.02em;
}
.quick-links-list {
  list-style: none;
  padding-left: 0;
  margin: 0;
  font-size: 0.95rem;
  line-height: 1.6;
  text-align: center;
}
.quick-links-list li {
  margin-bottom: 0.5rem;
}
.quick-links-list a {
  color: var(--text-main);
  font-weight: 700;
  text-decoration: none;
  background: rgba(15,23,42,0.6);
  border-radius: var(--radius-pill);
  padding: 0.6rem 0.9rem;
  display: inline-block;
  box-shadow: 0 16px 32px rgba(0,0,0,0.8);
  border: 2px solid rgba(148,163,184,0.3);
  transition: box-shadow 0.18s ease, transform 0.18s ease;
}
.quick-links-list a:hover {
  transform: translateY(-3px) scale(1.03);
  box-shadow: 0 24px 48px rgba(0,0,0,0.9);
}

/* FOOTER NOTE */
.footer-note {
  font-size: 0.8rem;
  color: var(--text-dim);
  text-align: center;
  line-height: 1.4;
  padding-bottom: 3rem;
  max-width: 600px;
  margin: 0 auto;
  font-family: var(--font-stack);
}
</style>

<div class="page-wrap">

  <!-- HEADER -->
  <section class="header-block">
    <h1 class="header-title">
      Mr Stewart’s Physics, Electronics and Engineering
    </h1>
  </section>

  <!-- CLASS BUTTON GRID -->
  <section class="tile-grid">

    <!-- S1 Science -->
    <a class="class-tile tile-s1" href="/classes/s1-science.html">
      <div class="class-inner">
        <div class="class-emoji">🧪</div>
        <h2 class="class-name">S1 Science</h2>
      </div>
    </a>

    <!-- S2 Science -->
    <a class="class-tile tile-s2" href="/classes/s2-science.html">
      <div class="class-inner">
        <div class="class-emoji">🔬</div>
        <h2 class="class-name">S2 Science</h2>
      </div>
    </a>

    <!-- S3 / National 5 Physics -->
    <a class="class-tile tile-n5" href="/classes/s3-n5-physics.html">
      <div class="class-inner">
        <div class="class-emoji">⚡</div>
        <h2 class="class-name">S3 / National 5 Physics</h2>
      </div>
    </a>

    <!-- Higher Physics -->
    <a class="class-tile tile-high" href="/classes/higher-physics.html">
      <div class="class-inner">
        <div class="class-emoji">🔭</div>
        <h2 class="class-name">Higher Physics</h2>
      </div>
    </a>

    <!-- Advanced Higher Physics -->
    <a class="class-tile tile-adv" href="/classes/adv-higher-physics.html">
      <div class="class-inner">
        <div class="class-emoji">🧠</div>
        <h2 class="class-name">Advanced Higher Physics</h2>
      </div>
    </a>

    <!-- Engineering Science -->
    <a class="class-tile tile-eng" href="/classes/engineering-science.html">
      <div class="class-inner">
        <div class="class-emoji">🧰</div>
        <h2 class="class-name">Engineering Science</h2>
      </div>
    </a>

    <!-- Practical Electronics -->
    <a class="class-tile tile-elec" href="/classes/practical-electronics.html">
      <div class="class-inner">
        <div class="class-emoji">💡</div>
        <h2 class="class-name">Practical Electronics</h2>
      </div>
    </a>

  </section>

  <!-- QUICK LINKS -->
  <section class="quick-links-card">
    <h3 class="quick-header">Quick Links</h3>
    <ul class="quick-links-list">
      <li>
        <a href="/quick-links">Revision / Study Links</a>
      </li>
      <li>
        <a href="/contact">Contact / Support</a>
      </li>
    </ul>
  </section>

  <!-- FOOTER NOTE -->
  <div class="footer-note">
    If you’re stuck, ask in class.<br />
    Be specific: “I don’t understand Q4(b)” is better than “I don’t get physics.”
  </div>

</div>