---
name: superheat-pitch-deck
description: Build a branded Superheat™ pitch deck or sales deck (16:9 HTML slides that export to PDF). Use whenever someone asks to create, draft, or restyle a Superheat pitch deck, sales deck, investor deck, or slide presentation, or wants slides that match the Superheat brand.
---

# Superheat™ Pitch-Deck Builder

You are producing a **brand-standard Superheat pitch deck**: a single self-contained
HTML file of 16:9 slides that navigates in the browser and prints to a `1280×720` PDF.

## Step 1 — Locate the template repo

Find the `superheat-templates` repo (typically a sibling folder, e.g.
`../superheat-templates` or `~/Documents/Github/superheat-templates`). You need:

- `templates/pitch-deck/template.html` — the scaffold to copy.
- `design-system/README.md` — the brand rules (read it once).
- `components/README.md` — copy-paste markup for every block.

If you can't find the repo, ask the user for its path. Do **not** invent the CSS
from memory — always start from the template so the brand CSS is exact.

## Step 2 — Gather the content

If the user gave you source material (a memo, notes, numbers), use it. Otherwise ask
for: the audience (investors / customers / partners), the core thesis in one line, the
3–5 proof points or numbers, and any tables/data. Keep asking-light — infer from
context where you reasonably can.

## Step 3 — Build the deck

1. **Copy** `templates/pitch-deck/template.html` to the user's target file
   (e.g. `my-deck.html`). Never edit the template in place.
2. **Set the frame:** `<title>`, the `.doc-tag` (a mono string like
   `Compute-Backed Finance · MM.YYYY`), and the closing tagline.
3. **Compose slides** from the catalog — replace every `[[PLACEHOLDER]]`. Add/remove
   `<section class="slide …">` blocks freely; navigation and the counter auto-update.

   | Need | Slide |
   |---|---|
   | Open / close | `orange .cover` |
   | Argument as pipeline | `dark` + `.flow` |
   | Old vs. new | `light` + `.eq` |
   | Proof numbers | `dark` + `.stats c3/c4` |
   | Comparison / market data | `light` + `.tbl-wrap` |
   | Parallel concepts | `dark` + `.cards c2/c3` |
   | Trend | `light` + `.bars` |
   | Next steps | `light` + `.nlist` |

## Step 4 — Enforce the brand (non-negotiable)

- **One accent color only** (`#FF5500`). Roughly **one orange moment per slide** — the
  payoff word in the headline, the number that matters, or the winning table cell.
- **Headlines** are Geist weight 400, two parts: setup in ink/white + payoff in
  `<span class="a">orange</span>`. They are *claims*, not labels ("Honest Numbers."
  not "Financials").
- **Every number is DM Mono** — use the `.stat .n` / `td.num` classes; never set
  figures in Geist.
- **Kicker** (Press Start 2P, orange, uppercase) on every content slide.
- **Wordmark** always carries `<sup>™</sup>`.
- **Keep the honest caveat** in `.foot-note` / `.tbl-note`. The Superheat voice states
  the optimistic number *and* the caveat. Never delete a caveat to clean up a slide.
- **One idea per slide.** If two elements are fighting, split into two slides.
- **Theme rhythm:** alternate `dark` / `light`; reserve `orange` for cover, section
  breaks, and the close (≤3 total).
- **Don't** touch the `<style>` block or delete the `<script>` (drives nav + theme sync).

## Step 5 — Verify & hand off

- Open the file mentally/structurally: every `[[…]]` replaced, counter total matches
  slide count, one thesis carried front to back.
- Tell the user how to view (open in Chrome; ← → space to navigate) and export
  (**Print → Save as PDF → Landscape → Margins None → Background graphics ON**,
  paper `1280×720` if offered).

When in doubt on any rule, re-read `design-system/README.md` in the repo — it is the
source of truth. Match the reference deck's density and voice; don't over-explain on a
slide when a number and a caveat will do.
