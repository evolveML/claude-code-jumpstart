---
title: "Detailed Install Guide"
permalink: /install/
---

# Detailed Install Guide

If the [Prework]({{ "/prework/" | relative_url }}) didn't work for you, or you want OS-specific detail, this is the full reference.

**Supported**: macOS, Windows 10/11, Linux.
**Not supported for the workshop**: Chromebooks, iPads, phones. If that's all you have, pair up with someone who has a Mac or Windows laptop.

> 📚 **Authoritative source**: [code.claude.com/docs/en/quickstart](https://code.claude.com/docs/en/quickstart#native-install-recommended) is Anthropic's official install guide. If anything below has gone stale, that page is the source of truth.

---

## macOS

### 1. VSCode

- Download from [code.visualstudio.com/download](https://code.visualstudio.com/download)
- Open the `.zip`, drag the VSCode app into your Applications folder, launch it.

When prompted, run **"Shell Command: Install 'code' command in PATH"** from the Command Palette (`Cmd+Shift+P`) so you can open folders in VSCode by typing `code .`.

### 2. Claude Code (native installer — recommended)

Open Terminal and paste:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

That's it — no Node.js, no npm, no Homebrew. The installer puts a `claude` binary on your PATH and bundles its own runtime.

**Close the terminal completely** and open a fresh one (so the new `claude` command is found). Verify:

```bash
claude --version
```

You should see a version number.

### 3. Sign in

```bash
claude
```

It opens your browser. Sign in to your Anthropic account. Done.

> 💡 **Want npm install instead?** It still works (`npm install -g @anthropic-ai/claude-code`) but requires you to install Node.js first. The native installer is simpler — start there unless you have a specific reason not to.

---

## Windows

### 1. VSCode

- Download the `.exe` installer from [code.visualstudio.com/download](https://code.visualstudio.com/download)
- During install, **check the box** that says "Add to PATH" — this lets you type `code .` in any terminal.

### 2. Open the right terminal

Windows is tricky — Claude Code works best in **PowerShell** or **Windows Terminal**, not the old `cmd.exe`.

- Press `Win+X` → choose **"Windows Terminal"** or **"Windows PowerShell"**.

### 3. Claude Code (native installer — recommended)

In PowerShell, paste:

```powershell
irm https://claude.ai/install.ps1 | iex
```

(If you must use `cmd.exe` instead: `curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd`)

**Close PowerShell completely** and open a fresh one. Verify:

```bash
claude --version
```

### 4. Sign in

```bash
claude
```

Browser will open for sign-in.

> 💡 **Want npm install instead?** Install Node.js LTS from [nodejs.org/en/download](https://nodejs.org/en/download) first, then run `npm install -g @anthropic-ai/claude-code` in PowerShell as Administrator. The native installer is simpler — try that first.

---

## Linux

### 1. VSCode

- Ubuntu/Debian: Download the `.deb` from [code.visualstudio.com/download](https://code.visualstudio.com/download), then `sudo dpkg -i code_*.deb`
- Fedora/RHEL: Download the `.rpm`, then `sudo rpm -i code_*.rpm`
- Arch: `yay -S visual-studio-code-bin`

### 2. Claude Code (native installer — recommended)

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Close the terminal** and open a fresh one. Verify:

```bash
claude --version
```

### 3. Sign in

```bash
claude
```

> 💡 **Want npm install instead?** Install Node.js (`curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt-get install -y nodejs` on Debian/Ubuntu, or use nvm), then `npm install -g @anthropic-ai/claude-code`. The native installer doesn't need any of that.

---

## VSCode Extension (any OS)

After Claude Code is installed at the command line, also install the VSCode extension for a visual UI:

1. Open VSCode
2. Click the **Extensions** icon (four squares on the left)
3. Search `Claude Code`
4. Install the **official Anthropic** one

Now you can open any folder in VSCode, click the Claude icon in the sidebar, and chat with Claude visually.

---

## Verify the full stack

In a fresh terminal:

```bash
claude --version  # any version (this is the only one strictly required)
code --version    # any version (Mac/Linux — Windows uses the GUI)
```

Both should return version numbers.

---

## Still stuck?

See [Troubleshooting]({{ "/troubleshooting/" | relative_url }}), or come to the workshop 15 minutes early.

---

← [Back to Claude Code Jumpstart home]({{ "/" | relative_url }}) · [Prework]({{ "/prework/" | relative_url }}) · [Troubleshooting]({{ "/troubleshooting/" | relative_url }})
