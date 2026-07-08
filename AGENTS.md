# AGENTS.md — building Superheat™ decks & papers with an AI agent

This file is the **tool-agnostic playbook** for any coding agent (Codex, Cursor,
Claude Code, Copilot, etc.) working in `superheat-templates`. It is the source of
truth for the workflow and brand rules; `CLAUDE.md` defers to it.

> **Task in one line:** copy a template from `templates/`, fill it with the user's
> content, enforce the brand rules below, and hand back a self-contained HTML file that
> prints to PDF. Never write the brand CSS from memory.

---

## When to act

Trigger this workflow whenever a user asks to create, draft, restyle, or "make on-brand"
any of: a Superheat **pitch deck / sales deck / investor deck / slides**, or a Superheat
**white paper / memo / research report / one-pager**.

- Deck-type request → use `templates/pitch-deck/template.html`.
- Paper-type request → use `templates/whitepaper/template.html`.

If both are wanted, build the paper first (full argument, sourced), then lift its stats,
tables, and headlines into the deck as one-idea-per-slide summaries.

---

## The workflow (do this every time)

1. **Read the rules once.** Open `design-system/README.md` (brand bible) and
   `components/README.md` (copy-paste markup). For the step-by-step procedure, the
   matching skill file is the detailed playbook:
   - `skills/superheat-pitch-deck/SKILL.md`
   - `skills/superheat-whitepaper/SKILL.md`

   (In Claude Code these load automatically as skills. In Codex/others, just open and
   follow them — they are plain Markdown.)

2. **Gather content.** Use whatever source material the user provided (a memo, notes,
   numbers, an existing doc). Otherwise ask briefly for: audience, the one-line thesis,
   3–5 proof points/numbers, and any tables. Infer from context where reasonable; don't
   interrogate.

3. **Copy, don't edit in place.** Copy the template to the user's target file
   (e.g. `my-deck.html`). Leave `templates/` untouched.

4. **Fill every `[[placeholder]]`.** Compose from the block catalog (below). Add or
   remove `<section>` blocks freely — deck navigation, counter, and progress bar update
   themselves.

5. **Enforce the brand.** Run the checklist below before handing off.

6. **Tell the user how to view & export** (see "Export").

---

## Non-negotiable brand rules

- **One accent color:** Superheat orange `#FF5500`. Never introduce a second hue.
  Aim for **one orange moment per slide/section** — the payoff word, the key number, or
  the winning table cell.
- **Three fonts only**, from Google Fonts (the `<link>` is already in every template):
  **Geist** (headlines & body), **DM Mono** (every number & data label),
  **Press Start 2P** (pixel kickers & `> TAG_` marks). Nothing else.
- **Headlines** are Geist **weight 400** (not bold), two-part: setup in ink/white +
  payoff in `<span class="a">orange</span>`. Write them as **claims, not labels**
  ("Honest Numbers." not "Financials").
- **Every number is DM Mono** — use `.stat .n` / `td.num`; never set figures in Geist.
- **Emphasis is `<b>` (weight 500)** — never 700, never italic except document titles.
- **Wordmark always carries** `<sup>™</sup>`.
- **Keep the honest caveat** in `.foot-note` / `.tbl-note` / `.tbl-cap` / `.small`. The
  Superheat voice states the optimistic number *and* the caveat. Never delete a caveat to
  tidy a slide. Cite live data inline (`· Vast.ai · 06.11.2026`).
- **Deck rhythm:** alternate `dark` / `light` themes; reserve `orange` for cover, section
  breaks, and the close (≤3 total). One idea per slide.
- **Don't** touch a template's `<script>` (deck navigation/theme sync) or the `<style>`
  block beyond synced brand changes. **Don't** add dependencies, a build step, gradients,
  or link to external CSS — the self-contained single file is the feature.

---

## Block catalog

**Deck** (each block lives in `<section class="slide dark|light|orange">`):

| Need | Block |
|---|---|
| Open / close | `orange .cover` |
| Argument as pipeline | `dark` + `.flow` |
| Old vs. new | `light` + `.eq` |
| Proof numbers | `dark` + `.stats c3/c4` |
| Comparison / market data | `light` + `.tbl-wrap` |
| Parallel concepts | `dark` + `.cards c2/c3` |
| Trend | `light` + `.bars` |
| Next steps | `light` + `.nlist` |

**White paper** (each block lives in `<section class="page">`):

| Need | Block |
|---|---|
| Section | `<h2><span class="no">N</span>Title</h2>` |
| Lead paragraph | `<p class="lede">` |
| The one line to remember | `.callout` |
| Headline numbers | `.stats` / `.stats.c3` |
| Data | `<table>` + `.tbl-cap` (`td.num`, `td.hl`) |
| Side-by-side | `.cols` |
| Action items | `.calls` |
| Assumptions / sourcing | `.small` |

Full markup for each → `components/README.md`.

---

## Pre-flight checklist

- [ ] Every `[[…]]` placeholder replaced.
- [ ] Exactly one accent color; ~one orange moment per slide/section.
- [ ] Every number is DM Mono; headlines are Geist 400 with an orange payoff.
- [ ] Kicker on each content slide (deck); numbered `<h2>` sections (paper).
- [ ] Wordmark carries `™`; honest caveats present, not deleted.
- [ ] Deck: dark/light alternate, orange ≤3, counter total matches slide count.
- [ ] Paper: page footers renumbered; no page overflows in print preview.
- [ ] One thesis carried from cover to close.

---

## Export

Both templates print from Chrome with zero setup (`Ctrl/Cmd-P` → **Save as PDF**,
**Background graphics ON**, **Margins None**):

- **Deck** → Layout **Landscape**, paper `1280×720` if offered. View: open in Chrome,
  navigate with ← → space.
- **White paper** → Layout **Portrait**, paper **Letter (8.5×11)**.

---

## Editing the brand itself (maintainers)

The brand CSS is duplicated on purpose: canonical in `design-system/superheat-*.css`,
inlined in `templates/*/template.html`. **Any CSS change must be applied in both places
in the same commit.** See `CONTRIBUTING.md`. Do not convert templates to link external
CSS — portability is the point.
