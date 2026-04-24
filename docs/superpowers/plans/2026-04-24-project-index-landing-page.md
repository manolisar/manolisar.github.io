# Project Index Landing Page Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the current static project index with a light-first nautical chart and instrument desk landing page for Fuel Master, Voyage Planner, Voyage Tracker v7, and legacy Voyage Tracker v6.

**Architecture:** Keep the site as one static `index.html` file in `manolisar.github.io`. Use semantic HTML, CSS custom properties for light/dark themes, and a small inline script for theme persistence and reveal behavior.

**Tech Stack:** Static HTML, CSS, vanilla JavaScript, GitHub Pages paths.

---

## File Structure

- Modify: `index.html`
  - Owns all page markup, styling, theme variables, responsive behavior, link targets, and the small script for theme persistence.
- No new build files, package files, or asset files are required.
- Do not commit `.superpowers/`, `.claude/`, `5BladeProp.jpg`, or `5BladeProp1.jpg`; those are existing untracked local files or brainstorming artifacts.

## Task 1: Replace The Static Page

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Replace the current HTML document**

Replace `index.html` with a complete static document that includes:

```html
<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Marine Engineering Tools</title>
  <meta name="description" content="Marine engineering tools for fuel conversion, voyage planning, and voyage fuel tracking.">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@500;600;700&family=Newsreader:opsz,wght@6..72,600;6..72,700&family=Source+Sans+3:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    /* Paste the CSS from Step 2 here before saving the file. */
  </style>
</head>
<body>
  <nav class="site-nav" aria-label="Primary navigation">
    <a class="brand" href="#top" aria-label="Marine Engineering Tools home">
      <span class="brand-mark" aria-hidden="true"></span>
      <span>
        <strong>Marine Engineering</strong>
        <small>Fuel · Voyage · Tracking</small>
      </span>
    </a>
    <div class="nav-actions">
      <a href="#tools">Tools</a>
      <a href="https://github.com/manolisar" target="_blank" rel="noopener">GitHub</a>
      <button class="theme-toggle" type="button" aria-label="Switch to dark theme" aria-pressed="false">
        <span class="theme-icon" aria-hidden="true"></span>
        <span class="theme-text">Dark</span>
      </button>
    </div>
  </nav>

  <main id="top">
    <section class="hero" aria-labelledby="hero-title">
      <div class="hero-copy">
        <p class="eyebrow">Engine Room Index</p>
        <h1 id="hero-title">Plan the leg.<br>Measure the burn.</h1>
        <p class="hero-lede">A light-first launch index for shipboard fuel and voyage tools: conversion, planning, active tracking, and a legacy path for older workflows.</p>
      </div>
      <aside class="instrument-panel" aria-label="Operational snapshot">
        <p class="panel-label">Operational Snapshot</p>
        <div class="route-line" aria-hidden="true"></div>
        <div class="gauge" aria-hidden="true"></div>
        <div class="metric-grid">
          <div><span>Fuel</span><strong>VCF</strong></div>
          <div><span>Route</span><strong>NM</strong></div>
          <div><span>Track</span><strong>MT</strong></div>
        </div>
      </aside>
    </section>

    <section class="tools" id="tools" aria-labelledby="tools-title">
      <div class="section-head">
        <p class="eyebrow">Project Registry</p>
        <h2 id="tools-title">The Toolkit</h2>
        <p>The first three cards are current tools. Voyage Tracker v6 is retained as a visually quieter legacy link.</p>
      </div>
      <div class="tool-grid">
        <a class="tool-card" href="/FuelMaster/">
          <span class="tool-number">01</span>
          <span class="tool-tag">Conversion</span>
          <h3>Fuel Master</h3>
          <p>Marine fuel mass-to-volume conversion using density at 15°C and observed bunkering temperature.</p>
          <span class="launch-label">Launch App</span>
        </a>
        <a class="tool-card" href="/voyage-planner/">
          <span class="tool-number">02</span>
          <span class="tool-tag">Planning</span>
          <h3>Voyage Planner</h3>
          <p>Speed, power, generator load, sea leg, port, and standby consumption planning.</p>
          <span class="launch-label">Launch App</span>
        </a>
        <a class="tool-card" href="/voyage-tracker-v7/">
          <span class="tool-number">03</span>
          <span class="tool-tag">Tracking · v7</span>
          <h3>Voyage Tracker v7</h3>
          <p>Current local-folder voyage fuel tracking with report forms, counter readings, and offline-first storage.</p>
          <span class="launch-label">Launch App</span>
        </a>
        <a class="tool-card legacy" href="/VoyageTracker/">
          <span class="tool-number">04</span>
          <span class="tool-tag">Tracking · legacy</span>
          <h3>Voyage Tracker v6</h3>
          <p>Legacy tracker retained for older workflows and reference access.</p>
          <span class="launch-label">Legacy Link</span>
        </a>
      </div>
    </section>
  </main>

  <footer class="site-footer">
    <p>Marine Engineering Tools</p>
    <a href="https://github.com/manolisar" target="_blank" rel="noopener">manolisar / dev</a>
  </footer>

  <script>
    /* Paste the theme persistence script from Step 3 here before saving the file. */
  </script>
</body>
</html>
```

