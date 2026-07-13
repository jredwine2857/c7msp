# CLAUDE.md — C7 MSP Website

## Project Overview

Corporate presence website for **C7 MSP**, a managed IT services provider. C7 MSP is a DBA of **Cyber7 Group LLC** (cyber7group.com), which acts as the umbrella/holding company for three DBAs:

| DBA | Focus | Domain |
|---|---|---|
| C7 MSP | Managed IT / cybersecurity for SMBs | c7msp.com (this repo) |
| C7 Infrastructure | Data center / systems integration | c7infrastructure.io |
| C7 Intelligence | AI integration / custom software dev | c7intelligence.io |

The three DBA sites are intentionally **visually distinct** from one another (no shared theme). The parent site cyber7group.com will eventually be remade as a holding-company page linking to all three.

## Tech Stack & Hosting

- **Pure static HTML/CSS** — single `index.html`, no build step, no framework, no dependencies beyond Google Fonts.
- **Hosted on GitHub Pages** — deploys from `main` branch, root folder.
- **Custom domain:** c7msp.com (DNS via GoDaddy — A records to GitHub Pages IPs, www CNAME).
- Workflow: edits are committed via GitHub Desktop or Claude Code; Pages auto-redeploys on push to `main`.

## Repo Structure

```
index.html                      # entire site (markup + CSS in one file)
CLAUDE.md                       # this file
assets/
  hero-bg.mp4                   # hero background video (10s loop, muted, 449KB)
  cta-bg.mp4                    # CTA section background video (7s loop, muted, 97KB)
  hero-poster.jpg               # poster/fallback frame for hero video
  cta-poster.jpg                # poster/fallback frame for CTA video
  brand-story.mp4               # 2:09 brand story promo video, 1080p w/ audio, click-to-play (24MB)
  brand-poster.jpg              # poster frame for brand story video
  c7-shield.png                 # shield-only logo mark (used in nav)
  c7group-logo-light.png        # full Cyber7 Group logo, light wordmark (used in footer on dark bg)
  favicon.png                   # 64px shield favicon
```

## Design System

- **Fonts:** Space Grotesk (headings), Inter (body), IBM Plex Mono (stats/labels/eyebrows)
- **Palette (CSS variables in `:root`):**
  - `--ink` #10151c / `--ink-2` #161d26 — dark backgrounds (hero, header, CTA, footer)
  - `--paper` #eceff3 / `--paper-2` #dfe4ea — light section backgrounds
  - `--amber` #f2a93b — primary accent (CTAs, highlights)
  - `--teal` #1b4b4a / `--teal-bright` #3fa79a — secondary accent (flat-fee band, tags)
- **Feel:** dark "network operations center" aesthetic; live-stats panel in hero; mono-font labels.
- Background videos: muted/loop/playsinline, dimmed by `.vid-overlay` gradients; hidden under `prefers-reduced-motion`.

## Page Sections (in order)

1. Header/nav — shield logo, links, phone, Get a Quote button
2. Hero — headline + background video + live stats panel
3. Trust strip — 4 quick stats
4. Services (`#services`) — 4 cards: Managed IT Support, Cloud Migration, Compliance & Risk, Data Security/DR (tags: CYBER CARE / CLOUD / SECURITY / BACKUP)
5. Flat-Fee Model (`#flatfee`) — teal band, included/never table
6. Our Story (`#story`) — dark section, click-to-play 2:09 brand video w/ controls + poster
7. Why C7 (`#why`) — 4-cell grid
8. CTA (`#contact`) — background video, call + email buttons
9. Footer — logos, links, client portals

## Key Content Facts

- **Phone:** 502-473-5020
- **Email:** info@c7msp.com
- **Remote Support portal:** https://cwa-c7g.screenconnect.com/ (nav + footer)
- **Payment Portal:** https://cyber7group.flexpmts.com/ (nav + footer)
- **LinkedIn:** https://www.linkedin.com/company/22302664 (footer)
- Stats used on site: 99.98% uptime, 2,367 projects, 400+ businesses, 5,489 end users, 15+ yrs avg engineer experience
- Selling points: flat-fee model (projects/maintenance/admin in one monthly price), vendor agnostic, white glove, single point of contact
- Content originally adapted from cyber7group.com

## Known Issues / TODO

- Background videos are 640×360 source; higher-res versions would look crisper if they become available.
- Contact is phone/email links only — if a contact form is added later, use a third-party endpoint (Formspree/Web3Forms etc.); never commit credentials to this public repo.

## Conventions for Edits

- Keep everything in the single `index.html` — don't split into separate CSS/JS files unless the site grows significantly.
- Keep total page weight low; compress any new media (target <1MB per asset) since this is GitHub Pages.
- This is a **public repo** — no secrets, keys, client names, or internal info, ever.
- Maintain the existing CSS variable palette for any new sections.
- Footer must retain "A Cyber7 Group company" attribution and the parent logo.
