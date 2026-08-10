# Responsive feature gallery design

## Goal

Prevent feature-gallery screenshots from overlapping their feature-story copy at constrained viewport sizes while preserving the existing large, two-column desktop presentation.

## Layout contract

- Wide, sufficiently tall viewports retain the current two-column dialog with the story panel beside the gallery.
- Tablet, mobile, and short-height viewports switch the dialog content to a single, normal-flow column: story first, gallery second.
- The dialog content may scroll vertically in these constrained layouts. The gallery itself must size from its available inline width and must not require a fixed minimum height.
- The screenshot frame keeps its natural visual proportion, is capped by available viewport height only when appropriate, and never extends into the story panel.
- Gallery controls, counter, and thumbnail rail remain within the gallery’s normal layout flow and retain touch-friendly dimensions.

## Verification

- Exercise each stage’s feature story at desktop, tablet portrait and landscape, mobile portrait, and short landscape dimensions.
- Confirm no story/media overlap, no horizontal document overflow, and usable close, previous, next, and thumbnail controls.
- Run JavaScript syntax and whitespace checks after the CSS-only change.
