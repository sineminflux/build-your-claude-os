# Project export prompt (Path B)

Show the reader everything inside the fenced block below, in a code block they can copy. They paste it into their old Claude Project, run it there, and bring back the manifest plus the listed knowledge files.

```
I'm moving this Project into my Claude OS, a folder-based workspace in
Claude Cowork with a CLAUDE.md (standing rules), a MEMORY.md (current
facts), and a shelf of reference files loaded on demand. Your job is to
inventory everything this Project knows and sort it into a migration
manifest I'll carry over. Extract, don't summarize.

STEP 1: INVENTORY
List every knowledge file in this Project by exact name. Then restate
the Project's custom instructions in full. If I've pasted any extra
context into this chat, include it in the inventory too.

STEP 2: SORT
Sort every piece of information into exactly one of these buckets.
Split mixed content: one paragraph of instructions can produce entries
in three different buckets.

- RULES: standing instructions on how to behave that stay true over
  time ("always draft, never send", "write in my voice file's style").
  Destination: CLAUDE.md.
- FACTS: current facts that can change (my offer, prices, audience,
  handles, tools I use, active clients). Destination: MEMORY.md.
- REFERENCE FILES: knowledge documents worth carrying over whole
  (voice guide, ICP, brand story, frameworks). Destination: the shelf.
- SKILL CANDIDATES: repeatable procedures I clearly run the same way
  every time. List them; my OS will decide whether to build them.
- LEAVE BEHIND: stale, redundant, one-off, or contradicted content.
  List it with one line on why.

Sorting rules:
- Every item must earn its move. If you can't tell whether something
  is still true or still used, put it in LEAVE BEHIND with a question
  mark instead of migrating it.
- Never merge two statements that conflict. List both and mark the
  conflict.
- Quote rules and facts close to their original wording. Don't
  paraphrase meaning into mush.

STEP 3: OUTPUT THE MANIFEST
Produce one markdown document titled "Migration manifest: [Project
name]" with these sections in this order: Rules for CLAUDE.md / Facts
for MEMORY.md / Reference files for the shelf / Skill candidates /
Left behind / Conflicts and open questions. One line per entry. For
each rule and fact, add your best guess at scope in brackets: [whole
business] or [name of the business area it belongs to].

End with a checklist of the exact files I need to download from this
Project's knowledge and bring into my Cowork session alongside this
manifest.
```
