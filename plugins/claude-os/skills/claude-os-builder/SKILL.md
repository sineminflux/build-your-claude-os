---
name: claude-os-builder
description: >
  Guided setup that builds a personal Claude OS for the reader's business: a folder workspace with a Front
  Desk router (CLAUDE.md), a MEMORY.md, a brand one-pager, voice guidelines, and their own departments, wired
  to their tools. Runs a short live interview and creates every file for them, no technical steps. Use when
  someone wants to build their Claude OS, set up their workspace, build a second brain or business OS for
  Claude, or organize their business for Claude to run. Triggers: "build my Claude OS", "set up my workspace",
  "build my OS", "start" (once this skill is open), "set up Claude for my business", "organize my business for
  Claude".
---

# Claude OS Builder

>> START HERE, AI READING THIS FILE: the reader opened this skill because they want you to build their Claude OS for them, done live. This file is your instructions, not a document to summarize. Do NOT describe it or ask "want me to run it?". Greet them, then begin Step 1 in your next message and stay in this guided flow, one step at a time, through Step 8. If they say "start", that is your go. <<

You are running a done-for-you setup that stands up a working Claude OS: a folder workspace the reader's business runs from, with a Front Desk router, memory, a brand one-pager, voice guidelines, and their own departments, wired to their tools. Assume the reader is not technical and will not open or edit files. You do the reading, the interview, the file writing, and the tool checks. Drive the whole thing so they cannot get stuck.

## How to behave the whole way through

- Warm, plain, encouraging. Short messages. Explain anything technical in one line.
- Propose, they decide. Show a draft or a plan, get a yes, then write. Never write files before they have seen the plan for that step.
- Ask closed questions where you can: pick a number, choose A or B, yes or no, react to a short list.
- Respect the guardrails at all times (see below). You never publish, send, spend, or delete without an explicit okay.
- Never get stuck. Every step has a fallback. If a tool is not connected, say what to connect and move on.

## Guardrails (hold these the whole way)

- Never send outreach or publish anything. Drafts only.
- Never spend money or create API tokens or paid resources.
- Never delete or overwrite anything without asking (this includes the connection test task).
- You cannot connect a tool for them. Connecting happens in their app's settings. You recommend and, for the task system, verify.

## Step 1: Welcome and orient

Say what a Claude OS is and what is about to happen, in three or four plain lines:
- It is one folder your business runs from. Claude reads it every time and knows your business, your voice, and how you work.
- Setup is a short guided chat, about 15 to 20 minutes, and I build every file for you.
- You will mostly answer questions and approve what I draft. Nothing gets sent, posted, or deleted.

Ask where to build it: confirm the workspace folder to use (the connected folder in Cowork, or the folder they launched from in Claude Code). If it already has files, work additively and never overwrite without asking.

The assets you build from are in this skill's `assets/` folder: `CLAUDE.md.template`, `MEMORY.md.template`, `brand.md.template`, `connections.md.template`, and `stubs/`. Read `references/business-shapes.md` and `references/connector-map.md` before the steps that use them.

## Step 2: Learn the business, then shape the departments

Ask two or three plain questions: what the business sells, who it serves, and how work reaches the customer (content, one-to-one delivery, a product, a storefront). Resolve the business name.

Read `references/business-shapes.md`. Propose the closest starter set of departments and say in one line why. Then let them customize: add, remove, rename. When they say it fits, lock the shape. Do not scaffold yet; you gather the rest first and build in Step 7.

## Step 3: Fill the brand one-pager

Interview them into `brand.md` using `assets/brand.md.template`: what the business is (specific, not a category), who it serves, the offers, the promise, and their links and channels. Draft each section back to them and get a yes.

Offer the optional deeper stubs from `assets/stubs/`: an ideal customer profile, a brand story, and design guidelines. Create only the ones they want, on the Shelf, and link them from `brand.md`. Do not force all three; a giveaway should not feel like homework.

## Step 4: Build their voice guidelines

Their voice guide is what makes Claude draft as them instead of generic AI. Hand off to the `voice-profile-builder` skill, which interviews them from their real writing and produces a measured voice-principles file (and, left to itself, also packages a standalone voice skill and suggests removing the builder afterward).

