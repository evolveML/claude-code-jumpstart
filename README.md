# Claude Code Jumpstart

**Get comfortable with AI by building three useful things, fast.**

This is a hands-on starter kit for people who have never used Claude Code (or any AI coding assistant) before. By the end, you will have built three small "agents" that help you in real life — and you will know how to build more.

> Originally built for the **City of Knowledge AI Symposium — May 2nd**. Free for anyone to use, fork, or run as their own workshop.

---

## What you will build

Each link below opens a self-contained page with the prompt to copy and step-by-step instructions. **No git clone needed** — open the page, copy the prompt, paste into Claude Code.

| # | Scenario | What it does | Time |
|---|---|---|---|
| 1 | **[Learning Companion ➜](scenarios/01-learning-companion/)** | Pick any YouTube video (e.g., "how to start a Shopify store"), and Claude turns it into a phased learning plan with TODOs. It teaches you, you learn alongside it. | ~25 min |
| 2 | **[Data → Dashboard ➜](scenarios/02-data-to-dashboard/)** | Drop in a spreadsheet, CSV, or screenshot. Claude analyzes it, finds the story, and writes a one-page summary or chart. | ~10 min |
| 3 | **[Interview Prep Coach ➜](scenarios/03-interview-prep/)** | Drop in your resume, the job description, and the interviewers' LinkedIn pages. Claude preps you with likely questions, your strongest answers, and what to ask back. | ~10 min |

**Then** — you take any of the three and turn it into a reusable agent. One file. One command. Forever yours.

---

## Before the workshop

**Do this 24 hours before** so we don't burn time installing in the room. It takes ~15 minutes:

➡️ **[Prework — install everything]({{ "/prework/" | relative_url }})**

> **Computer needed**: Mac, Windows, or Linux laptop. Chromebooks, iPads, and phones won't work for this workshop — bring a real laptop or pair up with someone who has one.

If you get stuck, no shame — show up early or pair up with someone who's done it.

---

## 📌 Don't worry about finishing in the workshop

Everything in this kit is online and free, forever. **You can pick it up tonight, this weekend, or six months from now** — the pages don't expire. Bookmark this URL:

> **`evolveml.github.io/claude-code-jumpstart`**

You have on this site:
- [Three scenarios]({{ "/scenarios/01-learning-companion/" | relative_url }}) with copy-paste prompts and sample data
- [Three reusable agents]({{ "/agents/" | relative_url }}) you install with one command
- [Prework]({{ "/prework/" | relative_url }}) and [detailed install]({{ "/install/" | relative_url }}) for any computer
- [Troubleshooting]({{ "/troubleshooting/" | relative_url }}) for the most common 7 issues
- A [printable handout]({{ "/handout/" | relative_url }}) summarizing everything in one page

In the workshop we'll do **just one** scenario together. Don't try to do all three live — try the others on your own this week.

---

## Quick start

Once you've done the [prework](PREWORK.md) (VSCode + Claude Code installed):

1. **Make a folder** anywhere on your computer — Desktop is fine: `mkdir my-claude-test && cd my-claude-test`
2. **Start Claude Code**: type `claude` in the terminal (or open the folder in VSCode and start Claude in the integrated terminal)
3. **Click any scenario above** ⬆ — each page has a copy-pasteable prompt and step-by-step instructions
4. **Paste the prompt** into Claude Code. That's it.

> 💡 **Want a local copy of all the files?** `git clone https://github.com/evolveML/claude-code-jumpstart.git` works too — but you don't need it. Everything is on these pages.

---

## All the pages

| Page | What it is |
|---|---|
| **[Prework]({{ "/prework/" | relative_url }})** | Install everything 24h before the workshop (start here) |
| **[Detailed install]({{ "/install/" | relative_url }})** | OS-specific guide for Mac, Windows, Linux |
| **[Troubleshooting]({{ "/troubleshooting/" | relative_url }})** | When things break |
| **[Scenario 1: Learning Companion]({{ "/scenarios/01-learning-companion/" | relative_url }})** | Pick a YouTube video → personal tutor with phases + TODOs |
| **[Scenario 2: Data → Dashboard]({{ "/scenarios/02-data-to-dashboard/" | relative_url }})** | CSV / spreadsheet / screenshot → analysis + optional chart |
| **[Scenario 3: Interview Prep Coach]({{ "/scenarios/03-interview-prep/" | relative_url }})** | Resume + JD + interviewer info → predicted questions + mock interview |
| **[Agents]({{ "/agents/" | relative_url }})** | Install any of the three as a permanent `@agent` you can use forever |
| **[Handout (1-pager)]({{ "/handout/" | relative_url }})** | Printable summary you can take home |

Each scenario page is self-contained: read it, copy the prompt, paste into Claude Code, done.

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
