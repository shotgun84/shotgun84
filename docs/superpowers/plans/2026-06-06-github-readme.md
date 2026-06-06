# GitHub Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a dark cyberpunk HUD-themed GitHub profile README (`README.md`) plus a custom SVG hero banner (`assets/hero-banner.svg`) for user @shotgun84.

**Architecture:** A single `README.md` file using GitHub-flavored Markdown with embedded HTML tables, external image references (shields.io badges, GitHub stats cards), and a custom SVG banner. No build step required — GitHub renders it directly.

**Tech Stack:** Markdown, HTML tables, SVG, shields.io, github-readme-stats, github-readme-streak-stats

---

## File Structure

```
shotgun84/
├── README.md                  # Main profile README (OVERWRITE existing)
└── assets/
    └── hero-banner.svg        # Custom SVG hero banner
```

---

## Prerequisites

- GitHub username: `shotgun84`
- Portfolio: `https://owaisimran.me`
- Email: `imranowaisofficial@gmail.com`
- Phone: `+971 52 226 3081`

---

## Task 1: Create Assets Directory

**Files:**
- Create directory: `assets/`

- [ ] **Step 1: Create the assets directory**

```bash
mkdir -p assets
```

- [ ] **Step 2: Commit directory placeholder**

```bash
git add assets/ && git commit -m "chore: create assets directory for README graphics"
```

---

## Task 2: Build the Hero Banner SVG

**Files:**
- Create: `assets/hero-banner.svg`

- [ ] **Step 1: Write the SVG file**

Create `assets/hero-banner.svg` with the following content:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 300" width="1200" height="300">
  <defs>
    <linearGradient id="bgGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" stop-color="#0d1117"/>
      <stop offset="100%" stop-color="#161b22"/>
    </linearGradient>
    <filter id="glow" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="4" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
    <pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse">
      <path d="M 40 0 L 0 0 0 40" fill="none" stroke="#21262d" stroke-width="0.5" opacity="0.4"/>
    </pattern>
    <linearGradient id="cyanGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#00f0ff"/>
      <stop offset="100%" stop-color="#7c3aed"/>
    </linearGradient>
  </defs>

  <!-- Background -->
  <rect width="1200" height="300" fill="url(#bgGrad)"/>
  <rect width="1200" height="300" fill="url(#grid)"/>

  <!-- Decorative corner brackets -->
  <path d="M 40 40 L 40 70 L 70 70" fill="none" stroke="#00f0ff" stroke-width="2" opacity="0.8"/>
  <path d="M 1160 40 L 1160 70 L 1130 70" fill="none" stroke="#00f0ff" stroke-width="2" opacity="0.8"/>
  <path d="M 40 260 L 40 230 L 70 230" fill="none" stroke="#ff00a0" stroke-width="2" opacity="0.8"/>
  <path d="M 1160 260 L 1160 230 L 1130 230" fill="none" stroke="#ff00a0" stroke-width="2" opacity="0.8"/>

  <!-- Scan lines -->
  <line x1="200" y1="120" x2="400" y2="120" stroke="#ff00a0" stroke-width="1" opacity="0.6"/>
  <line x1="800" y1="180" x2="1000" y2="180" stroke="#00f0ff" stroke-width="1" opacity="0.6"/>

  <!-- HUD data readout lines -->
  <text x="80" y="90" font-family="monospace" font-size="10" fill="#8b949e" opacity="0.7">SYS.INIT</text>
  <text x="80" y="105" font-family="monospace" font-size="10" fill="#8b949e" opacity="0.7">STATUS: ONLINE</text>
  <text x="1020" y="90" font-family="monospace" font-size="10" fill="#8b949e" opacity="0.7">ID: SHOTGUN84</text>
  <text x="1020" y="105" font-family="monospace" font-size="10" fill="#8b949e" opacity="0.7">SEC_LEVEL: HIGH</text>

  <!-- Main name -->
  <text x="600" y="145" font-family="system-ui, -apple-system, sans-serif" font-size="64" font-weight="800" fill="#00f0ff" text-anchor="middle" filter="url(#glow)" letter-spacing="4">OWAIS IMRAN</text>

  <!-- Subtitle -->
  <text x="600" y="185" font-family="system-ui, -apple-system, sans-serif" font-size="18" font-weight="400" fill="#e6edf3" text-anchor="middle" letter-spacing="6">AI SYSTEMS ENGINEER — WITH A SECURITY LENS</text>

  <!-- Decorative bottom line -->
  <line x1="350" y1="220" x2="850" y2="220" stroke="url(#cyanGrad)" stroke-width="1" opacity="0.5"/>
  <circle cx="600" cy="220" r="3" fill="#ff00a0"/>
