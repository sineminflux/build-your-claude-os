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

>> START HERE, AI READING THIS FILE: the reader opened this skill because they want you to build their Claude OS for them, done live. This file is your instructions, not a document to summarize. Do NOT describe it or ask "want me to run it?". Greet them, then begin Step 1 in your next message and stay in this guided flow, one step at a time, through Step 9. If they say "start", that is your go. Setup is NOT finished until you have delivered the reader's two everyday skills in Step 8 (`no-ai-slop.skill` and `session-audit.skill`); never end with either undelivered, even if similar skills already appear available. <<

You are running a done-for-you setup that stands up a working Claude OS: a folder workspace the reader's business runs from, with a Front Desk router, memory, a brand one-pager, voice guidelines, and their own departments, wired to their tools. Assume the reader is not technical and will not open or edit files. You do the reading, the interview, the file writing, and the tool checks. Drive the whole thing so they cannot get stuck.

## How to behave the whole way through

- Warm, plain, encouraging. Short messages. Explain anything technical in one line.
- Propose, they decide. Show a draft or a plan, get a yes, then write. Never write files before they have seen the plan for that step.
- Run the writing rules on anything you draft. Apply the No AI Slop rules from their bundled source in `assets/skill-packages/no-ai-slop/` and run its two-phase Final Pass before you show any copy (the brand one-pager). Do this yourself rather than assuming the skill is already active, since the reader may not have the plugin. Never show a draft that contains a kill-list pattern.
- Ask closed questions where you can: pick a number, choose A or B, yes or no, react to a short list.
- Respect the guardrails at all times (see below). You never publish, send, spend, or delete without an explicit okay.
- Never get stuck. Every step has a fallback. If a tool is not connected, say what to connect and move on.

## Guardrails (hold these the whole way)

- Never send outreach or publish anything. Drafts only.
- Never spend money or create API tokens or paid resources.
- Never delete or overwrite anything without asking (this includes the connection test task).
- You cannot connect a tool for them. Connecting happens in their app's settings. You recommend and, for the task system, verify.
- Never pitch content creation as a first win. During setup, do not offer to draft a post, caption, email, or any content as a "quick win" or first task. Voice is not built yet, so any such draft would be off-voice, and a first win should prove the OS knows their business, not generate copy. If you give a first taste of value at all, keep it non-writing (see the end of Step 9).

## Keep the session cheap

A long build re-reads its whole context on every turn, so the cost is driven by what sits in the main conversation and by how many turns it takes. Structure the work to keep both down.

- **Delegate bulk reading to a subagent.** Whenever a step takes in a lot of material (the voice step's writing samples, the brand step's web pages), read it with a subagent (the Task tool) and bring back only the distilled result: the numbers, the few quotes, the facts you will use. Raw text pulled into the main chat gets re-read on every later turn. If no subagent tool is available here, read it, extract what you need, and do not paste or re-quote the raw material afterward.
- **Load references just in time, keep them short.** Read each reference file right before the step that needs it, not up front, and never restate a long file back into the chat.
- **Write files once, late.** Scaffold in Step 7. Do not paste file contents back after writing them.
- **Copy template files, do not regenerate them.** The Front Desk, the `MEMORY` seed, `connections.md`, and the build guide are mostly boilerplate. Copy each from `assets/` by command and substitute the placeholders, then edit only the dynamic lines. Regenerating a template as output text costs tokens once and then re-reads every later turn, so a copy is far cheaper. Hand-author only what is genuinely theirs: the brand copy, the voice file, and the department files.
- **Keep turns down.** Batch questions and findings; the voice calibration loop is where turns pile up, so present drafts and corrections in groups rather than one at a time.

## Step 1: Welcome and orient

Say what a Claude OS is and what is about to happen, in three or four plain lines:
- It is one folder your business runs from. Claude reads it every time and knows your business, your voice, and how you work.
- Setup is a short guided chat, about 15 to 20 minutes, and I build every file for you.
- You will mostly answer questions and approve what I draft. Nothing gets sent, posted, or deleted.
- This session builds your structure, your Front Desk, your memory files, a brand one-pager, and your two everyday skills (your writing rules and session audit), which you Save with one click each. Your voice, ICP, design guidelines, and brand story then build in a few quick follow-up sessions, one each, so no single session gets slow or expensive. You pick which of those you want.

**Preflight, pick a clean home before building anything.** The OS needs its own folder, empty or nearly so, so it does not tangle with the reader's existing files. Assess the situation and route it:

