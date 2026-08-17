# Analytics (Google Analytics 4)

This site sends usage data to Google Analytics 4 (GA4), Measurement ID
`G-LBB1BJSGF4`, property "Rae Playbook Campaign" (Twimbit GA4 account).

The GA4 tag (`gtag.js`) is installed immediately after the opening `<head>`
tag on every page of the site — `index.html` and all six
`feature-*.dc.html` story pages — so every page is tracked, not just the
landing page.

## Where to view the data

- **Live / right now:** [analytics.google.com](https://analytics.google.com) →
  select the `explorae` property → **Reports → Realtime overview**. Updates
  within seconds. Use this to confirm tracking is working or to watch a demo
  click-through live.
- **Historical trends:** **Reports → Engagement → Events** (or **Pages and
  screens** for pageviews, **Acquisition** for traffic sources). Standard
  reports have a 24–48 hour processing delay — "No data available" on a
  same-day view is expected, not broken.
- **Custom breakdowns** (e.g. "which journey stage gets the most views"):
  left sidebar → **Explore**, build a free-form report using an event's
  parameters (`stage_name`, `cta_label`, etc.) as a dimension.

## What GA4 tracks automatically

No code in this repo is responsible for these — GA4's base tag and default
"Enhanced measurement" produce them on every page:

| Event | Fires when |
|---|---|
| `page_view` | A page loads |
| `session_start` | A new session begins (new visitor, or returning after 30+ min idle) |
| `first_visit` | The browser has never been seen by this property before |
| `scroll` | Visitor scrolls 90% down a page |
| `user_engagement` | Periodic "still active" ping used to compute engaged time |
| `click` | Outbound link to a different domain is clicked |

Plus, without any custom event at all: total users, unique visitors,
pageviews, sessions, device/browser/OS, country/city, and traffic source
(direct, referral, social, etc.).

## Custom events defined in this repo

These are fired explicitly from `index.html`'s inline `<script>` via a small
`trackEvent(name, params)` helper (defined near the top of the script,
wrapping `gtag('event', name, params)` — see `index.html`). They exist to
measure engagement with the actual journey story, not just raw pageviews.

| Event | Fires when | Parameters | Where in `index.html` |
|---|---|---|---|
| `screen_view` | Visitor moves between the Overview / Journey / "What's next" screens | `screen_name` | `setScreen()` |
| `journey_stage_view` | Visitor opens one of the 5 journey stage tabs (Research, Qualify, Propose, Practise, Share) | `stage_name`, `stage_index` | `setStage()` |
| `feature_gallery_open` | Visitor opens a feature's screenshot gallery dialog | `stage_name` | `openGallery()` |
| `cta_click` | Visitor clicks the "Try Rae" link | `cta_label` | `try-rae-link` click listener |
| `feature_suggestion_open` | Visitor opens the "Suggest a feature" form | — | `openSuggestionForm()` |
| `feature_suggestion_submitted` | Visitor completes and submits the suggestion form | — | suggestion form `submit` listener |

`journey_stage_view` and `feature_gallery_open` deliberately share
`stage_name` so you can compare "who looked at a stage" vs. "who actually
opened its feature gallery" per stage.

## Marking an event as a conversion ("key event")

None of the custom events above are marked as conversions by default. To
promote one (e.g. `cta_click`, since it's the main call to action):
**Admin → Events**, find the event name, toggle **"Mark as key event"**.
This makes it show up in the "Key events by Event name" card and in
conversion-focused reports.

## Adding a new event

Call the existing `trackEvent(name, params)` helper from the relevant
interaction handler, the same way the events above do — do not call
`gtag('event', ...)` directly. Keep event names in `snake_case` and
parameters descriptive (e.g. `stage_name` rather than `s`), matching GA4's
own naming convention for automatic events.

## Known limitation

`cta_click` records that a visitor clicked "Try Rae," but nothing beyond
that — the destination app at `rae.salesrechargekit.ai` is a separate
system with no shared analytics, so this site cannot see what a visitor
does after leaving it.
