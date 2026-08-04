# Voice Profile Builder

A guided wizard that turns your writing voice into a reusable skill. Run it, answer a short interview, and it builds your personal voice skill for you.

Most AI writing sounds the same: flat, over-polite, could-be-anyone. This fixes that by extracting how you actually write and packaging it so any AI drafts as you.

## What it does

You run it and it walks you through the whole thing:

1. Gathers your real writing (from your connected email and docs, or samples you paste).
2. Measures your mechanics with real numbers (sentence rhythm, punctuation habits, and more).
3. Extracts your patterns: your signature moves, the traps that break your voice, how you flex by platform.
4. Builds two files: `voice-principles.md` (how your voice works) and `voice-examples.md` (an annotated bank of your real passages).
5. Calibrates by drafting in your voice and letting you correct it, turning each correction into a rule.
6. Packages it all into your own `[name]-voice` skill and walks you through saving it.
7. Steps aside. Once your voice skill is saved, you can remove this builder.

## Who it's for

Anyone who writes and wants AI to sound like them: newsletter writers, founders, creators, ghostwriters, anyone tired of drafts that read like a stranger doing an impression of them. No technical setup required. The wizard does the work.

## How to run it

**In Claude Cowork:** save this as a skill (Save skill), then open it and say "start."

**In Claude Code:** unzip into `~/.claude/skills/voice-profile-builder/` and call it, or run it as a slash command.

**In a plain chat (no skill support):** open `starter-prompt.md`, paste the prompt, and follow along. It runs the same interview and hands you the files to save yourself.

## What you end up with

Your own `[name]-voice` skill: a small wrapper plus your two voice files. Load it whenever an AI writes for you and it drafts in your voice. The `voice-principles.md` inside is portable too: paste it into any AI's custom instructions or a Project for the same effect.

## What's inside this builder

- `SKILL.md`: the guided wizard.
- `references/extraction-method.md`: what to measure and extract, in layers.
- `references/voice-principles-schema.md`: the structure of the principles file.
- `references/examples-bank-schema.md`: the structure of the annotated examples bank.
- `references/output-skill-schema.md`: how your personal voice skill is packaged.
- `references/calibration-and-interview.md`: the interview questions and the calibration loop that make it accurate.
- `starter-prompt.md`: a copy-paste version for plain chats.

## Pair it with anti-slop rules

A voice profile says what your voice is. An anti-slop rule set says what to avoid (em dashes, "it's not X, it's Y" pivots, throat-clearing openers, forced metaphors). Load both. Used together, they keep your drafts honest.

## Credit and use

Built by Sinem Furtana as part of Leverage, Her Way, a newsletter on practical AI for women founders. Free to use, adapt, and share. If you pass it on or build on it, keep a line of credit to Leverage, Her Way. That's the only ask.

Version 2.0.0
