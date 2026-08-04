# Connectors and the task-system check

Two jobs here: interview the reader about the tools they already use and suggest which connectors to wire, and set up their task system with a live check so the session audit can trust it later.

Claude cannot connect a tool for the reader. Connecting happens in the reader's app settings. The builder's job is to ask, recommend, explain what each connection buys, and verify the one connection the OS depends on (their task system).

## Step A: Interview the tools

Ask what the reader already uses, in plain groups. Do not read a huge list at them; ask by job:

- **Email and calendar:** Gmail, Google Calendar, Outlook.
- **Notes and docs:** Notion, Google Drive, Obsidian.
- **Tasks and projects:** Notion, Todoist, Asana, Trello, Google Tasks, Linear.
- **Messaging:** Slack, Discord.
- **Publishing and audience:** their newsletter platform, social scheduler, LinkedIn.
- **Money and commerce:** Stripe, their store platform, their bookkeeping tool.

For each tool they name, search the connector registry (SearchMcpRegistry) and, if a connector exists, suggest it with one line on what it unlocks in the OS ("connect Gmail so the OS can draft replies and triage your inbox, drafts only"). If no connector exists, say so and move on.

## Step B: Recommend, do not connect

Give the reader a short, ranked list of connectors worth wiring for how they work, and tell them these are set up in their app's connector settings, not by Claude. Write the chosen list into `00_Shelf/connections.md` with a status of `requested` for each, so it is visible which are pending.

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
