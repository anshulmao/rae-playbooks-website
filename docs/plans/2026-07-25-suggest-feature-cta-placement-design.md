# Suggest feature CTA placement

Date: 2026-07-25

## Objective

Remove the implied relationship between “Suggest a feature” and Product
Playground by promoting the suggestion action to the main “What’s next” CTA row.

## Placement

The CTA row contains:

1. Try Rae
2. Suggest a feature
3. Return to journey

Product Playground retains its roadmap description but no nested action.

## Behavior

- Preserve the existing suggestion-dialog trigger and form behavior.
- Preserve focus restoration when the dialog closes.
- Rename the visual button class so its styling is not coupled to Product
  Playground.
- Retain responsive wrapping within the existing CTA row.

## Verification

- Confirm “Suggest a feature” appears only once.
- Confirm it is not nested inside the Product Playground roadmap item.
- Confirm it opens the existing suggestion dialog.
- Confirm the CTA row wraps cleanly at responsive widths.
