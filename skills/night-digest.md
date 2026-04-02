# Skill: Night Digest
> Trigger: `run night digest` | 22:00 WIB | end of day
> Style: thorough, reflective, complete — clear the dump, close the day

---

## WHEN

- User types `run night digest`
- Scheduled 22:00 WIB daily
- End of day — this is the full processing session
- Everything gets written. Dump gets cleared.

---

## DO

### Step 1 — Read today's daily page

```
1. Fetch Tasks DB → find today's page "[D Month]"
2. READ full current content — note manual tasks, completed items, open items
3. This is the reference state for the rest of the digest
```

### Step 2 — Read entire dump

- Fetch `/dump` — ALL unprocessed entries (no strikethrough yet)
- Include everything from today + any held #interrupt entries
- List all unique tags present

### Step 3 — Full classify + route

Apply ALL routing rules from `skills/classify-route.md`.
Night opens everything — no holds except tomorrow's #interrupt.

Run in this order to manage tool calls efficiently:

```
Pass 1 — Time-sensitive (Notion + GCal)
  #sched, #deadline → daily SCHEDULE + Google Calendar events

Pass 2 — Task writes (Notion)
  #todo, #task → daily TO DO (density check first)
  #project → matching Projects page (fetch → update)
  #random → Projects/🎲 Random Ideas Queue (fetch → append)

Pass 3 — Life pages (Notion)
  #feel, #journal → Life/journal/ + daily REFLECTION
  #money → Life/money-log/ table row
  #life → Life/step-tracking/ table row

Pass 4 — Knowledge (Obsidian)
  #know, #research → Obsidian Knowledge/ or Research/
    → concept-note template
    → at least 1 [[backlink]]
    → update MOC

Pass 5 — Language (Obsidian)
  #eng, #vocab → English/vocab-daily/YYYY-MM-DD.md + mistakes-log/
    → format: I wrote [X] | Better: [Y] | Why: [reason]

Pass 6 — Blog
  #blog → run 5-point qualify check
    score ≥ 4 → Notion Blog pipeline/🟡 flagged + Obsidian Output/blog-drafts/
    score < 4 → archive with reason

Pass 7 — Interrupts
  #interrupt entries held since morning → process now by content type
  Note "Was #interrupt" on each entry's destination
```

### Step 4 — Language scan (full)

Scan ALL dump text — not just #eng tagged entries.
Every grammatical error or awkward phrase gets logged:
```
I wrote: [X] | Better: [Y] | Why: [reason]
```
Write to: `Obsidian English/mistakes-log/YYYY-MM-DD.md`

### Step 5 — Fill HABITS

Check today's habit completion in daily page:
```
- [x] IELTS drill (30 min) — done / not done
- [x] English mistakes log — done / not done
- [x] Night digest 22:00 — ✓
```
Update based on what was actually done (check dump + calendar for evidence).

### Step 6 — Fill REFLECTION

From #feel/#journal entries + end-of-day context:
```
Format in daily page REFLECTION section:
[mood] | mental [score]/10 | [2–3 sentence reflection]
```

### Step 7 — Verification checklist

Before striking through ANYTHING:
```
- [ ] All #todo → daily TO DO
- [ ] All #sched → Google Calendar + SCHEDULE block
- [ ] All #project → matching project page updated
- [ ] All #feel/#journal → Life/journal/ + daily REFLECTION
- [ ] All #money → Life/money-log/ row
- [ ] All #life → Life/step-tracking/ row
- [ ] All #know/#research → Obsidian with [[backlinks]] + MOC
- [ ] All #eng/#vocab → English/ files
- [ ] All #blog → qualify check run
- [ ] All #interrupt → processed, noted "Was #interrupt"
- [ ] Language scan → mistakes-log written
- [ ] Master Review → ready to rewrite
```

If anything fails → go back and write it. Do not proceed to strikethrough.

### Step 8 — Strikethrough ALL processed entries

One by one. No batching. Character-for-character match:
```
old_str: "#feel tired, mental 7/10"
new_str: "~~#feel tired, mental 7/10~~ ✓ synced 2026-03-30 22:00 WIB"
```
Never delete. Only strikethrough + timestamp.
Entries already struck through from earlier syncs → skip.

### Step 9 — Master Review full rewrite

Fetch current Master Review → use replace_content for full rewrite:
```
## YYYY-MM-DD Night Digest — synced HH:MM WIB

**Entries processed:** [N total] | [N Notion] | [N Obsidian] | [N GCal]
**Interrupts processed:** [N] (were held since [time])

### GOALS recap
1. [goal 1] — ✓ done / partial / → tomorrow
2. [goal 2]
3. [goal 3]

### Language
Mistakes logged: [N] | Vocab added: [N words]
Highlight: [most interesting correction]

### Blog pipeline
[any new flags or status updates]

### Reflection
[1-line honest reflection on the day]

### Tomorrow
[1–2 things to front-load in morning brief]
```

---

## WRITE TO

| Destination | What |
|-------------|------|
| Notion `Tasks/[D Month]` | HABITS (checked), REFLECTION, any remaining TO DO |
| Notion `Projects/[matching]` | All #project updates with timestamps |
| Notion `Projects/` (Random Ideas Queue) | All #random/#idea entries |
| Notion `Life/journal/` | Dated #feel/#journal entry |
| Notion `Life/money-log/` | Table row per #money entry |
| Notion `Life/step-tracking/` | Table row per #life entry |
| Notion `Blog pipeline/🟡 flagged` | Blog entries scoring ≥ 4 |
| Obsidian `Knowledge/` or `Research/` | #know/#research — concept notes |
| Obsidian `English/vocab-daily/YYYY-MM-DD.md` | Vocab from #eng/#vocab |
| Obsidian `English/mistakes-log/YYYY-MM-DD.md` | Full language scan output |
| Obsidian `Life/journal/YYYY-MM-DD.md` | Journal mirror |
| Obsidian `Output/blog-drafts/` | Blog entries that passed qualify |
| Google Calendar `[your-email@gmail.com]` | Events from #sched entries |
| Notion `Master Review` | Full rewrite with day summary |
| Notion `/dump` | Strikethrough ALL processed entries |

---

## NIGHT TONE

Thorough. Honest. No rush, but no padding.
Reflect in the user's voice: direct, curious, Indonesian perspective.
One-line reflection at the end — real, not motivational.
