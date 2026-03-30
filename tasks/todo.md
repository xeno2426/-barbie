# Plan: Customer Feedback System

## Phase 1: `feedbacks.html` Creation
1. Set up boilerplate HTML matching the design system (CSS vars, dark theme background `var(--brown)`, noise texture overlay, fonts).
2. Create Top Bar with brand name (linking to `index.html`) and "← Back" link.
3. Build the Hero Section ("What Our Guests Say").
4. Implement the Feedback Grid container.
5. Add floating bottom-center "✍ Leave Feedback" button.

## Phase 2: Feedback Modals & `localStorage`
1. Build the "Share Your Experience" modal structure (hidden by default).
   - Elements: Name input, Star Rating component (interactive keyboard-accessible), Textarea, Submit Button, Close Button.
2. Build the "Thank You" modal structure (hidden by default).
3. Implement Javascript logic for the Modals:
   - Floating Action Button toggles the Feedback modal.
   - Setup tab trapping inside modal logic + Esc key to close + Scroll locking.
   - Hover/Click events for Star ratings (storing 1-5 result in hidden input).
   - Form submission: prevent default, validate fields, show shaking error animations on empty fields.
   - Successful Submit -> save to `localStorage("wv_reviews")` -> hide feedback modal -> show Thank You modal.
   - Closing Thank You modal toggles review grid refresh.
4. Implement Javascript logic for rendering `localStorage("wv_reviews")` to the grid:
   - Handle Empty state: "Be the first to leave your mark."
   - Handle populated state: generating `.review-card` HTML with stars, name, date, text.

## Phase 3: `index.html` Integration (Reviews Section)
1. Add `<section id="reviews">` between `#offers` and `#contact`.
2. Provide Section Headings: "GUEST VOICES", "What People Are Saying".
3. Write Vanilla JS inside `index.html` to load up to 3 most recent reviews on `DOMContentLoaded`.
   - Show placeholder if < 3 or 0 reviews.
   - Append "Read All Reviews →" linking to `feedbacks.html`.
4. Apply `.reveal` class for scroll animation integration.

## Phase 4: `index.html` Nav Links Updates
1. Add the "Feedback" link into the mobile drawer explicitly (`.mobile-drawer a:nth-child(5)` mapping to `transition-delay: 0.5s` and appending the drawer DOM).
2. Verify desktop layout isn't touched for the header nav.
3. Add `feedbacks.html` link to the footer navigation right next to the current social/games links.

## Phase 5: Testing & QA
- Check accessibility: `aria-labels`, Focus traps in modals, Enter/Space keybindings on interactive elements.
- Mentally verify mobile views.
