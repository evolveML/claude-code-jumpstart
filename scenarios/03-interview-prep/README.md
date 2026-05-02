---
title: "Scenario 3: Interview Prep Coach"
permalink: /scenarios/03-interview-prep/
---

# Scenario 3: Interview Prep Coach

**Going in for an interview? Drop in your resume, the job description, and the interviewers' info. Claude preps you with likely questions, your strongest answers, and what to ask back.**

> ⏱ **Time**: ~10 minutes for the prep, plus an optional mock interview
> 🛠 **You need**: Claude Code installed (see [Prework]({{ "/prework/" | relative_url }}))
> 📂 **No git clone required** — everything is on this page

---

## How to do it

### Step 1 — Make a folder for this interview

```bash
mkdir my-interview-at-acme   # use the actual company name
cd my-interview-at-acme
claude
```

### Step 2 — Drop your files into the folder

Filenames don't matter — Claude figures it out. Add whatever you have:

| File | What |
|---|---|
| `resume.txt` (or `.pdf`) | Your resume |
| `job-description.txt` | Paste the JD from the listing |
| `company-overview.txt` | A paragraph or two about the company (their About page works) |
| `interviewer-1-jane-doe.txt` | LinkedIn profile of person #1 |
| `interviewer-2-john-smith.txt` | LinkedIn profile of person #2 |

You don't need ALL of these. Even just resume + JD is enough.

#### How to grab a LinkedIn profile as text

LinkedIn doesn't have a clean export, but here are 3 ways:

1. **Easiest**: Visit their profile, `Cmd/Ctrl+A` to select-all, copy, paste into a `.txt` file. Messy but works.
2. **Better**: Their LinkedIn page → "More" → "Save to PDF". Drop the PDF in the folder.
3. **Most polished**: Use a browser extension like "Save Page WE" to save as a single HTML file.

If they have a personal website, recent talks, or articles, drop those text in too.

### Step 3 — Copy this prompt

```
You are my interview coach. In this folder are some or all of:
- My resume
- The job description
- Company background
- LinkedIn profiles or pages for the people interviewing me

Read everything in this folder. Then do the following:

1. Map me to the role. Look at the JD requirements vs my resume. For each major requirement:
   - Where am I strong? Cite specific things from my resume.
   - Where am I weak or have gaps? Be honest — don't soft-pedal.

2. Predict the questions. Generate 8 to 12 likely interview questions. Mix:
   - Behavioral ("tell me about a time you...")
   - Role-specific ("how would you approach X in this job?")
   - Concern-driven (questions designed to dig at my weak spots — be sharp here)
   - Interviewer-specific (if you can read their backgrounds, infer what they care about)

3. Draft my strongest answers. For 3 of the most important questions, write a draft answer using STAR format (Situation, Task, Action, Result). Pull real material from my resume — don't make stuff up.

4. What to ask back. Generate 3 thoughtful questions per interviewer that show I've done my homework on them and the role. These should NOT be generic ("what's the culture like?"). They should reference something specific from their background or the company.

5. What to research more. Note what's missing or weak in the materials I've given you (e.g., "I don't see anything about company X's recent product launch — go research it before the interview").

6. Likely concerns about me. Be the interviewer. What would I worry about, looking at my resume vs this JD? What's the honest answer to that worry?

Write everything to INTERVIEW_PREP.md in this folder. Use clear headings. Include the actual draft answers — not just outlines.

Be direct. Don't flatter. The goal is for me to walk into the interview overprepared, not to feel good about myself.
```

### Step 4 — Paste into Claude Code

Paste the prompt. Hit Enter. Claude will read everything in the folder and write `INTERVIEW_PREP.md`.

### Step 5 — Open and review `INTERVIEW_PREP.md`

You should see:
- The gap map (where you're strong vs weak)
- 8–12 predicted questions
- 3 fully-drafted STAR answers
- Questions to ask each interviewer
- What to research before the interview
- Likely concerns about you (and honest responses)

### Step 6 — Run a mock interview (most important step)

Most people read prep notes. Very few actually rehearse out loud. Don't be that person. Paste:

```
Now interview me.

Ask me ONE question at a time. After each answer, give me feedback:
- What worked
- What didn't
- A better version of the answer

Don't move on to the next question until I say "next." Start with the hardest question on the list.
```

Speak your answers out loud (yes, even if alone). Claude will critique and you'll iterate. This is the single highest-leverage thing you can do before any interview.

---

## Variations

- **First-round phone screen**: tell Claude. The questions and depth will differ.
- **Behavioral round only**: "Generate 10 STAR-format prep questions, focus only on behavioral, drill me on one."
- **Technical round**: "What technical concepts should I review? Drill me on them — start with [topic]."
- **Sales/pitching role**: "I'll be doing a 60-second pitch in the interview. Help me draft it, then critique it."

---

## When you're done — have Claude build you an `@interview-coach` agent

Don't curl our file. Have Claude turn what just happened into an agent for you.

In the same Claude session, paste:

```
Turn what we just did into a reusable Claude Code agent.

Write the agent definition to ~/.claude/agents/interview-coach.md with:
- YAML frontmatter with `name: interview-coach` and a description of when to invoke it (e.g., "use when the user is preparing for a job interview and the folder has resume/JD/interviewer info")
- A system prompt that captures the phases of what you just did: read everything, map the gap (resume vs JD), predict 8-12 questions including concern-driven ones, draft 3 STAR-format answers, generate questions to ask back (specific not generic), call out concerns about me + honest answers
- The mock interview mode: when I say "interview me," ask one question at a time, give 3-part feedback (what worked / what didn't / better version), don't move on until I say "next"
- The style: direct, not gentle. No flattery. Anchor everything to evidence in the resume/JD.

Use the standard Claude Code agent format. Read it back to me when done.
```

Claude writes the agent. Restart Claude. Next time you have an interview:

```
@interview-coach prep me — files are in this folder
```

> 💡 **Want a polished reference?** [Here's our curated `interview-coach.md`]({{ "/agents/" | relative_url }}) — read it after Claude writes yours. Compare. The version Claude built for you might miss something ours has, or might be sharper in places. Edit yours and you've got the best of both.

---

## Privacy note

Claude Code runs on your computer, but it sends your prompts (including resume content) to Anthropic's API. Treat it like email:
- Fine for typical resume/JD info
- If your resume has SSN, full home address, salary history — redact those before pasting
- If interviewing with a competitor of your current company and the JD is highly sensitive, use generic descriptions instead of pasting verbatim

After the interview, you can delete the folder. Nothing stays on Anthropic's side.

---

← [Back to home]({{ "/" | relative_url }}) · [Scenario 1: Learning Companion]({{ "/scenarios/01-learning-companion/" | relative_url }}) · [Scenario 2: Data → Dashboard]({{ "/scenarios/02-data-to-dashboard/" | relative_url }}) · [Agents]({{ "/agents/" | relative_url }}) · [Troubleshooting]({{ "/troubleshooting/" | relative_url }})
