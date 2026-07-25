# Screenshot-specific feature stories

Date: 2026-07-25

## Objective

Make the feature gallery's left panel tell a complete, distinct story for every
screenshot, instead of retaining generic stage copy while only the screenshot
caption changes.

## Content model

Each gallery image carries its own story data:

- an eyebrow identifying the feature step;
- a concise, screenshot-specific headline;
- a supporting paragraph with fuller context;
- a "Solution in view" statement describing the concrete outcome.

Changing a screenshot updates all left-panel fields, the image, active
thumbnail, and counter together. The top-level stage title remains the entry
point that opens the gallery; it is not reused as static content inside it.

## Controls

- Remove the visible "Browse" and "Esc Close" keyboard-control guide.
- Keep existing keyboard behavior and accessible labels unchanged.
- Retain circular previous and next buttons, with each arrow centered both
  horizontally and vertically, and aligned with its counterpart.

## Verification

- Browse each screenshot in all five stages and confirm that the complete
  left-side story is unique to the selected image.
- Confirm arrows, thumbnails, and keyboard navigation select the same content.
- Confirm no keyboard-guide text remains visible.
- Check the navigation controls at desktop and responsive breakpoints for
  centered, aligned arrows.
