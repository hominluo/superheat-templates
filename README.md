# Superheat™ Templates

Brand-standard templates, a design system, and AI-agent skills for building
**Superheat pitch decks, sales decks, and white papers** — so anyone on the team can
produce a well-formatted, on-brand document without starting from a blank page.
Works by hand, or drive it with **Claude Code** or **Codex** (see
[Using with AI agents](#using-with-ai-agents)).

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

## Pick your path

**I want to build a deck/paper by hand →**
Copy a file from [`templates/`](templates/), fill in the `[[placeholders]]`, open in
Chrome, print to PDF. That's it — no build step, no dependencies.

- [Pitch / sales deck guide](templates/pitch-deck/README.md)
- [White paper / memo guide](templates/whitepaper/README.md)

**I want an AI agent to build it for me →**
See [Using with AI agents](#using-with-ai-agents) below — works with Claude Code, Codex,
or any coding agent. In short: *"Build a Superheat pitch deck from this memo."*

**I want to understand or extend the brand →**
Read the [design system](design-system/README.md) and the
[component gallery](components/README.md).

## Using with AI agents

This repo is built to be **driven by a coding agent**. The brand rules and the exact
build workflow live in two agent-readable files so a model produces on-brand output
without you spelling out the design each time:

- **[`AGENTS.md`](AGENTS.md)** — the tool-agnostic playbook (workflow + brand rules).
  Codex, Cursor, and most agents read this automatically from the repo root.
- **[`CLAUDE.md`](CLAUDE.md)** — Claude Code specifics; defers to `AGENTS.md` for the rules.
- **[`skills/`](skills/)** — two skills (`superheat-pitch-deck`, `superheat-whitepaper`)
  that package the workflow as a first-class, auto-invoked capability in Claude Code.

### With Claude Code

1. Install the skills once (per-project or personal) — see [`skills/README.md`](skills/README.md):
   ```bash
   cp -r superheat-templates/skills/*  ~/.claude/skills/     # personal, all projects
   ```
2. Keep `superheat-templates` checked out near your work (a sibling folder is easiest).
3. Just ask — the matching skill fires automatically:
   > "Build a Superheat investor deck from `notes.md`."
   > "Draft a Superheat whitepaper on our GPU unit economics."
   > "/superheat-pitch-deck"  ← invoke explicitly

   Claude reads `CLAUDE.md` → `AGENTS.md`, copies the right template, fills it from your
   content, and enforces the brand.

### With Codex (or Cursor, Copilot, etc.)

These tools don't have Claude Code's skill mechanism, but they read `AGENTS.md`
automatically. So:

1. Open `superheat-templates` (or add it to your workspace) so `AGENTS.md` is in scope.
2. Ask for the document:
   > "Following AGENTS.md, build a Superheat pitch deck from this memo."
3. If the agent doesn't pick up `AGENTS.md` on its own, point it there and at the skill
   file for the detailed steps: `skills/superheat-pitch-deck/SKILL.md` (or
   `…/superheat-whitepaper/SKILL.md`) — they're plain Markdown playbooks.

### What the agent does either way

Copies the correct `templates/*/template.html`, replaces every `[[placeholder]]` with
your content, keeps one accent color and DM-Mono numbers, preserves the honest caveats,
and hands you a self-contained HTML file ready to print to PDF — no build step.

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
