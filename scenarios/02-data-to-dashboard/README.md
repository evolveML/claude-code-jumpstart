# Scenario 2: Data → Dashboard

**Drop in any data — a CSV, a spreadsheet, a screenshot of your bills — and Claude finds the story.**

This is a take-home scenario. Try it after the workshop.

---

## What you'll build

A folder with:
- Your input data (a CSV, an image, a pasted table)
- A `ANALYSIS.md` written by Claude with key findings
- An optional `dashboard.html` Claude generates if you ask for charts

---

## Three ways to use it

### A. CSV → Analysis (easiest)

You have a CSV — could be a budget, sports stats, sales data, anything.

Try with our sample first:

```bash
cd scenarios/02-data-to-dashboard
claude
```

Then paste the prompt from `PROMPT_TEMPLATE.md` referencing `sample-data/family-budget.csv`. Claude will read it and write an analysis.

### B. Screenshot → Analysis (most jaw-dropping)

You have a screenshot — your phone's subscriptions page, a receipt, a chart from a website.

Drag the image into Claude Code (or use `claude --image path/to/screenshot.png`) and ask: "What's in this image and what should I notice?"

Claude reads the image, extracts the data, and writes findings.

### C. CSV → Dashboard HTML (most impressive)

Same as A, but tell Claude: "After the analysis, also write a single-file `dashboard.html` with charts using Chart.js. I want to be able to open it in any browser."

Claude writes a self-contained HTML file with charts you can open with a double-click. No build, no server.

---

## Sample data included

| File | What it is | Try this |
|---|---|---|
| `sample-data/family-budget.csv` | A made-up family's monthly spending across 12 months | "Where am I overspending? What's trending up?" |
| `sample-data/nba-2024-stats.csv` | Top 30 NBA players' 2023–24 season stats | "Who had the most efficient season? Compare LeBron vs Jokic." |

---

## When to use which

| You have... | Use approach |
|---|---|
| A CSV from your bank, Excel, or a download | A — CSV → Analysis |
| A screenshot of a chart, receipt, or table | B — Screenshot → Analysis |
| A CSV and you want to share visualizations | C — CSV → Dashboard HTML |
| A messy mix of files | Just put them all in one folder, point Claude at the folder, and ask: "What can you tell me from these files?" |

---

## Real-world examples

- **Personal finance**: "Here's my last 12 months of credit card statements as CSVs. Categorize my spending and find the 3 categories where I've been creeping up."
- **Sports**: "Compare these two players' seasons stats. Who was more valuable to their team and why?"
- **Small business**: "Here are my last 6 months of Shopify orders. Which products have the best margins? Which customers come back?"
- **Health**: "Here's a year of Apple Health step data. What's my pattern? When am I most active?"
- **Job search**: "Here's a CSV of every job I've applied to. What's working? Where am I getting ghosted?"

---

## Convert it to an agent

Once you've used this twice, install it as a reusable agent:

```bash
mkdir -p ~/.claude/agents
cp ../../agents/data-analyst.md ~/.claude/agents/
```

Now in any folder with data, you can say `@data-analyst what's the story here?` and Claude knows the drill.
