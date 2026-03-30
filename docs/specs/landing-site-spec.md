# Bite Buddy Landing Site — Spec

## Overview
Single-page marketing site + privacy policy for Bite Buddy. Static HTML/CSS, hosted on GitHub Pages from a public `bitebuddy-site` repo. Must load in < 3 seconds on mobile.

## URLs
- `/` — Landing page
- `/privacy` — Privacy policy (served as `privacy/index.html`)

## Landing Page (`index.html`)

### Hero Section
- App icon (fork + spoon mascot)
- "Bite Buddy" title
- Tagline: "ADHD-friendly meal companion. One bite at a time."
- Two CTA buttons: App Store / Google Play (placeholder `#` links until live)

### Screenshot Walkthrough
- 4 screenshots in a horizontal scroll / carousel strip (no JS required — CSS `overflow-x: scroll` with `scroll-snap`)
- Order: Setup → Preparing → Take Bite → Done
- Captions under each:
  1. "Set your bites"
  2. "Get ready..."
  3. "Take your bite!"
  4. "You did it!"

### Features Section
- 3-4 cards, each with an emoji icon + short text:
  - "No rush, no pressure" — calm timer guides each bite
  - "ADHD-friendly design" — no red, no urgency, no overload
  - "Zero data collection" — no tracking, no ads, no internet required
  - "Built by a parent" — designed with and for real kids

### Footer
- Link to privacy policy (`/privacy`)
- Contact email
- "Made with love for picky eaters everywhere"

## Privacy Policy (`privacy/index.html`)
- Copy the content from `docs/privacy-policy.html` (already written)
- Same visual style as landing page (shared CSS)
- Back link to `/`

## Design Constraints
- **Colors**: Match the app — dark background (`#1A0533` → `#0A2A1A` gradient), yellow (`#FFE066`), green (`#A3FF6B`), pink (`#FF6BDF`)
- **Font**: Fredoka from Google Fonts (CSS import, fine for a public site)
- **Max width**: 640px centered content (mobile-first)
- **Total page weight**: < 100KB including images (compress screenshots to WebP)
- **No JavaScript** unless scroll-snap needs a polyfill (it won't)
- **Responsive**: Single column, works on phone/tablet/desktop

## Assets to Copy from App Repo
- `assets/icon/app_icon.png` → site root, convert to WebP
- `assets/store/screenshots/01-04` → `images/`, convert to WebP
- `docs/privacy-policy.html` → content source for `privacy/index.html`

## Repo Structure
```
bitebuddy-site/
├── index.html
├── privacy/
│   └── index.html
├── images/
│   ├── icon.webp
│   ├── 01_setup.webp
│   ├── 02_preparing.webp
│   ├── 03_take_bite.webp
│   └── 04_done.webp
├── style.css
├── CNAME              (optional, if custom domain later)
└── README.md
```

## GitHub Pages Setup
- Public repo: `stevendiamante/bitebuddy-site`
- Branch: `main`
- Source: root (`/`)
- Result: `stevendiamante.github.io/bitebuddy-site`

## Done When
- [ ] Both pages render correctly on iPhone Safari and Chrome desktop
- [ ] Lighthouse mobile performance score > 95
- [ ] Total transfer < 100KB
- [ ] Privacy policy URL works for store submissions
- [ ] Store buttons present (even if linking to `#` until apps are live)