</svg>
```

- [ ] **Step 2: Verify SVG renders**

Open the SVG in a browser or image viewer to confirm it displays correctly with the dark background, grid, neon text, and corner brackets.

- [ ] **Step 3: Commit**

```bash
git add assets/hero-banner.svg
git commit -m "feat: add cyberpunk hero banner SVG"
```

---

## Task 3: Write the README.md — Header & Identity

**Files:**
- Overwrite: `README.md`

- [ ] **Step 1: Write the top of README.md**

```markdown
<!-- Hero Banner -->
<p align="center">
  <img src="./assets/hero-banner.svg" alt="Owais Imran — AI Systems Engineer" width="100%">
</p>

<!-- Tagline -->
<p align="center">
  <i>Pre-training LLMs, building ML pipelines, and studying how these systems break.</i>
</p>

<br>
```

- [ ] **Step 2: Commit**

```bash
git add README.md && git commit -m "feat: add hero banner and tagline"
```

---

## Task 4: Write the README.md — Status Bar

**Files:**
- Modify: `README.md` (append)

- [ ] **Step 1: Append status bar section**

Add this to `README.md`:

```markdown
<!-- Status Bar -->
<p align="center">
  <a href="https://owaisimran.me">
    <img src="https://img.shields.io/badge/Portfolio-owaisimran.me-ff00a0?style=for-the-badge&logo=google-chrome&logoColor=white&labelColor=0d1117" alt="Portfolio">
  </a>
  <img src="https://img.shields.io/badge/Location-Dubai,_UAE-00f0ff?style=for-the-badge&logo=google-maps&logoColor=white&labelColor=0d1117" alt="Location">
  <img src="https://img.shields.io/badge/Focus-AI_Security_+_LLM_Systems-7c3aed?style=for-the-badge&logo=openai&logoColor=white&labelColor=0d1117" alt="Focus">
</p>

<br>
```

- [ ] **Step 2: Commit**

```bash
git add README.md && git commit -m "feat: add status badge bar"
```

---

## Task 5: Write the README.md — Experience & Projects Grid

**Files:**
- Modify: `README.md` (append)

- [ ] **Step 1: Append experience and projects section**

Add this to `README.md`:

```markdown
<!-- Experience & Projects -->
<h2 align="center">
  <img src="https://img.shields.io/badge/◈_CURRENTLY_BUILDING-00f0ff?style=flat-square&labelColor=0d1117" alt="">
</h2>

