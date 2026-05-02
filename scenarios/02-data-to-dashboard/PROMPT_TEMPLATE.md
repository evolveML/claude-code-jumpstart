# The Prompt — Data Analyst

Three variations depending on what you want.

---

## Variation A — CSV/Excel Analysis (most common)

```
You are my data analyst. I have a data file in this folder. Here's what I want:

1. **Read the file** — figure out the format, columns, and what each column means.
2. **Find the story.** Don't just summarize. Look for:
   - The biggest insight (what would surprise me?)
   - Trends (what's going up, what's going down?)
   - Outliers (what's weirdly high or low?)
   - What's missing (what data would I need to make this more useful?)
3. **Write `ANALYSIS.md`** in this folder with:
   - **Top finding** in 1 sentence at the top
   - **3 key insights** (with the actual numbers, not vague claims)
   - **What I should do next** based on this data
   - **What I should ask next** to dig deeper
4. **Be specific with numbers.** If you say "spending on dining is creeping up," show me the months and amounts.

The file is: [REPLACE WITH FILENAME, e.g., sample-data/family-budget.csv]

Some context about me/this data: [DESCRIBE — e.g., "this is my family's actual budget" or "I'm a sports fan trying to settle a debate"]

Don't write code unless I ask. Just analyze.
```

---

## Variation B — Screenshot/Image Analysis

```
I'm pasting/attaching an image. Tell me:

1. **What is this image?** (a chart, a receipt, a screenshot of a webpage, etc.)
2. **What data is in it?** Extract the actual values you can see.
3. **What's the story?** Same as before — surprises, trends, outliers, what's missing.
4. **Write `ANALYSIS.md`** with the extracted data + your insights.

Don't worry about being perfect on numbers — call out anything you're uncertain about.

Context: [DESCRIBE WHAT THE IMAGE IS, e.g., "this is my Apple subscriptions page"]
```

---

## Variation C — CSV → Dashboard HTML

```
You are my data analyst AND my front-end developer. I want both an analysis and a visual dashboard.

1. **Read** the data file: [FILENAME]
2. **Write `ANALYSIS.md`** with the findings (as in Variation A).
3. **Write `dashboard.html`** — a SINGLE HTML FILE that I can open by double-clicking, with:
   - 3–5 charts that visualize the most important findings
   - Use Chart.js loaded from a CDN — no npm, no build
   - Embed the data directly in the HTML (don't reference external CSVs)
   - Clean, modern styling (use a simple dark or light theme — your call)
   - Include a 1-paragraph intro at the top explaining what someone is looking at

Show me the file paths when done so I can open them.

Context: [DESCRIBE]
```

---

## Quick tips

- **Drag-and-drop images**: in VSCode's Claude sidebar, you can drag an image straight in. From terminal: `claude --image path/to/image.png`.
- **Multiple files**: drop multiple CSVs in the folder and ask "give me a combined analysis across all of these."
- **"Compare two things" prompt**: "Compare X and Y. Who/which is more [efficient / valuable / interesting] and why? Use specific numbers."
