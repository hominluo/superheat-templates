# Contributing to Superheat Templates

This repo is a **brand asset**. Small, deliberate changes — not churn. The goal is that
every Superheat deck and paper stays visually identical over time.

## The one thing to know: CSS lives in two places by design

- `design-system/superheat-*.css` — the **canonical, documented** source.
- `templates/*/template.html` — the **inlined** copy, so each template is a single
  self-contained file you can email/print with no build step.

They must stay identical. When you change a brand rule:

1. Edit the rule in the relevant `design-system/superheat-*.css`.
2. Re-inline it into the affected `templates/*/template.html` `<style>` block
   (copy the changed rule across verbatim).
3. If it's a token (color, font), also update the token table in
   `design-system/README.md` and the snippet in `components/README.md`.
4. Sanity-check by opening both a template and the reference doc — they should match.

This duplication is intentional. Don't "fix" it by making templates link to the external
CSS: self-contained files are the feature (they survive being copied out of the repo).

## Changing brand fundamentals

Color, the three font families, and the core type moves are the brand. Change them only
with sign-off, and change them **everywhere** in one commit (both CSS files, both
templates, both READMEs, the component gallery). A half-applied brand change is worse
than none.

## Adding a component

1. Add the CSS to the right `design-system/superheat-*.css` (deck and/or whitepaper).
2. Inline it into the template(s) and add a scaffold block with `[[placeholders]]`.
3. Add a copy-paste entry to `components/README.md`.
4. Reference it in the template's `README.md` catalog table.

Keep new components consistent with the existing ones: same tokens, same border-radius
(`16px` cards / `14px` list items on deck), same accent discipline (one orange moment).

## Testing a change

There's no build. Verify by eye in Chrome:

- Open the edited template — fonts load, layout holds, themes switch (deck).
- `Ctrl/Cmd-P` → Save as PDF with **Background graphics ON** — colors and backgrounds
  render; deck is landscape `1280×720`, paper is portrait Letter with correct page breaks.
- Diff against the reference deck/whitepaper for drift.

## Style of the docs

Match the existing READMEs: terse, table-driven, example-first. The brand voice
(claims not labels, numbers first) applies to our own docs too.
