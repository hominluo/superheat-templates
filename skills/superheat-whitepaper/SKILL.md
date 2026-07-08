---
name: superheat-whitepaper
description: Build a branded Superheat™ white paper, memo, or research report (US-Letter HTML pages that export to PDF). Use whenever someone asks to create, draft, or restyle a Superheat whitepaper, memo, research report, one-pager, or long-form document that should match the Superheat brand.
---

# Superheat™ White-Paper Builder

You are producing a **brand-standard Superheat white paper / memo**: a single
self-contained HTML file of US-Letter (8.5×11in) pages that prints to a multi-page PDF.
It is the dense, footnoted twin of the pitch deck — same brand, more words per page.

## Step 1 — Locate the template repo

Find the `superheat-templates` repo (typically a sibling folder, e.g.
`../superheat-templates` or `~/Documents/Github/superheat-templates`). You need:

- `templates/whitepaper/template.html` — the scaffold to copy.
- `design-system/README.md` — the brand rules (read it once).
- `components/README.md` — copy-paste markup for every block.

If you can't find the repo, ask the user for its path. Do **not** reconstruct the CSS
from memory — start from the template so the brand CSS is exact.

## Step 2 — Gather the content

Use any source material the user provides (research, data, an existing deck). Otherwise
ask for: the document type (whitepaper / internal memo / one-pager), the thesis, the
sections, the key numbers and tables, and the audience/confidentiality level. Prefer
inferring from context over interrogating.

## Step 3 — Build the document

1. **Copy** `templates/whitepaper/template.html` to the target file. Don't edit the
   template in place.
2. **Set the cover** (orange): doc type, title in two lines, one-paragraph abstract,
   and the confidentiality/date foot.
3. **Set the memo header** on page 2: Re / Date / Sources.
4. **Write the body** — replace every `[[PLACEHOLDER]]`. Each `<section class="page">`
   is exactly one printed page; compose from:

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

5. **Paginate:** keep pages from overflowing. Renumber every `.pfoot` (`02 / 09` …) to
   match the final page count.

## Step 4 — Enforce the brand (non-negotiable)

- **One accent color only** (`#FF5500`): section numbers, stat numbers, key table cells,
  callout borders, inline `<span class="a">`. Nothing else colored.
- **Type discipline:** body is Geist 300 at `9.4pt`; every figure is **DM Mono**;
  emphasis is `<b>` (weight 500), never 700 and never italic except document titles.
- **Sizing is in points (pt)** — it maps 1:1 to the printed page. Never switch to px/rem.
- **Wordmark** always carries `<sup>™</sup>`.
- **Sourcing is the standard.** Cite live data in `.tbl-cap`; end with an "Assumptions
  and sourcing" `.small` block that lists assumptions to replace with actuals and cites
  every external fact. State the optimistic number *and* the honest caveat.
- **Voice:** claims, not labels; numbers first, adjectives never; name the failure modes
  (include a risk register / anti-pattern section for anything investment-facing).
- **Don't** modify the `<style>` block.

## Step 5 — Verify & hand off

- Every `[[…]]` replaced; page footers numbered correctly; no page overflowing in print
  preview; the thesis stated in the exec summary and echoed in the conclusion.
- Tell the user to open in Chrome and export: **Print → Save as PDF → Portrait → Paper
  Letter → Margins None → Background graphics ON.**

When unsure on any rule, re-read `design-system/README.md` in the repo — it is the source
of truth. If the user also wants a deck, the [`superheat-pitch-deck`](../superheat-pitch-deck/)
skill turns this paper's stats, tables, and headlines into one-idea-per-slide summaries.
