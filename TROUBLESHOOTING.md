---
title: "Troubleshooting"
permalink: /troubleshooting/
---

# Troubleshooting

**If something broke — this isn't your fault, and you're not the only one.** Computers are weird the first time you set new things up. Almost everyone hits at least one snag.

Here are the seven things that go wrong most often, with exactly how to fix each one. None of these mean Claude Code is broken or that you did something wrong. They're all small setup hiccups, and each has a clear fix.

If you're stuck, take a breath. Try the matching fix below. If it still doesn't work, ask the person running the workshop or open an issue on this repo.

---

## 1. `claude: command not found` after I installed it

**Cause #1 (most common)**: You haven't restarted your terminal since the install. The new PATH entry isn't picked up by the old terminal session.

**Fix**: Close your terminal completely and open a fresh one. Try `claude --version` again.

**Cause #2**: The native installer's PATH entry isn't being loaded by your shell.

**Fix (Mac/Linux)**:
```bash
# Native installer puts claude in ~/.local/bin
ls -la ~/.local/bin/claude

# If it's there but not on PATH, add it:
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

**Fix (Windows)**: Restart PowerShell. If still failing, log out and log back in (sometimes Windows needs that for new PATH entries).

**If you used `npm install -g` instead of the native installer**: switch to the native installer — it usually fixes PATH issues. See [the install guide]({{ "/install/" | relative_url }}).

---

## 2. `npm install -g` fails with EACCES / permission denied

**Best fix**: Switch to the native installer instead — it doesn't need npm at all.

```bash
# Mac/Linux
curl -fsSL https://claude.ai/install.sh | bash

# Windows PowerShell
irm https://claude.ai/install.ps1 | iex
```

The native installer avoids all of npm's permission issues. See [the install guide]({{ "/install/" | relative_url }}).

**If you must use npm** (for some reason): set up a user-owned npm prefix so you never need sudo:

```bash
mkdir -p ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.zshrc
source ~/.zshrc
npm install -g @anthropic-ai/claude-code
```

---

## 3. Claude opens, but says "authentication failed" or won't sign me in

**Cause**: Browser flow got interrupted, or you signed in to the wrong Anthropic account.

**Fix**:

```bash
# Sign out and sign in again
claude /logout
claude
```

The browser should re-open. If it doesn't, copy the URL it prints and paste it manually.

If you don't have an Anthropic account yet, create one at [console.anthropic.com](https://console.anthropic.com/) first.

---

## 4. `claude` runs but it can't read my files

**Cause**: Claude Code asks permission for the folder it's in. If you said "no" or "no, never," it's stuck.

**Fix**:

```bash
# In the folder you want to use, run:
claude --dangerously-skip-permissions  # NOT recommended long-term
```

Or, edit `~/.claude/settings.json` and remove the folder from the deny list. Or just `claude /reset-permissions` and start over.

---

## 5. The transcript download from notegpt.io / YouTube doesn't work

**Cause**: The video has captions disabled, or the page is rate-limiting.

**Fixes (in order)**:

1. Pick a video that **definitely has captions** — most major YouTube channels do (search for "CC" badge in the video player).
2. Try [notegpt.io/youtube-transcript-generator](https://notegpt.io/youtube-transcript-generator) — paste the YouTube URL, copy the transcript.
3. If notegpt is slow, try [downsub.com](https://downsub.com/) or [youtubetranscript.com](https://youtubetranscript.com/) as alternatives.
4. **Last resort**: use the sample transcript provided in `scenarios/01-learning-companion/sample-transcript.txt` — it's a fully formed transcript you can practice with.

---

## 6. Claude is "thinking" forever / seems frozen

**Cause**: Big task, slow internet, or rate limit.

**Fix**:
- Wait 60 seconds. Most "frozen" Claude is actually just thinking.
- Press `Esc` once to interrupt the current operation.
- Press `Ctrl+C` to fully cancel.
- If you genuinely hit a rate limit, wait 1 minute and try again.

---

## 7. I can't `git clone` the repo

**Cause**: Git not installed, or HTTPS blocked by firewall.

**Fix**:
```bash
# Check git is installed:
git --version

# If not on Mac:
xcode-select --install

# If not on Windows: download from git-scm.com
# If not on Linux: sudo apt install git (or your distro equivalent)

# If you can't clone over HTTPS, just download the ZIP from
# https://github.com/evolveML/claude-code-jumpstart/archive/refs/heads/main.zip
# and unzip it.
```

---

## Still stuck?

Open an issue on this repo, or ask the person running the workshop. We'll add your problem to this doc so the next person doesn't hit it.

---

← [Back to Claude Code Jumpstart home]({{ "/" | relative_url }}) · [Prework]({{ "/prework/" | relative_url }}) · [Detailed install guide]({{ "/install/" | relative_url }})