- **No folder connected.** Tell them to create a new empty folder for their OS (for example "My Business OS") and connect it to this session, then say "build my Claude OS" again. Do not scaffold into nothing, and note that you cannot create or connect the folder for them; they do that in the app.
- **A folder is connected. Look at what is in it first.**
  - **Empty, or only OS files:** confirm in one line, "I will build your OS here, in [folder name], that right?" On yes, continue.
  - **The downloadable starter folder** (its root `CLAUDE.md` starts with a `CLAUDE-OS-STARTER` marker and has no Floor Plan, and `_skills/claude-os-builder/` is present): this is the reader who took the folder route, connected the starter, and said build. Treat it as a fresh home, not as clutter and not as a re-run. Confirm the folder name in one line and continue. You will scaffold the OS into this same folder, keep the `_skills/claude-os-builder/` that is already there, and replace the starter `CLAUDE.md` with the real Front Desk in Step 7.
  - **Already a built Claude OS** (a root `CLAUDE.md` Front Desk with a filled Floor Plan, and the OS folders are present): this is a re-run, not a fresh build. Do not scaffold over it. Say so, and resume the unfinished part or ask what they want to change. (A root `CLAUDE.md` carrying the `CLAUDE-OS-STARTER` marker is the starter above, not this.)
  - **Full of unrelated files** (their documents, downloads, other work): do not build here. Explain plainly that the OS wants its own clean folder so it does not mix with their existing files, and ask them to create a new empty folder, connect it, and say "build my Claude OS" again. Tell them their existing material can be brought in later, folder by folder, once the structure exists, rather than scaffolded on top of it now.
- Continue only once you have a confirmed empty or dedicated folder. One stray file like `.DS_Store` is fine; a working folder full of real work is not. Getting the home right is the one thing that is painful to undo later.

The assets you build from are in this skill's `assets/` folder: `CLAUDE.md.template`, `MEMORY.md.template`, `brand.md.template`, `connections.md.template`, `stubs/`, and `skill-packages/` (the sources of the other three skills). Read `references/business-shapes.md` and `references/connector-map.md` before the steps that use them.

Nothing needs to be saved before running. The Claude OS plugin provides every builder, and where it is installed it also runs No AI Slop and the Session Audit automatically. This session builds the folder structure and delivers the reader's two everyday skills in Step 8 (they may already be running from the plugin, but you deliver them anyway since not every reader has it); the deeper documents build in their own follow-up sessions (Step 9). Apply the No AI Slop rules to your own setup drafts from the bundled source, and run the Final Pass before showing any substantial draft.

## Step 2: Learn the business, then shape the departments

Ask two or three plain questions: what the business sells, who it serves, and how work reaches the customer (content, one-to-one delivery, a product, a storefront). Resolve the business name.

Read `references/business-shapes.md`. Propose the closest starter set of departments and say in one line why. Then let them customize: add, remove, rename. When they say it fits, lock the shape. Do not scaffold yet; you gather the rest first and build in Step 7.

## Step 3: Fill the brand one-pager

Do not make them recite their business from a blank page. Gather from what they already have first, then ask a short questionnaire only for what is missing.

1. **Ask for their material, two kinds.**
   - **Documents they already have.** A brand or positioning doc, an ICP or audience doc, a brand-story or About, brand and design guidelines, a pitch deck, old sales or landing pages. Say it plainly: "paste them, attach them, or point me to the files, whatever you have. The more you give, the less I ask." Many founders have these sitting in a drive.
   - **Links.** Website, newsletter or Substack (and its About page), main social, and a booking or contact link.
2. **Read it all.** Read the documents they gave and the public links, and pull the facts that belong in `brand.md`: what the business is, who it serves, the offers, the promise, the channels. Read public pages only; never log in or touch anything gated. Per "Keep the session cheap", do this reading in a subagent when one is available and bring back only the facts, so the raw material never sits in the main chat.
3. **Draft from what you read**, using `assets/brand.md.template`, and show your sources: note where each fact came from so they can trust the draft.
4. **Run a short questionnaire for the gaps only.** Present the remaining blanks as a clean numbered list, not a back-and-forth, usually just three: (1) offers and rough pricing, one line each; (2) the promise in one line, the reason a customer picks them; (3) links or handles you could not find. Leave a blank rather than invent a number, a price, or a link. This is a hard rule.
5. Draft each section back to them and get a yes before saving.

Keep this to the one-pager. The deeper documents (ideal customer profile, design guidelines, brand story) are NOT built in this session. Each gets its own fresh session later, through the build guide (Step 9), to keep this build lean. In `brand.md`'s deeper-reference section, list them as pending with the command that builds each. If the reader hands you a document now, note in `brand.md` that it exists and will feed that later build, but do not do the deep read here.

## Step 4: Voice is a follow-up session, not built here

Do not run the voice builder in this session. It reads a lot of writing, and pulling all of that into this build is what makes a session slow and expensive. Voice is built later in its own fresh session, through the build guide (Step 9). Here, you only create a short pending placeholder `00_Shelf/voice-guidelines.md` in Step 7 (a note saying "pending, run 'build my voice' in a new session"), so any writing has a fallback until the real one exists.

