# Output Skill Schema

What the wizard produces: the user's own reusable voice skill. This is the thing they keep and load forever. It wraps the two voice files in a tiny skill so any AI that loads it writes as them.

---

## Folder structure

```
[name]-voice/
├── SKILL.md            (short wrapper: write as [Name], load the two files)
├── voice-principles.md (built via voice-principles-schema.md)
└── voice-examples.md   (built via examples-bank-schema.md)
```

Use the person's name in kebab-case: `jordan-voice`, `sarah-chen-voice`. Confirm the name with them before building.

---

## The wrapper SKILL.md

Keep it short. Its only job is to point any AI at the two files and set the rule. Use this shape, filling the brackets:

```markdown
---
name: [name]-voice
description: >
  Write in [Name]'s real voice. Use whenever drafting anything as [Name]:
  posts, captions, emails, newsletters, replies, DMs. Load the voice files
  and follow them over generic AI defaults. Triggers: "write as [Name]",
  "in my voice", "draft this for me", or any writing task for [Name].
metadata:
  version: "1.0.0"
  updated: "[date]"
---

# [Name]'s Voice

Write as [Name]. Match this voice over your own defaults.

Two files carry the voice:
- `voice-principles.md` is how the voice works: measured mechanics, punctuation,
  signature moves, the never-list, and how the voice flexes by platform. Load it
  for every draft.
- `voice-examples.md` is an annotated bank of [Name]'s real passages. Load it too
  before drafting anything long-form, and imitate the examples, not the abstractions.

If [Name] corrects one of your drafts, treat that edit as a correction to
voice-principles.md: fix the rule and follow it from then on.

Pair with an anti-slop rule set if one is available. This voice file is the
personal layer. Anti-slop is the general one.
```

---

## Packaging

Follow the same rules as any skill package:

1. The `.skill` is a zip whose root contains `SKILL.md` plus the two `.md` files (not nested inside a subfolder).
2. Stage in a temp folder, zip, and verify with `unzip -l` that `SKILL.md` is at the archive root.
3. Name the file `[name]-voice.skill` so the `name:` in the frontmatter matches and it installs cleanly.

Then hand the `.skill` to the user and tell them how to install it: Cowork uses Save skill, Claude Code unzips it into the skills folder.

If you cannot write or zip files (a plain chat), skip packaging. Paste the three files as copy-blocks instead and tell the user exactly where to save each one, or that they can paste `voice-principles.md` straight into any AI's custom instructions or a Project.

---

## Portability note for the user

The voice files are not locked to one tool. `voice-principles.md` can be pasted into any AI's system prompt, custom instructions, or a Project, and it gives the same voice calibration. The skill wrapper just makes it one click in Cowork and Claude Code.
