# How It Works

## The 3 Brains System

Your life OS splits information across three "brains":

1. **Brain 01 — Biological**: Your actual thoughts. Always on.
2. **Brain 02 — Mobile capture (Notion `/dump`)**: One file where everything lands. Phone or desktop, any time.
3. **Brain 03 — Deep library (Obsidian vault)**: Your knowledge graph. Linked notes, backlinks, MOCs.

**Claude is the bridge** between Brain 02 and Brain 03. It reads your raw dump, classifies each entry, and routes it to the correct destination.

## Routing Logic

Every dump entry gets classified by its tag (or by meaning if untagged) and routed to the right system.

### The core rule

> **Notion = what you do. Obsidian = what you know. Google Calendar = what has a fixed time.**

### Tag → Destination mapping

| Tag | Notion | Obsidian | Google Cal |
|-----|--------|----------|------------|
| `#todo` `#task` | Daily Planner → TO DO | never | if time specified |
| `#sched` `#deadline` | Daily Planner → SCHEDULE | never | always (with reminders) |
| `#feel` `#journal` | Daily Planner → REFLECTION | Life/journal/ | never |
| `#know` `#research` | never | Knowledge/ or Research/ | never |
| `#eng` `#vocab` | never | English/vocab-daily/ + mistakes-log/ | never |
| `#money` | Life/money-log/ | never | never |
| `#life` | Life/step-tracking/ | never | never |
| `#blog` | Blog pipeline (if score ≥ 4) | Output/blog-drafts/ | never |
| `#project` | Projects/ page → append update | never | never |
| `#interrupt` | held until night digest | — | — |
| no tag | classified by meaning | classified by meaning | — |

### How a sync runs (step by step)

```
1. CHECK daily planner page
   → Search Tasks DB for today's page ("28 March")
   → If missing, create from DAILY PLANNER template
   → If exists, read current content (never overwrite manual entries)

2. READ the /dump page
   → Get all entries since last sync

3. CLASSIFY each entry by tag or meaning

4. ROUTE to destinations
   → Notion: append to daily planner sections
   → Obsidian: create/update .md files with [[backlinks]]
   → Google Calendar: create events with popup reminders

4.5. UPDATE Life pages
   → Life/journal/ — dated entry for each #feel/#journal
   → Life/money-log/ — table row for each #money
   → Life/step-tracking/ — table row for each #life
   → All entries timestamped YYYY-MM-DD HH:MM [timezone]

5. SYNC manual tasks
   → Read daily planner for manually written tasks
   → Create Google Calendar events for any with times

6. LANGUAGE SCAN
   → Scan all dump text for grammar errors
   → Write to English/mistakes-log/

7. VERIFY all routes were written
   → Checklist: every tag type routed to correct destination
   → If anything missing, go back and write it first

8. STRIKE THROUGH processed entries
   → Each entry: ~~original text~~ ✓ synced YYYY-MM-DD HH:MM
   → One at a time, never batch

9. UPDATE Master Review page
   → Sync summary, goals, language drill, blog flags
```

### Conflict handling

Before scheduling anything to Google Calendar, Claude:
1. Fetches all existing events for the target date
2. Checks for direct overlaps or insufficient buffer (< 15 min before meetings)
3. If conflict found → suggests the next free slot instead of overwriting

### The Obsidian rules

- Every note gets at least one `[[backlink]]` to an existing note
- MOC (Map of Content) files get updated when new notes are added
- Templates are used for consistency (concept-note, daily-journal, vocab-daily, etc.)
- Tasks, schedules, and checkboxes **never** go into Obsidian

### The Notion rules

- Daily planner pages: one per day, named "D Month" (e.g. "28 March")
- Always check before creating — never duplicate
- Manually written tasks are sacred — append only, never overwrite
- Master Review page is fully rewritten each sync (using `replace_content`)

## Sync Tiers

| Tier | Purpose | Depth | Token cost |
|------|---------|-------|------------|
| Morning brief | Plan the day | Short — goals, schedule, quick route | ~2–3% |
| Midday flush | Clear morning chaos | Quick — process new entries, update schedule | ~2–3% |
| Night digest | Full processing | Thorough — deep Obsidian writes, blog check, reflection, clear dump | ~8–10% |

> Night digests with large dumps or many `#know` entries can exceed 10%. Split into two passes if needed — see [Known Bugs](known-bugs.md#token-context-limit--night-digest).

## Blog Qualify Checklist

Entries tagged `#blog` go through a 5-point check:
1. Clear perspective or argument
2. Interesting outside your head
3. Connects to a bigger idea
4. Written in your voice
5. 300–1500 words when expanded

Score ≥ 4/5 → flagged for review. Score < 4 → archived with reason.
