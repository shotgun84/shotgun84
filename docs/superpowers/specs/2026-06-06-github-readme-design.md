# GitHub Profile README — Design Spec

**Project:** `shotgun84/shotgun84` GitHub Profile README  
**Date:** 2026-06-06  
**Approach:** Cyberpunk HUD Dashboard  
**Aesthetic:** Dark, neon-accented, systems/dashboard-inspired  

---

## 1. Context & Goals

The user (Owais Imran, GitHub: @shotgun84) wants a visually striking GitHub profile README that replaces a basic existing header. The README should reflect his identity as an AI Systems Engineer with a security lens, showcase his work, and link to his portfolio (owaisimran.me). It must work within GitHub's Markdown rendering constraints (no custom CSS, no scripts, but SVGs, HTML tables, images, and badges are supported).

### Key Constraints

- GitHub sanitizes HTML — no `<style>` blocks, no inline `style` attributes, no JS.
- SVGs render but some advanced filters may not work in all contexts.
- External images must be served over HTTPS.
- Dark mode is the target viewing context (most devs use it).

---

## 2. Identity & Copy


| Field     | Value                                                                           |
| --------- | ------------------------------------------------------------------------------- |
| Full Name | Owais Imran                                                                     |
| Title     | AI Systems Engineer — with a security lens                                      |
| Tagline   | Pre-training LLMs, building ML pipelines, and studying how these systems break. |
| GitHub    | @shotgun84                                                                      |
| Portfolio | [owaisimran.me](https://owaisimran.me)                                          |
| Email     | [imranowaisofficial@gmail.com](mailto:imranowaisofficial@gmail.com)             |
| Phone     | +971 52 226 3081                                                                |
| LinkedIn  | `https://linkedin.com/in/owais-imran` (update if different)                     |
| WhatsApp  | +971 52 226 3081                                                                |


### Past Experience Note

- KaiDubai: Jun 2025 – Jan 2026 (AI Voice Agent project). Mentioned as **past experience**, not current. Do **not** mention Vapi. ElevenLabs may be kept if relevant.

---

## 3. Visual System

### Color Palette


| Role           | Hex        | Usage                                            |
| -------------- | ---------- | ------------------------------------------------ |
| Background     | `#0d1117`  | Deep space black, blends with GitHub dark mode   |
| Primary Neon   | `#00f0ff`  | Cyan — main highlights, borders, links, headings |
| Secondary Neon | `#ff00a0`  | Magenta — accents, AI tool badges, CTAs          |
| Tertiary Neon  | `#7c3aed`  | Electric violet — tertiary elements, gradients   |
| Grid/Border    | `#21262d`  | Subtle HUD panel borders, dividers               |
| Text Primary   | `#e6edf3`  | Bright white for headings, names                 |
| Text Secondary | `#8b949ed` | Muted gray for body, descriptions                |


### Typography

- GitHub's native system font stack for all body text (no custom web fonts possible).
- Hero name rendered via **custom SVG** with neon glow styling.
- Monospace (`code` blocks) used for "terminal" flavored sections.

### Visual Motifs

- **Grid lines** — subtle horizontal rules that evoke dashboard panels.
- **Glow effects** — achieved via SVG filters on the hero banner.
- **Pill badges** — shields.io badges with custom neon color styling.
- **Panel cards** — HTML tables used to create bordered content cells.

---

## 4. Section Architecture

### Section 1: Hero Banner (SVG Image)

- Full-width custom SVG.
- Background: dark gradient (`#0d1117` → `#161b22`) with subtle grid overlay.
- "OWAIS IMRAN" in large display text with cyan glow (`#00f0ff`).
- Horizontal scan line accents in magenta (`#ff00a0`).
- Small decorative HUD elements (corner brackets, data readout lines).
- Below the name, smaller text: *"AI Systems Engineer — with a security lens"*.
- Rendered as external SVG file referenced via `<img>` tag.

### Section 2: Identity / Tagline

- Plain Markdown below the hero.
- Italic tagline: *"Pre-training LLMs, building ML pipelines, and studying how these systems break."*
- Center-aligned using `<p align="center">`.

### Section 3: Status / Connect Bar

- Horizontal row of compact shields.io badges:
  - `Portfolio → owaisimran.me` (magenta badge, clickable)
  - `Location: Dubai, UAE` (cyan badge)
  - `Focus: AI Security + LLM Systems` (violet badge)
- Arranged in a single centered line.

### Section 4: Experience & Projects

- **Past Role:** KaiDubai AI Voice Agent (Jun 2025 – Jan 2026) — cold-calling lead qualification system using ElevenLabs + OpenAI LLMs. Brief 2-line mention.
- **Active Projects:** Shown in a 3-column HTML table (HUD panel style):


| AI Trading Bot                                                    | Disaster Monitor                                                                           | LLM Security Research                                                          |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| Yahoo Finance + LLM trading signals. Early-stage experimentation. | Global real-time disaster dashboard. NASA EONET, USGS, GDACS, OpenWeather. React + Vercel. | Studying how LLM systems break. Pre-training experiments, adversarial testing. |


- Each card has thin `#21262d` borders, title in cyan, description in muted gray.

### Section 5: Tech Arsenal (Badge Matrix)

- Category headers in bold cyan text.
- Shields.io badges organized by row:
  - **Languages:** Python, JavaScript, TypeScript, HTML/CSS
  - **AI/ML:** OpenAI, ElevenLabs, LangChain, PyTorch
  - **Frontend:** React, Next.js, Tailwind CSS
  - **Backend/Deploy:** Vercel, Node.js, FastAPI
  - **Data/Finance:** yfinance, Pandas, NumPy, REST APIs
- All badges use `for-the-badge` style with dark background and neon border styling via shields.io parameters.

### Section 6: System Stats (GitHub Metrics)

- 2×2 grid using HTML table:
  - Top-left: GitHub Stats Card (`github-readme-stats.vercel.app/api?username=shotgun84&theme=dark&hide_border=true&title_color=00f0ff&icon_color=ff00a0&text_color=e6edf3&bg_color=0d1117`)
  - Top-right: GitHub Streak Stats (`github-readme-streak-stats.herokuapp.com/?user=shotgun84&theme=dark&hide_border=true&stroke=00f0ff&ring=ff00a0&fire=ff00a0&currStreakNum=00f0ff&sideNums=e6edf3&currStreakLabel=8b949e&sideLabels=8b949e&dates=8b949e&background=0d1117`)
  - Bottom-left: Top Languages Card (`github-readme-stats.vercel.app/api/top-langs/?username=shotgun84&theme=dark&hide_border=true&title_color=00f0ff&text_color=e6edf3&bg_color=0d1117&layout=compact`)
  - Bottom-right: GitHub contribution graph (standard 3D contribution calendar from github-readme-activity-graph or similar dark-themed render)

### Section 7: Contact / Uplink

- Styled as a terminal command block:

```bash
$ connect --portfolio owaisimran.me --github shotgun84
```

- Below: actual contact links in a clean list:
  - 📧 [imranowaisofficial@gmail.com](mailto:imranowaisofficial@gmail.com)
  - 🌐 [owaisimran.me](https://owaisimran.me)
  - 💼 LinkedIn
  - 📱 +971 52 226 3081 (WhatsApp)

### Section 8: Footer

- Thin horizontal rule (`<hr>`) in `#21262d`.
- Small centered text: *"System online. Always building."*
- Optional: tiny animated dot indicator using an SVG or GIF.

---

## 5. File Structure

```
shotgun84/
├── README.md              # Main profile README (all content + image refs)
├── assets/
│   └── hero-banner.svg    # Custom SVG hero banner
```

- `README.md` lives at repo root (standard for GitHub profile repos).
- `assets/hero-banner.svg` is referenced via raw GitHub content URL after commit.

---

## 6. Dependencies & External Services


| Service                                  | Purpose                              |
| ---------------------------------------- | ------------------------------------ |
| shields.io                               | Tech badges with custom neon styling |
| github-readme-stats.vercel.app           | GitHub stats card                    |
| github-readme-streak-stats.herokuapp.com | Contribution streak card             |
| GitHub raw content CDN                   | Serving the SVG hero banner          |


---

## 7. Accessibility & Fallbacks

- All images have `alt` text.
- Links are descriptive (not "click here").
- Color contrast checked: cyan `#00f0ff` on `#0d1117` exceeds 4.5:1.
- If external stats services are down, the README still renders with broken-image placeholders — acceptable for profile pages.

---

## 8. Success Criteria

- README renders cleanly in GitHub dark mode.
- Hero banner SVG loads and displays correctly.
- All shields.io badges render with neon color styling.
- GitHub stats/streak cards load with matching dark theme.
- Portfolio link (owaisimran.me) is prominently featured.
- No mention of Vapi. ElevenLabs mentioned only in KaiDubai context.
- Contact info (email, phone, LinkedIn, WhatsApp) is present.
- Overall impression: memorable, cyberpunk HUD aesthetic, clearly engineered.

