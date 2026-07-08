# Examples — the canonical reference documents

The Superheat design system was distilled from two live, fully-built documents. When you
want to see every component in real use — real copy, real numbers, real rhythm — read
these. They are the gold standard the templates reproduce.

They live in the **[`superheat-workspace`](https://github.com/hominluo/superheat-workspace)**
repo, under `market-research/`:

| Reference | File | What to study |
|---|---|---|
| **Strategy deck** (30 slides) | `superheat_strategy_deck.html` | Slide rhythm (dark/light/orange), two-part headlines, the flow / equation / stats / table / cards / bars / numbered-list patterns, the pre-mortem slide, cover ↔ close mirroring. |
| **Whitepaper memo** (9 pages) | `Superheat_Whitepaper_Memo.html` | Memo header, numbered sections, ledes, callouts, dense tables with captions, the risk register, the "assumptions and sourcing" close. |
| Rendered PDFs | `Superheat Strategy Deck 0.1.0.pdf`, `Superheat Research Memo 0.1.0.pdf` | How the HTML prints. |

## How to use them

- **Learning the brand:** open the two HTML files in Chrome side-by-side with a template
  from this repo. Same tokens, same components, at real density.
- **Building something new:** don't copy the reference file — copy the matching
  `templates/*/template.html` (it's the clean scaffold) and use the reference for *how
  much* to put on a slide and *how* the voice sounds.

## Want a live example inside this repo?

If it's useful to have a rendered sample here (e.g. a filled-in `example-deck.html`),
build one with the `superheat-pitch-deck` skill and drop it in this folder. Keep any
example clearly named `example-*` so it's never mistaken for a template.
