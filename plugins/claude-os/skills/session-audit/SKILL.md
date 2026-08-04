---
name: session-audit
description: End-of-session audit for your Claude OS. Scans the conversation for corrections, preferences, decisions, and new facts that should be saved, and proposes exactly where each goes across your CLAUDE.md and MEMORY.md files. If you connected a task system during setup, it also catches tasks you mentioned that are not tracked yet and, on your confirmation, creates them. Everything is proposed first and written only on your approval. Use when you say "audit this session", "session audit", "what did we miss", "end of session check", or "save what we learned".
---

# Session Audit

An end-of-session pass that catches anything from the conversation worth saving or acting on, so nothing has to be repeated. Everything is proposed first and applied only on approval. This skill never writes without a yes.

## Step 0: Read the OS and the task mode

Find the workspace root (the folder with a `CLAUDE.md` and the Floor Plan at its top level). Read:

1. Root `CLAUDE.md` (standing instructions)
2. Root `MEMORY.md` (accumulated facts)
3. The newest file in `memory/` (the last session log), if one exists
4. `00_Shelf/connections.md` (this sets the task mode)
5. Any department or desk `CLAUDE.md` and `MEMORY.md` actually used this session

**Task mode.** Read the task settings in `00_Shelf/connections.md`:
- `task_capture: on` plus `verified: yes` means you run in **capture + tasks** mode.
- Anything else (off, no task system, or never verified) means **capture-only**: save learnings to files, and do NOT attempt to create tasks.

If `connections.md` is missing, assume capture-only and mention once that a task system can be wired by re-running the builder's connection step.

## Step 1: Scan the conversation for learnings

Go through the whole conversation top to bottom. Look for four signal types:

**A. Corrections.** They edited, rejected, or rewrote your output. Ask what underlying rule drove the change. (Changed "Best regards" to "Thanks" implies a sign-off rule.)

**B. Explicit preferences.** Direct instructions: "always", "never", "I prefer", "from now on", "don't do that".

**C. Decisions.** A choice that affects future work: picking one option, setting a deadline, resolving an ambiguity, so it is not re-asked later.

**D. New facts.** Something about them, the business, or their world that was not known before: a contact, a price change, a channel, a client status, a launch date.

## Step 2: Decide where each one goes

Sort each finding with the OS's own three tests:

- **Prescribes behavior?** ("always", "never", "before X do Y") goes in a `CLAUDE.md`: root if it applies everywhere, the department's own file if it only applies there.
- **A fact about the current state of the business?** (status, contacts, prices, dated decisions) goes in a `MEMORY.md` at the level it is true for (root, or the department or desk it belongs to).
- **Something clipped or studied from outside the business?** goes in a notes or knowledge folder if the workspace keeps one, never in `MEMORY.md`.

If more than one file fits, name the one you would choose and your reason, then wait for confirmation.

For each finding, state the exact file, the section, and the wording you would write.

## Step 3: Scan for task gaps (capture + tasks mode only)

Skip this entire step in capture-only mode.

Look for anything that sounds like a commitment or a next step ("I should...", "I need to...", "let's do X by Friday") that is not already tracked.

Read the current tasks from the connected system first, then compare, so you only surface genuinely missing ones. Use whichever connector `connections.md` names. Present the candidates and let them confirm which are real. Confirmation gates everything: nothing is created until they say a task is valid. Propose only here; writes happen in Step 5.

## Step 4: Present findings

Group into clear sections. Use this format for each item:

```
[Number]. [What happened]
- The rule / fact / task: [exact wording or draft task]
- Where it goes: [file + section, or the task system]
- Why: [one sentence]
```

Sections:
- **Memory and preferences.** Split into "Recommend (apply unless you object)" and "Your call".
- **Tasks** (capture + tasks mode only). Each confirmed task as a draft, with any due date mentioned. Marked "Your call".

Before listing anything, filter against what is already saved. Skip anything already in the files or already a task. If a scan is clean, say so plainly: "Clean session, nothing new to capture."

## Step 5: Apply approved changes

After approval (all, some, or none):

- **Files.** Write the approved learnings into the right `CLAUDE.md` or `MEMORY.md`. After each write, drop the marker (below) so the change is visible.
- **Tasks** (capture + tasks mode only). For each approved task, create it in the connected system with the fields that system uses (title, due date, list or project). Confirm with the new task's link.

Never write anything (file or task) that was not approved. Present first, wait.

## The memory marker

Every time you write to a `MEMORY.md`, a `CLAUDE.md`, or a session log, drop one line so the change is visible:

`📝 remembered: <the thing> → <file>`

One line per write. Never emit it if you did not actually write. This marker is a functional log line, the one intentional exception to the no-emoji rule the OS otherwise follows.
