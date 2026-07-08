# Superheat™ Design System

The brand standard for every Superheat pitch deck, sales deck, and white paper.
Read this once; then use the [templates](../templates/) and [components](../components/)
to build fast without re-deriving the rules.

> **The one rule that matters:** every document is built from the same three
> ingredients — **Geist** for words, **DM Mono** for numbers, **Press Start 2P**
> for the pixel voice — on **ink / paper / one orange**. Nothing else.

---

## 1. Color

Exactly one accent color. Never introduce a second hue — hierarchy comes from
ink/gray/orange and from dark/light/orange backgrounds, not from a palette.

| Token | Hex | Use |
|---|---|---|
| `--orange` | `#FF5500` | The brand. Accents, stat numbers, kickers, key table cells, the orange background. |
| `--orange-deep` | `#F24820` | Pressed states / gradient partner only. |
| `--ink` | `#0A0A0A` | Deck dark background & darkest text. (Whitepaper softens this to `#1F1F1F`.) |
| `--ink-2` | `#1F1F1F` | Body text on light; softer dark surfaces. |
| `--paper` | `#FFFFFF` | White. |
| `--gray` | `#767676` | Secondary text on light backgrounds. |
| `--gray-2` | `#A8A8A8` | Secondary text on dark backgrounds. |
| `--card` | `#F0F0F0` | Card / table fill on light. |
| `--card-dark` | `#1A1A1A` | Card / table fill on dark. |
| `--line` | `#E0E0E0` | Hairline on light. |
| `--line-dark` | `#2A2A2A` | Hairline on dark. |

**Accent discipline.** Orange marks the *one thing that matters* on a slide — the
punchline word in a headline, the number a reader should remember, the winning
column in a table. If everything is orange, nothing is. Aim for one orange
moment per slide.

---

## 2. Typography