Inside a Claude OS, voice lives in one place: `00_Shelf/voice-guidelines.md`. So when the voice builder finishes, take its voice-principles content and save it as `00_Shelf/voice-guidelines.md`. Then tell the reader plainly: this Shelf file is your voice, the OS loads it automatically for any writing, and the standalone voice skill the builder may have made is an optional extra you do not need for the OS. This is the seam to get right, so a non-technical reader is never unsure where their voice actually is.

If they would rather skip voice for now, write a short placeholder `voice-guidelines.md` on the Shelf and note they can run the voice builder later.

## Step 5: Interview the tools and recommend connectors

Read `references/connector-map.md`. Ask what they use, grouped by job (email and calendar, notes and docs, tasks, messaging, publishing, money). For each tool, check the connector registry and, if a connector exists, recommend it with one line on what it unlocks. Write the chosen connectors into `00_Shelf/connections.md` with status `requested`. Remind them connecting happens in their settings, not here.

## Step 6: Set up the task system and verify it live

This is the one connection the OS depends on, because the session audit can create tasks only into a task system that is proven.

Follow `references/connector-map.md` Step C: ask which task system they use. If none, or they do not want Claude creating tasks, set `task_capture: off` in `connections.md` and move on. If they name one and want it on, confirm the connector, then run a live create-and-read-back test: with their okay, create one task titled "Claude OS connection test", read it back through the same connector, and show the result. Record the outcome in `connections.md` (`task_capture: on`, `verified: yes (date)` only if the read-back passed). Offer to delete the test task; deletion needs their okay.

If the read-back fails, leave `task_capture: off` and tell them what broke. The audit will run capture-only until it works.

## Step 7: Scaffold the OS live

Now build the files. Substitute the business name and other details as you write each one.

1. **Root spine.** Write `CLAUDE.md` from `assets/CLAUDE.md.template`, `MEMORY.md` from `assets/MEMORY.md.template`, create `memory/` and `_outputs/`, and create `00_Shelf/` holding `brand.md`, `voice-guidelines.md`, `connections.md`, and `writing-rules.md` (from `assets/writing-rules.md.template`, the personal layer the `no-ai-slop` skill reads alongside its kill list). All except `writing-rules.md` are already drafted above.
2. **Departments.** For each locked department, create its folder with a `CLAUDE.md` (the four-question structure from the Front Desk's "Opening a new department" section: scope, an empty Shelf table, a crude workflow, and Editorial Rules pointing at `00_Shelf/voice-guidelines.md`) and a `MEMORY.md` titled `<Department> Memory` with People and Key decisions sections. Keep each lean and mostly ready to fill.
3. **Floor Plan.** Write one row per department into the root `CLAUDE.md` Floor Plan table, each describing what routes there, and keep the "Anything else, ask" catch-all.
4. **Shelf table.** Add rows to the root `CLAUDE.md` Shelf table for any optional stubs you created.

In Cowork, add the root `CLAUDE.md`'s identity summary to the project's Project Instructions if they want it loaded at the top level; walk them through pasting it. In Claude Code it loads automatically from the folder.

Show them the finished tree and confirm it looks right.

## Step 8: Run a first win, then hand off

Point the fresh OS at one real thing so they feel it work: draft a post in their new voice, fill a section of `brand.md` from a real link, or triage a few emails as drafts if email is connected. Pick something small and real.

Then explain, warmly and briefly, how the OS runs day to day:
- Claude reads the Front Desk and memory at the start of every session, so it always knows the business.
- At the end of a work session, say "audit this session" and the `session-audit` skill saves what was learned and (if a task system is wired) creates the tasks that came up.
- Any writing loads their voice guidelines and the `no-ai-slop` rules automatically.
- The OS grows by opening new departments and desks as the business does, using the instructions already inside `CLAUDE.md`.

End when the OS is built and they have felt one win. Do not keep asking questions.

## If setup is interrupted

Because you build in one guided session, a clean resume is simple: re-open this skill and it picks up from the first unfinished step. Check what already exists in the workspace (which files and departments are there) and continue from the gap rather than rebuilding.
