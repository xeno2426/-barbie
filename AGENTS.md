# The Waffle Villa — Washim · Project Brief

## Client
**Business:** The Waffle Villa — premium dessert café  
**Location:** Maharatha Complex, Washim, Maharashtra, India  
**Phone:** +91 93739 51796  
**Instagram:** @waffle_villa.01  
**WhatsApp:** https://wa.me/919373951796  
**Domain:** https://thewafflevilla.in  
**Opening Date:** March 31, 2026  

---

## Project Structure

```
waffle-villa-washim/
├── index.html          ← Single-page site (all sections in one file)
├── AGENTS.md           ← This file
└── tasks/
    ├── todo.md
    └── lessons.md
```

---

## Tech Stack

- **Pure HTML/CSS/JS** — no framework, no build step
- **Fonts (Google Fonts CDN):** Playfair Display · Cormorant Garamond · DM Sans
- **Deployment:** GitHub Pages (repo: xeno2426/waffle-villa-washim)

---

## Design System

### Colors (CSS variables)
```css
--gold:        #C9922A
--gold-light:  #E8B84B
--gold-pale:   #F5DFA0
--brown:       #1A0F05   /* page background */
--brown-mid:   #2D1A08
--brown-light: #4A2E10
--cream:       #F9F0DC
--red:         #C0392B
--white:       #FEFEFE
```

### Typography
- **Headings:** Playfair Display (serif, 400/700/900 + italic)
- **Subheadings:** Cormorant Garamond (300/400/600)
- **Body/UI:** DM Sans (300/400/500)

### Tone
Warm, premium, local. Not flashy — elegant and appetizing.

---

## Current Site — Sections (all in index.html)

| Section | ID | Status |
|---|---|---|
| Nav (desktop + mobile hamburger) | `.site-header` | ✅ Done |
| Opening banner bar | `.opening-banner` | ✅ Done |
| Hero (shimmer title + tagline) | `#hero` | ✅ Done |
| Countdown timer → "Now Open" swap | `#countdown-section` | ✅ Done |
| Menu (6 categories, ₹ prices) | `#menu` | ✅ Done |
| Contact + WhatsApp CTA | `#contact` | ✅ Done |
| Footer | `.site-footer` | ✅ Done |

### Menu Categories & Items
- **Waffles:** Classic, Choco, Nutella, Strawberry, Oreo, Blueberry, Mix Fruit (₹89–₹149)
- **Pancakes:** Classic, Choco, Blueberry, Strawberry (₹79–₹119)
- **Shakes:** Choco, Oreo, Strawberry, Vanilla, Butterscotch (₹79–₹99)
- **Desserts:** Nutella Sandwich, Brownie, Lava Cake, Waffle Sandwich, Ice Cream (₹49–₹129)
- **Juices:** Mosambi, Pomegranate, Orange, Strawberry, Mix (₹60–₹90)
- **Beverages:** Cold Coffee variants, Masala Chai (₹25–₹100)

---

## Implemented Features

- **SEO:** Title, meta description, OG tags (WhatsApp/Instagram previews), Twitter card, canonical URL
- **Accessibility:** Skip link, `aria-label` on all interactive elements, `role` attributes on menu lists, visible focus ring, `prefers-reduced-motion` respected
- **Performance:** GPU-promoted noise texture overlay (`will-change: transform`), passive scroll listeners, `requestAnimationFrame` for nav solidify
- **Animations:** Hero shimmer gradient, `fadeUp` entry animations, scroll reveal via IntersectionObserver, staggered menu row reveals (40ms), nav digit tick pulse
- **Countdown:** Auto-clears interval when target passes; banner + section both swap to "We're Now Open!" message
- **Mobile:** Hamburger drawer, body scroll lock when open, closes on link click

---

## Known Gaps / Possible Next Tasks

- [ ] No `og-cover.jpg` image yet (referenced in OG tags but file doesn't exist)
- [ ] Map placeholder is a styled div — could embed a real Google Maps iframe
- [ ] No favicon
- [ ] No `robots.txt` or `sitemap.xml`
- [ ] Prices may need updating if client changes them

---

## Do Not Break

- The countdown `TARGET` date is `2026-03-31T00:00:00+05:30` — do not change unless client explicitly asks
- WhatsApp link includes a pre-filled message — preserve it
- All `aria-*` attributes — accessibility is intentional
- CSS variable names — used consistently throughout the file

---

## Agent Workflow Rules

### Plan First
- For any non-trivial change (3+ steps): write your plan to `tasks/todo.md` before touching code
- If something breaks, STOP and re-plan — do not keep patching

### Verify Before Done
- Never mark a task complete without checking it renders correctly
- Test mobile layout mentally — this site has many mobile-specific styles

### Capture Lessons
- After any correction: log the pattern to `tasks/lessons.md`

### Autonomous Execution
- When given a bug or feature request: just fix it. No hand-holding needed.
- Point at the relevant section/class/ID in index.html, then resolve it.

### Elegance Check
- For non-trivial edits: ask "is there a simpler way that doesn't add new dependencies?"
- This is a zero-dependency site — keep it that way unless there's a strong reason.

### Core Principles
- Bias toward action, not questions
- Correctness over speed
- Minimal surface area — smallest change that solves the problem
- Preserve accessibility — never remove aria attributes
- Fail loudly — if something is broken or uncertain, surface it
