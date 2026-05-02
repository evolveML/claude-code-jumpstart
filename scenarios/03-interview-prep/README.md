# Scenario 3: Interview Prep Coach

**Going in for an interview? Drop in your resume, the JD, and the interviewers' LinkedIn pages. Claude preps you.**

This is a take-home scenario. Try it the next time you have a real interview.

---

## What you'll build

A folder with:
- Your resume (text file)
- The job description (text file)
- Company background (one paragraph or company website text)
- LinkedIn profile exports of each interviewer (text — see below)
- A `INTERVIEW_PREP.md` written by Claude with likely questions, your strongest answers, what to ask back, and what to research more

---

## Folder setup

```bash
mkdir my-interview-at-acme
cd my-interview-at-acme

# Drop in these files (filenames don't matter — Claude figures it out):
# - resume.txt or resume.pdf
# - job-description.txt
# - company-overview.txt (optional but helpful)
# - interviewer-1-jane-doe.txt (LinkedIn export — see below)
# - interviewer-2-john-smith.txt
# ... etc

claude
```

---

## How to get LinkedIn profile text

LinkedIn doesn't have a clean export, but here are 3 ways:

1. **Easiest**: Just visit their LinkedIn profile, select-all (`Cmd/Ctrl+A`), copy, paste into a `.txt` file. It'll be messy but Claude can sort it out.
2. **Better**: Use a browser extension like "Save Page WE" to save the rendered page as a single HTML file.
3. **Most polished**: Their LinkedIn page → "More" → "Save to PDF". Drop the PDF in the folder.

If they have a personal website or recent talks/articles, drop those in too.

---

## The prompt

Use [PROMPT_TEMPLATE.md](PROMPT_TEMPLATE.md). Paste it into Claude after you've put your files in the folder.

---

## What "good" looks like

After running the prompt, you should have:

```
my-interview-at-acme/
├── resume.txt
├── job-description.txt
├── company-overview.txt
├── interviewer-1.txt
├── interviewer-2.txt
└── INTERVIEW_PREP.md   ← The good stuff
```

`INTERVIEW_PREP.md` should contain:
- **Top 3 questions you should expect** (specific to the JD + interviewers)
- **Your strongest 3 stories** (mapped from your resume)
- **3 great questions to ask back** (per interviewer, where you have info)
- **What to research more before the interview** (gaps Claude noticed)
- **Likely concerns about you** (things Claude noticed in the gap between your resume and the JD — and how to address them honestly)

---

## Variations

- **First-round phone screen**: tell Claude that. The questions and depth will differ.
- **Behavioral round**: "Generate 10 STAR-format prep questions for this role and walk me through one."
- **Technical round**: "What are the technical concepts I should review? Drill me on them."
- **Mock interview**: "Now interview me. Ask me one question at a time. Critique my answers."

The mock interview mode is the most under-used and most valuable. Try it.

---

## Convert to an agent

Once you've used this for one real interview, install it:

```bash
mkdir -p ~/.claude/agents
cp ../../agents/interview-coach.md ~/.claude/agents/
```

Now: `@interview-coach prep me — files are in this folder`. Done.
