---
layout: none
title: Home
---

<style>
:root {
  --blue1: #2196f3;
  --blue2: #1565c0;
  --blue3: #0d47a1;
  --bg-page: #f7f9fc;
  --text-main: #0f172a;
  --text-dim: #475569;
  --radius-card: 1rem;
  --radius-pill: 0.5rem;
  --shadow-card: 0 10px 25px rgba(0,0,0,0.1);
  --font-stack: "Trebuchet MS","Segoe UI",sans-serif;
}

/* Page shell */
body {
  background: var(--bg-page);
  color: var(--text-main);
  font-family: var(--font-stack);
  -webkit-font-smoothing: antialiased;
  line-height: 1.5;
  margin: 0;
  padding: 0;
}

.page-wrap {
  max-width: 1100px;
  margin: 2rem auto 4rem;
  padding: 0 1rem;
  font-family: var(--font-stack);
  color: var(--text-main);
}

/* HEADER */
.header-block {
  background: linear-gradient(270deg, var(--blue1), var(--blue2), var(--blue3));
  background-size: 600% 600%;
  animation: gradientShift 12s ease infinite;
  border-radius: var(--radius-card);
  color: #fff;
  box-shadow: var(--shadow-card);
  border: 2px solid var(--blue3);
  padding: 1.5rem 1rem 1.25rem;
  margin-bottom: 2rem;
  text-align: center;
}
@keyframes gradientShift {
  0% {background-position: 0% 50%;}
  50% {background-position: 100% 50%;}
  100% {background-position: 0% 50%;}
}
.header-title {
  font-size: 1.6rem;
  font-weight: 700;
  margin: 0 0 0.5rem 0;
  color: #fff;
  font-family: var(--font-stack);
}
.header-desc {
  font-size: 1rem;
  margin: 0;
  line-height: 1.4;
  color: rgba(255,255,255,0.9);
}

/* GRID OF CLASS TILES */
.tile-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(240px,100%),1fr));
  gap: 1rem;
  margin-bottom: 2rem;
}

/* each tile */
.class-tile {
  background: #fff;
  color: var(--text-main);
  text-decoration: none;
  border-radius: var(--radius-card);
  padding: 1rem 1rem 1.25rem;
  box-shadow: var(--shadow-card);
  border: 1px solid rgba(0,0,0,0.05);
  display: block;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  min-height: 150px;
}
.class-tile:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 30px rgba(0,0,0,0.15);
}
.class-heading {
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--blue3);
  margin: 0 0 0.5rem 0;
  line-height: 1.3;
  font-family: var(--font-stack);
}
.class-desc {
  font-size: 0.9rem;
  color: var(--text-dim);
  margin: 0;
  line-height: 1.4;
}

/* QUICK LINKS SECTION */
.quick-links-card {
  background: #fff;
  border-radius: var(--radius-card);
  border: 1px solid rgba(0,0,0,0.05);
  box-shadow: var(--shadow-card);
  padding: 1rem 1rem 1.25rem;
  margin-bottom: 2rem;
}
.quick-header {
  font-size: 1.1rem;
  font-weight: 700;
  color: var(--blue3);
  margin: 0 0 0.75rem;
  font-family: var(--font-stack);
}
.quick-links-list {
  list-style: none;
  padding-left: 0;
  margin: 0;
  font-size: 0.95rem;
  line-height: 1.5;
}
.quick-links-list li {
  margin-bottom: 0.5rem;
}
.quick-links-list a {
  color: var(--blue2);
  font-weight: 600;
  text-decoration: none;
  border-bottom: 2px solid transparent;
}
.quick-links-list a:hover {
  border-bottom: 2px solid var(--blue2);
}

/* FOOTER / NOTE */
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
    <h1 class="header-title">Welcome 👋</h1>
    <p class="header-desc">
      This site is for students of Berwickshire High School.<br />
      Choose your class to get notes, homework, revision links, and support.
    </p>
  </section>

  <!-- CLASS GRID -->
  <section class="tile-grid">

    <a class="class-tile" href="/classes/s1-science.html">
      <h2 class="class-heading">S1 Science</h2>
      <p class="class-desc">
        Topics, notes, revision videos, and homework.
      </p>
    </a>

    <a class="class-tile" href="/classes/s2-science.html">
      <h2 class="class-heading">S2 Science</h2>
      <p class="class-desc">
        Resources and tasks for S2.
      </p>
    </a>

    <a class="class-tile" href="/classes/s3-n5-physics.html">
      <h2 class="class-heading">S3 / National 5 Physics</h2>
      <p class="class-desc">
        Course notes, past papers, required formulas.
      </p>
    </a>

    <a class="class-tile" href="/classes/higher-physics.html">
      <h2 class="class-heading">Higher Physics</h2>
      <p class="class-desc">
        Past papers by topic, tricky questions, Scholar, and more.
      </p>
    </a>

    <a class="class-tile" href="/classes/adv-higher-physics.html">
      <h2 class="class-heading">Advanced Higher Physics</h2>
      <p class="class-desc">
        AH past paper questions, Scholar, Flash Physics animations.
      </p>
    </a>

    <a class="class-tile" href="/classes/engineering-science.html">
      <h2 class="class-heading">Engineering Science</h2>
      <p class="class-desc">
        Circuits, mechanics, control systems, assignments.
      </p>
    </a>

    <a class="class-tile" href="/classes/practical-electronics.html">
      <h2 class="class-heading">Practical Electronics</h2>
      <p class="class-desc">
        Build guides, circuit diagrams, component lists.
      </p>
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
    If you’re stuck, ask in class first.  
    Be specific: “I don’t understand Q4(b)” is better than “I don’t get physics.”
  </div>

</div>