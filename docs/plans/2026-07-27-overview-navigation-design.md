# Overview navigation design

## Goal

Give users an obvious way to return to the opening Overview screen and reduce excess vertical space below the fixed header on mobile.

## Header control

- Add a compact “← Home” button to the story-navigation area of the shared header.
- Show the control on the Journey and What’s Next screens.
- Hide it on Overview, where returning home would be redundant.
- Use the existing `data-go-screen="overview"` navigation behavior so transitions, history, focus, and accessibility remain consistent.

## Mobile spacing

- Reduce the mobile content offset below the fixed header while retaining device safe-area padding.
- Reduce the mobile margin between the stage counter and journey introduction.
- Keep the header and content visually separated without the large empty band shown in the reference screenshot.

## Responsive behavior

- Keep the control readable and touch-friendly at narrow widths.
- Preserve room for the brand lockup and story-position dots.
- Avoid horizontal overflow at the existing 320px minimum supported width.

## Verification

- Confirm the Home control appears on Journey and What’s Next, returns to Overview, and is hidden on Overview.
- Check header geometry and horizontal overflow at 320px, 390px, tablet, and desktop widths.
- Visually verify the reduced mobile top spacing.
- Run inline JavaScript and whitespace checks.
