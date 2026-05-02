---
title: "Pre-Workshop Setup"
permalink: /prework/
---

# Pre-Workshop Setup

**Do this 24 hours before the workshop.** Total time: about 15 minutes.

If everyone shows up with this done, we spend the workshop *building*, not *installing*.

---

## Will my computer work?

| Computer | Will it work? |
|---|---|
| **Mac** (Intel or Apple Silicon, macOS 11+) | ✅ Yes — full instructions below |
| **Windows 10 or 11** | ✅ Yes — full instructions below |
| **Linux** (Ubuntu, Fedora, etc.) | ✅ Yes — see [INSTALL.md](INSTALL.md) for distro-specific notes |
| **Chromebook** | ⚠️ **Likely no for this workshop.** Standard Chromebooks don't run Node.js or Claude Code. (Newer ones with Linux/Crostini enabled *can* technically work, but setting that up for the first time is more than the workshop's 15-min budget.) **Bring a Mac or Windows laptop instead, or pair up with someone who has one.** |
| **iPad / tablet / phone** | ❌ No — Claude Code is a desktop tool. Tablets and phones can't run it. |

If you only have a Chromebook, please reach out to the workshop organizer or pair up with someone — we don't want you sitting on the sidelines.

---

## What you need to install

| Tool | Why | Time |
|---|---|---|
| **VSCode** | Your editor — where you write and see files | 3 min |
| **Claude Code** | The AI tool we're learning — one-line installer, no other dependencies | 2 min |
| **An Anthropic account** | So Claude knows it's you | 5 min |

That's it — three things. (You don't need Node.js, npm, or git to use the kit. The Claude Code native installer bundles everything it needs.)

---

## Step 1: Install VSCode (3 min)

VSCode is a free code editor from Microsoft. Don't worry — you don't need to "code" with it. We use it because it's the friendliest way to see files and run Claude side-by-side.

➡️ **[Download VSCode](https://code.visualstudio.com/download)**

The page has three big buttons — one for each operating system. **Click the one that matches your computer:**

![VSCode download page — three big platform buttons: Windows, Linux (penguin), Mac (Apple)]({{ "/assets/screenshots/06-vscode-download.png" | relative_url }})

Install it like any normal app. Open it once when done.

---

## Step 2: Install Claude Code (2 min — native installer)

Claude Code has a one-line native installer. It does not need Node.js, npm, or any other dependency. Just open your **Terminal** and paste the line for your operating system:

**On Mac or Linux**, open Terminal (Mac: `Cmd+Space` → "Terminal") and paste:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**On Windows**, open PowerShell (Start menu → "Windows PowerShell") and paste:

```powershell
irm https://claude.ai/install.ps1 | iex
```

The installer takes about 30 seconds. When it's done, **close the terminal completely and open a fresh one** (the new terminal needs to pick up the updated PATH). Then verify:

```bash
claude --version
```

You should see a version number like `2.1.x` or higher.

> 📚 **Official source**: [Claude Code Quickstart — Native install (recommended)](https://code.claude.com/docs/en/quickstart#native-install-recommended)

> 💡 **Already had Claude Code installed via npm?** No problem — the native installer will take over. You can also continue to use the npm version if you prefer; both work the same.

---

## Step 3: Create an Anthropic account (5 min)

Claude Code needs to know it's you so it can talk to Claude.

➡️ **[Sign up at console.anthropic.com](https://console.anthropic.com/)**

Use any email. You will get **$5 of free credits** to start, which is plenty for the workshop. (One full hands-on session uses well under $1.)

After signing up, you do **NOT** need to manually grab an API key — Claude Code will walk you through sign-in.

---

## Step 4: Sign Claude Code into your Anthropic account

In your terminal, navigate to any folder (or just stay in your home directory) and run:

```bash
claude
```

It will:
1. Ask permission to use the current folder — say yes.
2. Pop open your browser to sign you into Anthropic.
3. After you sign in, it will return to the terminal ready to chat.

Try typing:

```
hello! say hi back and tell me what you can do
```

Claude will introduce itself. **You are now ready for the workshop.** Type `/exit` to close it.

---

## Step 5: Install the VSCode extension (recommended, 1 min)

In VSCode:
1. Click the **Extensions** icon on the left sidebar (the four squares).
2. Search for **"Claude Code"**.
3. Click **Install** on the official Anthropic extension.

This gives you a sidebar UI where you can run Claude visually without typing in a terminal. Either way works — the extension is just friendlier for first-timers.

---

---

## You're done!

Show up to the workshop with:
- ✅ VSCode installed
- ✅ Claude Code working (`claude --version` returns a number)
- ✅ Signed into Anthropic (you ran `claude` and chatted with it once)

If **anything** broke, see [Troubleshooting]({{ "/troubleshooting/" | relative_url }}) or just show up 15 minutes early to the workshop.

---

## What we'll do at the workshop (preview)

- 🎬 **Watch a 3-minute "wow" demo** — Claude reads a screenshot and finds patterns
- 🛠️ **Build a Learning Companion** — pick a YouTube video about anything, Claude turns it into your personal tutor with phases and TODOs
- 🤖 **Convert it to a reusable agent** — one file, infinite re-use
- 💡 **Get sent home with two more recipes** — data-to-dashboard and interview prep

See you there!

---

← [Back to Claude Code Jumpstart home]({{ "/" | relative_url }}) · [Detailed install guide]({{ "/install/" | relative_url }}) · [Troubleshooting]({{ "/troubleshooting/" | relative_url }})
