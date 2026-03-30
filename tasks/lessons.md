# Lessons Log

- **Mobile Drawer Stagger Logic:** When adding new links to `.mobile-drawer`, always verify the `nth-child(n)` counts. Inserting an element pushes down the elements below it, requiring `transition-delay` adjustments for the new and subsequently shifted elements to preserve the staggered animation.
- **Form Length Counters:** Vanilla JS character counters should safely check `length > MAX` and conditionally apply error classes, supplementing the HTML `maxlength` or backend bounds properly.
