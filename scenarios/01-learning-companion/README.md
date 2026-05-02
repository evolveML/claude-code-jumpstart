---
title: "Scenario 1: Learning Companion"
permalink: /scenarios/01-learning-companion/
---

# Scenario 1: Learning Companion

**Pick something you've always wanted to learn. Claude turns a YouTube video about it into your personal tutor.**

By the end you'll have a `LEARNING_PLAN.md` with phases and TODOs, and Claude teaching you Phase 1 alongside you.

> ⏱ **Time**: ~25 minutes for the full first phase
> 🛠 **You need**: Claude Code installed (see [PREWORK](../../PREWORK.md))
> 📂 **No git clone required** — everything you need is on this page

---

## How to do it

### Step 1 — Make a folder for this and open Claude Code

Anywhere on your computer (Desktop is fine):

```bash
mkdir my-learning
cd my-learning
claude
```

Or in VSCode: File → Open Folder → make a new folder → open it → start `claude` in the integrated terminal.

### Step 2 — Get a YouTube transcript

Pick a YouTube video (5–15 minutes) about something you want to learn. Then:

1. Go to **[notegpt.io/youtube-transcript-generator](https://notegpt.io/youtube-transcript-generator)**
2. Paste the YouTube URL → click **Generate** → click **Copy Transcript**

> 💡 **Don't have a video picked yet?** Use our [sample transcript](sample-transcript.txt) about starting a Shopify side hustle. Right-click → Save As, or copy the text from there.

### Step 3 — Copy this prompt

```
You are my learning companion. I want to learn the topic in the YouTube transcript below.

Here is what I need you to do:

1. Read the transcript carefully and identify the topic, the depth covered, and the natural phases or chapters of learning that emerge from it. If the transcript only covers basics, infer what intermediate and advanced phases would be too — but mark them clearly as "out of scope of this video."

2. Write a file called LEARNING_PLAN.md in the current folder with:
   - Topic: the topic in one sentence
   - My goal: what success looks like for me as a learner (ask me if you're not sure)
   - Phases: 4 to 6 phases ordered from foundational to advanced, each with:
     - Phase title
     - What I will know after this phase
     - 3 to 5 specific concepts/skills to learn (these become my TODOs)
     - One small hands-on exercise I can do to prove I learned it
     - Estimated time
   - My current progress: a checklist starting all unchecked

3. Set up your internal TODO list with each phase as a top-level item and the concepts as sub-items. Use the TodoWrite tool.

4. Save the original transcript as transcript.txt in this folder so we can reference it later.

5. DON'T start teaching yet. After the plan is ready, summarize the plan back to me in 5 bullets and ask: "Ready to start Phase 1, or do you want to tweak the plan?"

When I say "start Phase 1," you will:
- Explain the first concept clearly, like a great tutor would
- Give me a small, concrete exercise (5 minutes max)
- Wait for me to do it and report back
- Mark the TODO complete
- Move to the next concept
- At the end of Phase 1, write progress/phase-1-notes.md with a summary of what we covered and what I produced

Be warm, direct, and patient. When I get something wrong, don't just give me the answer — ask me a guiding question first.

---

Transcript:

[PASTE TRANSCRIPT HERE]
```

### Step 4 — Paste it into Claude Code

In Claude Code, paste the prompt from above. **Then replace `[PASTE TRANSCRIPT HERE]` with your actual transcript** from Step 2. Hit Enter.

### Step 5 — Watch Claude build your plan

Claude will:
- Read the transcript
- Ask you what your goal is (answer briefly)
- Write `LEARNING_PLAN.md` with 4–6 phases
- Set up its TODO list
- Show you the plan and ask if you're ready

Open `LEARNING_PLAN.md` in VSCode to see what it built.

### Step 6 — Tell Claude: "start phase 1"

Now the magic. Claude will:
- Explain the first concept
- Give you a small exercise
- Wait for you to do it
- Mark TODOs as you go
- Move you through the phase

When Phase 1 is done, you have notes saved in `progress/phase-1-notes.md`. Come back tomorrow, type "where were we" and Claude picks up.

---

## Topic ideas (if you don't have one)

| Topic | Why it works | Search YouTube for |
|---|---|---|
| Start a Shopify side hustle | Universal, actionable, abundant content | "how to start a Shopify store 2024" |
| Salary negotiation | Practical, immediate value | "salary negotiation tips" |
| Facebook ads for small business | Entrepreneurial | "Facebook ads for beginners" |
| Photography fundamentals | Visual, fun, easy to practice | "photography basics for beginners" |
| Fantasy football draft | Sports fans | "fantasy football draft strategy" |
| ETF investing basics | Universal | "ETF investing for beginners" |
| Public speaking | Universal anxiety | "how to give a great presentation" |
| Spanish (or any language) | Always useful | "Spanish for beginners" |
| Excel pivot tables | Office work superpower | "Excel pivot tables in 10 minutes" |
| Cooking a regional cuisine | Fun, sensory | "how to make biryani" |

The trick: pick a video that's **5–15 minutes long** and has **closed captions** (most popular videos do).

---

## When you're done — install this as a reusable agent

So you don't have to paste the prompt every time, install the Learning Companion as a Claude Code agent. One line:

```bash
mkdir -p ~/.claude/agents && curl -fsSL https://raw.githubusercontent.com/evolveML/claude-code-jumpstart/main/agents/learning-companion.md -o ~/.claude/agents/learning-companion.md
```

Restart Claude Code. Now anywhere on your computer, in any folder:

```
@learning-companion teach me about [whatever you want to learn next]
```

That's it. No prompt to remember. The agent handles the whole flow.

---

## What "good" looks like

After running this, your folder should have:

```
my-learning/
├── transcript.txt              ← what you pasted
├── LEARNING_PLAN.md            ← Claude's phased plan
└── progress/
    └── phase-1-notes.md        ← Claude writes this as you go
```

For a reference of what `LEARNING_PLAN.md` should look like, see [sample-output.md](sample-output.md).

---

## Variations

- **No transcript handy**: skip Step 2, modify the prompt to "I want to learn X — build me a 4-phase plan from your own knowledge."
- **Use a book/article instead**: paste the article text where the transcript would go.
- **Resume an old plan**: in the same folder later, just type "where were we?" — Claude reads `LEARNING_PLAN.md` and picks up.
- **Switch the pace**: tell Claude "go faster, I already know the basics" or "slow down, this is too much."
