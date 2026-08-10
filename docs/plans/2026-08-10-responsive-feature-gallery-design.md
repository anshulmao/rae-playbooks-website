# Responsive feature gallery design

## Goal

Prevent feature-gallery screenshots from overlapping their feature-story copy at constrained viewport sizes while preserving the existing single-viewport presentation.

## Layout contract

- Wide, sufficiently tall viewports retain the current two-column dialog with the story panel beside the gallery.
- Tablet and mobile viewports switch the dialog content to a single, normal-flow column: story first, gallery second.
- Short-height and browser-zoomed desktop viewports retain a compact two-column dialog. Desktop pointer/hover capability, rather than the CSS width produced by browser zoom, selects this treatment; type, spacing, controls, and the gallery frame reduce within the available viewport instead of switching the document into vertical scrolling.
- The overview screen retains its two-column composition in the same compact desktop range, with its product visual and annotation scaled to the available grid space.
- The overview product visual and its annotation remain level at every viewport size.
- All top-level story screens preserve their desktop grids in the compact range: the journey condenses its stage panel and the final roadmap screen condenses its copy and rows rather than changing to a scrollable single column.
- The compact journey override restores all three stage-panel columns, its fixed next-step control, and their desktop alignment after the narrower-layout defaults have applied.
- The screenshot frame keeps its natural visual proportion, is capped by available viewport height only when appropriate, and never extends into the story panel.
- Gallery controls, counter, and thumbnail rail remain within the gallery’s normal layout flow and retain touch-friendly dimensions.

## Verification

- Exercise each stage’s feature story at desktop, tablet portrait and landscape, mobile portrait, and short landscape dimensions.
- Confirm no story/media overlap, no document scrolling on the single-viewport experience, no horizontal overflow, and usable close, previous, next, and thumbnail controls.
- Run JavaScript syntax and whitespace checks after the CSS-only change.
