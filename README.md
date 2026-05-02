# Claude Code Jumpstart

**Get comfortable with AI by building three useful things, fast.**

This is a hands-on starter kit for people who have never used Claude Code (or any AI coding assistant) before. By the end, you will have built three small "agents" that help you in real life — and you will know how to build more.

> Originally built for the **City of Knowledge AI Symposium — May 2nd**. Free for anyone to use, fork, or run as their own workshop.

---

## What you will build

| Scenario | What it does | Time |
|---|---|---|
| 1. **Learning Companion** | Pick any YouTube video (e.g., "how to start a Shopify store"), and Claude turns it into a phased learning plan with TODOs. It teaches you, you learn alongside it. | ~25 min |
| 2. **Data → Dashboard** | Drop in a spreadsheet, CSV, or screenshot. Claude analyzes it, finds the story, and writes a one-page summary or chart. | ~10 min |
| 3. **Interview Prep Coach** | Drop in your resume, the job description, and the interviewers' LinkedIn pages. Claude preps you with likely questions, your strongest answers, and what to ask back. | ~10 min |

**Then** — you take any of the three and turn it into a reusable agent. One file. One command. Forever yours.

---

## Before the workshop

**Do this 24 hours before** so we don't burn time installing in the room. It takes ~15 minutes:

➡️ **[PREWORK.md — install everything](PREWORK.md)**

If you get stuck, no shame — show up early or pair up with someone who's done it.

---

## Quick start

If you've already done the prework, in the workshop you will:

```bash
# 1. Clone this repo
git clone https://github.com/evolveML/claude-code-jumpstart.git
cd claude-code-jumpstart

# 2. Open it in VSCode
code .

# 3. Start Claude Code in the integrated terminal
claude

# 4. Follow Scenario 1
# Open scenarios/01-learning-companion/PROMPT_TEMPLATE.md
# Paste the prompt into Claude
# Magic happens
```

---

## What's in this repo

```
.
├── PREWORK.md                  ← Install everything before workshop
├── INSTALL.md                  ← Detailed install for Mac/Windows/Linux
├── TROUBLESHOOTING.md          ← When things break
├── scenarios/
│   ├── 01-learning-companion/  ← The in-room scenario
│   ├── 02-data-to-dashboard/   ← Try at home
│   └── 03-interview-prep/      ← Try at home
└── agents/                     ← Three reusable agents to install
    ├── learning-companion.md
    ├── data-analyst.md
    └── interview-coach.md
```

Every scenario has a `README.md` (what you're building), a `PROMPT_TEMPLATE.md` (the literal prompt to paste), and sample data so you can try it without bringing your own.

---

## What is Claude Code?

Claude Code is a command-line tool from Anthropic that lets you talk to Claude (the AI) from inside any folder on your computer. Unlike ChatGPT, it can:

- **Read your files** (the CSV on your desktop, the PDF in your Downloads)
- **Edit your files** (write your learning plan to disk, build a chart, draft a doc)
- **Run things** (execute commands, open a web browser, fetch a URL)
- **Stay focused on a task** with a TODO list it manages itself

You can use it as a **terminal command** (`claude` in any folder) or inside **VSCode** (recommended for beginners — it has a sidebar UI).

---

## License

MIT. Use it, fork it, run your own workshop, change it. Just keep the attribution.

Built with care by [EvolveML](https://evolveml.io).
