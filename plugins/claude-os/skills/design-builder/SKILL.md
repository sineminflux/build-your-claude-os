---
name: design-builder
description: >
  Builds your brand design guidelines into 00_Shelf/design-guidelines.md inside a Claude OS. Run it in a fresh
  session once your OS structure is set up. It gathers your existing brand and style material, reads it, asks
  only for the gaps, writes the file, and links it from brand.md. A one-time build skill, safe to remove after.
  Use when someone says "build my design guidelines", "build my design.md", "build my brand style guide",
  "capture my brand design", "set up my visual guidelines".
---

# Design Guidelines Builder

>> START HERE, AI READING THIS FILE: the reader opened this skill to build their design guidelines, done for them. Begin Step 1 in your next message and stay in this flow, one step at a time, to the end. If they say "start", that is your go. <<

You build one file, `00_Shelf/design-guidelines.md`, then step aside. Assume a non-technical reader. Propose, they approve, then write. Keep bulk reading out of the main chat: read source material with a subagent (the Task tool) if one is available and bring back only the facts. Run the `no-ai-slop` skill on anything you write.

## Step 1: Gather

Ask for a brand or style guide, a design system, logo files, or their site and social profiles. Say it plainly: "paste them, attach them, or point me to the files, whatever you have." Also read `00_Shelf/brand.md` for context.

## Step 2: Read

Read what they gave and any public links (in a subagent when available), and bring back only the facts that fill the fields below. If they have a live site, note the actual colours and fonts in use.

## Step 3: Fill the fields, ask only for gaps

Draft these sections from what you read, and ask a short numbered questionnaire only for what is missing. Leave a blank rather than invent a colour or a font.
- Colours, with hex codes (primary and accent)
- Type: heading font, body font, and where each is used
- Logo and marks: where the files live, and the rules for using them
- Look and feel: three to five words, plus a link or two to examples to match
- Do not: colours, effects, or layouts that are off-brand

## Step 4: Write and link

Write `00_Shelf/design-guidelines.md` with those sections. In `00_Shelf/brand.md`, change the design-guidelines line from "pending" to a live link. Confirm what you wrote.

## Step 5: Done, and cleanup

This builder has done its job. Tell them, warmly: "Your design guidelines are saved to `00_Shelf/design-guidelines.md`. You can remove the Design Guidelines Builder from your skills now to keep things tidy; the file stays, and its source is in `_skills/design-builder/` if you ever want to rebuild." Make it a suggestion. End when the file is written; do not keep asking questions.
