# Skill: Morning Brief
> Trigger: `run morning brief` | 05:00 WIB | start of day
> Style: short, action-focused, set the day's direction

---

## WHEN

- User types `run morning brief`
- Scheduled 05:00 WIB daily
- After sleep — processing overnight dump + planning the day ahead

---

## DO

Run these steps in order. No deep Obsidian writes at this sync.

### Step 1 — Daily page check

```
1. Fetch Tasks database (live — never hardcode template IDs)
   URL: https://www.notion.so/[YOUR_TASKS_DB_ID]
2. Search for today's page named "[D Month]" (e.g. "30 March")
3. Page EXISTS → READ current content first, then append only
4. Page MISSING → create using DAILY PLANNER template
   Name: "[D Month]" | Date: today (YYYY-MM-DD) | Icon: 📅
```

### Step 2 — Read dump

- Fetch Notion `/dump` page
- Focus on entries since ~22:00 yesterday (overnight captures)
- Note all tags: #todo, #sched, #feel, #project, #random, etc.

### Step 3 — Quick route

Apply routing rules from `skills/classify-route.md`.
Morning restrictions:
- ✅ Route: #todo, #task, #sched, #project, #random, #money, #life, #feel
- ⏸ HOLD: #interrupt entries — do NOT process until 22:00
- ⚡ Quick only: #know, #eng → log to queue, deep write at night

For each #sched entry → also create Google Calendar event (before checking conflicts).

### Step 4 — Calendar conflict check

Before adding anything to SCHEDULE block:
1. Fetch Google Calendar for today — `[your-email@gmail.com]`, [Your/Timezone]
2. Also check `[optional-secondary-calendar-id@group.calendar.google.com]`
3. Flag any conflicts: "⚠️ [task] conflicts with [event] at [time] — reschedule?"

### Step 5 — Set GOALS

Fill the GOALS callout blocks in today's daily page:
- Goal 1: top identity priority (PhD / research push)
- Goal 2: today's key grind task (from dump or context)
- Goal 3: English/IELTS progress

Keep to 1 sentence each. These frame the whole day.

### Step 6 — Set HABITS template

Fill HABITS callout blocks (if not already set by template):
```
- [ ] IELTS drill (30 min)
- [ ] English mistakes log
- [ ] Night digest 22:00
```

### Step 7 — Language drill (short)

Pick 3 vocab words from dump or yesterday's reading.
Write to `English/vocab-daily/YYYY-MM-DD.md` — format:
```
**word** /pronunciation/ — definition
Example: [natural sentence]
IELTS relevance: [academic context]
```

### Step 8 — Task density check

Before finalizing TO DO:
- Count existing 🔥 grind tasks on today's page
- Max 3. Overflow → Projects queue.
- See full rule: `CLAUDE.md` → Task Density Rule

### Step 9 — Master Review update

Rewrite Master Review page with morning summary:
```
## 2026-MM-DD Morning Brief — synced HH:MM WIB
**Goals today:** [3 goals]
**Grind tasks:** [count/3 slots filled]
**Dump processed:** [N entries]
**Interrupts held:** [N]
**Language drill:** [3 words]
**Calendar:** [any conflicts flagged]
```

### Step 10 — Strikethrough processed entries

For each processed dump entry (not #interrupt):
```
~~[exact original text]~~ ✓ synced YYYY-MM-DD HH:MM WIB
```

---

## WRITE TO

| Destination | What |
|-------------|------|
| Notion `Tasks/[D Month]` | GOALS, HABITS, TO DO (grind tasks), SCHEDULE (timed events) |
| Google Calendar `[your-email@gmail.com]` | Events from #sched entries + popup reminders |
| Obsidian `English/vocab-daily/YYYY-MM-DD.md` | Morning 3-word drill |
| Notion `Master Review` | Morning sync summary (replace_content) |
| Notion `/dump` | Strikethrough processed entries |

---

## MORNING TONE

Short. Direct. Action-forward.
No long explanations. No "here's what I did" summaries.
Give [your name] the 3 goals + a clean plan. Done.
