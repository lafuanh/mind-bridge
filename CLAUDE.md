# CLAUDE.md — Your Life OS
> Read this file first. Every session. No exceptions.
> Last updated: 2026-03-28

---

## Who You Are

**Name:** [Your name]
**Email:** [your-email@gmail.com]
**Location:** [Your city] — timezone [Your timezone]
**Status:** [Your current role / focus]
**Background:** [Your domain or interests]

---

## The 3 Brains System

| # | Brain | Tool | Access | Role |
|---|-------|------|--------|------|
| 01 | Biological | Your own thought | always on | raw generation |
| 02 | Mobile capture | Notion /dump | phone + desktop | everything lands here |
| 03 | Deep library | Obsidian vault | laptop only, OneDrive | knowledge graph |

**Claude is the bridge** — reads Brain 02, classifies, writes to Brain 03 and back into Notion organized folders.

---

## Identity Stack

Define 5–10 traits that describe who you are becoming.
Example:
1. Deep thinker
2. Clear communicator
3. High performer
4. Curious learner
5. Consistent builder

**Identity loop:** read → classify → present → evaluate → reflect → write → publish → read ↺

---

## Active Targets

Define 3–5 current goals. Examples:
- Language learning goal (e.g. IELTS, TOEFL target score)
- Career or academic application goal
- Personal project (website, blog, app)
- Knowledge graph growth target

---

## Sync Schedule

| Time | Name | Claude does |
|------|------|------------|
| Morning | Morning brief | Process overnight dump · fill today's planner goals · language drill · short + sharp |
| Midday | Midday flush | Process morning dump · reschedule interrupts · update planner · quick |
| Night | Night digest | Full classify · deep Obsidian writes · blog check · fill reflection + habits · archive dump · thorough |

> Set your preferred sync times in Google Calendar as recurring events.

---

## Notion Structure

```
Notion workspace/
├── /dump                  ← Brain 02. One file. Everything lands here.
├── Master review          ← Claude updates 3x daily
├── Tasks/                 ← database with DAILY PLANNER pages per day
├── Projects/
│   ├── [your-os]          ← this system
│   ├── [project-1]
│   ├── [project-2]
│   └── [project-3]
├── Life/
│   ├── journal/
│   ├── money-log/
│   └── step-tracking/
├── Blog pipeline/
│   ├── 🟡 flagged
│   ├── ✅ approved
│   └── 📤 published
└── _archive/
```

---

## Tasks Database — Daily Planner Rule

**One page per day. Check first. Create only if missing.**

### The logic Claude follows every time

```
BEFORE writing any task or schedule entry:

1. Fetch the Tasks database to see existing pages
2. Search for a page named "[D Month]" for the target date
   Examples: "28 March", "1 April", "15 April"

3. Page EXISTS?
   → Update it — append task to TO DO or SCHEDULE section
   → Never create a duplicate

4. Page DOES NOT EXIST?
   → Fetch Tasks database to get live template list
   → Use the DAILY PLANNER template (find it in <templates> section)
   → Create page with template_id + Name + Date properties
   → Then add the task content
```

### Why fetch live instead of hardcoding template IDs
Template IDs can change if the database is modified. Always fetch fresh.
The Tasks database URL: `https://www.notion.so/[YOUR_TASKS_DB_ID]`

### Page naming convention
- Format: "[D Month]" — "28 March", "1 April", "15 April"
- Date property: YYYY-MM-DD
- Icon: 📅

### Daily Planner structure (two-column layout)
**Left column:**
- Checklist items (Plan tomorrow, Plan this week)
- SCHEDULE section — hourly slots 6A through 11P
  Format: `**9A** Meeting with [person]`

**Right column:**
- GOALS — top 3 for the day (Claude fills at morning brief)
- HABITS — checked at night digest
- TO DO — checkboxes
  Format: `- [ ] task text`

**Bottom:**
- REFLECTION — from #feel entries at night digest

### What Claude fills in per sync

