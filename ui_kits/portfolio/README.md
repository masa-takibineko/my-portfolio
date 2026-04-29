# takibineko Portfolio UI Kit

## Overview
High-fidelity interactive recreation of the takibineko portfolio site (`masa-takibineko/my-portfolio`). Cyberpunk / synthwave aesthetic with full animations, 3D tilt cards, glitch effects, and custom cursor.

## Components

| Component | Description |
|---|---|
| `PlasmaBlobs` | Fixed animated radial-gradient blobs (cyan/pink/purple) with `mix-blend-mode: screen` |
| `Nav` | Fixed top nav with logo flicker, active state underline grow, scroll-triggered backdrop |
| `SectionLabel` | Section number + scramble title + gradient divider dot |
| `HeroSection` | Full-viewport hero with glitch title, typewriter subtitles, CTA buttons |
| `ServiceCard` | 3D tilt card with conic rotating border, holographic shine, neon icon |
| `WorkItem` | 16:9 work tile with tilt, overlay reveal, optional external link |
| `AboutSection` | Two-column with skill bars (shimmer), stat items |
| `StatItem` | Number card with hover lift + bottom accent line |
| `ContactSection` | Email link + social ghost links |
| `Footer` | Minimal copyright + dimmed TBN mark |
| `BtnPrimary` | Cyan fill-sweep button |
| `BtnSecondary` | Pink border/text on hover |
| `Tag` | Cyan uppercase chip with hover glow |
| `SocialLink` | Ghost link turns pink on hover |

## Design Notes
- **No rounded corners anywhere** — 0px radius is a core brand rule
- **Fonts**: Orbitron (display) + Space Mono (body/mono) from Google Fonts CDN
- **Cursor**: Custom cyan dot with trailing ring; turns pink on interactive elements
- **Background layers**: CSS grid, scanlines, plasma blobs (all `position:fixed`, z-index 0)
- **Animations**: All scroll reveals use IntersectionObserver; 3D tilt tracks mouse in real-time

## Usage
Open `index.html` directly. No build step needed — React + Babel loaded from CDN.