<table align="center" width="100%">
  <tr>
    <td width="33%" valign="top">
      <h3 align="center">🤖 AI Trading Bot</h3>
      <p align="center">
        <sub>Yahoo Finance + LLM trading signals. Early-stage experimentation with financial time-series and reasoning models.</sub>
      </p>
      <p align="center">
        <img src="https://img.shields.io/badge/python-00f0ff?style=flat-square&logo=python&logoColor=white&labelColor=0d1117" alt="Python">
        <img src="https://img.shields.io/badge/yfinance-ff00a0?style=flat-square&logo=yahoo&logoColor=white&labelColor=0d1117" alt="yfinance">
        <img src="https://img.shields.io/badge/OpenAI-7c3aed?style=flat-square&logo=openai&logoColor=white&labelColor=0d1117" alt="OpenAI">
      </p>
    </td>
    <td width="33%" valign="top">
      <h3 align="center">🌍 Disaster Monitor</h3>
      <p align="center">
        <sub>Global real-time disaster dashboard. Aggregates NASA EONET, USGS, GDACS, and OpenWeather data.</sub>
      </p>
      <p align="center">
        <img src="https://img.shields.io/badge/react-00f0ff?style=flat-square&logo=react&logoColor=white&labelColor=0d1117" alt="React">
        <img src="https://img.shields.io/badge/vercel-ff00a0?style=flat-square&logo=vercel&logoColor=white&labelColor=0d1117" alt="Vercel">
        <img src="https://img.shields.io/badge/APIs-7c3aed?style=flat-square&logo=fastapi&logoColor=white&labelColor=0d1117" alt="APIs">
      </p>
    </td>
    <td width="33%" valign="top">
      <h3 align="center">🔐 LLM Security Research</h3>
      <p align="center">
        <sub>Studying how LLM systems break. Pre-training experiments, adversarial testing, and red-teaming AI pipelines.</sub>
      </p>
      <p align="center">
        <img src="https://img.shields.io/badge/PyTorch-00f0ff?style=flat-square&logo=pytorch&logoColor=white&labelColor=0d1117" alt="PyTorch">
        <img src="https://img.shields.io/badge/OpenAI-ff00a0?style=flat-square&logo=openai&logoColor=white&labelColor=0d1117" alt="OpenAI">
        <img src="https://img.shields.io/badge/ML-7c3aed?style=flat-square&logo=scikitlearn&logoColor=white&labelColor=0d1117" alt="ML">
      </p>
    </td>
  </tr>
</table>

<br>

<!-- Past Experience -->
<p align="center">
  <sub><b>Past:</b> AI Voice Agent @ KaiDubai (Jun 2025 – Jan 2026) — Built cold-calling lead qualification system using ElevenLabs + OpenAI LLMs.</sub>
</p>

<br>
```

- [ ] **Step 2: Commit**

```bash
git add README.md && git commit -m "feat: add projects grid and experience"
```

---

## Task 6: Write the README.md — Tech Arsenal Badges

**Files:**
- Modify: `README.md` (append)

- [ ] **Step 1: Append tech arsenal section**

Add this to `README.md`:

```markdown
<!-- Tech Arsenal -->
<h2 align="center">
  <img src="https://img.shields.io/badge/◈_TECH_ARSENAL-ff00a0?style=flat-square&labelColor=0d1117" alt="">
</h2>

<p align="center">
  <b>Languages</b><br>
  <img src="https://img.shields.io/badge/Python-00f0ff?style=for-the-badge&logo=python&logoColor=white&labelColor=0d1117" alt="Python">
  <img src="https://img.shields.io/badge/JavaScript-ff00a0?style=for-the-badge&logo=javascript&logoColor=white&labelColor=0d1117" alt="JavaScript">
  <img src="https://img.shields.io/badge/TypeScript-7c3aed?style=for-the-badge&logo=typescript&logoColor=white&labelColor=0d1117" alt="TypeScript">
  <img src="https://img.shields.io/badge/HTML/CSS-e6edf3?style=for-the-badge&logo=html5&logoColor=white&labelColor=0d1117" alt="HTML/CSS">
</p>

<p align="center">
  <b>AI / ML</b><br>
  <img src="https://img.shields.io/badge/OpenAI-00f0ff?style=for-the-badge&logo=openai&logoColor=white&labelColor=0d1117" alt="OpenAI">
  <img src="https://img.shields.io/badge/ElevenLabs-ff00a0?style=for-the-badge&logo=elevenlabs&logoColor=white&labelColor=0d1117" alt="ElevenLabs">
  <img src="https://img.shields.io/badge/LangChain-7c3aed?style=for-the-badge&logo=langchain&logoColor=white&labelColor=0d1117" alt="LangChain">
  <img src="https://img.shields.io/badge/PyTorch-e6edf3?style=for-the-badge&logo=pytorch&logoColor=white&labelColor=0d1117" alt="PyTorch">
