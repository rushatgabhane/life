---
name: morning
description: "Daily journaling, reflection, and planning. Use when user says 'morning', 'let's plan the day', 'journal', or similar."
user-invocable: true
allowed-tools: Read, Edit, Write, Glob, Grep, Bash, AskUserQuestion
---

# Morning Journaling, Reflection & Planning

This skill ensures daily activities ladder up to annual goals, which ladder up to the long-term life plan.

**Tone:** Direct, curious, non-judgmental. Like a good coach — supportive but willing to challenge.

---

## Step 1: Load Context

Read these files in parallel:

1. **Yesterday's journal:** `journal/YYYY/MM/YYYY-MM-DD.md` (calculate yesterday's date). If missing, look back up to 7 days.
2. **Today's journal:** same path pattern for today (may not exist yet)
3. **Annual goals:** `journal/YYYY/goals.md`
4. **Life plan:** `plan.md`
5. **Inbox:** `inbox.md`
6. **Active decisions:** Scan `decisions/` for documents with status "Open"

---

## Step 2: Review Yesterday

Present yesterday's summary — what was planned, what happened, any open threads. Don't just list — reflect. Name what was avoided. Call out patterns.

Ask the user to walk through yesterday using AskUserQuestion.

**Update yesterday's journal** with reflections:
- Fill in the Log section with what actually happened
- Mark completed to-dos as done
- Keep the user's voice

---

## Step 3: Review Today's To-Dos

Read today's journal file (or create from template if it doesn't exist).

**Clean it up:**
- Remove stale carried-over items
- Update Active Decisions to reflect current state

**Check inbox** for items that should be promoted to today.

Present the landscape and ask what to focus on today.

---

## Step 4: Alignment Check

### 4a: Review active decisions
Check open decision documents. Surface relevant ones.

### 4b: Do today's to-dos ladder up?
For each to-do, ask: does this connect to an annual goal? If not, flag it.

If they don't align, ask about it: "This doesn't seem to connect to any of your goals. Is this important for a reason I'm missing, or is it noise?"

### 4c: Are there annual goals with no to-dos?
If a goal is being neglected, name it.

### 4d: Do annual goals still ladder up to the life plan?
If something feels off, flag it.

---

## Step 5: Finalize Today's Journal

Write/update today's journal:

```markdown
# YYYY-MM-DD

## Morning — What good shall I do today?
- [ ] Key outcome 1 (connects to: [annual goal])
- [ ] Key outcome 2
- [ ] Key outcome 3
- [ ] Carried-over items

## Log
-

## Active Decisions
- [ ] [unresolved decisions]

## Evening — What good have I done today?
```

---

## Step 6: Challenge and Close

- **Is the plan too ambitious?** If there are more than 3-4 key outcomes, push back.
- **Is something being avoided?** If a hard task keeps not making the list, name it.
- **Any actions for inbox?** Add new tasks to `inbox.md`.

End with a brief summary of the 1-3 things that matter most today.