- [ ] **Step 2: Add complete CSS in the existing `<style>` block**

Implement these required CSS groups in `index.html`:

```css
:root {
  --bg: #edf7f5;
  --bg-strong: #dcefeb;
  --panel: rgba(255, 255, 255, 0.66);
  --panel-solid: #ffffff;
  --text: #102f39;
  --muted: rgba(16, 47, 57, 0.68);
  --faint: rgba(16, 47, 57, 0.44);
  --line: rgba(16, 47, 57, 0.14);
  --teal: #0a767f;
  --teal-soft: rgba(10, 118, 127, 0.12);
  --signal: #d66338;
  --signal-soft: rgba(214, 99, 56, 0.12);
  --shadow: 0 24px 70px rgba(17, 47, 59, 0.12);
  --grid-line: rgba(17, 47, 59, 0.055);
  color-scheme: light;
}

:root[data-theme="dark"] {
  --bg: #071a22;
  --bg-strong: #0c242d;
  --panel: rgba(15, 43, 53, 0.72);
  --panel-solid: #102b35;
  --text: #e8f3ef;
  --muted: rgba(232, 243, 239, 0.72);
  --faint: rgba(232, 243, 239, 0.46);
  --line: rgba(232, 243, 239, 0.16);
  --teal: #42b9bd;
  --teal-soft: rgba(66, 185, 189, 0.16);
  --signal: #ff8a5c;
  --signal-soft: rgba(255, 138, 92, 0.14);
  --shadow: 0 24px 70px rgba(0, 0, 0, 0.34);
  --grid-line: rgba(232, 243, 239, 0.055);
  color-scheme: dark;
}
```

Then add these page styles after the theme variables:

```css
body {
  min-height: 100vh;
  margin: 0;
  font-family: "Source Sans 3", sans-serif;
  color: var(--text);
  background:
    linear-gradient(var(--grid-line) 1px, transparent 1px),
    linear-gradient(90deg, var(--grid-line) 1px, transparent 1px),
    radial-gradient(circle at 85% 8%, var(--teal-soft), transparent 32rem),
    linear-gradient(135deg, var(--bg), var(--bg-strong));
  background-size: 28px 28px, 28px 28px, auto, auto;
}

*, *::before, *::after {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

a {
  color: inherit;
}

.site-nav {
  position: sticky;
  top: 0;
  z-index: 20;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1.5rem;
  min-height: 4.75rem;
  padding: 0 clamp(1rem, 4vw, 3rem);
  border-bottom: 1px solid var(--line);
  background: color-mix(in srgb, var(--bg) 82%, transparent);
  backdrop-filter: blur(18px);
}

.brand {
  display: inline-flex;
  align-items: center;
  gap: 0.8rem;
  text-decoration: none;
}

.brand-mark {
  width: 2.15rem;
  height: 2.15rem;
  border: 1px solid var(--line);
  border-radius: 50%;
  background:
    radial-gradient(circle at center, var(--signal) 0 12%, transparent 13%),
    conic-gradient(from 220deg, var(--teal) 0 34%, var(--signal) 34% 48%, transparent 48% 100%);
}

.brand strong,
.brand small,
.nav-actions a,
.theme-toggle,
.eyebrow,
.panel-label,
.tool-tag,
.launch-label,
.site-footer {
  font-family: "IBM Plex Mono", monospace;
  letter-spacing: 0.14em;
  text-transform: uppercase;
}

.brand strong {
  display: block;
  font-size: 0.78rem;
  color: var(--text);
}

.brand small {
  display: block;
  margin-top: 0.2rem;
  font-size: 0.58rem;
  color: var(--faint);
}

.nav-actions {
  display: flex;
  align-items: center;
  gap: clamp(0.8rem, 2vw, 1.8rem);
}

.nav-actions a {
  font-size: 0.64rem;
  font-weight: 700;
  color: var(--muted);
  text-decoration: none;
}

.theme-toggle {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  min-height: 2.25rem;
  padding: 0 0.8rem;
  border: 1px solid var(--line);
  border-radius: 999px;
  color: var(--text);
  background: var(--panel);
  cursor: pointer;
}

.theme-icon {
  width: 0.65rem;
  height: 0.65rem;
  border-radius: 50%;
  background: var(--signal);
  box-shadow: 0 0 0 0.28rem var(--signal-soft);
}

main {
  overflow: hidden;
}

.hero {
  min-height: calc(100vh - 4.75rem);
  display: grid;
  grid-template-columns: minmax(0, 1.08fr) minmax(18rem, 0.92fr);
  align-items: center;
  gap: clamp(2rem, 5vw, 4.5rem);
  padding: clamp(4rem, 8vw, 7rem) clamp(1rem, 4vw, 3rem) clamp(2.5rem, 6vw, 5rem);
  max-width: 78rem;
  margin: 0 auto;
}

.eyebrow,
.panel-label,
.tool-tag {
  margin: 0 0 1rem;
  font-size: 0.68rem;
  font-weight: 700;
  color: var(--signal);
}

.hero h1,
.section-head h2 {
  margin: 0;
  font-family: "Newsreader", Georgia, serif;
  font-weight: 700;
  letter-spacing: -0.055em;
  color: var(--text);
}

.hero h1 {
  max-width: 11ch;
  font-size: clamp(4rem, 10vw, 8.7rem);
  line-height: 0.84;
}

.hero-lede {
  max-width: 37rem;
  margin: 1.5rem 0 0;
  font-size: clamp(1rem, 1.55vw, 1.2rem);
  line-height: 1.7;
  color: var(--muted);
}

.instrument-panel {
  min-height: 24rem;
  position: relative;
  overflow: hidden;
  padding: 1.4rem;
  border: 1px solid var(--line);
  border-radius: 1.35rem;
  background: var(--panel);
  box-shadow: var(--shadow);
  backdrop-filter: blur(14px);
}

.instrument-panel::before {
  content: "";
  position: absolute;
  inset: 0;
  background:
    linear-gradient(var(--grid-line) 1px, transparent 1px),
    linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
  background-size: 1.4rem 1.4rem;
}

.route-line {
  position: absolute;
  left: 8%;
  right: 10%;
  top: 34%;
  height: 6rem;
  border-top: 2px dashed color-mix(in srgb, var(--teal) 48%, transparent);
  border-right: 2px dashed color-mix(in srgb, var(--teal) 48%, transparent);
  border-radius: 0 5rem 0 0;
  transform: rotate(-7deg);
}

.route-line::after {
  content: "";
  position: absolute;
  right: -0.38rem;
  top: -0.38rem;
  width: 0.75rem;
  height: 0.75rem;
  border-radius: 50%;
  background: var(--signal);
}

.gauge {
  position: absolute;
  right: 12%;
  top: 23%;
  width: 8.6rem;
  aspect-ratio: 1;
  border-radius: 50%;
  background: conic-gradient(from 220deg, var(--teal) 0 34%, var(--signal) 34% 52%, transparent 52% 100%);
  mask: radial-gradient(circle, transparent 47%, #000 48%);
}

.metric-grid {
  position: absolute;
  left: 1.4rem;
  right: 1.4rem;
  bottom: 1.4rem;
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 0.75rem;
}

.metric-grid div {
  min-width: 0;
  padding: 1rem;
  border: 1px solid var(--line);
  border-radius: 0.8rem;
  background: color-mix(in srgb, var(--panel-solid) 72%, transparent);
}

.metric-grid span {
  display: block;
  margin-bottom: 0.4rem;
  font-family: "IBM Plex Mono", monospace;
  font-size: 0.62rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--faint);
}

.metric-grid strong {
  font-family: "Newsreader", Georgia, serif;
  font-size: clamp(1.4rem, 3vw, 2.1rem);
  line-height: 1;
}

.tools {
  max-width: 78rem;
  margin: 0 auto;
  padding: 0 clamp(1rem, 4vw, 3rem) clamp(4rem, 8vw, 7rem);
}

.section-head {
  display: grid;
  grid-template-columns: minmax(0, 1fr) minmax(18rem, 28rem);
  gap: 2rem;
  align-items: end;
  margin-bottom: 1.25rem;
}

.section-head h2 {
  font-size: clamp(2.8rem, 6vw, 5.4rem);
  line-height: 0.9;
}

.section-head > p:last-child {
  margin: 0;
  color: var(--muted);
  line-height: 1.55;
}

.tool-grid {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  border: 1px solid var(--line);
  border-radius: 1.3rem;
  overflow: hidden;
  background: var(--panel);
  box-shadow: var(--shadow);
}

.tool-card {
  min-height: 19rem;
  position: relative;
  display: flex;
  flex-direction: column;
  padding: 1.35rem;
  border-right: 1px solid var(--line);
  color: var(--text);
  text-decoration: none;
  background: color-mix(in srgb, var(--panel-solid) 54%, transparent);
  transition: transform 180ms ease, background-color 180ms ease;
}

.tool-card:last-child {
  border-right: 0;
}

.tool-card:hover {
  background: color-mix(in srgb, var(--teal-soft) 72%, var(--panel-solid));
}

.tool-card.legacy {
  background:
    repeating-linear-gradient(-45deg, transparent 0 0.7rem, color-mix(in srgb, var(--text) 4%, transparent) 0.7rem 1.4rem),
    color-mix(in srgb, var(--panel-solid) 44%, transparent);
}

.tool-number {
  margin-bottom: 1.5rem;
  font-family: "Newsreader", Georgia, serif;
  font-size: 2.9rem;
  font-weight: 700;
  line-height: 1;
  color: var(--faint);
}

.tool-card h3 {
  margin: 0 0 0.7rem;
  font-size: clamp(1.3rem, 2vw, 1.55rem);
  line-height: 1.05;
}

.tool-card p {
  margin: 0 0 2rem;
  color: var(--muted);
  line-height: 1.55;
}

.launch-label {
  margin-top: auto;
  font-size: 0.65rem;
  font-weight: 700;
  color: var(--signal);
}

.site-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  padding: 1.5rem clamp(1rem, 4vw, 3rem);
  border-top: 1px solid var(--line);
  color: var(--faint);
  font-size: 0.62rem;
}

.site-footer p {
  margin: 0;
}

.site-footer a {
  color: var(--muted);
  text-decoration: none;
}

:focus-visible {
  outline: 3px solid var(--signal);
  outline-offset: 4px;
}

@media (max-width: 980px) {
  .hero,
  .section-head {
    grid-template-columns: 1fr;
  }

  .hero {
    min-height: auto;
  }

  .tool-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .tool-card {
    border-bottom: 1px solid var(--line);
  }

  .tool-card:nth-child(2n) {
    border-right: 0;
  }
}

@media (max-width: 680px) {
  .site-nav {
    min-height: 4.3rem;
  }

  .nav-actions a {
    display: none;
  }

  .hero {
    padding-top: 3rem;
  }

  .hero h1 {
    font-size: clamp(3.45rem, 18vw, 4.8rem);
  }

  .instrument-panel {
    min-height: 21rem;
  }

  .metric-grid,
  .tool-grid,
  .section-head {
    grid-template-columns: 1fr;
  }

  .tool-card {
    min-height: 15rem;
    border-right: 0;
  }

  .site-footer {
    align-items: flex-start;
    flex-direction: column;
  }
}

@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    scroll-behavior: auto !important;
    transition-duration: 0.01ms !important;
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
  }
}
```