</p>

<p align="center">
  <b>Frontend</b><br>
  <img src="https://img.shields.io/badge/React-00f0ff?style=for-the-badge&logo=react&logoColor=white&labelColor=0d1117" alt="React">
  <img src="https://img.shields.io/badge/Next.js-ff00a0?style=for-the-badge&logo=nextdotjs&logoColor=white&labelColor=0d1117" alt="Next.js">
  <img src="https://img.shields.io/badge/Tailwind_CSS-7c3aed?style=for-the-badge&logo=tailwindcss&logoColor=white&labelColor=0d1117" alt="Tailwind CSS">
</p>

<p align="center">
  <b>Backend / Deploy</b><br>
  <img src="https://img.shields.io/badge/Vercel-00f0ff?style=for-the-badge&logo=vercel&logoColor=white&labelColor=0d1117" alt="Vercel">
  <img src="https://img.shields.io/badge/Node.js-ff00a0?style=for-the-badge&logo=nodedotjs&logoColor=white&labelColor=0d1117" alt="Node.js">
  <img src="https://img.shields.io/badge/FastAPI-7c3aed?style=for-the-badge&logo=fastapi&logoColor=white&labelColor=0d1117" alt="FastAPI">
</p>

<p align="center">
  <b>Data / Finance</b><br>
  <img src="https://img.shields.io/badge/yfinance-00f0ff?style=for-the-badge&logo=yahoo&logoColor=white&labelColor=0d1117" alt="yfinance">
  <img src="https://img.shields.io/badge/Pandas-ff00a0?style=for-the-badge&logo=pandas&logoColor=white&labelColor=0d1117" alt="Pandas">
  <img src="https://img.shields.io/badge/NumPy-7c3aed?style=for-the-badge&logo=numpy&logoColor=white&labelColor=0d1117" alt="NumPy">
  <img src="https://img.shields.io/badge/REST_APIs-e6edf3?style=for-the-badge&logo=postman&logoColor=white&labelColor=0d1117" alt="REST APIs">
</p>

<br>
```

- [ ] **Step 2: Commit**

```bash
git add README.md && git commit -m "feat: add tech arsenal badge matrix"
```

---

## Task 7: Write the README.md — GitHub Stats Grid

**Files:**
- Modify: `README.md` (append)

- [ ] **Step 1: Append GitHub stats section**

Add this to `README.md`:

```markdown
<!-- System Stats -->
<h2 align="center">
  <img src="https://img.shields.io/badge/◈_SYSTEM_STATS-7c3aed?style=flat-square&labelColor=0d1117" alt="">
</h2>

<table align="center" width="100%">
  <tr>
    <td width="50%" align="center">
      <img src="https://github-readme-stats.vercel.app/api?username=shotgun84&theme=dark&hide_border=true&title_color=00f0ff&icon_color=ff00a0&text_color=e6edf3&bg_color=0d1117&show_icons=true&rank_icon=github" alt="GitHub Stats" width="100%">
    </td>
    <td width="50%" align="center">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=shotgun84&theme=dark&hide_border=true&stroke=00f0ff&ring=ff00a0&fire=ff00a0&currStreakNum=00f0ff&sideNums=e6edf3&currStreakLabel=8b949e&sideLabels=8b949e&dates=8b949e&background=0d1117" alt="GitHub Streak" width="100%">
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=shotgun84&theme=dark&hide_border=true&title_color=00f0ff&text_color=e6edf3&bg_color=0d1117&layout=compact&langs_count=8" alt="Top Languages" width="100%">
    </td>
    <td width="50%" align="center">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=shotgun84&theme=github-compact&hide_border=true&bg_color=0d1117&color=00f0ff&line=ff00a0&point=e6edf3&area=true&area_color=ff00a020" alt="Contribution Graph" width="100%">
    </td>
  </tr>
</table>

