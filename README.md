# Wachira Interactive Portfolio v7

Version 7 focuses on content UX while retaining the Canvas/WebP frame engine.

## V6 changes
- Hero transition no longer fades/blinks: Video 1 → 8-frame hold → match cut → Video 2.
- Name enters without fade, holds longer, then slides out as the chapter menu moves into the center.
- 5 portfolio chapter cards use real images from the Sheet registry.
- Mobile chapter cards are horizontal swipe / scroll-snap cards.
- ABOUT ME, TEACHING & PERFORMANCE, PROFESSIONAL GROWTH, and PEOPLE & COMMUNITY now use compact equal-sized horizontal content rows.
- Content rows support click-to-read and left/right swipe in the full-screen viewer.
- Photo Archive remains available.
- DIGITAL SYSTEMS is presented as two equal system cards using real system screenshots.
- Secondary system live link added: ระบบส่งงานนักเรียน CMW.
- Primary system live link added: ระบบเช็คชื่อและคะแนน.
- Digital Systems becomes horizontal swipe cards on mobile.

## Test
Recommended: VS Code + Live Server.

Desktop: 1366×768 / 1920×1080
Mobile: 390×844 / 430×932


## Version 7 — Mobile Gesture Anchor
Mobile motion scenes no longer force UI into a bottom sheet while the character is pointing. The UI first appears beside the hand, then moves into the central reading/interaction area as the character exits. Desktop behavior remains unchanged.
