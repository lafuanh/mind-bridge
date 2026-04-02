# Skill: Classify + Route
> The core tag → destination map.
> Applied at every sync. Read this before routing any dump entry.

---

## The Core Rule

> **Notion = what you do. Obsidian = what you know. Google Calendar = what has a fixed time.**

---

## Tag → Destination Table

| Tag | Notion | Obsidian | Google Cal | Notes |
|-----|--------|----------|------------|-------|
| `#todo` `#task` | Daily Planner → TO DO | ❌ | if time specified | density limit applies |
| `#sched` `#deadline` | Daily Planner → SCHEDULE | ❌ | ✅ always + reminders | conflict check first |
| `#know` `#research` | ❌ | Knowledge/ or Research/ | ❌ | concept-note template, backlinks required |
| `#eng` `#vocab` | ❌ | English/vocab-daily/ + mistakes-log/ | ❌ | always explain WHY |
| `#feel` `#journal` | Life/journal/ + daily REFLECTION | Life/journal/ | ❌ | mood + mental score |
| `#money` | Life/money-log/ table row | ❌ | ❌ | date \| amount \| category \| note |
| `#life` | Life/step-tracking/ table row | ❌ | ❌ | date \| metric \| notes |
| `#blog` | Blog pipeline/🟡 (if score ≥ 4) | Output/blog-drafts/ (if score ≥ 4) | ❌ | run 5-point check first |
| `#project` | Projects/[matching page] → append | ❌ | ❌ | fetch page first, append with timestamp |
| `#random` `#idea` `#randomidea` `#random-project` | Projects/🎲 Random Ideas Queue | ❌ | ❌ | queue only — never create project page |
| `#interrupt` | HOLD at 05:00 + 11:45 | — | — | process at 22:00 only |
| no tag | classify by meaning → same rules above | | | |

---

## Decision Tree — when unsure

```
Is this something I want to DO or track?
  YES → Notion (task, schedule, money, life, project)

Is this something I want to UNDERSTAND or reference later?
  YES → Obsidian (knowledge, research, vocab, blog draft)

Does it have a specific time?
  YES → Google Calendar (with popup reminder) + daily SCHEDULE block

Is it a build idea / future project?
  YES → Projects/🎲 Random Ideas Queue (NEVER Obsidian, NEVER full project page)

Am I in the middle of something (flow state)?
  YES → mark #interrupt, process at 22:00 only
```

---

## Hard Distinctions (read before classifying)

### #random-project vs #know
```
#random-project = something to BUILD someday
  → Notion Projects queue ONLY
  → Example: "idea for a chain-memory AI tool"

#know = something you already UNDERSTAND and want to SAVE
  → Obsidian ONLY
  → Example: "attention mechanisms in transformers — how they work"

A project idea about AI memory is NOT a knowledge concept.
It is a build idea. Queue it. Never Obsidian.
```

### #project vs #random
```
#project = you are actively working on this (e.g. mind-bridge, PhD app)
  → Update the matching Notion Projects page
  → Add actionable tasks to daily planner

#random = idea you may want to build one day
  → Queue in Projects/🎲 Random Ideas Queue
  → Light note in daily planner only
  → Never creates a project page
```

### #feel vs #journal
Both route to the same places. Use `#feel` for quick mood captures.
Use `#journal` when you want a fuller written entry.

---

## Routing Execution Rules

### #project (multi-step)
```
STEP A: Search Notion for the project page by name
  notion-search with project name from the dump entry

STEP B: Fetch the matching page
  notion-fetch → get exact current content

STEP C: Append update
  content_updates: [{
    old_str: "[last section header or last line on page]",
    new_str: "[same] + \n\n**YYYY-MM-DD HH:MM WIB** [update text]"
  }]

STEP D: Add actionable next step to daily planner TO DO
```

### #random (multi-step)
```
STEP A: Fetch Notion Projects page
  https://www.notion.so/[YOUR_PROJECTS_PAGE_ID]

STEP B: Append to 🎲 Random Ideas Queue
  old_str: "- [ ] *(Claude appends new ideas below this line)*"
  new_str: "- [ ] [idea text] — added YYYY-MM-DD\n- [ ] *(Claude appends new ideas below this line)*"

STEP C: Add light note to daily planner TO DO
  "💡 [idea] → queued in Projects"
```

### Notion update format (CRITICAL)
```
Always fetch the page first — get exact current text.
content_updates must be an ARRAY of objects:
[{ "old_str": "<exact text>", "new_str": "<same text + new content>" }]

To APPEND: set old_str = section header, new_str = header + new content below it
To REWRITE: use command="replace_content" (Master Review only)
```

---

## Task Density Filter

Before writing ANY task to daily planner TO DO:

```
1. Count existing 🔥 grind tasks (unchecked)
2. If count < 3 → add up to the limit
3. If count = 3 → DO NOT add more grind tasks today
   → Overflow to Projects/ "Schedule Project (Queue)" with [next week]
   → Note in daily page: "→ [task] queued (density limit)"

What counts as grind (toward limit):
  🔥 project work, coding, writing, research, design

What does NOT count:
  ✅ IELTS drill, English log, habits, night digest
  📅 meetings, fixed-time events (go in SCHEDULE, not TO DO)
```

---

## Sync-Level Restrictions

| Tag | Morning 05:00 | Midday 11:45 | Night 22:00 |
|-----|--------------|--------------|-------------|
| #todo #task | ✅ route | ✅ route | ✅ route |
| #sched #deadline | ✅ route | ✅ route | ✅ route |
| #project | ✅ route | ✅ route | ✅ route |
| #random | ✅ route | ✅ route | ✅ route |
| #money #life | ✅ route | ✅ route | ✅ route |
| #feel #journal | ✅ quick | ✅ quick | ✅ full write |
| #know #research | ⏸ queue | ⏸ queue | ✅ deep write |
| #eng #vocab | ✅ quick drill | ⏸ queue | ✅ deep write |
| #blog | ⏸ queue | ⏸ queue | ✅ qualify + flag |
| #interrupt | ⏸ HOLD | ⏸ HOLD | ✅ process |
