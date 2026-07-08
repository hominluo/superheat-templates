# Superheat™ Templates

**English** · [中文](README.zh-CN.md)

Brand-standard templates, a design system, and AI-agent skills for building
**Superheat pitch decks, sales decks, and white papers** — so anyone on the team can
produce a well-formatted, on-brand document without starting from a blank page.
Works by hand, or just ask **Claude Code** or **Codex** to build it (see [Use it](#use-it)).

> The heater is the commodity. The **presentation** shouldn't be. Every Superheat
> deck and paper should look like it came from the same house — same orange, same
> Geist headlines, same DM Mono numbers, same pixel voice.

## What's inside

```
superheat-templates/
├── design-system/     the brand: color, type, components, voice + canonical CSS
│   ├── README.md              ← the brand bible (start here)
│   ├── superheat-tokens.css   ← color, type families, reset
│   ├── superheat-deck.css     ← 16:9 deck layout + components
│   └── superheat-whitepaper.css ← letter-page layout + components
├── templates/         copy-and-fill starting points (self-contained HTML)
│   ├── pitch-deck/     template.html + guide  → 16:9 slides, landscape PDF
│   └── whitepaper/     template.html + guide  → US-Letter pages, portrait PDF
├── components/        copy-paste markup for every block (stats, tables, cards…)
├── skills/            AI-agent skills — "make a Superheat deck about X"
│   ├── superheat-pitch-deck/
│   └── superheat-whitepaper/
├── examples/          pointers to the canonical reference deck & whitepaper
├── AGENTS.md          the agent playbook (Codex & any tool) — workflow + brand rules
├── CLAUDE.md          Claude Code specifics (defers to AGENTS.md)
└── CONTRIBUTING.md    how to change a brand rule and keep everything in sync
```

## Use it

**Just ask an AI agent (easiest).** Open this repo in **Claude Code** or **Codex** and ask:

> "Build a Superheat pitch deck from this memo." · "Draft a Superheat whitepaper on X."

The agent reads the rules on its own (`CLAUDE.md` / [`AGENTS.md`](AGENTS.md)), copies the
right template, fills it in, and hands you a print-ready HTML file. Nothing to configure.

*In Claude Code, want it as a one-word command?* Install the skills once:

```bash
cp -r superheat-templates/skills/*  ~/.claude/skills/
```

**Or do it by hand.** Copy [`templates/pitch-deck/template.html`](templates/pitch-deck/)
or [`templates/whitepaper/template.html`](templates/whitepaper/), replace the
`[[placeholders]]`, open in Chrome, print to PDF. No build step, no dependencies.

## The brand in 20 seconds

- **Color:** one accent — Superheat orange `#FF5500` — on ink/paper. Never a second hue.
- **Type:** **Geist** (headlines & body, weight 400/300), **DM Mono** (all numbers &
  data), **Press Start 2P** (pixel kickers & tags). Loaded from Google Fonts.
- **Move:** headlines set the point in two colors — setup in ink, payoff in
  `<span class="a">orange</span>`. Numbers are always mono. One orange moment per slide.
- **Voice:** claims not labels; numbers first; always keep the honest caveat.

Full rules → [`design-system/README.md`](design-system/README.md).

## Export to PDF

Both templates print with zero setup from Chrome (`Ctrl/Cmd-P` → **Save as PDF**,
**Background graphics ON**, **Margins None**):

- **Deck** → Layout **Landscape**, paper `1280×720` if offered.
- **White paper** → Layout **Portrait**, paper **Letter (8.5×11)**.

## Reference material

The design system was distilled from the live Superheat strategy deck and whitepaper
memo. See [`examples/`](examples/) for where to find them in the
[`superheat-workspace`](https://github.com/hominluo/superheat-workspace) repo.

---

Maintained for the Superheat team. Changing a brand rule? Read
[`CONTRIBUTING.md`](CONTRIBUTING.md) first — the CSS lives in two places by design and
must stay in sync.
