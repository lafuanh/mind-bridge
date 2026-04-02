# Known Bugs

## Cowork Scheduler Desktop Bug 

**Status:** Solved → place folder on home dir
**Affects:** Claude Code desktop app → Cowork Scheduler feature

### Description

The Cowork Scheduler on the desktop app fails to read local `.md` files when triggered by a scheduled run. The scheduler fires correctly, but Claude cannot access the local filesystem to read `CLAUDE.md` or other project files.

### Steps to Reproduce

1. Set up Cowork with the sync prompt from `.claude/cowork-sync-prompt.md`
2. Configure a scheduled run (e.g. `/schedule` for morning brief)
3. Wait for the scheduled trigger to fire
4. Observe: Claude reports it cannot read `CLAUDE.md` or local files

### Expected Behavior

Scheduled Cowork runs should have the same file access as manual Cowork sessions — able to read `CLAUDE.md` and all project files.

### Actual Behavior

Claude fails with file access errors. The sync cannot proceed because `CLAUDE.md` contains all routing rules.

### Workaround

Use one of these alternatives:
- **Claude Code web** (claude.ai/code) — Cowork Scheduler works correctly there
- **Manual paste** — copy the sync prompt into a regular Claude session
- **CLI** — run syncs manually via `claude` in your terminal

---

## AutoJourney-Cowork (Obsidian Vault Builder) Bug

**Status:** Open
**Affects:** Night digest → Obsidian vault auto-write flow

### Description

The AutoJourney-cowork flow, which automatically builds Obsidian vault entries during the night digest sync, fails to trigger correctly. The night event that should kick off deep Obsidian writes (journal entries, knowledge notes, blog drafts) does not execute the full pipeline.

### Root Cause (Suspected)

The night digest event trigger depends on the Cowork Scheduler firing and having both Notion read access and local filesystem write access simultaneously. When the scheduler fires, it loses the local file context needed to write to the Obsidian vault directory.

This is related to the Cowork Scheduler Desktop Bug above — the same file access limitation prevents writing to the vault.

### Affected Flow

```
Night digest trigger
  → Read dump entries
  → Classify #know, #research, #feel, #eng entries
  → Write to obsidian-vault/ directories     ← FAILS HERE
  → Update MOCs and backlinks                ← Never reached
```

### Workaround

Run the night digest manually via CLI or web:
```
run night digest
```

Manual runs have full filesystem access and can write to the Obsidian vault correctly.

---

## Token Context Limit — Night Digest

**Status:** Known constraint
**Affects:** Night digest with large dumps or many `#know`/`#research` entries

### Description

If the `/dump` page has accumulated a large number of unprocessed entries (e.g. after a skipped sync or a heavy research day), the night digest can approach or hit the session context limit before completing all Obsidian writes. Claude may stop mid-sync without writing all destinations.

### Signs this is happening

- Night digest completes Notion writes but Obsidian notes are missing
- Session ends abruptly without a verification checklist output
- Master Review is not fully rewritten

### Workaround

Split the night digest into two passes:

**Pass 1** — Notion + Calendar writes only:
```
run night digest — notion and calendar only, skip obsidian writes
```

**Pass 2** — Obsidian writes only (new session):
```
run night digest — obsidian writes only, dump already processed
```

Alternatively, process `#know` and `#research` entries during the day using `obsidian write [topic]` so the night digest has less to write.

### Prevention

- Keep daily dump entries concise — one idea per line
- Use `#interrupt` to defer non-urgent captures rather than dumping mid-flow
- Run midday flush consistently — smaller batches = lower per-sync token cost
