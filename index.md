---
layout: none
title: Home
---
<style>
:root {
  --accent-blue: #1565c0;
  --accent-blue-dark: #0d47a1;
  --bg-soft: #f5f8ff;
  --text-dark: #0f172a;
  --radius-card: 1rem;
  --radius-button: 0.65rem;
  --gap-lg: 1rem;
  --gap-xl: 1.5rem;
  --shadow-card: 0 12px 24px rgba(0,0,0,0.08);
  --shadow-button: 0 8px 16px rgba(0,0,0,0.12);
  --font-stack: -apple-system, BlinkMacSystemFont, "Inter", "Roboto", "Segoe UI", sans-serif;
}

body {
  font-family: var(--font-stack);
  color: var(--text-dark);
  background-color: white;
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}

/* Page wrapper */
.page-wrap {
  max-width: 1000px;
  margin: 2rem auto;
  padding: 1rem;
  color: var(--text-dark);
  font-family: var(--font-stack);
}

/* Big tile grid on homepage */
.tile-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(240px,100%),1fr));
  gap: var(--gap-lg);
  margin-top: var(--gap-xl);
  margin-bottom: var(--gap-xl);
}

.class-tile {
  background: linear-gradient(135deg, var(--accent-blue) 0%, var(--accent-blue-dark) 100%);
  color: #fff;
  border-radius: var(--radius-card);
  padding: 1.25rem 1rem;
  text-decoration: none;
  box-shadow: var(--shadow-card);
  display: block;
}

.class-tile h2 {
  font-size: 1.1rem;
  margin: 0 0 0.5rem 0;
  font-weight: 600;
  color: #fff;
}

.class-tile p {
  margin: 0;
  font-size: 0.9rem;
  color: rgba(255,255,255,0.9);
  line-height: 1.4;
}

/* Divider */
hr.clean-line {
  margin:2rem 0;
  border:none;
  border-top:1px solid rgba(0,0,0,0.1);
}

/* Quick links section */
.quick-links h3 {
  font-size:1.1rem;
  font-weight:600;
  margin-bottom:0.75rem;
}

.quick-links ul {
  list-style:disc;
  padding-left:1.25rem;
  line-height:1.5;
  font-size:1rem;
}
</style>

<main class="page-wrap">

  <h1 style="font-size:1.5rem; font-weight:600; line-height:1.2; margin-bottom:0.5rem;">
    Welcome 👋
  </h1>

  <p style="font-size:1rem; line-height:1.5; margin-bottom:1.5rem;">
    This site is for students of Berwickshire High School.<br />
    Choose your class below to get notes, videos, OneDrive resources, and homework.
  </p>

  <div class="tile-grid">

    <a class="class-tile" href="/classes/s1-science.html">
      <h2>S1 Science</h2>
      <p>Topics, notes, revision videos, and homework.</p>
    </a>

    <a class="class-tile" href="/classes/s2-science.html">
      <h2>S2 Science</h2>
      <p>Resources and tasks for S2.</p>
    </a>

    <a class="class-tile" href="/classes/s3-n5-physics.html">
      <h2>S3 / National 5 Physics</h2>
      <p>Course notes, past papers, required formulas.</p>
    </a>

    <a class="class-tile" href="/classes/higher-physics.html">
      <h2>Higher Physics</h2>
      <p>Lesson slides, practice questions, videos.</p>
    </a>

    <a class="class-tile" href="/classes/adv-higher-physics.html">
      <h2>Advanced Higher Physics</h2>
      <p>AH notes, investigations, prep for assessments.</p>
    </a>

    <a class="class-tile" href="/classes/engineering-science.html">
      <h2>Engineering Science</h2>
      <p>Circuits, mechanics, control systems, assignments.</p>
    </a>

    <a class="class-tile" href="/classes/practical-electronics.html">
      <h2>Practical Electronics</h2>
      <p>Build guides, circuit diagrams, component lists.</p>
    </a>

  </div>


  <hr class="clean-line"/>

  <section class="quick-links">
    <h3>Quick Links</h3>
    <ul>
      <li><a href="/quick-links">Revision / Study Links</a></li>
      <li><a href="/contact">Contact / Support</a></li>
    </ul>
  </section>

</main>
