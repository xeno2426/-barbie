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
├── index.html          ← Single-page site (all sections in one file, ~1350 lines)
├── games.html          ← Mini games page (3 canvas games)
├── AGENTS.md           ← This file — read at start of every session
└── tasks/
    ├── todo.md
    └── lessons.md
```

---

## Tech Stack

- **Pure HTML/CSS/JS** — no framework, no build step, zero npm
- **3D:** Three.js r128 via CDN (`cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js`)
- **Fonts (Google Fonts CDN):** Playfair Display · Cormorant Garamond · DM Sans
- **Deployment:** GitHub Pages (repo: `xeno2426/waffle-villa-washim`) — auto-deploys on git push
- **Zero external dependencies rule** — keep it this way

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
--focus-ring:  #E8B84B
```

### Typography
- **Headings:** Playfair Display (serif, 400/700/900 + italic)
- **Subheadings:** Cormorant Garamond (300/400/600)
- **Body/UI/Nav:** DM Sans (300/400/500)

### Tone
Warm, luxurious, indulgent. NOT cartoon, NOT balloon-and-confetti, NOT clipart.
Aesthetic: dark luxury editorial.
Taglines: *"Where Sweet Cravings Meet Their Match"* / *"Your waffle, our muse."*

---

## index.html — Full Section Map

| Section | Selector | Status |
|---|---|---|
| Grand opening banner bar | `.opening-banner` | ✅ Done |
| Nav — desktop + mobile hamburger | `.site-header` / `.site-nav` | ✅ Done |
| Mobile drawer overlay | `.mobile-drawer` / `#mobile-drawer` | ✅ Done |
| Hero — shimmer title + 3D waffle grid | `#hero` / `#hero-canvas` | ✅ Done |
| Countdown → "We're Open!" swap | `#countdown-section` | ✅ Done |
| About / Our Story | `#about` / `.about-section` | ✅ Done |
| Menu — 6 categories, real ₹ prices | `#menu` | ✅ Done |
| Offers — Opening Day combo | `#offers` / `.offers-section` | ✅ Done |
| Contact + WhatsApp CTA + map placeholder | `#contact` | ✅ Done |
| Games teaser block | inline `<section>` after `</main>` | ✅ Done |
| Footer | `.site-footer` | ✅ Done |

### Nav Link Order (do not change)
About → Menu → Offers → Contact ← both desktop `.nav-links` and `.mobile-drawer`

---

## index.html — Implemented Features

- **SEO:** title, meta description, OG tags, Twitter card, canonical URL
- **Accessibility:** skip link (`#main-content`), `aria-label` on all interactive elements, `role` attributes on menu lists, visible focus ring (`:focus-visible`), `prefers-reduced-motion` respected
- **Performance:** GPU-promoted noise texture (`will-change:transform`), passive scroll listeners, `requestAnimationFrame` for nav solidify, IntersectionObserver pauses Three.js when hero off-screen
- **Animations:** hero shimmer gradient (`@keyframes shimmer`), `fadeUp` entry, scroll reveal (`.reveal` → `.visible`), staggered menu row reveals (40ms cascade), countdown digit tick pulse (`.tick` class)
- **Countdown:** `TARGET = 2026-03-31T00:00:00+05:30` — auto-clears interval when passed; banner + section both swap to "We're Now Open!" + WhatsApp CTA
- **Mobile:** hamburger drawer, body scroll lock when open, closes on link click
- **3D hero:** Three.js r128 — 6×6 floating waffle grid, gold particles, mouse/touch parallax; pauses via IntersectionObserver when off-screen
- **User select disabled:** `user-select: none` on body (intentional — prevents text highlight on mobile)

---

## Full Menu & Prices (source of truth)

### Villa Speciality
| Item | Price |
|------|-------|
| Choco Waffles | ₹300 |
| Lotus Biscoff Pancake (18 pcs) | ₹260 |
| Brownie Shake | ₹200 |

