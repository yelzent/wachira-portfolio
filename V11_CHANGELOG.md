# V11 — Adaptive 3 Device Modes

## Device modes
- Desktop: >= 1200px
- Tablet: 768–1199px (portrait/landscape adaptive)
- Phone: <= 767px, vertical-first UX

## Performance
- Phone Canvas DPR capped at 1.25, cache 10, 2 concurrent frame loads, frame stride 2.
- Tablet DPR capped at 1.45, cache 16, 3 concurrent loads.
- Desktop DPR capped at 1.85, cache 24, 4 concurrent loads.
- Phone/Tablet ignore height-only Safari address-bar resize events.
- Inactive motion scenes release most frame cache and stop RAF loops.
- Static gallery images use lazy loading and async decoding.

## Layout
- Phone uses vertical section cards, one-column content, swipe only for evidence/gallery.
- Tablet uses two-column/hybrid layouts; portrait systems can swipe.
- Desktop retains editorial multi-column layout.
- Mobile section headers are normal-flow to prevent eyebrow/description overlap.
- Motion scroll distances shortened on phone.
