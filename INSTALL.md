# Install Build Your Own Claude OS

You install this once. After that, "build my Claude OS" runs the setup.

## In Cowork (Claude desktop app)

Most readers use this path.

1. Open the Claude desktop app and go to **Cowork**.
2. In the left sidebar, open **Customize**, then **Plugins**.
3. Choose **Personal**, then **Add marketplace from GitHub**.
4. Paste the repository link:
   ```
   https://github.com/sineminflux/build-your-claude-os
   ```
5. The **Claude OS** plugin appears in the list. Click **Install**.
6. Open a folder for your business as your workspace (an empty folder is fine), and say **"build my Claude OS"**.

That is it. The builder takes it from there.

## In Claude Code (the command-line tool)

For people who use the CLI.

1. Add the marketplace:
   ```
   /plugin marketplace add sineminflux/build-your-claude-os
   ```
2. Install the plugin:
   ```
   /plugin install claude-os@leverage-her-way
   ```
3. From your business folder, launch Claude Code and say **"build my Claude OS"**.

## If the install does not appear

Plugin tooling changes over time, and direct file uploads of plugins have been unreliable, which is why this uses a GitHub link instead. If the steps above do not match what you see, check the current plugin install help in the Claude app, then come back and add the marketplace by the same repository link.

## What gets installed

Four skills: the Claude OS Builder, the Voice Profile Builder, No AI Slop, and the Session Audit. Nothing runs on its own. You trigger each by talking to Claude.
