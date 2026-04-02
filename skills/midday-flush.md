# Skill: Midday Flush
> Trigger: `run midday flush` | 11:45 WIB | between work sessions
> Style: quick, no deep writes, clear morning chaos

---

## WHEN

- User types `run midday flush`
- Scheduled 11:45 WIB daily
- Between morning grind and afternoon session
- Goal: process new captures, update schedule, keep momentum

---

## DO

### Step 1 — Read today's daily page

```
1. Fetch Tasks DB → find today's page "[D Month]"
2. READ full current content
3. Note: what's already checked, what's still open, current SCHEDULE state
4. Never overwrite — append only
```

### Step 2 — Read dump (morning entries only)

- Fetch `/dump` — entries since last strikethrough timestamp (~05:00 this morning)
- Quick scan all tags

### Step 3 — Route (quick pass)

Apply `skills/classify-route.md` routing rules. Midday restrictions:

- ✅ Route now: #todo, #task, #sched, #project, #random, #money, #life
- ⏸ HOLD: #interrupt — do NOT process, note count: "N interrupts held for 22:00"
- ⏸ HOLD: #know, #eng, #feel — log as queued, deep write at night

For #project entries → append update to matching Notion project page.
For #sched entries → check calendar conflict, create Google Cal event.

### Step 4 — Calendar conflict check

Before updating SCHEDULE block:
1. Fetch current Google Calendar for today (primary + class calendar)
2. Check if any morning entries conflict with afternoon
3. Flag conflicts: "⚠️ [task] conflicts with [event]"
4. Reschedule: suggest next free block

### Step 5 — Update SCHEDULE block

Add any new timed entries to the daily SCHEDULE:
```
Format: **2P** Meeting with [person]
```
Do not overwrite existing SCHEDULE entries — append at the correct time slot.

### Step 6 — Task density recheck

- Count current 🔥 grind tasks (checked + unchecked)
- If anything new from dump hits the limit → overflow to Projects queue
- Note: "→ [task] queued (density limit)"

### Step 7 — Master Review update (quick)

Append midday note to Master Review — do NOT full rewrite:
```
**Midday flush HH:MM WIB** — [N entries processed] | [N interrupts held] | [any reschedules]
```

### Step 8 — Strikethrough

Strike processed entries. Leave #interrupt untouched:
```
~~[entry text]~~ ✓ synced YYYY-MM-DD 11:45 WIB
```

---

## WRITE TO

| Destination | What |
|-------------|------|
| Notion `Tasks/[D Month]` | New TO DO items, SCHEDULE block updates |
| Notion `Projects/[matching page]` | #project update + timestamp |
| Google Calendar | New timed events from morning dump |
| Notion `Master Review` | Quick midday note (append, not replace) |
| Notion `/dump` | Strikethrough processed entries |

---

## MIDDAY TONE

Quick. No commentary. Scan → route → done.
Max 2 sentences of output per processed entry.
If everything is clean and no new entries, say: "Dump clean. No new entries since morning."
