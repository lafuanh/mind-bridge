<p align="center">
  <h1 align="center">Mind Bridge</h1>
  <p align="center">
    A personal cognitive OS for knowledge workers <br/>
    Raw thought to structured knowledge. Built on Claude, Notion, and Obsidian. Three syncs a day. Zero manual sorting.
  </p>
</p>

<p align="center">
  <a href="skills/classify-route.md"><img src="https://img.shields.io/badge/routing%20tags-12-green" alt="12 Routing Tags"></a>
  <a href="skills/"><img src="https://img.shields.io/badge/skills-5-blueviolet" alt="5 Skills"></a>
  <a href="https://docs.anthropic.com/en/docs/claude-code"><img src="https://img.shields.io/badge/built%20for-Claude%20Cowork-f5f5f5?logo=anthropic" alt="Built for Claude Code"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT License"></a>
</p>

---

## Table of Contents

- [Foreword](#foreword)
- [Preview](preview)
- [Schedule Tiers](#schedule-tiers)
- [Quick Start](#quick-start)
- [Docs](#docs)
  - [Documentation](#documentation)
  - [Skills](#skills)
  - [Token Cost](#estimated-token-cost-per-sync)
  - [How It Runs](#how-this-system-runs)
- [License](#license)



## Foreword
When designing systems or games, my brain never stops. Ideas keep coming even when I'm watching movies on the couch. If I don't write them down right away, they create too much noise and I get serious brain fog.
I used to dump everything into an empty WhatsApp group, but it grew too fast and became overwhelming to manage. After trying tons of note apps (which all felt too heavy), Claude's new scheduling features gave me an idea.

Now it's simple, I just type my thoughts into one Notion page on my phone, and Claude automatically summarizes my daily, builds knowledge graphs, organizes my project, reviews my writing skills and schedules important stuff for me

## Preview

![Pipeline Preview](./resources/pipeline01.png)


**Claude is the bridge** — reads **Dump file**, classifies, writes to Obsidian & Notion organized folders

---

## Schedule Tiers

The three sync windows map to natural cognitive transitions in a knowledge worker's day:

| Sync | Time | Function | Depth |
|------|------|----------|-------|
| Morning brief | 05:00 | Set goals, plan schedule, morning drill | Short — action-forward |
| Midday flush | 11:45 | Clear morning captures, update schedule, hold interrupts | Quick — no deep writes |
| Night digest | 22:00 | Full classify, Obsidian writes, reflection, clear dump | Thorough — complete processing |

---

## Quick Start

> This is a **template repository** — click **Use this template** on GitHub to create your own copy, then customize `CLAUDE.md` with your Notion IDs, Obsidian paths, and identity stack.

1. **Clone this repo**
   ```bash
   git clone https://github.com/lafuanh/mind-bridge.git
   cd mind-bridge
   ```

2. **Personalize `CLAUDE.md`** — fill in the `[bracketed placeholders]` with your name, email, timezone, and Notion database IDs

3. **Set up Notion** — create the workspace structure described in [`docs/setup.md`](docs/setup.md)

4. **Set up Obsidian** — open `obsidian-vault/` as a vault

5. **Connect Google Calendar** *(optional)* — follow [`docs/setup.md`](docs/setup.md#step-4-connect-google-calendar-optional) for timed reminders and conflict checking

6. **Run your first sync**
   ```
   run morning brief
   ```
   or using cowork desktop
![cowork Preview](./resources/how1.png)

   See [`docs/usage-guide.md`](docs/usage-guide.md) for all methods — CLI, web, Cowork scheduler, and manual paste

---

## Docs

### Documentation

| File | What it covers |
|------|----------------|
| [`docs/setup.md`](docs/setup.md) | First-time setup — Notion, Obsidian, Google Calendar |
| [`docs/how-it-works.md`](docs/how-it-works.md) | Architecture, routing logic, sync step-by-step |
| [`docs/usage-guide.md`](docs/usage-guide.md) | Running syncs — all methods including Cowork scheduler |
| [`docs/known-bugs.md`](docs/known-bugs.md) | Known issues and workarounds |
| [`docs/architecture-visual.html`](docs/architecture-visual.html) | Interactive pipeline diagram |

### Skills

| File | Triggered by | Purpose |
|------|-------------|---------|
| [`skills/morning-brief.md`](skills/morning-brief.md) | `run morning brief` | 05:00 — goals, plan, morning drill |
| [`skills/midday-flush.md`](skills/midday-flush.md) | `run midday flush` | 11:45 — clear chaos, hold interrupts |
| [`skills/night-digest.md`](skills/night-digest.md) | `run night digest` | 22:00 — full classify, reflect, clear dump |
| [`skills/classify-route.md`](skills/classify-route.md) | every sync | Core tag → destination routing map |
| [`skills/interrupt.md`](skills/interrupt.md) | `#interrupt` tag | Hold until night digest — sacred |

### Estimated token cost per sync

| Sync | Typical cost | Notes |
|------|-------------|-------|
| Morning brief | ~2–3% session | Short — no deep Obsidian writes |
| Midday flush | ~2–3% session | Quick pass — interrupts held |
| Night digest | ~8–10% session | Full classify + Obsidian writes |
| Heavy Obsidian night | ~10%+ | Large knowledge entries; batch if possible |

*Typical cost estimate on Pro plan, March 2026*
*I do recommend using Haikyu only*

### How this system runs

| Method | Sync | Mode |
|--------|------|------|
| Claude Code web (private repo) | Morning brief | Automatic — scheduled, runs unattended |
| Cowork desktop | Midday flush + Night digest | Semi-automatic — Cowork scheduler triggers it, you review output |

Setup for both methods: [`docs/usage-guide.md`](docs/usage-guide.md)

---

## License

MIT  use it, fork it, build your own OS on top of it.

If this helped you, consider starring the repo or sharing your own fork
feel free to edit
thanks
