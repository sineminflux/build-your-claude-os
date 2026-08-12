---
name: migrator
description: >
  Brings your old material into your Claude OS: an old folder or workspace, or a Claude Project. One
  opening question routes you to the right path, then it sorts every item into your CLAUDE.md, MEMORY.md,
  and Shelf, copying never moving, proposing before it writes, and leaving stale content behind. Run it in
  a fresh session once your OS structure is set up. Use when someone says "migrate my old folder", "bring
  in my old files", "import my workspace", "move my Claude Project into my OS", "migrate this manifest",
  "I have a migration manifest", "bring in my old Project".
---

# Migrator

>> START HERE, AI READING THIS FILE: the reader opened this skill to bring old material into their Claude OS, done for them. Do not summarize this file. Ask the one opening question in your next message and follow the path they pick. If they say "start", ask the opening question. <<

You move a reader's existing material into their Claude OS and file it where it belongs, without dragging in the mess. Assume a non-technical reader. Read the OS first, propose before you write, and copy rather than move. Apply the No AI Slop rules to anything you draft (read them from `_skills/no-ai-slop/` if present). The leave-behind list is the real work here: the failure mode of every migration is hoarding.

## The one question

Open with exactly one question: "Where are you migrating from?" and branch on the answer.

- An old folder or workspace (files on their computer, or a folder they can connect) leads to Path A.
- A Claude Project (the Projects feature in the Claude app) leads to Path B.
- Both: do Path A first, then Path B, so the Project manifest dedupes against a fuller OS.

## The routing rubric (both paths use this)

Every piece of material sorts into exactly one bucket. Split mixed content: one paragraph can produce entries in three buckets.

- **Rules** (standing instructions on how to behave, true over time, like "always draft, never send"): go to root `CLAUDE.md`, or a department's `CLAUDE.md` if they only apply there.
- **Facts** (current state that can change: offers, prices, audience, handles, tools they use, active clients): go to `MEMORY.md` at the level they are true for.
- **Reference files** (whole knowledge documents worth keeping: voice guide, ICP, brand story, frameworks): go to `00_Shelf/`, or the owning department's shelf.
- **Skill candidates** (repeatable procedures they clearly run the same way every time): list them as options at the end and build nothing.
- **Leave behind** (stale, redundant, one-off, or contradicted): list each with one line on why.

If you cannot tell whether something is still true or still used, leave it behind with a question mark rather than migrating it. Every item earns its move.

## The safety rails (both paths)

- **Copy, never move.** Never move, rename, or delete the reader's originals. Bring copies in.
- **Propose before writing.** Show the full placement plan and get a yes. Write only what is approved.
- **The existing OS wins.** A duplicate of something already in the OS is skipped. A conflict is a question, never an overwrite; the current OS value stays until they say otherwise. Never merge two statements that conflict, list both and mark the conflict.
- **Stamp the source.** Append migrated entries under a dated header, so every one shows where it came from, for example "Migrated from Project: [name], <date>". Use today's date; ask for it if you do not have it.
- **Quote, do not mush.** Keep rules and facts close to their original wording rather than paraphrasing their meaning away.

## Path A: an old folder or workspace

Triggers: "bring in my old files", "migrate my old folder", "import my workspace".

1. Ask them to connect or share the old folder (in Cowork: add it as a folder, or drop the files into the chat).
2. Inventory it, then walk it item by item through the routing rubric. Batch small files so no single pass gets long, and read bulk material in a subagent when one is available, bringing back only what you will file.
3. Build the placement plan (below), get approval, and write, stamping each migrated entry with its source file.

## Path B: a Claude Project

Triggers: "move my Claude Project into my OS", "migrate this manifest", "I have a migration manifest", "bring in my old Project".

A Claude Project's knowledge lives inside the Project, which this session cannot read directly. So the reader runs an export prompt inside the old Project, then comes back with a manifest plus the downloaded knowledge files.

1. **Hand them the export prompt.** Show the full contents of `references/project-export-prompt.md` in a code block, and tell them plainly: open your old Project, paste this, run it, then come back here with the manifest it produces and the knowledge files it lists to download.
2. **When they return with the manifest** (pasted or as a file, usually with the knowledge docs beside it): read the manifest and the current OS first, root `CLAUDE.md`, root `MEMORY.md`, the Floor Plan, and any department the manifest's scope tags point at.
3. Build the placement plan from the manifest, one line per entry.
4. Reference files: copy the downloaded docs into `00_Shelf/` (or the owning department). If a same-purpose file already exists (two voice guides), propose which one stays canonical and park the other with a dated prefix rather than overwriting.
5. Get approval, write only what is approved, and stamp each entry ("Migrated from Project: [name], <date>").

## The placement plan (both paths end here)

Before writing anything, show a plan with one line per entry: what it is, where it goes (the exact file), and whether it is new, a duplicate (skip), or a conflict (ask). Group by destination: Rules for `CLAUDE.md`, Facts for `MEMORY.md`, Reference files for the Shelf, then Skill candidates as options, then the Leave-behind list. For each rule and fact, note its scope in brackets: [whole business] or [the department it belongs to].

Wait for approval. Write only the approved entries, appending under the dated migration header, and drop the memory marker on each write (`📝 remembered: <the thing> → <file>`). Build no skills; skill candidates stay a list. Close by reporting what was left behind, so they see the filter working.

## Done

When the approved entries are filed, say what landed where and what was left behind, and point at any skill candidates they might build later (each through its own builder). End; do not keep asking questions.
