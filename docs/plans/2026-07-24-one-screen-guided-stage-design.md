# Rae one-screen guided stage redesign

Date: 2026-07-24

## Objective

Replace the current long, multi-section marketing page with a calm, interactive
single-screen product story for external visitors. The redesigned experience
should communicate Rae's journey, features, value, and results without asking
visitors to process several competing sections at once.

## Experience principles

- One clear focal point at a time.
- The five-stage sales journey is the primary navigation.
- Product screenshots remain the source of truth.
- Results appear only where they support the selected stage.
- Photography adds atmosphere, not another content layer.
- Typography uses a restrained, consistent scale.
- Desktop is locked to one viewport; mobile may use a short controlled layout.

## Desktop layout

The page occupies one `100dvh` canvas with four layers:

1. A small Rae SVG brand mark, without a conventional navigation bar.
2. A centered headline: “AI-powered Business Enablement Ecosystem,” followed
   by one concise explanatory sentence.
3. A five-step Journey control above one large, centered product screenshot.
4. A compact contextual area containing one feature statement and up to two
   relevant impact figures.

The page will not include the existing problem section, ecosystem card grid,
long journey scrollytelling, demo, roadmap, closing section, or persistent
results crawler.

## Guided stages

| Stage | Primary feature | Atmospheric direction | Contextual impact |
| --- | --- | --- | --- |
| Research | Rae Chat and News Feed | Connected city or information landscape | 5,000+ conversations and time saved |
| Qualify | Persona intelligence | Human-scale architecture and perspective | Buyer-specific messaging |
| Propose | Proposal Generator | Structured editorial workspace | 400+ proposals and multi-million TCV |
| Practise | Sales Simulator | Focused preparation environment | Objection practice before live meetings |
| Share | Digital Profile and follow-up | Connected horizon and communication | 400+ bespoke content pieces |

Selecting a stage crossfades the atmospheric image, replaces the product
screenshot, updates the feature statement, and reveals only the relevant proof.
The layout remains fixed during the transition.

## Visual system

- Use `assets/rae-logo.svg` as the brand mark.
- Retain Rae's deep navy foundation and yellow active accent.
- Use one licensed, locally stored, compressed atmospheric image per stage.
- Apply consistent navy colour grading so photography remains subordinate.
- Present real Rae screenshots in a refined browser mockup with subtle
  perspective, edge lighting, and tinted shadow.
- Limit the visible type hierarchy to a display heading, interface labels, and
  body/supporting copy.
- Avoid multiple cards, decorative icon grids, excessive gradients, and
  competing animation.

## Detail overlay

Clicking the main screenshot or feature label opens a full-viewport overlay for
the selected stage. The overlay contains an enhanced gallery of relevant Rae
screens, a concise feature explanation, previous and next controls, a clear
close control, keyboard arrow support, Escape-to-close behaviour, and managed
keyboard focus.

The overlay keeps visitors in the one-screen experience instead of navigating
to the existing feature-detail pages.

## Responsive behaviour

Desktop and large tablets use a locked viewport. On smaller screens, the same
content order becomes a short, controlled vertical layout to preserve
readability. The detail experience becomes a full-screen panel.

## Technical design

The existing vanilla HTML, CSS, and JavaScript stack remains in place. A single
JavaScript data structure will define each stage's labels, copy, screenshots,
gallery, atmospheric asset, and proof points. One render function will update
the visible state.

No new framework or runtime dependency is required. Existing feature pages and
assets remain in the repository, even though the redesigned home page no longer
links visitors away from the main experience.

## Accessibility and verification

- Use semantic buttons and landmarks.
- Provide visible focus states and meaningful image alternatives.
- Support keyboard navigation for stages and the gallery.
- Respect `prefers-reduced-motion`.
- Prevent background interaction while the overlay is open.
- Verify desktop, tablet, and mobile layouts.
- Verify all five stage transitions and every overlay gallery.
- Confirm there is no unintended vertical desktop scroll.
