# Guidance for Claude working in this repo

This is `superheat-templates` — the brand asset repo for Superheat decks and papers.

## When someone asks for a deck or paper

Use the skills in [`skills/`](skills/):
- Pitch/sales deck → the `superheat-pitch-deck` skill.
- White paper / memo / report → the `superheat-whitepaper` skill.

Always **copy** a file from `templates/` and fill it in. Never write the brand CSS from
memory — start from the template so it's exact. Read `design-system/README.md` for the
rules and `components/README.md` for markup.

## Non-negotiable brand rules

- One accent color: Superheat orange `#FF5500`. Never a second hue.
- Three fonts only: Geist (headlines/body), DM Mono (all numbers), Press Start 2P
  (kickers/tags). Loaded from Google Fonts.
- Headlines: Geist weight 400, two-part (ink setup + `<span class="a">` orange payoff),
  written as claims not labels.
- Every number is DM Mono. Emphasis is `<b>` (500), never 700, never italic (except doc
  titles).
- One orange moment per slide. Keep the honest caveat in footnotes/captions.
- Wordmark always carries `<sup>™</sup>`.

## Editing the templates or CSS

The brand CSS is duplicated on purpose: canonical in `design-system/superheat-*.css`,
inlined in `templates/*/template.html`. **Any CSS change must be applied in both places
in the same commit.** See [`CONTRIBUTING.md`](CONTRIBUTING.md). Don't convert the
self-contained templates to link external CSS — that portability is the point.

## What not to do

- Don't add dependencies or a build step. These are zero-build, self-contained HTML files.
- Don't touch a template's `<script>` (deck navigation/theme) or its `<style>` structure
  beyond synced brand changes.
- Don't add a second accent color, gradients, or fonts outside the three.
