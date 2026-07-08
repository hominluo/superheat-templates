# Pitch / Sales Deck Template

A self-contained, brand-standard 16:9 slide deck. One HTML file, no build step,
prints to a clean `1280×720` PDF. Built on the [Superheat Design System](../../design-system/).

## Quick start

1. **Copy** `template.html` into your deck folder and rename it (`gpu-pitch-deck.html`).
2. **Set the frame:** the `<title>`, the `.doc-tag` in the chrome, and the closing
   tagline. Update the `.counter` if you want a fixed total (it auto-counts anyway).
3. **Fill the slides.** Every editable spot is marked `[[LIKE THIS]]`. Duplicate or
   delete `<section class="slide …">` blocks freely — navigation, the counter, and the
   progress bar all update automatically.
4. **Preview** in Chrome. Navigate with **← → space PageUp/Down Home End**.
5. **Export to PDF:** `Ctrl/Cmd-P` → Destination **Save as PDF** → Layout **Landscape**
   → Margins **None** → **Background graphics ON**. Choose paper `1280×720` if offered,
   otherwise any landscape size works.

## Slide catalog

Each slide is one `<section class="slide THEME">`. Pick a theme, pick a body layout.

| # | Slide | Theme | Body layout | Use it for |
|---|---|---|---|---|
| 01 | **Cover** | `orange` | `.cover` | Title + tagline + one-line promise. |
| 02 | **Thesis + Flow** | `dark` | `.flow` | The core argument as a pipeline of steps. |
| 03 | **Equation / Reframe** | `light` | `.eq` | Old way vs. Superheat way, side by side. |
| 04 | **Stats** | `dark` | `.stats c3/c4` | 3–4 proof numbers. |
| 05 | **Table** | `light` | `.tbl-wrap` | Dense comparison / market data. |
| 06 | **Cards** | `dark` | `.cards c2/c3` | Parallel concepts (layers, products, reasons). |
| 07 | **Bars** | `light` | `.bars` | A simple honest trend chart. |
| 08 | **Numbered list** | `light` | `.nlist` | Action items / next steps (5-up grid). |
| 09 | **Close** | `orange` | `.cover` | Restate the thesis as a memorable line. |

These are the building blocks, not a required order. A real deck reorders, repeats,
and drops them — the reference [`superheat_strategy_deck`](../../examples/) uses 30 slides
built from exactly these nine patterns.

## Themes — when to use each

- **`dark`** — the default; most content slides.
- **`light`** — tables and dense data (easier to read); use it to break up runs of dark.
- **`orange`** — cover, section breaks, closing punchline **only**. Loud on purpose; ≤3 per deck.

Alternate `dark` / `light` so consecutive slides don't blur. See the design system's
[rhythm rules](../../design-system/README.md#5-rhythm--layout-rules).

## Component cheatsheet

| Want | Markup |
|---|---|
| Orange word in a headline | `<span class="a">word</span>` |
| A number | `<div class="n">$0.40<small>/hr</small></div>` inside `.stat` |
| Highlight a table cell | `<td class="num hl">$0.40</td>` |
| A caveat / footnote | `<p class="foot-note">…</p>` |
| A flow arrow | `<span class="arr">→</span>` between `.step`s |

Full copy-paste gallery: [`components/README.md`](../../components/README.md).

## Do / don't

- **Do** keep one idea per slide and one orange moment per slide.
- **Do** keep the honest caveat in `.foot-note` / `.tbl-note`.
- **Don't** add a second accent color, bold headlines to 700, or set numbers in Geist.
- **Don't** delete the `<script>` — it drives navigation and theme sync.

Prefer to have Claude build it for you? Use the
[`superheat-pitch-deck` skill](../../skills/superheat-pitch-deck/).