- [ ] **Step 3: Add the theme script**

Add this script at the end of `body`:

```html
<script>
  const root = document.documentElement;
  const toggle = document.querySelector('.theme-toggle');
  const label = document.querySelector('.theme-text');
  const storageKey = 'marine-tools-theme';

  function applyTheme(theme) {
    const normalized = theme === 'dark' ? 'dark' : 'light';
    root.dataset.theme = normalized;
    const isDark = normalized === 'dark';
    toggle.setAttribute('aria-pressed', String(isDark));
    toggle.setAttribute('aria-label', isDark ? 'Switch to light theme' : 'Switch to dark theme');
    label.textContent = isDark ? 'Light' : 'Dark';
  }

  applyTheme(localStorage.getItem(storageKey) || 'light');

  toggle.addEventListener('click', () => {
    const next = root.dataset.theme === 'dark' ? 'light' : 'dark';
    localStorage.setItem(storageKey, next);
    applyTheme(next);
  });
</script>
```

- [ ] **Step 4: Commit the page replacement**

Run:

```bash
git add index.html
git commit -m "Redesign project index landing page"
```

Expected: only `index.html` is committed.

## Task 2: Verify Behavior In Browser

**Files:**
- Test: `index.html`

- [ ] **Step 1: Serve the static site locally**

