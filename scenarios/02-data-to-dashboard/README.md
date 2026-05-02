---
title: "Scenario 2: Data → Dashboard"
permalink: /scenarios/02-data-to-dashboard/
---

# Scenario 2: Data → Dashboard

**Drop in any data — a CSV, a spreadsheet, even a screenshot — and Claude finds the story. Optionally, it builds you a chart.**

> ⏱ **Time**: ~10 minutes
> 🛠 **You need**: Claude Code installed (see [Prework]({{ "/prework/" | relative_url }}))
> 📂 **No git clone required** — everything is on this page

---

## How to do it

### Step 1 — Make a folder and open Claude Code

```bash
mkdir my-data-analysis
cd my-data-analysis
claude
```

### Step 2 — Get some data into the folder

Three options, pick one:

**A. Use sample data** (zero setup):
- Family budget CSV: [sample-data/family-budget.csv](sample-data/family-budget.csv) — fictional 12 months of household spending
- NBA stats CSV: [sample-data/nba-2024-stats.csv](sample-data/nba-2024-stats.csv) — 2023–24 season top 30 players

Right-click → Save As, save to your `my-data-analysis` folder.

**B. Bring your own CSV**: download from your bank, Apple Health, Yahoo Finance, anywhere. Drop it in the folder.

**C. Use a screenshot**: take a screenshot of a chart, receipt, or table. Save it as `screenshot.png` in the folder.

### Step 3 — Copy this prompt (pick the one that matches your data)

#### Variation A — CSV/Spreadsheet → Analysis

```
You are my data analyst. I have a data file in this folder. Here's what I want:

1. Read the file — figure out the format, columns, and what each column means.
2. Find the story. Don't just summarize. Look for:
   - The biggest insight (what would surprise me?)
   - Trends (what's going up, what's going down?)
   - Outliers (what's weirdly high or low?)
   - What's missing (what data would I need to make this more useful?)
3. Write ANALYSIS.md in this folder with:
   - Top finding in 1 sentence at the top
   - 3 key insights (with the actual numbers, not vague claims)
   - What I should do next based on this data
   - What I should ask next to dig deeper
4. Be specific with numbers. If you say "spending on dining is creeping up," show me the months and amounts.

The file is: [REPLACE WITH YOUR FILENAME, e.g., family-budget.csv]

Some context about me/this data: [DESCRIBE — e.g., "this is my family's actual budget" or "I'm a sports fan trying to settle a debate"]

Don't write code unless I ask. Just analyze.
```

#### Variation B — Screenshot/Image → Analysis

```
I'm pasting/attaching an image. Tell me:

1. What is this image? (a chart, a receipt, a screenshot of a webpage, etc.)
2. What data is in it? Extract the actual values you can see.
3. What's the story? Same as before — surprises, trends, outliers, what's missing.
4. Write ANALYSIS.md with the extracted data + your insights.

Don't worry about being perfect on numbers — call out anything you're uncertain about.

Context: [DESCRIBE WHAT THE IMAGE IS, e.g., "this is my Apple subscriptions page"]
```

To attach the image in Claude Code: drag-and-drop into the VSCode Claude sidebar, OR run `claude --image screenshot.png`.

#### Variation C — CSV → Visual Dashboard (the showstopper)

```
You are my data analyst AND my front-end developer. I want both an analysis and a visual dashboard.

1. Read the data file: [FILENAME]
2. Write ANALYSIS.md with the findings (as in Variation A).
3. Write dashboard.html — a SINGLE HTML FILE that I can open by double-clicking, with:
   - 3 to 5 charts that visualize the most important findings
   - Use Chart.js loaded from a CDN — no npm, no build
   - Embed the data directly in the HTML (don't reference external CSVs)
   - Clean, modern styling (use a simple dark or light theme — your call)
   - Include a 1-paragraph intro at the top explaining what someone is looking at

Show me the file paths when done so I can open them.

Context: [DESCRIBE]
```

When Claude is done, double-click `dashboard.html` — it opens in your browser as a real interactive dashboard.

### Step 4 — Paste, run, read

Paste the prompt into Claude Code. Replace the placeholders. Hit Enter. Open the resulting `ANALYSIS.md` (and `dashboard.html` if you used Variation C).

---

## Real-world examples

| What you have | Try this prompt |
|---|---|
| Last 12 months of credit card statements (CSVs) | "Categorize my spending and find the 3 categories where I've been creeping up." |
| Apple Health step data | "What's my activity pattern? When am I most active? When do I fall off?" |
| A receipt photo | "What did I buy and what's the most expensive item per dollar of weight?" |
| Your last 6 months of Shopify orders | "Which products have the best margins? Which customers come back?" |
| Sports stats for two players | "Compare these two players. Who was more valuable to their team and why?" |
| A CSV of every job you applied to | "What's working? Where am I getting ghosted? Patterns by role/company size?" |

---

## When you're done — have Claude build you a `@data-analyst` agent

Don't download our file — let Claude write the agent for you, based on what just worked.

In the same Claude session, paste:

```
Turn what we just did into a reusable Claude Code agent.

Write the agent definition to ~/.claude/agents/data-analyst.md with:
- YAML frontmatter with `name: data-analyst` and a description of when to invoke it (e.g., "use when the user has a data file, screenshot of data, or messy folder of files and wants insights")
- A system prompt that captures how you analyzed my data — the inventory step (figure out what files are here, what columns mean), the find-the-story step (the biggest insight, trends, outliers, what's missing), and the output format (top finding in 1 sentence, 3 key insights with actual numbers, what to do next)
- The style rules: always cite specific numbers, lead with the surprise (not the obvious), don't write code unless asked

Use the standard Claude Code agent format. Read it back to me when done.
```

Claude writes the agent. Restart Claude (`/exit`, then `claude`). Then in any folder with data:

```
@data-analyst what's the story in this folder?
```

The agent does what just worked, every time, forever. **You built it by talking.**

> 💡 **Want a polished reference?** [Here's our curated `data-analyst.md`]({{ "/agents/" | relative_url }}) — compare with what Claude wrote for you. Steal ideas. The agent file is yours to edit anytime in VSCode.

---

## Tip: the screenshot trick

The most under-used capability of Claude Code is **image input**. Try:
- Screenshot your phone's Subscriptions screen → "what am I spending and where can I cut?"
- Screenshot a chart from a news article → "is this chart misleading? what's the actual story?"
- Screenshot a complicated form → "extract this into a CSV"

You don't need to type any data — Claude reads the image.

---

← [Back to home]({{ "/" | relative_url }}) · [Scenario 1: Learning Companion]({{ "/scenarios/01-learning-companion/" | relative_url }}) · [Scenario 3: Interview Prep]({{ "/scenarios/03-interview-prep/" | relative_url }}) · [Agents]({{ "/agents/" | relative_url }}) · [Troubleshooting]({{ "/troubleshooting/" | relative_url }})
