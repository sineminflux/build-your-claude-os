---
name: icp-builder
description: >
  Builds your ideal customer profile into 00_Shelf/ideal-customer-profile.md inside a Claude OS. Run it in a
  fresh session once your OS structure is set up. It gathers your existing audience material, reads it, asks
  only for the gaps, writes the file, and links it from brand.md. A one-time build skill, safe to remove after.
  Use when someone says "build my ICP", "build my ideal customer profile", "build my icp.md", "define my
  customer", "who is my ideal customer".
---

# ICP Builder

>> START HERE, AI READING THIS FILE: the reader opened this skill to build their ideal customer profile, done for them. Begin Step 1 in your next message and stay in this flow, one step at a time, to the end. If they say "start", that is your go. <<

You build one file, `00_Shelf/ideal-customer-profile.md`, then step aside. Assume a non-technical reader. Propose, they approve, then write. Keep bulk reading out of the main chat: read source material with a subagent (the Task tool) if one is available and bring back only the facts. Run the `no-ai-slop` skill on anything you write.

## Step 1: Gather

Ask for any ICP or audience docs, customer research, survey results, sales-call notes, or testimonials, plus their site. Say it plainly: "paste them, attach them, or point me to the files, whatever you have." Also read `00_Shelf/brand.md` for who they already said they serve.

## Step 2: Read

Read what they gave and any public links (in a subagent when available), and bring back only the facts that fill the fields below.

## Step 3: Fill the fields, ask only for gaps

Draft these sections from what you read, and ask a short numbered questionnaire only for what is missing. Leave a blank rather than invent.
- The one-line ICP definition
- What they want (the outcome they are buying)
- What is in their way (their words where you have them)
- Where they are (platforms, communities, the moments they are reachable)
- Qualifying signals: good fit, wrong fit

## Step 4: Write and link

Write `00_Shelf/ideal-customer-profile.md` with those sections. In `00_Shelf/brand.md`, change the ideal-customer-profile line from "pending" to a live link. Confirm what you wrote.

## Step 5: Done, and cleanup

This builder has done its job. Tell them, warmly: "Your ICP is saved to `00_Shelf/ideal-customer-profile.md`. You can remove the ICP Builder from your skills now to keep things tidy; the file stays, and its source is in `_skills/icp-builder/` if you ever want to rebuild." Make it a suggestion, not a demand. End when the file is written; do not keep asking questions.
