# Product Playground suggestion form

Date: 2026-07-24

## Objective

Replace “Co-create what comes next” on the What’s next screen with “Product
Playground” and give CelcomDigi teams a clear way to suggest new Rae features.

## What’s next screen

The third roadmap item becomes:

- Title: “Product Playground”
- Description: “Test early ideas, share what your team needs, and help shape
  the next Rae workflow.”
- Action: “Suggest a feature”

The action opens a modal so the existing three-screen experience remains
contained within one desktop viewport.

## Suggestion form

The modal collects:

- Name
- Team or role
- Feature suggestion
- Problem it would solve
- Expected impact

Name, feature suggestion, and problem are required. Team or role and expected
impact are optional.

## Email handoff

The site remains static and does not claim to submit data in the background.
Submitting the form opens the visitor’s default email client with:

- To: `anshul@twimbit.com`
- CC: `parthiben@celcomdigi.com`, `darrylteo@celcomdigi.com`
- Subject: “Rae Product Playground feature suggestion”
- Body: a clearly labelled summary of every completed form field

The submit button says “Review and send email” to set an accurate expectation.

## Interaction and accessibility

- Use a native dialog where supported.
- Restore focus to the Product Playground action after closing.
- Support Escape-to-close and backdrop click.
- Show clear labels above every field.
- Display inline validation for required fields.
- Use a high-contrast yellow primary action and a visible close button.
- Keep the form usable on mobile through internal dialog scrolling.

## Verification

- Confirm Product Playground replaces the previous roadmap item.
- Confirm the modal opens and closes from keyboard and pointer input.
- Confirm required-field validation is visible and focus moves to the first
  invalid field.
- Confirm the generated email has the correct To, CC, subject, and body.
- Confirm no form data is stored by the page.
- Confirm focus returns to “Suggest a feature” after closing.
- Confirm desktop and mobile layouts do not overflow horizontally.
