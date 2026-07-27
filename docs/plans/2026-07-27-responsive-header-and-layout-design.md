# Responsive header and layout design

## Goal

Improve the Rae story experience across desktop, tablet, mobile, and short landscape viewports without changing its content or interaction model.

## Header

- Give the shared story header a solid deep-navy surface so the Rae and CelcomDigi marks remain legible over every stage photograph.
- Keep the header visible while the active screen scrolls.
- Add a restrained lower divider and support device safe-area insets.
- Preserve the existing brand link and three-screen story navigation.

## Photo credits

- Remove the visible Unsplash credit anchor from the journey screen.
- Remove the related DOM lookup and per-stage text/link updates.
- Keep the locally stored atmosphere images and their internal source documentation.

## Responsive behavior

- Preserve the current three-column journey composition on sufficiently large viewports.
- Move tablet and mobile layouts into normal document flow so story copy, product imagery, impact metrics, and navigation cannot overlap.
- Let journey stage tabs scroll horizontally on narrow screens.
- Keep the final journey CTA in normal flow below the content on smaller and short viewports.
- Use dynamic viewport units and safe-area padding for mobile browsers.
- Constrain text and media widths, use fluid spacing and type, and prevent fixed minimum dimensions from forcing horizontal overflow.

## Accessibility and interaction

- Retain visible keyboard focus states, tab semantics, screen navigation, dialogs, and reduced-motion behavior.
- Maintain touch-friendly control sizes.
- Ensure the sticky header does not cover anchored or focused content.

## Verification

- Check the overview, journey, and next screens at representative desktop, tablet, mobile portrait, and short landscape sizes.
- Confirm there is no horizontal overflow or overlap between the header, stage content, bottom CTA, and viewport edges.
- Confirm the Unsplash credit is absent from rendered markup and stage-update JavaScript.
- Run JavaScript syntax and whitespace checks.
