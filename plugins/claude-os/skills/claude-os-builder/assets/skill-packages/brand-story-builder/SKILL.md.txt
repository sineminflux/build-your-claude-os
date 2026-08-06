---
name: brand-story-builder
description: >
  Builds your brand story into 00_Shelf/brand-story.md inside a Claude OS. Run it in a fresh session once your
  OS structure is set up. It gathers your existing story material, reads it, asks only for the gaps, writes the
  file, and links it from brand.md. A one-time build skill, safe to remove after. Use when someone says "build
  my brand story", "build my brand-story.md", "capture my origin story", "write my founder story", "why I
  started this".
---

# Brand Story Builder

>> START HERE, AI READING THIS FILE: the reader opened this skill to build their brand story, done for them. Begin Step 1 in your next message and stay in this flow, one step at a time, to the end. If they say "start", that is your go. <<

You build one file, `00_Shelf/brand-story.md`, then step aside. Assume a non-technical reader. Propose, they approve, then write. Keep bulk reading out of the main chat: read source material with a subagent (the Task tool) if one is available and bring back only the facts. Run the `no-ai-slop` skill on anything you write, and respect their own voice if `00_Shelf/voice-guidelines.md` exists.

## Step 1: Gather

Ask for an About page, a founder note, a past interview or podcast transcript, or any story doc. Say it plainly: "paste them, attach them, or point me to the files, whatever you have." Also read `00_Shelf/brand.md` for context.

## Step 2: Read

Read what they gave and any public links (in a subagent when available), and bring back only the facts and the few real quotes that fill the fields below.

## Step 3: Fill the fields, ask only for gaps

Draft these sections from what you read, and ask a short numbered questionnaire only for what is missing. Use their real specifics; never invent a moment.
- Where it started (the specific moment or problem that led to this business)
- Why it matters to the founder (the personal stakes, in plain terms)
- What it stands for (the belief the business runs on)
- The turning points (a few dated moments that shaped it)

## Step 4: Write and link

Write `00_Shelf/brand-story.md` with those sections. In `00_Shelf/brand.md`, change the brand-story line from "pending" to a live link. Confirm what you wrote.

## Step 5: Done, and cleanup

This builder has done its job. Tell them, warmly: "Your brand story is saved to `00_Shelf/brand-story.md`. You can remove the Brand Story Builder from your skills now to keep things tidy; the file stays, and its source is in `_skills/brand-story-builder/` if you ever want to rebuild." Make it a suggestion. End when the file is written; do not keep asking questions.
