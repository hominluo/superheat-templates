# White Paper / Memo Template

A self-contained, brand-standard US-Letter document. One HTML file, no build step,
prints to a clean multi-page PDF. Built on the [Superheat Design System](../../design-system/).

## Quick start

1. **Copy** `template.html` and rename it (`superheat-market-memo.html`).
2. **Set the frame:** the `<title>`, the orange cover, and the `.memo-head` block on page 2
   (Re / Date / Sources).
3. **Write the body.** Every editable spot is marked `[[LIKE THIS]]`. Add or remove
   `<section class="page">` blocks — each one is exactly one printed page.
4. **Renumber footers.** Update the page count in each `.pfoot` (`02 / 09`, `03 / 09`, …).
   Watch for content overflowing a page in print preview and split where needed.
5. **Export to PDF:** `Ctrl/Cmd-P` → Destination **Save as PDF** → Layout **Portrait**
   → Paper **Letter (8.5×11)** → Margins **None** → **Background graphics ON**.

## Page & block catalog

The document is a stack of `<section class="page">` elements. Inside, compose from:

| Block | Markup | Use it for |
|---|---|---|
| **Cover** | `.page.cover` | Orange title page: wordmark, doc type, title, abstract, confidentiality line. |
| **Memo header** | `.memo-head` + `.memo-grid` | The Re / Date / Sources block at the top of page 2. |
| **Section head** | `<h2><span class="no">1</span>Title</h2>` | Numbered section. The `.no` is the orange section number. |
| **Sub-head** | `<h3>` | Sub-sections (3.1, 3.2 …). |
| **Lede** | `<p class="lede">` | The lead paragraph of a section — slightly larger. |
| **Callout** | `.callout` | The one line to remember — orange left border. |
| **Stat row** | `.stats` / `.stats.c3` | 3–4 headline numbers (DM Mono, orange). |
| **Table** | `<table>` + `.tbl-cap` | Dense data. `td.num` for figures, `td.hl` for the key cell. |
| **Bullets** | `<ul><li>` | Lists inside a section. |
| **Two-column** | `.cols` | Side-by-side blocks (e.g. Product A vs Product B). |
| **Call list** | `.calls` | Numbered action items in a 2-up grid. |
| **Small print** | `.small` | Assumptions, sourcing, footnotes. |
| **Page footer** | `.pfoot` | Running footer with brand string + orange page number. |

## Deck ↔ paper

The white paper is the **dense, footnoted twin** of the pitch deck: same brand, same
components, more words per page. A common workflow is to write the paper first (the
full argument, sourced) and then lift its stats, tables, and headlines into the
[pitch deck](../pitch-deck/) as one-idea-per-slide summaries.

## Do / don't

- **Do** keep body copy at the set `9.4pt` and size everything in **points** — it maps
  1:1 to the printed page. Don't switch to `rem`/`px`.
- **Do** cite sources in `.tbl-cap` and the closing `.small` block. Sourcing is the standard.
- **Do** check print preview for page overflow before you ship; split long sections.
- **Don't** add a second accent color or bold headlines past weight 500.

Prefer to have Claude build it for you? Use the
[`superheat-whitepaper` skill](../../skills/superheat-whitepaper/).
