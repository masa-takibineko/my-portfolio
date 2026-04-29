# takibineko Design System

**Brand:** takibineko (abbreviated: TBN)  
**Creator:** masa-takibineko — Freelance Developer & Creator  
**Tagline:** Developer & Creator / アイデアを動くデジタルに変える  
**Contact:** baseball.masa.89@gmail.com  

---

## Overview

takibineko is a one-person freelance operation specializing in three core services:

1. **HP / LP 制作** — Stylish, animated websites (HTML/CSS, TypeScript, React)
2. **Bot 開発** — LINE auto-reply bots, Slack/Discord integrations (Python)
3. **AI エージェント開発** — LLM-powered agents & chat apps (Claude API, OpenAI, LangChain, Streamlit)

The brand is built around a **cyberpunk / synthwave** aesthetic: dark space backgrounds, neon cyan/pink/purple accents, glitch effects, scan lines, and heavy motion design. The portfolio itself is the primary product showcase.

### Sources
- **Portfolio codebase:** https://github.com/masa-takibineko/my-portfolio (`index.html` — single-file SPA)
- **Demo sites repos:** masa-takibineko/hp-demos, masa-takibineko/chatei-hatou-demo, masa-takibineko/yellow-komazawa-koen, masa-takibineko/realestate-hp, masa-takibineko/yorimichi, masa-takibineko/streamlit-llm-app, etc.

---

## CONTENT FUNDAMENTALS

### Language & Tone
- **Bilingual**: Japanese primary for service descriptions and CTAs; English used for section titles, labels, nav, and technical terms
- **Japanese copy** is warm, approachable, informal: 「こんなこと頼めるかな？という段階でOK」— casual invitation to consult
- **English copy** is terse, techy, uppercase-heavy: "SELECTED WORKS", "GET IN TOUCH", "// Freelance Creator & Developer"
- **Vibe**: confident but not cold; technical but not intimidating; creative and slightly irreverent
- **Person**: speaks as "I" (私 implied); addresses client as "you" (あなた implied via casual Japanese)
- **Casing**: Section numbers use "01 / SERVICES" format; labels ALL CAPS with letter-spacing; body text sentence case
- **No emoji** used anywhere — brand is too sleek for emoji
- **Punctuation style**: uses `//` as code-comment prefix for labels; uses `·` and `→` as decorative separators
- **Numbers**: displayed as Arabic numerals with `+` suffix for stats (50+, 30+)

### Examples
> 「こんなこと頼めるかな？」という段階でOK。  
> 案件の規模や内容に応じて、まずは柔軟に話し合いましょう。

> // Freelance Creator & Developer  
> Turning Ideas into Digital Reality

---

## VISUAL FOUNDATIONS

### Color System
| Token | Value | Usage |
|---|---|---|
| `--bg` | `#03030f` | Primary background (near-black indigo) |
| `--bg2` | `#060614` | Card/panel background |
| `--cyan` | `#00f0ff` | Primary accent, glows, CTA borders |
| `--pink` | `#ff0099` | Secondary accent, hover states, glitch layers |
| `--purple` | `#7700ff` | Tertiary accent, plasma blobs, gradients |
| `--text` | `#c8d6e5` | Body text (cool light blue-grey) |
| `--text-dim` | `#5a6a7a` | Muted text, labels, placeholders |

**Color vibe**: Cool, neon-lit darkness. All colors are saturated neons against deep near-black. No warm tones. No browns, oranges, or yellows.

### Typography
- **Display / Brand**: Orbitron (Google Fonts) — weights 400, 600, 700, 900. Used for logo, section titles, card titles, stat numbers. All-caps by nature.
- **Body / Code**: Space Mono (Google Fonts) — weights 400, 700. Monospaced. Used for ALL body text, nav links, buttons, descriptions.
- **Type scale**: `clamp()` fluid sizing throughout. Hero: clamp(2.5rem, 9vw, 7rem). Section titles: clamp(1.4rem, 4vw, 2.2rem).
- **Letter spacing**: Generous. Labels: 0.3–0.4em. Nav: 0.2em. Body: 0.08em.
- **Line height**: 1.9–2.1 for body copy. 1 for display.
- **No serif fonts** anywhere.

### Backgrounds & Textures
- **Fixed canvas layers** (z-index 0): CSS grid pattern (cyan 4% opacity, 60px), animated scanlines, SVG fractal noise at 2.5% opacity
- **Plasma blobs**: 3 large radial-gradient circles (cyan, pink, purple) with `filter: blur(90px)`, `mix-blend-mode: screen`, 13% opacity — float slowly around viewport
- **Warp canvas**: Hyperspace starfield streaks in canvas, 60% opacity behind hero content
- **Particle system**: 110 floating particles with connecting lines, shooting stars, mouse-reactive
- **Section backgrounds**: Hero is full-viewport with all layers; Works/Contact sections get `rgba(0,0,0,0.25)` overlay