<br>
```

- [ ] **Step 2: Commit**

```bash
git add README.md && git commit -m "feat: add GitHub stats dashboard grid"
```

---

## Task 8: Write the README.md — Contact & Footer

**Files:**
- Modify: `README.md` (append)

- [ ] **Step 1: Append contact and footer section**

Add this to `README.md`:

```markdown
<!-- Contact / Uplink -->
<h2 align="center">
  <img src="https://img.shields.io/badge/◈_UPLINK-00f0ff?style=flat-square&labelColor=0d1117" alt="">
</h2>

<p align="center">
  <img src="https://img.shields.io/badge/📧_imranowaisofficial@gmail.com-ff00a0?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0d1117" alt="Email">
</p>
<p align="center">
  <a href="https://owaisimran.me">
    <img src="https://img.shields.io/badge/🌐_owaisimran.me-00f0ff?style=for-the-badge&logo=google-chrome&logoColor=white&labelColor=0d1117" alt="Portfolio">
  </a>
  <a href="https://linkedin.com/in/owais-imran">
    <img src="https://img.shields.io/badge/💼_LinkedIn-7c3aed?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0d1117" alt="LinkedIn">
  </a>
  <a href="https://wa.me/971522263081">
    <img src="https://img.shields.io/badge/📱_+971_52_226_3081-e6edf3?style=for-the-badge&logo=whatsapp&logoColor=white&labelColor=0d1117" alt="WhatsApp">
  </a>
</p>

<br>

<!-- Footer -->
<p align="center">
  <img src="https://img.shields.io/badge/SYSTEM_ONLINE-00f0ff?style=flat-square&labelColor=0d1117" alt="">
  <img src="https://img.shields.io/badge/ALWAYS_BUILDING-ff00a0?style=flat-square&labelColor=0d1117" alt="">
</p>

<p align="center">
  <sub><i>System online. Always building.</i></sub>
</p>
```

- [ ] **Step 2: Commit**

```bash
git add README.md && git commit -m "feat: add contact section and footer"
```

---

## Task 9: Final Verification

**Files:**
- Read: `README.md` (full file)
- Read: `assets/hero-banner.svg`

- [ ] **Step 1: Verify README structure**

```bash
wc -l README.md
```

Expected: ~180-220 lines.

- [ ] **Step 2: Verify SVG exists**

```bash
ls -la assets/hero-banner.svg
```

Expected: File exists, non-zero size.

- [ ] **Step 3: Preview README in Markdown renderer**

Open `README.md` in any Markdown preview tool (VS Code preview, GitHub file view after push, etc.) and confirm:
- [ ] Hero banner image reference points to `./assets/hero-banner.svg`
- [ ] All shields.io badges render with dark background + neon text
- [ ] GitHub stats cards use correct username (`shotgun84`)
- [ ] All 4 stats cards load (stats, streak, languages, activity graph)
- [ ] Project grid has 3 columns
- [ ] Contact badges are clickable links
- [ ] No broken image references

- [ ] **Step 4: Final commit**

```bash
git add README.md assets/
git commit -m "feat: complete cyberpunk HUD GitHub profile README"
```

---

## Self-Review Checklist

**Spec coverage:**
- [x] Hero banner SVG with neon glow — Task 2
- [x] Identity: name, title, tagline — Task 3
- [x] Status bar with portfolio/location/focus — Task 4
- [x] Project grid (3 cards) — Task 5
- [x] Past experience (KaiDubai, no Vapi) — Task 5
- [x] Tech arsenal badge matrix — Task 6
- [x] GitHub stats 2×2 grid — Task 7
- [x] Contact section (email, portfolio, LinkedIn, WhatsApp) — Task 8
- [x] Footer — Task 8

**Placeholder scan:**
- [x] No TBD/TODO/fill-in-later found
- [x] All URLs are concrete
- [x] All code blocks contain real code

**Type consistency:**
- [x] Username `shotgun84` consistent across all stats URLs
- [x] Color hex codes consistent with spec
- [x] Badge style (`for-the-badge` vs `flat-square`) used appropriately