| Section | Source | When |
|---------|--------|------|
| GOALS | Top 3 from identity + today's context | Morning |
| SCHEDULE | #sched entries at correct time slot | On #sched |
| TO DO | #todo and #task entries | Any sync |
| HABITS | dump check + language drill + steps | Night |
| REFLECTION | #feel entries | Night |

---

## Routing Rules

### #todo #task
→ Daily Planner TO DO section as `- [ ] task`
→ If due date mentioned → that date's planner
→ NEVER Obsidian

### #sched #deadline
→ Daily Planner SCHEDULE section at correct time slot
→ Google Calendar `[your-email@gmail.com]` — your timezone
  Reminders: 1 day before popup + 30 min popup
→ Note in TO DO: "(reminder in Google Cal ✓)"
→ NEVER Obsidian

### #know #research
→ Obsidian `Knowledge/` or `Research/` via concept-note template
→ Add `[[backlinks]]` to at least 1 existing note + update MOC
→ NEVER Notion Tasks

### #eng #vocab
→ Obsidian `English/vocab-daily/YYYY-MM-DD.md`
→ Obsidian `English/mistakes-log/YYYY-MM-DD.md`
→ Always explain WHY the correction is better
→ Focus on your target language goal

### #feel #journal (Life page)
→ Notion `Life/journal/` — dated entry (YYYY-MM-DD) with mood, mental score, reflection
→ Daily Planner REFLECTION section
→ Obsidian `Life/journal/YYYY-MM-DD.md` (daily-journal template)
→ If mental score → also `Life/mental-log/`

### #money (Life page)
→ Notion `Life/money-log/` — table row: date | amount | category | note
→ Daily Planner REFLECTION — note total

### #life (Life page)
→ Notion `Life/step-tracking/` — table row: date | metric (steps/sleep/health) | notes
→ Daily Planner REFLECTION — note steps + health

### #blog
→ Run 5-point qualify check
→ Score ≥ 4 → Notion `Blog pipeline/ 🟡 flagged` + Obsidian `Output/blog-drafts/`
→ Score < 4 → archive with reason

### #project
→ Notion `Projects/` matching page → append update + timestamp
→ Daily Planner TO DO — add actionable tasks (subject to density limit below)

### #random #idea #randomidea #random-project #randomproject
→ Notion `Projects/` page → append to `🎲 Random Ideas Queue` section
→ Daily Planner TO DO — light note only: "💡 [idea] → queued in Projects"
→ NEVER create a full project page for random ideas — queue only
→ **NEVER Obsidian — even if the idea sounds technical or research-flavored**

> ⚠️ HARD DISTINCTION — read before classifying:
> - `#random-project` = something to BUILD someday → Notion Projects queue ONLY
> - `#know` = something you already understand and want to SAVE as knowledge → Obsidian ONLY
> A project idea about AI memory is NOT a knowledge concept. It is a build idea. Queue it.

### #interrupt
→ Morning and midday: HOLD, do not process
→ Night digest ONLY: process by content type, note "Was #interrupt"

### No tag → classify by meaning, route same as above

---

## Task Density Rule — anti-overwhelm (hard limit)

**Max 3 grind tasks per day in the daily planner TO DO. No exceptions.**

### What counts toward the limit
| Type | Counts? | Examples |
|------|---------|---------|
| 🔥 Grind | ✅ YES | project work, coding, writing, research, design |
| ✅ Routine | ❌ NO | IELTS drill, English log, habits |
| 📅 Schedule | ❌ NO | meetings, fixed-time events |

### TO DO structure — always in this order
```
🔥 [grind task 1]     ← max 3
🔥 [grind task 2]
🔥 [grind task 3]
---
✅ IELTS drill (30 min)
✅ English mistakes log
✅ Night digest 22:00
```

### Overflow rule
If 3 grind slots are already filled → do NOT add more to today.
→ Append overflow task to `Projects/ Schedule Project (Queue)` with `[next week]` label.
→ Write in daily planner: `→ [task] queued (density limit)` as a plain note, not a checkbox.

