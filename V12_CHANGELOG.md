# V12 — Stable Responsive UI

## Structure

- Moved the accumulated inline CSS out of `index.html` into `styles.css`.
- Replaced versioned override layers with one design system and four focused media queries.
- Consolidated spacing, color, radius, shadow, and typography values into CSS custom properties.

## Layout stability

- Removed the `9ch` section-title constraint that split Thai headings unexpectedly.
- Added explicit sizing rules for long English headings without overflowing their grid column.
- Rebuilt hub cards, profile facts, content strips, system cards, and closing content around `minmax(0, 1fr)` and intrinsic sizing.
- Replaced single-line truncation on important labels with controlled two-line clamps.
- Fixed mobile hero copy so `WACHIRA UTHAWANG` remains inside the frame at 360px and 390px widths.
- Fixed modal width calculations so gallery panels stay inside the viewport.

## Accessibility and interaction

- Added consistent `:focus-visible` treatment.
- Added dialog roles, labels, `aria-modal`, live counters, accessible button labels, and explicit button types.
- Added modal focus entry, keyboard focus trapping, Escape handling, and focus restoration.
- Added disabled states and ARIA pressed states to gallery controls.

## Verification targets

- Phone: 360×800 and 390×844
- Tablet: 768×1024 and 1024×768
- Desktop: 1440×900
- Verified no document-level horizontal overflow and no console errors.