### Stick Waffles — Popsi / Candy / Cone
| Flavour | Popsi | Candy | Cone |
|---------|-------|-------|------|
| Dark Chocolate | ₹70 | ₹80 | ₹90 |
| White Chocolate | ₹70 | ₹80 | ₹90 |
| Milk Chocolate | ₹70 | ₹80 | ₹90 |
| Triple Chocolate | ₹80 | ₹90 | ₹100 |
| KitKat Chocolate | ₹80 | ₹90 | ₹100 |
| Oreo Chocolate | ₹80 | ₹90 | ₹100 |
| Red Velvet | ₹90 | ₹100 | ₹100 |
| Strawberry | ₹80 | ₹90 | ₹100 |
| Almond Milk | ₹90 | ₹100 | ₹110 |
| Nutella | ₹90 | ₹100 | ₹110 |
| Biscoff | ₹100 | ₹110 | ₹110 |
| Kunfa Pistachio | ₹100 | ₹110 | ₹110 |

### Cone Waffles
| Item | Price |
|------|-------|
| Naughty Nutella Waffle | ₹120 |
| Dark Chocolate Waffle | ₹100 |
| White Chocolate Waffle | ₹100 |
| Triple Chocolate Waffle | ₹100 |
| Chocolate Overloaded | ₹110 |
| KitKat Crunchy White | ₹130 |
| KitKat Crunchy Dark | ₹130 |
| Red Velvet White | ₹130 |
| Red Velvet Dark | ₹130 |
| Oreo White Chocolate | ₹130 |
| Oreo Dark Chocolate | ₹130 |
| Blueberry Waffle | ₹130 |
| Strawberry Waffle | ₹110 |
| Almond Chocolate Waffle | ₹150 |
| Kiki & Oreo Waffle | ₹160 |
| Kunfa Pistachio | ₹160 |
| Lotus Biscoff | ₹160 |

### Ice Cream Waffles — Small / Large
| Item | Small | Large |
|------|-------|-------|
| Butterscotch Waffle | ₹90 | ₹130 |
| Vanilla Waffle | ₹90 | ₹130 |
| Strawberry Waffle | ₹90 | ₹130 |
| Choco Bar Waffle | ₹90 | ₹130 |
| Choco Nut Bar Waffle | ₹110 | ₹160 |
| Kaju Kishmish Waffle | ₹110 | ₹160 |
| Choco Crunch | ₹90 | ₹130 |

### Pancakes — 6 pcs / 12 pcs
| Item | 6 pcs | 12 pcs |
|------|-------|--------|
| Dark Chocolate | ₹80 | ₹115 |
| White Chocolate | ₹80 | ₹115 |
| Triple Chocolate | ₹80 | ₹120 |
| Chocolate Overloaded | ₹90 | ₹120 |
| KitKat Crunchy White | ₹90 | ₹120 |
| KitKat Crunchy Dark | ₹90 | ₹120 |
| Red Velvet White | ₹90 | ₹120 |
| Red Velvet Dark | ₹90 | ₹120 |
| Oreo White Chocolate | ₹90 | ₹120 |
| Oreo Dark Chocolate | ₹90 | ₹120 |
| Naughty Nutella | ₹120 | ₹150 |
| Kunfa Pistachio | ₹130 | ₹190 |

### Beverages
| Item | Price |
|------|-------|
| Vanilla Shake | ₹130 |
| Chocolate Shake | ₹130 |
| Strawberry Shake | ₹140 |
| KitKat Shake | ₹140 |
| Cold Coffee | ₹70 |
| Oreo Cold Coffee | ₹90 |
| Cold Coffee With Ice Cream | ₹100 |
| Masala Chai | ₹25 |

---

## Opening Day Offer
- **Combo:** Waffle + Shake = ₹149
- **Discount:** First 50 customers get 20% OFF
- **Valid:** 31st March 2026 (opening day only)
- **WhatsApp offer link:** `https://wa.me/919373951796?text=Hi!%20I%20want%20the%20Opening%20Day%20Combo%20offer%20%F0%9F%A7%87`

---

## games.html — Full Context

