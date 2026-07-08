# CLAUDE.md — Claude Code in this repo

This is `superheat-templates` — the brand asset repo for Superheat™ decks and papers.

**The full workflow and brand rules live in [`AGENTS.md`](AGENTS.md). Read it.**
This file only adds what's specific to Claude Code.

## Skills do the work

When someone asks for a deck or paper, the two skills in [`skills/`](skills/) fire
automatically — you don't need to wire anything up:

- Pitch / sales / investor deck, slides → **`superheat-pitch-deck`**
- White paper / memo / research report / one-pager → **`superheat-whitepaper`**

Each skill is the step-by-step playbook (locate repo → gather content → copy template →
fill → enforce brand → export). Follow it. If a user is in another project and the skill
isn't installed, point them at [`skills/README.md`](skills/README.md) to install it, or
just follow [`AGENTS.md`](AGENTS.md) directly.

## The rules you cannot break (summary — full list in AGENTS.md)

- One accent color: Superheat orange `#FF5500`. Never a second hue; ~one orange moment per slide.
- Three fonts only: **Geist** (headlines/body), **DM Mono** (all numbers), **Press Start 2P** (kickers/tags).
- Headlines: Geist weight 400, two-part (ink setup + `<span class="a">` orange payoff), written as claims.
- Every number is DM Mono. Emphasis is `<b>` (500), never 700, never italic (except doc titles).
- Wordmark carries `<sup>™</sup>`. Always keep the honest caveat in footnotes/captions.
- Always **copy** a `templates/` file and fill it — never write the brand CSS from memory.

## Editing the brand itself

The CSS is duplicated on purpose: canonical in `design-system/superheat-*.css`, inlined
in `templates/*/template.html`. **Any CSS change goes in both places in one commit.**
See [`CONTRIBUTING.md`](CONTRIBUTING.md). Don't add dependencies or a build step, don't
touch a template's `<script>`, and don't convert templates to link external CSS — the
self-contained single file is the feature.
