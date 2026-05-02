---
title: "Troubleshooting"
permalink: /troubleshooting/
---

# Troubleshooting

The seven problems that hit 80% of first-time users, with fixes.

---

## 1. `claude: command not found` after I installed it

**Cause**: Your terminal can't find where `npm` put the `claude` binary.

**Fix**:

Close your terminal completely and open a fresh one. If it still fails:

**Mac/Linux**:
```bash
# Find where npm puts global packages
npm config get prefix
# It will print something like /usr/local or /Users/you/.npm-global

# Add /bin to that path and put it in your shell config:
echo 'export PATH="$(npm config get prefix)/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

**Windows**: Restart your terminal as Administrator. If still failing, reinstall Node.js with the option "Add to PATH" checked.

---

## 2. `npm install -g` fails with EACCES / permission denied

**Cause**: npm wants to write to a system folder and your user account doesn't have permission.

**Best fix (Mac/Linux)**: Set up a user-owned npm prefix so you never need sudo:

```bash
mkdir -p ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.zshrc   # use ~/.bashrc on Linux
source ~/.zshrc
npm install -g @anthropic-ai/claude-code
```

**Quick fix**: `sudo npm install -g @anthropic-ai/claude-code` (works but isn't great long-term)

**Windows**: Run terminal as Administrator.

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
