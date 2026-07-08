# Superheat Skills

Two [Claude Code](https://claude.com/claude-code) skills that let anyone on the team
say *"make a Superheat pitch deck about X"* or *"draft a Superheat whitepaper on Y"* and
get a brand-standard document back — no design knowledge required.

| Skill | Produces |
|---|---|
| [`superheat-pitch-deck`](superheat-pitch-deck/) | 16:9 HTML slide deck → landscape PDF |
| [`superheat-whitepaper`](superheat-whitepaper/) | US-Letter HTML memo/report → portrait PDF |

## Install

Skills load from `.claude/skills/`. Pick one scope:

**Per-project** (recommended — everyone who clones the project gets them):

```bash
mkdir -p your-project/.claude/skills
cp -r superheat-templates/skills/superheat-pitch-deck  your-project/.claude/skills/
cp -r superheat-templates/skills/superheat-whitepaper  your-project/.claude/skills/
```

**Personal** (available in all your projects):

```bash
mkdir -p ~/.claude/skills
cp -r superheat-templates/skills/superheat-pitch-deck  ~/.claude/skills/
cp -r superheat-templates/skills/superheat-whitepaper  ~/.claude/skills/
```

Or symlink instead of copy so they stay in sync with the repo:

```bash
ln -s "$(pwd)/superheat-templates/skills/superheat-pitch-deck"  ~/.claude/skills/superheat-pitch-deck
ln -s "$(pwd)/superheat-templates/skills/superheat-whitepaper"  ~/.claude/skills/superheat-whitepaper
```

## Use

In Claude Code, just describe what you want:

- *"Build a Superheat investor pitch deck from `market-research/memo.md`."*
- *"Draft a Superheat whitepaper on our GPU unit economics."*
- *"/superheat-pitch-deck"* (invoke explicitly)

The skill finds this repo, copies the right template, fills it from your content, and
enforces the brand rules. Keep the `superheat-templates` repo checked out nearby — the
skills read `templates/`, `design-system/`, and `components/` from it.

> Skills work best when Claude can see both this repo and your source content in the
> same workspace. Cloning `superheat-templates` as a sibling of your working folder is
> the simplest setup.

## Not using Claude Code?

The skill mechanism is Claude-Code-specific, but the workflow isn't. Codex, Cursor, and
other agents read [`../AGENTS.md`](../AGENTS.md) from the repo root — it contains the same
build workflow and brand rules. The `SKILL.md` files here are plain Markdown playbooks any
model can follow; point your agent at the relevant one. See
[Using with AI agents](../README.md#using-with-ai-agents) in the root README.