### Purpose
Mini games page accessible from the main site. Linked from:
- Games teaser section (after `</main>` in index.html)
- Footer link (`🎮 Games`)

### Games Implemented
| Game | Panel ID | Canvas ID | High Score Key |
|------|----------|-----------|---------------|
| 🧇 Waffle Stacker | `#panel-stacker` | `#stacker-canvas` | `waffleStacker` |
| 🥤 Shake Catcher | `#panel-catcher` | `#catcher-canvas` | `shakeCatcher` |
| 🍫 Dessert Match (memory) | `#panel-memory` | DOM grid | `dessertMemory` |

### Games Tech
- Pure canvas 2D (no libraries) for Stacker and Catcher
- DOM grid (divs) for Memory Match
- High scores stored in `localStorage` (top 5 per game)
- Tab switching via `switchGame(id, btn)` — **must pass `this`** as second arg from onclick
- Touch-enabled: `ontouchmove` for Catcher, `ontouchstart` for Stacker
- Spacebar support in Stacker

### games.html Design
- Same CSS variable palette as index.html (dark brown + gold)
- Sticky top bar with back link to `index.html`
- `localStorage` for scores — persists across sessions (clears if user wipes browser data, acceptable)

---

## Known Gaps / Open Issues

- [ ] `og-cover.jpg` missing — OG image referenced in meta tags but file doesn't exist (critical for WhatsApp link previews)
- [ ] No favicon yet
- [ ] No `robots.txt` or `sitemap.xml`
- [ ] Google Maps iframe not embedded — currently a styled `<a>` linking to Google Maps
- [ ] Payment terms NOT discussed with client yet
- [ ] No client email on record
- [ ] Real food photos not available — client shoots on opening day (March 31)
- [ ] WhatsApp automation scope unclear — currently manual `wa.me` links only

---

## Do Not Break

- Countdown `TARGET = 2026-03-31T00:00:00+05:30` — do not change
- WhatsApp links with pre-filled messages — preserve exact URL encoding
- All `aria-*` attributes — accessibility is intentional, never remove
- CSS variable names — used consistently throughout both files
- Nav link order: About → Menu → Offers → Contact
- `user-select: none` on body — intentional, keeps mobile UI clean
- Three.js CDN version: r128 — do not upgrade without testing
- `switchGame(id, btn)` in games.html — second param `btn` is required, do not revert to global `event`

---

## Lessons Log (known past mistakes)

- **Double animation declaration on `.hero-title`:** Had two `animation:` lines — second one overrode the first, killing the `fadeUp`. Always use a single combined `animation:` declaration: `animation: fadeUp 0.9s 0.1s ease both, shimmer 6s 1.5s ease-in-out infinite;`
- **"Biscof" spelling:** Correct spelling is **Biscoff** (double-f). Appears in: Villa Speciality (Lotus Biscoff Pancake), Stick Waffles (Biscoff), Cone Waffles (Lotus Biscoff).
- **`switchGame` global event:** Never use bare `event.target` in onclick handlers — pass `this` explicitly: `onclick="switchGame('stacker', this)"`.

---

## Agent Workflow Rules

### Plan First
- For any non-trivial change (3+ steps): write your plan to `tasks/todo.md` before touching code
- If something breaks, STOP and re-plan — do not keep patching

### Verify Before Done
- Never mark a task complete without checking it renders correctly
- Test mobile layout mentally — mobile is the primary device for this audience (Android phones)

### Capture Lessons
- After any correction: log the pattern to `tasks/lessons.md`

### Autonomous Execution
- When given a bug or feature request: just fix it. No hand-holding needed.
- Reference the relevant section/class/ID, then resolve it.

### Elegance Check
- For non-trivial edits: ask "is there a simpler way that doesn't add new dependencies?"
- This is a zero-dependency site — keep it that way

### Core Principles
- Bias toward action, not questions
- Correctness over speed
- Minimal surface area — smallest change that solves the problem
- Preserve accessibility — never remove aria attributes
- Mobile-first — always check `@media (max-width: 700px)` implications
- Fail loudly — if something is broken or uncertain, surface it
