# Portfolio Redesign Plan — James Parker Style

## Feasibility: YES, fully doable

This is a clean, handcrafted HTML/CSS build. No obscure framework, no complex animations —
just modern CSS Grid and good typography. The rebuild is significant (not a CSS tweak on top
of Massively) but entirely manageable.

---

## Design Analysis

### Color Palette
| Role | Color |
|---|---|
| Primary accent | Royal blue `#1a4fdb` (approx.) |
| Background | Cream / off-white `#f5f0e8` (approx.) |
| Card surface | White `#ffffff` |
| Text | Near-black `#1a1a1a` |

### Typography
- **Headlines:** Condensed serif — style of *Editorial New* or *Playfair Display* (large, expressive, bold)
- **Body / labels:** Clean sans-serif — *Inter* or *DM Sans*
- **Accent labels:** Small uppercase or monospace for tags like "CASE STUDIES", "AVAILABLE NOW"

Both fonts are available free on Google Fonts, so no licensing issues.

### Layout Pattern
The hero uses a **bento grid** — a CSS Grid where cards of different sizes are placed on a
shared grid. This is the most distinctive and technically interesting part of the design.
The rest of the page (case studies, stats, services) uses simpler two-column layouts.

---

## What Has to Change

The current **Massively** template (HTML5UP) is architecturally incompatible with this style.
It uses a fixed dark theme, full-width magazine layout, and jQuery-heavy scroll animations.
We would **replace everything** — HTML structure, CSS, and page templates — starting fresh.

What we keep:
- Your content (text, links, social icons)
- Font Awesome (already loaded, used for icons)
- The 3-page structure (Home, My Journey, My Story)
- The file/folder setup (`assets/`, `home.html`, `cv.html`, `story.html`)

---

## Page-by-Page Plan

### Page 1 — Home (`home.html`)
Rebuilt as the bento hero layout:
- Top nav: name logo left, links center (with • separators), email right
- Bento grid hero:
  - Large blue card: your photo + your name
  - Left panel: headline tagline ("At the intersection of finance, data and AI")
  - Right panel: featured project preview card (links to a project or your GitHub)
  - Bottom strip: skills list (left), location + time (center), availability badge (right)
- Below fold: short intro paragraph + a link to My Story

### Page 2 — My Journey (`cv.html`)
Rebuilt using the stats + services layout style:
- Stats row: key numbers (years of experience, projects, skills, etc.)
- Career timeline as a numbered services-style list (each role = one row)
- Clean two-column: dates on the left, description on the right

### Page 3 — My Story (`story.html`)
Rebuilt as an editorial text layout:
- Large serif headline
- One or two column text blocks (your personal/professional narrative)
- Optionally a testimonial-style pull quote section

---

## Technical Approach

| Concern | Decision |
|---|---|
| CSS framework | None — pure CSS with custom properties |
| Layout engine | CSS Grid (bento) + Flexbox (nav, rows) |
| JS | Minimal — only for live clock or any small interactions |
| jQuery | Removed (Massively depends on it; new design does not need it) |
| Fonts | Google Fonts: one serif + one sans-serif |
| Icons | Font Awesome (kept) |

### New file structure
```
assets/
  css/
    style.css        ← single new stylesheet (replaces all of Massively's CSS)
  fonts/             ← optional, if self-hosting fonts
home.html
cv.html
story.html
index.html           ← kept as redirect (already exists)
```

---

## Effort Estimate

| Task | Effort |
|---|---|
| Design system (CSS variables, typography, base styles) | ~1 hr |
| Nav component | ~30 min |
| Bento hero grid (Home) | ~2 hr (most complex piece) |
| Home page below-fold sections | ~1 hr |
| My Journey page | ~1 hr |
| My Story page | ~45 min |
| Responsive / mobile pass | ~1 hr |
| **Total** | **~7–8 hours of build work** |

---

## Risks / Things to Confirm Before Starting

1. **Your photo** — the design features a portrait photo prominently in the hero card.
   Do you have a good quality photo you want to use?
2. **Featured project** — the hero has a "case study" preview card. Do you have a project
   (with an image) you want to feature, or should this be adapted to something else?
3. **Content for stats** — the design shows numbers (120+ projects, 10+ years, etc.).
   What are your real stats to display?
4. **"Available Now" badge** — do you want to keep an availability indicator?

---

## Summary

This redesign is **feasible and worth doing**. The result will look dramatically more modern
and professional than the current Massively template. The main investment is the bento hero
grid on the home page — the other two pages are simpler. No exotic tooling required; it is
plain HTML and CSS that you can host on GitHub Pages exactly as you do today.

Ready to start when you confirm the questions above.
