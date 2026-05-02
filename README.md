# Claude Code Jumpstart

**Get comfortable with AI by building three useful things, fast.**

> 🎨 **Don't worry — you won't write any code.** The name says "Code," but you talk to Claude exactly the way you'd talk to a smart intern, in plain English. The "code" part just means Claude can read and edit files on your computer (like writing notes, organizing data, building a learning plan for you). You stay in plain English the whole time. If you can write a text message, you can use this.

This is a hands-on starter kit for people who have never used an AI tool like this before — designers, writers, marketers, founders, students, anyone. By the end, you will have built three small "agents" that help you in real life — and you will know how to build more, just by talking to Claude.

> Originally built for the **City of Knowledge AI Symposium — May 2nd**. Free for anyone to use, fork, or run as their own workshop.

---

## What you will build

Each link below opens a self-contained page with the prompt to copy and step-by-step instructions. **No git clone needed** — open the page, copy the prompt, paste into Claude Code.

| # | Scenario | What it does | Time |
|---|---|---|---|
| 1 | **[Learning Companion ➜](scenarios/01-learning-companion/)** | Pick any YouTube video (e.g., "how to start a Shopify store"), and Claude turns it into a phased learning plan with TODOs. It teaches you, you learn alongside it. | ~25 min |
| 2 | **[Data → Dashboard ➜](scenarios/02-data-to-dashboard/)** | Drop in a spreadsheet, CSV, or screenshot. Claude analyzes it, finds the story, and writes a one-page summary or chart. | ~10 min |
| 3 | **[Interview Prep Coach ➜](scenarios/03-interview-prep/)** | Drop in your resume, the job description, and the interviewers' LinkedIn pages. Claude preps you with likely questions, your strongest answers, and what to ask back. | ~10 min |

**Then** — the magic moment — you ask Claude to turn what you just did into a reusable agent. **Claude writes the agent for you, by reflecting on the conversation you just had.** No code, no download. Use it forever as `@your-agent` in any folder. ([How that works ➜]({{ "/agents/" | relative_url }}))

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

## Quick start (no terminal needed)

Once you've done the [prework]({{ "/prework/" | relative_url }}) (VSCode + Claude Code installed):

1. **Open VSCode** (the app you installed in prework).
2. **File → New Folder** — name it anything (e.g., `my-claude-test`). Save it on your Desktop.
3. **Open that folder in VSCode**: File → Open → pick the folder you just made.
4. **Click the Claude icon in the left sidebar.** It looks like the Claude logo. (If you don't see it, click the Extensions icon — four squares — and make sure "Claude Code" is installed.)
5. **A chat panel opens on the right.** If it asks you to sign in, do that. **You're now talking to Claude.**
6. **Click any scenario above ⬆**, copy the prompt from that page, paste it into the Claude chat. That's it.

That's the whole flow. No terminal commands. No git. No code.

> 💡 **Comfortable with the terminal?** You can also open any folder in your terminal and type `claude` to start a session. Both paths work — pick the one that feels easier.

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