Three families, loaded from Google Fonts. Put this in every `<head>`:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Geist:wght@300;400;500&family=Press+Start+2P&display=swap" rel="stylesheet">
```

| Family | Role | Weights | Notes |
|---|---|---|---|
| **Geist** | Headlines & body | 300 / 400 / 500 | Headlines are **weight 400** (not bold) with tight `letter-spacing:-0.05em`. Body lede is **weight 300**. Emphasis is 500, never 700. |
| **DM Mono** | Numbers, data, labels | 400 / 500 | Every figure, `$/hr`, percentage, table number, and uppercase column label. This is what makes the data read as *measured*. |
| **Press Start 2P** | Pixel voice | single | Kickers, doc tags, list numbers, the `> TAGLINE_` marks. Used sparingly and small — it is seasoning, never body text. |

### The type moves that define the brand

- **Headlines set the point in two colors.** Write the setup in ink/white and the
  payoff in orange via `<span class="a">`:
  `<h1>Same Machine.<br><span class="a">Better Asset.</span></h1>`
- **Kickers are pixel + orange + uppercase**, one short line above the headline:
  `THE THESIS`, `LIVE MARKET · VAST.AI · 06.2026`.
- **Numbers are always DM Mono.** A stat is a big DM Mono number in orange with a
  small `<small>` unit, a plain-Geist title, and a gray description.
- **Emphasis is weight, not italic.** `<b>` → 500. Reserve italics for document
  titles inside prose.

---

## 3. The two document types

| | Pitch / sales deck | White paper / memo |
|---|---|---|
| **Stylesheet** | `superheat-deck.css` | `superheat-whitepaper.css` |
| **Canvas** | 16:9 slides, `1280×720` PDF | US-Letter `8.5×11in` pages |
| **Unit** | `<section class="slide">` | `<section class="page">` |
| **Theme** | Per-slide: `.dark` / `.light` / `.orange` | Light pages + one orange cover |
| **Sizing** | Fluid `clamp()` / viewport units | Fixed **points (pt)** — maps 1:1 to print |
| **Navigation** | Scroll-snap + arrow keys + progress bar | Scroll; pages stack |
| **Density** | One idea per slide, big type | Dense, ~9.4pt body, footnoted |
| **Export** | Browser → Print → Save as PDF (landscape) | Browser → Print → Save as PDF (portrait) |

Both share the identical token set and the same components (stats, tables, cards,
flows, callouts) — a deck slide and a whitepaper section are visibly the same
brand at two densities.

---

## 4. Slide themes (deck)

Each slide declares one theme class. The template JS reads it and recolors the
fixed chrome (wordmark, counter, progress bar) automatically.

- **`.dark`** — the default. Ink background, white text. Use for most content.
- **`.light`** — white background, ink text. Use for tables and dense data (easier
  to read), and to create rhythm between dark slides.
- **`.orange`** — full orange. Reserve for the **cover, section breaks, and the
  closing punchline** only. It is the loudest surface; two or three per deck.

Alternate dark/light so consecutive content slides don't blur together; bookend
with orange covers.

---

## 5. Rhythm & layout rules

- **One idea per slide.** A kicker, a two-part headline, and *one* supporting
  element (a stat row, one table, or one card grid). If you need two elements,
  you probably need two slides.
- **Vertical centering.** Slides center their content; whitepaper pages flow top-down.
- **Footnotes carry the honesty.** The brand voice states the optimistic number
  *and* the honest caveat. Put the caveat in `.foot-note` (deck) or `.tbl-cap` /
  `.small` (whitepaper). Never delete the caveat to make a slide cleaner.
- **Sources are visible, not hidden.** Cite live data inline (`· Vast.ai · 06.11.2026`)
  and in captions.
- **Max line lengths are set in the CSS** (`max-width` in `ch`). Don't override
  them — they keep prose readable.

---

## 6. Brand voice

The writing is as much a standard as the CSS. Match it:

- **Wordmark:** `Superheat<sup>™</sup>` — always with the superscript trademark.
- **Pixel tags:** short, uppercase, wrapped in `> … _`, e.g.
  `> THE HEATER THAT PAYS YOU BACK_`, `> ORIGINATE. PACKAGE. SELL. REPEAT_`.
- **Headlines are claims, not labels.** "Honest Numbers." beats "Financials".
  "Prices Fall. Underwrite the Curve." beats "Pricing trends".
- **Numbers first, adjectives never.** "18-month payback, 45% IRR, 2× coverage"
  does the persuading. Let DM Mono carry the weight.
- **Name the failure modes.** Decks include a pre-mortem / anti-pattern slide;
  whitepapers include a risk register. Credibility is part of the brand.
- **Doc tag line:** a mono string in the chrome / footer, e.g.
  `Compute-Backed Finance · 06.2026`.

---

## 7. Files in this folder

| File | What it is |
|---|---|
| `superheat-tokens.css` | Color, type families, reset. **Import first.** |
| `superheat-deck.css` | 16:9 deck layout + every deck component. |
| `superheat-whitepaper.css` | Letter-page layout + every whitepaper component. |

The [templates](../templates/) ship these **inlined** so a single `.html` file is
self-contained and portable (email it, print it, no build step). These external
files are the canonical source — when you change a brand rule, change it here and
re-inline into the templates. See [`../CONTRIBUTING.md`](../CONTRIBUTING.md).

---

## 8. Quick checklist before you ship

- [ ] Google Fonts link present; Geist / DM Mono / Press Start 2P all rendering.
- [ ] Exactly one accent color; roughly one orange moment per slide.
- [ ] Every number is DM Mono; every headline is Geist 400 with an orange payoff.
- [ ] Kicker on every content slide; wordmark carries the `™`.
- [ ] Honest caveats present in footnotes/captions, not deleted.
- [ ] Deck: dark/light/orange alternates with a rhythm; orange used ≤3×.
- [ ] Prints correctly (deck → landscape 1280×720; paper → portrait Letter).
