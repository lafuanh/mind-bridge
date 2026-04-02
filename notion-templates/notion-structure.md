# Notion Structure — Your Life OS
*Last updated: 2026-03-28*

## Workspace layout

```
Notion workspace/
├── /dump                    ← Brain 02 capture point. One file. Everything here first.
├── Master review            ← Command center. Claude updates 3× daily.
├── Tasks/                   ← Daily planners + tasks. Claude manages this.
│   ├── [TODAY view]         ← filtered: Date = today
│   ├── [THIS WEEK view]     ← filtered: Date this week, sorted ascending
│   ├── [CALENDAR view]      ← calendar by Date
│   └── [daily pages]        ← e.g. "28 March", "29 March" — one per day
├── Projects/
│   ├── [your-os]            ← this system
│   ├── [project-1]          ← your active project
│   ├── [project-2]          ← your active project
│   └── [project-3]          ← side project or business idea
├── Life/
│   ├── journal/             ← processed #feel entries
│   ├── money-log/           ← processed #money entries
│   └── step-tracking/       ← processed #life entries
├── Blog pipeline/
│   ├── flagged           ← Claude flagged, awaiting approval
│   ├── approved          ← ready to write/publish
│   └── published         ← live on your site
└── _archive/                ← all old pages quarantined, nothing deleted
    └── [dated-archive]/     ← e.g. notion-2026-03-27
```

---

## Tasks database — daily planner rules

**Database ID:** [YOUR_TASKS_DB_ID]
**Collection:** [YOUR_COLLECTION_ID]

### Templates (fetch dynamically — IDs may change)
Always fetch the Tasks DB before creating pages to get current template IDs.
Never hardcode template IDs in prompts.

Current templates:
- DAILY PLANNER
- WEEKLY PLANNER
- MONTHLY PLANNER

### Daily page naming convention
Format: "[D Month]" — e.g. "28 March", "1 April"
- No leading zero on day
- No year
- No "th", "st", "rd" suffix

### Create vs update logic (Claude must follow this every sync)
```
Search Tasks DB for today's page name
  ↓
Found? → READ content first → APPEND only → never overwrite
  ↓
Not found? → Fetch DB for template ID → Create with DAILY PLANNER template
```

### Daily planner page structure (two-column layout)

**Left column:**
- Task checklist (nested, with @mention dates for Notion phone notifications)
- SCHEDULE block — hourly rows 6A through 11P

**Right column:**
- GOALS — top 3 (callout blocks with numbered icons)
- HABITS — top 3 (callout blocks)
- TO DO — simple checklist (5 slots)

**Bottom:**
- REFLECTION section

### Reminders — how they work

| Method | How | Phone notification? |
|--------|-----|-------------------|
| Notion @remind | User types it manually in page | Yes — direct |
| Google Calendar | Claude creates via API | Yes — popup |
| Notion /remindme | In task properties | Yes |

Claude writes to Google Calendar for all timed tasks.
Claude CANNOT write Notion @mention reminders via API — user adds those manually.
Claude's job: create the GCal event so the phone still gets notified.

---

## Master review page structure

Updated by Claude at every sync. Open this first every session.

```
## [Date] — [Day of week]
Syncs: Morning ✓ | Midday ✓ | Night ✓

### Today's flow blocks
- [ ] Block 1: [90min grind target]
- [ ] Block 2: [90min grind target]

### Language drill
Word: | Mistake: | Rewrite:

### Interrupt buffer
[#interrupt items waiting for night digest]

### Blog qualify check
[Claude flags here — approve or skip]

### Reflect (night only)
[prompt: what moved today? what didn't?]

### Timestamp log
- Morning — processed [N] entries
- Midday — processed [N] entries
- Night — processed [N] entries
```

---

## Setup checklist

To use this system:

1. Create a Tasks database in Notion
2. Add templates: DAILY PLANNER, WEEKLY PLANNER, MONTHLY PLANNER
3. Note your database ID from the URL: `notion.so/[YOUR_TASKS_DB_ID]`
4. Replace `[YOUR_TASKS_DB_ID]` and `[YOUR_COLLECTION_ID]` in CLAUDE.md
5. Create a `/dump` page — this is your capture inbox
6. Create a `Master review` page — Claude updates this each sync
