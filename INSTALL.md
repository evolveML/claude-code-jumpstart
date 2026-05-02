# Detailed Install Guide

If [PREWORK.md](PREWORK.md) didn't work for you, or you want OS-specific detail, this is the full reference.

**Supported**: macOS, Windows 10/11, Linux.
**Not supported for the workshop**: Chromebooks (no Node.js without enabling Linux/Crostini, which is itself a setup project), iPads, phones. If that's all you have, pair up with someone who has a Mac or Windows laptop.

---

## macOS

### 1. VSCode

Easiest:
- Download from [code.visualstudio.com/download](https://code.visualstudio.com/download)
- Open the `.zip`, drag the VSCode app into your Applications folder, launch it.

When prompted, run **"Shell Command: Install 'code' command in PATH"** from the Command Palette (`Cmd+Shift+P`) so you can open folders in VSCode by typing `code .`.

### 2. Node.js

Two options:

**Option A — Direct install (easiest):**
- Download the LTS `.pkg` from [nodejs.org/en/download](https://nodejs.org/en/download)
- Double-click and install with defaults.

**Option B — Homebrew (if you already have it):**
```bash
brew install node@20
```

Verify: `node --version` → should show `v20.x.x` or higher.

### 3. Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

If you get a permissions error, try:
```bash
sudo npm install -g @anthropic-ai/claude-code
```

Verify: `claude --version`.

### 4. Sign in

```bash
claude
```

It will open your browser. Sign in to your Anthropic account. Done.

---

## Windows

### 1. VSCode

- Download the `.exe` installer from [code.visualstudio.com/download](https://code.visualstudio.com/download)
- During install, **check the box** that says "Add to PATH" — this lets you type `code .` in any terminal.

### 2. Node.js

- Download the LTS Windows Installer (`.msi`) from [nodejs.org/en/download](https://nodejs.org/en/download)
- Install with defaults.

### 3. Open the right terminal

Windows is tricky — Claude Code works best in **Windows Terminal** or **PowerShell**, not the old `cmd.exe`.

- Press `Win+X` → choose **"Windows Terminal"** or **"PowerShell"**.

### 4. Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

Verify: `claude --version`.

### 5. Sign in

```bash
claude
```

Browser will open for sign-in.

> **Windows tip**: If `npm install -g` fails with a permissions error, run your terminal **as Administrator** (right-click → "Run as administrator") and try again.

---

## Linux

### 1. VSCode

- Ubuntu/Debian: Download the `.deb` from [code.visualstudio.com/download](https://code.visualstudio.com/download), then `sudo dpkg -i code_*.deb`
- Fedora/RHEL: Download the `.rpm`, then `sudo rpm -i code_*.rpm`
- Arch: `yay -S visual-studio-code-bin`

### 2. Node.js

```bash
# Ubuntu/Debian
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs

# Or use nvm (node version manager) if you prefer:
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
nvm install 20
nvm use 20
```

### 3. Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

If permissions fail, either use `sudo` or set up an `npm` global directory:
```bash
mkdir -p ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
npm install -g @anthropic-ai/claude-code
```

### 4. Sign in

```bash
claude
```

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
node --version    # v20.x or higher
npm --version     # 10.x or higher
claude --version  # any version
git --version     # any version
code --version    # any version (Mac/Linux only — Windows uses the GUI)
```

All five commands should return version numbers, not errors.

---

## Still stuck?

See [TROUBLESHOOTING.md](TROUBLESHOOTING.md), or come to the workshop 15 minutes early.