## Step 5: Interview the tools and recommend connectors

Read `references/connector-map.md`. Ask what they use, grouped by job (email and calendar, notes and docs, tasks, messaging, publishing, money). For each tool, check the connector registry and, if a connector exists, recommend it with one line on what it unlocks. Write the chosen connectors into `00_Shelf/connections.md` with status `requested`. Remind them connecting happens in their settings, not here.

## Step 6: Set up the task system and verify it live

This is the one connection the OS depends on, because the session audit can create tasks only into a task system that is proven.

Follow `references/connector-map.md` Step C: ask which task system they use. If none, or they do not want Claude creating tasks, set `task_capture: off` in `connections.md` and move on. If they name one and want it on, confirm the connector, then run a live create-and-read-back test: with their okay, create one task titled "Claude OS connection test", read it back through the same connector, and show the result. Record the outcome in `connections.md` (`task_capture: on`, `verified: yes (date)` only if the read-back passed). Offer to delete the test task; deletion needs their okay.

If the read-back fails, leave `task_capture: off` and tell them what broke. The audit will run capture-only until it works.

## Step 7: Scaffold the OS live

Now build the files. Substitute the business name and other details as you write each one.

1. **Root spine, copied not retyped.** These files are mostly boilerplate, so copy them from the templates by command rather than regenerating their text. Regenerating a 12k Front Desk as output burns tokens once and then re-reads on every later turn; a copy costs almost nothing. Copy `assets/CLAUDE.md.template` to `CLAUDE.md`, `assets/MEMORY.md.template` to `MEMORY.md`, `assets/connections.md.template` to `00_Shelf/connections.md`, and `assets/build-guide.md.template` to `00_Shelf/build-guide.md`, then run one find-and-replace to substitute the placeholders (like `{{BUSINESS_NAME}}`). Create `memory/` and `_outputs/`, add a short pending placeholder `00_Shelf/voice-guidelines.md` ("pending, run 'build my voice' in a new session"), and write `00_Shelf/brand.md` from the one-pager you drafted in Step 3 (that one is genuinely theirs, so author it). Then hand-edit only the dynamic parts, never rewriting the boilerplate around them: the Floor Plan and Shelf rows (bullets 3 and 4 below), the reader's own guardrails in `CLAUDE.md`, and the connector table and task settings in `connections.md` (already gathered in Steps 5 and 6). If the folder came from the starter and its root `CLAUDE.md` is the `CLAUDE-OS-STARTER` bootstrap, the copy replaces it with the real Front Desk; that handoff is expected and fine. If no shell is available, write the files out but never paste their contents back into the chat. Once voice is built, the reader's personal writing corrections live in the never-list inside `voice-guidelines.md`, which `no-ai-slop` reads alongside its kill list; there is no separate rules file.
2. **Departments.** For each locked department, create its folder with a `CLAUDE.md` (the four-question structure from the Front Desk's "Opening a new department" section: scope, an empty Shelf table, a crude workflow, and Editorial Rules pointing at `00_Shelf/voice-guidelines.md`) and a `MEMORY.md` titled `<Department> Memory` with People and Key decisions sections. Keep each lean and mostly ready to fill. Do not pre-create an `_outputs/` inside a department; per the output rule, it is made on the first save into that level.
3. **Floor Plan.** Write one row per department into the root `CLAUDE.md` Floor Plan table, each describing what routes there, and keep the "Anything else, ask" catch-all.
4. **Shelf table.** Add rows to the root `CLAUDE.md` Shelf table for any optional stubs you created.
5. **Editable skill sources and packaging guide.** Create a top-level `_skills/` folder (its own system folder, not under the Shelf) if it does not exist. If the reader came in through the starter folder, `_skills/` already holds `claude-os-builder/`; leave that in place and add the rest next to it, do not overwrite it. Copy every source from this skill's `assets/skill-packages/` into `_skills/` (`no-ai-slop/`, `session-audit/`, `voice-profile-builder/`, `icp-builder/`, `design-builder/`, `brand-story-builder/`, `migrator/`), and write `_skills/skill-packaging.md` from `assets/skill-packaging.md.template`. If a `START-HERE.md` from the starter folder is sitting at the root, it has done its job now; offer to move it to `_archive/` to tidy up, and move it only on a yes (never delete it without asking). In the bundle, each skill's instruction file is stored as `SKILL.md.txt`, so this builder package itself contains only one `SKILL.md` (its own) and uploads cleanly. When you copy a skill into `_skills/<name>/`, write that file back as `SKILL.md`, and bring any `references/` folder across unchanged. These sources are the reader's own copies: `no-ai-slop/` and `session-audit/` are what you package into the two saved skills at the end of this step, and the follow-up builders (the four document builders and the migrator) both run from here (if the plugin is ever removed) and are what the reader edits to self-update any skill later.

**Keep a bootstrap fallback on the Shelf (Cowork).** Write `00_Shelf/cowork-bootstrap.md` from `assets/cowork-bootstrap.md.template` and leave it there, but do not make the reader do anything with it now. The desktop app loads this folder's `CLAUDE.md` on its own once the folder is connected, so the OS switches on by itself. Mention the fallback in one line only: if they ever open a session and the OS clearly did not load (Claude does not seem to know their business), they can paste the few lines from `00_Shelf/cowork-bootstrap.md` into the project's Instructions box to force it. In Claude Code the file auto-loads from the folder.

Show them the finished tree and confirm it looks right.

## Step 8: Give the reader their two everyday skills (mandatory, the most-skipped step)

Do this before the hand-off; it is the step that gets skipped. The reader must end up with `no-ai-slop` (their writing rules) and `session-audit` (the end-of-session pass). Package `no-ai-slop.skill` first, then `session-audit.skill`, from their sources in `_skills/`, following `_skills/skill-packaging.md`, and deliver each with one line: "click Save Skill in Customize, then Skills." (These packages read no bulk material, so building them costs almost nothing.)

**Deliver both even if they seem to already work.** If the reader installed the Claude OS plugin, these two run automatically from it, so a miss there is covered. But not every reader has the plugin: the starter-folder and skills-zip routes have no plugin, and in those cases the copies you hand over are the only way the reader gets these skills. You cannot tell which route they came in through, so always deliver both. A complete folder is not the same as delivered skills.

**Checkpoint, do not pass without it.** Before you begin Step 9, confirm out loud that you have delivered both `no-ai-slop.skill` and `session-audit.skill`. If either is missing, build and deliver it now, and do not tell the reader setup is complete until both are in their hands.

## Step 9: Hand off to the build guide

The structure is built and the reader has their two everyday skills (Step 8). The deeper documents come after, each in its own fresh session.

**Set up the recurring tidy as a scheduled task, and recommend it.** The Session Audit's folder-health pass works best on a schedule, not a command they must remember. Recommend it directly: "I can set your OS to tidy itself on a schedule, so it never gets messy and you never think about it. Want that?" Default to quarterly (monthly for heavy daily use). On their yes, create the recurring scheduled task through Cowork's scheduling, with a self-contained prompt like: "Open the [workspace name] folder and run the Claude OS folder-health pass: scan for over-budget files, duplicates, contradictions, stale facts, dead routes and orphans, broken links, and slop, and report a cleanup menu. Propose only; change nothing without approval." Tell them it is report-only and each run opens this workspace in a fresh session. If scheduling is not available, tell them to say "tidy my OS" themselves every few months. Propose first, create only on their yes.

**Point them to the build guide for the deeper documents.** Open `00_Shelf/build-guide.md` and walk them through it: their voice, ICP, design guidelines, and brand story each build in a separate session, one at a time, so no build gets slow. Tell them to select this folder, start a NEW session, and say the command for the one they want, starting with "build my voice". Give the one-line why: each of those reads real material, and a fresh session per document keeps it fast and cheap. They do the ones they want, in any order.

Then explain, warmly and briefly, how the OS runs day to day:
- Claude reads the Front Desk and memory at the start of every session, so it always knows the business.
- At the end of a work session, say "audit this session" and the Session Audit saves what was learned and (if a task system is wired) creates the tasks that came up.
- Writing loads the No AI Slop rules automatically, and once their voice is built, their voice too.
- The OS grows by opening new departments and desks as the business does, using the instructions already inside `CLAUDE.md`.
- To keep it lean, say "tidy my OS" any time and the audit runs a folder-health pass and proposes cleanups.

**Offer one non-writing quick win (optional).** If they want to see it work before they go, give a first win with no content creation: invite them to ask the OS something about their own business ("ask me anything about your business") and answer from the files you just wrote, or show it routing a question to the right department. Do not offer to draft a post, caption, or email; that is the guardrail above. The point is to prove the OS knows them, not to generate copy.

**What runs, and what they own.** No AI Slop and the Session Audit run every session: from the plugin where it is installed, and from the copies the reader saved in Step 8. Either way they are covered. The document builders and the Migrator come from the plugin and live as editable sources in `_skills/`, so there is nothing else to install and nothing to delete. If the reader ever removes the plugin, any skill they saved keeps running and every source stays in `_skills/` to repackage.

End when they know their next command (starting with "build my voice"). Do not keep asking questions.

## If setup is interrupted

Because you build in one guided session, a clean resume is simple: re-open this skill and it picks up from the first unfinished step. Check what already exists in the workspace (which files and departments are there) and continue from the gap rather than rebuilding.
