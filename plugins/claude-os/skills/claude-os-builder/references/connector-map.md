# Connectors and the task-system check

Two jobs here: map the reader's whole working stack and find the gaps (not just list what is already connected), and set up their task system with a live check so the session audit can trust it later.

Claude cannot connect a tool for the reader. Connecting happens in the reader's app settings. The builder's job is to ask, recommend, explain what each connection buys, and verify the one connection the OS depends on (their task system).

## Step A: Map the working stack, then find the gaps

The goal is not to inventory what happens to be connected. It is to learn the tools the reader actually uses day to day and see which are wired, which are worth wiring, and which they use that the OS cannot reach yet. Even when a lot is already connected, do the interview, because the live connectors are rarely the whole stack.

Start by noting what is already connected in this session as a first inventory. Then go job by job and ask what they use for each, letting them name the tool:

- Email and calendar
- Notes and docs
- Tasks and projects
- Messaging
- Publishing and audience (newsletter, social, scheduler)
- Money and commerce (payments, store, bookkeeping)
- Design and creative
- Automation and data (Zapier, Make, scrapers)
- Anything else they live in daily

For each tool they name, check it against what is connected and against the connector registry (SearchMcpRegistry), and sort it into one of three buckets:

1. **Connected already.** Map it to how the OS would use it ("Gmail, so the OS drafts replies and triages, drafts only").
2. **Has a connector, not wired.** Recommend connecting it, one line on what it unlocks.
3. **No connector exists.** Name the gap and the manual path ("no connector for that yet, so the OS drafts it and you paste").

Also flag blanks: a job with no tool at all is a gap worth naming (no task system, or nowhere their notes live).

## Step B: Present the stack map and recommend

Give the reader the three-bucket map, so both the wins and the gaps are visible: what is connected and how the OS uses it, what is worth wiring next (ranked, one line each), and what they use that has no connector (with the manual workaround). This is where missing connections surface, which is the point of the step.

Write the connected and worth-wiring tools into `00_Shelf/connections.md` (status `connected` or `requested`), and record the no-connector gaps too, so a future session knows what the OS cannot reach. Tell them the wiring itself happens in their app's connector settings, not by Claude.

Respect the guardrails: never suggest a connection that spends money or posts publicly as an automatic action. Connections are for reading and drafting by default.

## Step C: The task-system check (the one that must work)

The session audit can create tasks, but only into a task system that is connected and proven. Do this during onboarding:

1. **Ask which task system they use**, from the list above. If they do not use one, or do not want the OS creating tasks, set `task_capture: off` in `connections.md` and skip the rest of this step. The audit will run capture-only.
2. **If they name one and want task capture on**, confirm the connector is available (SearchMcpRegistry) and ask them to connect it in their settings if it is not already.
3. **Run a live create-and-read-back test.** With their okay, create one throwaway task titled something obvious like "Claude OS connection test", then read it back through the same connector to confirm it exists. Show them the result.
4. **Record the outcome** in `00_Shelf/connections.md`:
   - the task system name,
   - `task_capture: on`,
   - `verified: yes` and the date, or `verified: no` with the error if the read-back failed.
5. **Clean up.** Offer to delete the test task, or tell them to remove it (deletion needs their okay per the guardrails).

If the read-back fails, do not set `verified: yes`. Tell the reader what broke and leave `task_capture` off until it works, so the audit never tries to write into a connection that is not there.

## What connections.md drives

The session-audit skill reads `00_Shelf/connections.md` at the start of every audit. `task_capture: on` plus `verified: yes` is the only combination that lets it create tasks. Anything else and it runs capture-only, saving learnings to files without touching a task system.