Run:

```bash
python3 -m http.server 4173
```

Expected: local server starts for `http://localhost:4173/`.

- [ ] **Step 2: Verify visual layout**

Open `http://localhost:4173/` in the in-app browser and check:

- The page defaults to the light theme.
- The first viewport shows the hero and a visible hint of the tools section.
- The active cards are visually primary.
- The v6 card is visually quieter and marked as legacy.
- The footer credit reads `manolisar / dev` and is discreet.

- [ ] **Step 3: Verify links**

Inspect or click-check these link targets:

```text
/FuelMaster/
/voyage-planner/
/voyage-tracker-v7/
/VoyageTracker/
https://github.com/manolisar
```

Expected: all anchor `href` values match exactly.

- [ ] **Step 4: Verify theme persistence**

In the browser:

1. Click the theme toggle.
2. Confirm the page changes to dark theme and the button text changes to `Light`.
3. Reload the page.
4. Confirm dark theme persists.
5. Click the toggle again.
6. Confirm light theme returns and the button text changes to `Dark`.

- [ ] **Step 5: Verify responsive layouts**

Check at these viewport widths:

- Desktop: 1440px wide
- Tablet: 834px wide
- Mobile: 390px wide

Expected:

- No text overlaps.
- No horizontal scrolling.
- Cards are four columns on wide desktop, two columns on tablet, one column on mobile.
- Navigation remains usable on mobile.

- [ ] **Step 6: Verify keyboard focus**

Use Tab navigation.

Expected:

- Brand link, nav links, theme toggle, tool cards, and footer credit receive visible focus outlines.
- The theme toggle works with keyboard activation.

- [ ] **Step 7: Commit any verification fixes**

If verification requires CSS or markup fixes, run:

```bash
git add index.html
git commit -m "Polish project index responsiveness"
```

Expected: only `index.html` is committed.
