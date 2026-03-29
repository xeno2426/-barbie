# Current Plan: Add Offers Section

1. **Reorder Navigation Vectors**
   - Update desktop nav links: About → Menu → Offers → Contact.
   - Update mobile menu nav links identically.
   - Add new `transition-delay` CSS rule for 4th link in mobile drawer.

2. **Add Offers CSS Architecture**
   - Base `.offers-section` matching dark aesthetic of `.about-section` or countdown.
   - `.offer-card` styling for high contrast and hover effects.
   - `.urgency-badge` styling with red alarm color.

3. **Insert Offers HTML Structure**
   - Build a new `<section id="offers">` component.
   - Place between Menu and Contact items.
   - Wire up the customized WhatsApp URL for CTA conversion.

4. **Add Mobile Quality Customizations**
   - Tweak padding for `.offer-card` inside `@media (max-width: 700px)`.