**Why:** 3 hard things done beats 9 things half-done. Protect the grinder's focus.

---

## Language Scan (every sync, automatic)

Scan ALL dump text for grammar errors and awkward phrasing.
→ `English/mistakes-log/YYYY-MM-DD.md`
Format: `I wrote: [X] | Better: [Y] | Why: [reason]`

---

## Obsidian Hard Rules

- NEVER write tasks, todos, checkboxes to Obsidian
- NEVER write schedules, timetables, daily logs to Obsidian
- IF entry has BOTH knowledge AND task → split them
- Every note gets at least one `[[backlink]]`

**Obsidian = what I know. Notion = what I do.**

### Vault structure
```
Research/papers/ · reading-notes/ · drafts/
Knowledge/books/ · concepts/ · [your-domain-1]/ · [your-domain-2]/ · AI/
English/vocab-daily/ · mistakes-log/ · writing-samples/ · language-tracker/
Life/journal/ · mental-log/ · step-tracking/ · money-log/
Output/blog-drafts/ · published/ · website-ideas/
_templates/
_archive/
```

---

## Blog Qualify Checklist (5 points)

- [ ] Clear perspective or argument
- [ ] Interesting outside my head
- [ ] Connects to a bigger idea
- [ ] Written in my voice
- [ ] 300–1500 words when expanded

Need ≥ 4/5 to flag.

---

## Flow State

```
[90 min DEEP GRIND] → [15 min buffer + dump] → [90 min DEEP GRIND] → [15 min review]
```

Interrupt rule: `#interrupt` in dump → hold → process at night digest only.

---

## Google Calendar

- Primary: `[your-email@gmail.com]` | Timezone: `[Your/Timezone]`
- Default: 30 min popup
- Notion @remind cannot be written via API — use Google Cal for all timed reminders
- Run syncs manually by pasting the cowork prompt

---

## Claude Behavior Rules

