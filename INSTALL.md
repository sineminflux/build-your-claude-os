# Install Build Your Own Claude OS

You install this once. After that, "build my Claude OS" runs the setup.

> Before you share this: replace `YOUR-GITHUB-USERNAME` below with your real GitHub username (or wherever you host this repo). The install works by pointing Claude at that repository link.

## In Cowork (Claude desktop app)

Most readers use this path.

1. Open the Claude desktop app and go to **Cowork**.
2. In the left sidebar, open **Customize**, then **Plugins**.
3. Choose **Personal**, then **Add marketplace from GitHub**.
4. Paste the repository link:
   ```
   https://github.com/YOUR-GITHUB-USERNAME/build-your-claude-os
   ```
5. The **Claude OS** plugin appears in the list. Click **Install**.
6. Open a folder for your business as your workspace (an empty folder is fine), and say **"build my Claude OS"**.

That is it. The builder takes it from there.

## In Claude Code (the command-line tool)

For people who use the CLI.

1. Add the marketplace:
   ```
   /plugin marketplace add YOUR-GITHUB-USERNAME/build-your-claude-os
   ```
2. Install the plugin:
   ```
   /plugin install claude-os@leverage-her-way
   ```
3. From your business folder, launch Claude Code and say **"build my Claude OS"**.

## If the install does not appear

Plugin tooling changes over time, and direct file uploads of plugins have been unreliable, which is why this uses a GitHub link instead. If the steps above do not match what you see, check the current plugin install help in the Claude app, then come back and add the marketplace by the same repository link.

## What gets installed, and how you end up owning it

Five builders: the Claude OS Builder, the Voice Profile Builder, and the ICP, Design Guidelines, and Brand Story builders. Installing the plugin makes all five available. You do not save any of them yourself.

You run them by command:

1. "build my Claude OS" builds your folder structure and, in the same session, your two everyday skills, No AI Slop and the Session Audit. Each is handed to you as a `.skill` file and you click Save once. Those are the only two skills you save, and you never hunt for or upload them.
2. Then, in fresh sessions, "build my voice", "build my ICP", "build my design guidelines", and "build my brand story" build the deeper reference files, in any order.

Every builder drops its editable source into a top-level `_skills/` folder in your workspace, so the skills are yours. Change any by asking Claude to edit its source and rebuild it, then click Save again for the two saved ones. You can remove the plugin afterward and keep everything: the two saved skills keep running and every source stays in `_skills/`. Keep the plugin installed (or re-add it by its GitHub link) if you want to re-run a document builder later.
