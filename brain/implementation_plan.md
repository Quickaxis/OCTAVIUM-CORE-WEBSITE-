# Implementation Plan - Performance & Mobile Fixes

## Goal Description
Optimize the Octavium Core landing page for performance and responsiveness. This includes reducing particle calculations, removing costly CSS animations and 3D tilts, debouncing scroll events, and implementing a vertical stacked layout for the process section on mobile.

## Proposed Changes

### [Component] Styling & Performance (FIX 1)
#### [MODIFY] [index.html](file:///c:/Users/chitr/Downloads/my websites/OCTAVIUM CORE WEBSITE/index.html)
- **Particles**: Reduce count from 120 to 40 and connection distance from 110 to 80.
- **Orbs**: Remove drift animations from `.orb1, .orb2, .orb3` and set static visibility.
- **3D Tilt**: Disable mouse-triggered tilt on all cards.
- **will-change**: Apply `will-change: transform` to carousel track and hero orbit only.
- **Animations**: Set `animation-play-state: paused` for non-visible components (using IntersectionObserver).
- **Images**: Add `decoding="async"` to all carousel images.

### [Component] Service Cards (FIX 2)
#### [MODIFY] [index.html](file:///c:/Users/chitr/Downloads/my websites/OCTAVIUM CORE WEBSITE/index.html)
- Ensure all `.srv-card` elements have `opacity: 0` for their `::before` and `::after` overlays by default (including the first one).

### [Component] Mobile Layout (FIX 3 & 4)
#### [MODIFY] [index.html](file:///c:/Users/chitr/Downloads/my websites/OCTAVIUM CORE WEBSITE/index.html)
- **Process Section**: Implement a vertical stacked layout with a left-side timeline for mobile devices. Hide horizontal timeline elements.
- **Grids**: Ensure all grids (Services, Why, Testimonials, Pricing) switch to single-column on mobile.
- **Hero Stats**: Layout in a 2x2 grid on mobile.

## Verification Plan
### Manual Verification
- Test scroll performance on desktop (smooth scrolling and no lag).
- Verify mobile layout using browser devtools (mobile emulator).
- Confirm that the first service card does not have a persistent glow on load.
- Ensure the custom cursor is disabled on touch-enabled devices.