1. Read CLAUDE.md first — every session
2. Never ask me to organize — do it yourself
3. Timestamp everything: `YYYY-MM-DD HH:MM [timezone]`
4. Tasks: check page exists → update → create only if missing
5. Fetch Tasks database live for template IDs — never hardcode
6. Write in user's voice: direct, curious, honest
7. Language feedback: always explain WHY
8. Flag blog, never auto-publish — user approves
9. #interrupt: hold until night digest, sacred
10. Every Obsidian note: at least one `[[backlink]]`
11. Morning: short. Night: thorough. Midday: quick.
12. Life pages updated every sync: journal/ (one entry per #feel/#journal), money-log/ (one row per #money), step-tracking/ (one row per #life)
13. All Life/* entries must include timestamps: `YYYY-MM-DD HH:MM [timezone]`
14. Before striking through dump entries, verify all routes were written (see Verification Checklist)

---

## Skills Index

Each sync has a dedicated skill file with full step-by-step execution.
Read the relevant skill before running a sync.

| Skill file | Triggered by | Purpose |
|-----------|--------------|---------|
| `skills/morning-brief.md` | `run morning brief` | 05:00 — set goals, plan day |
| `skills/midday-flush.md` | `run midday flush` | 11:45 — clear morning chaos |
| `skills/night-digest.md` | `run night digest` | 22:00 — full classify + reflect |
| `skills/classify-route.md` | every sync | core tag → destination map |
| `skills/interrupt.md` | `#interrupt` tag | hold until 22:00 |

Reference files in `.claude/`:
- `routing-rules.md` — quick routing table
- `brain-map.md` — 3-brain architecture diagram
- `interrupt-protocol.md` — interrupt rules in full

---

## Quick Commands

| Command | Action |
|---------|--------|
| `run morning brief` | Morning sync |
| `run midday flush` | Midday sync |
| `run night digest` | Full night sync |
| `show master page` | Today's dashboard |
| `language drill` | 5 vocab + 1 mistake + 1 rewrite |
| `blog check` | Review flagged posts |
| `obsidian write [topic]` | New vault note |

---

## Project Root

`~/your-os/`
- `CLAUDE.md` — this file (identity + routing index)
- `skills/` — execution skills for each sync type
- `.claude/` — reference files (routing table, brain map, interrupt protocol)
- `.claude/cowork-sync-prompt.md` — paste into Cowork + /schedule
- `.claude-plugin/plugin.json` — plugin descriptor
- `obsidian-vault/` — local copy (OneDrive or cloud sync is source of truth)
- `notion-templates/import/` — projects, tasks, calendar, journal, money

---

## Calendar Conflict Check

**Before scheduling ANY task or event, Claude must:**

1. Fetch Google Calendar for the target date — your primary calendar, your timezone
2. Read all existing events for that day
3. Check if the proposed time conflicts with anything already booked
4. If conflict → pick the next free slot OR flag it instead of overwriting

### What counts as a conflict
- Direct overlap with any existing event
- Less than 15 min buffer before a meeting (need prep time)
- Scheduling during the 3 OS sync windows

### What to do when conflict found
- Do NOT silently overwrite or ignore
- Note in the Daily Planner: "⚠️ [task] conflicts with [event] at [time] — reschedule?"
- Suggest the next free block instead
- Add to #interrupt buffer if time-sensitive — process at night digest

### Additional calendars to check
If you have class, work, or shared calendars, list their IDs here:
- Calendar ID: `[optional-secondary-calendar-id@group.calendar.google.com]`

---

## Tasks database — daily planner logic

**Database:** Tasks (collection://[YOUR_COLLECTION_ID])
**Templates available:**
- DAILY PLANNER — fetch dynamically from Tasks DB
- WEEKLY PLANNER — fetch dynamically from Tasks DB
- MONTHLY PLANNER — fetch dynamically from Tasks DB

### Daily page rules (CRITICAL — never break these)

1. **Check before create** — before making any daily page, search Tasks db for a page named "[D Month]" (e.g. "28 March"). If it exists → UPDATE it, never create a new one.
2. **Create if missing** — if today has no page, create one using DAILY PLANNER template with Name="[D Month]" and Date=today.
3. **Never hardcode template IDs** in the sync prompt — always fetch the Tasks database first to get current template IDs dynamically.
4. **Page format** — name must match exactly: "27 March", "1 April" (day + month, no leading zero, no year).
5. **Manually written tasks are sacred** — when syncing, READ the existing page content first. Append new tasks below existing ones. NEVER overwrite what the user already wrote manually.
6. **Sync bidirectionally** — tasks written manually in the daily page are treated as #todo entries. Claude reads them at each sync and ensures they appear in Google Calendar if they have a time, or stay as-is if they don't.

### What the daily planner page contains

Left column:
- Checklist of tasks (nested, with @remind date mentions for phone notifications)
- SCHEDULE block — hourly slots 6A through 11P

Right column:
- GOALS — top 3 (callout blocks)
- HABITS — top 3 (callout blocks)
- TO DO — simple checklist

Bottom:
- REFLECTION section

### Reminder system (important)

Notion's native `@remind [date] [time]` sends directly to phone — Claude CANNOT write these programmatically via API.
Workaround: Claude adds the task to **Google Calendar** with popup reminder instead.
Rule: if a task has a specific time → Google Calendar event + popup reminder. Notion page gets the task text only (no @mention).

### Sync behavior for tasks

At each sync Claude must:
1. Fetch Tasks DB to get current template IDs (don't hardcode)
2. Search for today's page by name — "28 March" etc.
3. If missing → create with DAILY PLANNER template
4. If exists → READ current content, then APPEND new items only
5. For any task with a time → also create Google Calendar event
6. For manually written tasks found in the page → validate they're in Google Calendar if time-bound
7. Update SCHEDULE block if new timed events were added