### Borders & Cards
- Cards use `border: 2px solid rgba(0,240,255,0.15)` at rest
- On hover: conic-gradient rotating border animation (`@property --ba`) — full RGB sweep
- Cards: `background: rgba(6,6,20,0.7)`, `backdrop-filter: blur(10px)`
- **No traditional border-radius** — cards are sharp rectangles (0px radius). This is intentional cyberpunk aesthetic.
- Inner holographic shine: `radial-gradient` following mouse position

### Shadows & Glow
- Text glow: `text-shadow: 0 0 20px var(--cyan), 0 0 40px rgba(0,240,255,0.4)` (multi-stop)
- Box glow: `box-shadow: 0 20px 60px rgba(0,240,255,0.15), 0 0 40px rgba(0,240,255,0.08)`
- Hover glow intensifies: `0 0 30px var(--cyan), 0 0 60px rgba(0,240,255,0.3)`
- No drop-shadow filter used; all shadows are box-shadow/text-shadow

### Animations & Motion
- **Scroll reveal**: `IntersectionObserver` — cards translate up + rotateX(8deg) on entry, 0.7s ease
- **Text scramble**: section titles scramble through random ASCII chars on scroll into view
- **Glitch effect**: hero title has `::before`/`::after` pseudo-elements with clip-path splits, triggered on 3s intervals
- **Logo flicker**: Orbitron logo flickers like a neon sign (text-shadow on/off)
- **Page glitch**: random full-page micro-glitch every 4–10 seconds
- **Typewriter**: cycling phrases with blinking cursor
- **3D tilt**: cards do `perspective(700px) rotateY/X` on mouse move (±20deg for service cards, ±12deg for work items)
- **Easing**: mostly `ease`, `cubic-bezier(0.175, 0.885, 0.32, 1.275)` for spring-out; `linear` for infinite spins
- **Durations**: reveals 0.7–0.8s; hover transitions 0.3s; tilt 0.08s

### Hover & Press States
- Links: color changes from `--text-dim` to `--cyan` + underline grows from 0 to 100% width
- Buttons: fill sweep from left (`translateX(-100%)` → 0) + color inversion
- Cards: 3D tilt + glow intensification + rotating conic border
- Cursor: custom cursor turns pink on interactive elements; ring expands

### Cursor
- Custom cursor: 10px cyan dot with neon glow, `mix-blend-mode: screen`
- Trailing ring: 36px circle outline, follows with 0.12 lerp
- 14-point trail: fading dots behind cursor
- Turns pink on hover over interactive elements

### Corner Radii
- **0px everywhere** — no rounded corners. This is a deliberate aesthetic choice.

### Spacing System
- Sections: `padding: 8rem 4rem` (desktop), `5rem 2rem` (mobile)
- Grid gaps: `2rem` (services), `1.5rem` (works)
- Nav: `1.5rem 4rem`

### Imagery
- **No photography** used in the main portfolio (all work items use CSS gradient placeholders)
- Demo sites link out — some use Unsplash photography with dark overlay tints
- Color palette of imagery: cool-tinted with dark overlays (`rgba(0,10,30,0.55)` etc.)
- No illustrations; no hand-drawn assets

---

## ICONOGRAPHY

- **No icon library** used anywhere in the portfolio
- **Unicode geometric symbols** as icons: `◈` (web), `◇` (bot), `◉` (AI) — minimal, geometric
- **No SVG icons**, no icon fonts, no emoji
- These symbols are styled with `text-shadow` neon glow
- Section numbering uses `01 /`, `02 /` format as visual anchors

### Assets Available
- No logo image file exists — the brand mark is the text "TBN" set in Orbitron 900 weight
- See `assets/` for any exported assets

---

## Files Index

```
README.md                    — This file
SKILL.md                     — Agent skill definition
colors_and_type.css          — CSS custom properties (colors + type)
assets/                      — Brand assets (fonts referenced via Google Fonts CDN)
preview/                     — Design System card HTML files
ui_kits/
  portfolio/
    README.md                — UI kit documentation
    index.html               — Interactive portfolio prototype
    Hero.jsx                 — Hero section component
    Nav.jsx                  — Navigation component
    ServiceCard.jsx          — Service card with 3D tilt
    WorkItem.jsx             — Work grid item
    AboutSection.jsx         — About + skills section
    ContactSection.jsx       — Contact section
```

### Google Fonts Used
- Orbitron: https://fonts.google.com/specimen/Orbitron
- Space Mono: https://fonts.google.com/specimen/Space+Mono

*No substitute fonts needed — both are freely available on Google Fonts.*
