# Scenario 1: Learning Companion

**Pick something you've always wanted to learn. Claude turns a YouTube video about it into your personal tutor.**

This is the in-room scenario for the workshop.

---

## What you'll build

A folder with:
- The YouTube transcript you grabbed
- A `LEARNING_PLAN.md` that Claude wrote, with phases and TODOs
- A `progress/` folder where Claude tracks what you've learned and what you've practiced

By the end, Claude will be teaching you Phase 1 — quizzing you, suggesting exercises, and checking off TODOs as you go.

---

## The flow

```
Pick a topic
    ↓
Find a YouTube video (5–15 min) about it
    ↓
Grab the transcript using notegpt.io
    ↓
Paste into Claude Code with the prompt template
    ↓
Claude writes your LEARNING_PLAN.md with phases + TODOs
    ↓
Work through Phase 1 alongside Claude
    ↓
(Optional) Convert into a reusable agent
```

---

## How to use this folder

1. **Open this folder in VSCode**:
   ```bash
   cd scenarios/01-learning-companion
   code .
   ```

2. **Start Claude Code in the integrated terminal**:
   ```bash
   claude
   ```

3. **Get a transcript**:
   - Open [notegpt.io/youtube-transcript-generator](https://notegpt.io/youtube-transcript-generator)
   - Paste your YouTube URL
   - Click "Generate" → copy the transcript text
   - **Or** use the [sample-transcript.txt](sample-transcript.txt) we provide (a real "How to Start a Shopify Store" transcript)

4. **Open [PROMPT_TEMPLATE.md](PROMPT_TEMPLATE.md)** and copy the prompt. Paste it into Claude, with your transcript inside the `[PASTE TRANSCRIPT HERE]` placeholder.

5. **Watch Claude work**. It will:
   - Read the transcript
   - Identify the natural phases of the topic
   - Write a `LEARNING_PLAN.md` to disk
   - Set up its TODO list with each phase

6. **Tell Claude: "Let's start Phase 1"**. It will explain the concept, give you exercises, and mark progress as you go.

---

## Topic suggestions

If you don't have a topic in mind, here are some great picks for a 5–15 minute YouTube video:

| Topic | Why it works | Search term |
|---|---|---|
| **Start a Shopify side hustle** | Universal, actionable, abundant content | "how to start a Shopify store 2024" |
| **Negotiate your salary** | Practical, immediate value | "salary negotiation tips" |
| **Run Facebook ads for a small business** | Entrepreneurial | "Facebook ads for beginners 2024" |
| **Photography fundamentals** | Visual, fun, easy to practice | "photography basics for beginners" |
| **Reading fantasy football stats** | Sports fans | "fantasy football draft strategy" |
| **Personal finance / ETFs** | Universal | "ETF investing for beginners" |
| **Public speaking** | Universal anxiety | "how to give a great presentation" |
| **Spanish (or any language) basics** | Always useful | "Spanish for beginners 5 minutes" |
| **Excel pivot tables** | Office work superpower | "Excel pivot tables in 10 minutes" |
| **Cooking a regional cuisine** | Fun, sensory, tangible | "how to make biryani" |

The trick: pick a video that's **5–15 minutes long** (long enough to have substance, short enough that the transcript fits) and has **closed captions** (most popular videos do).

---

## What "good" looks like

After running the prompt, your folder should contain:

```
01-learning-companion/
├── transcript.txt              ← what you pasted
├── LEARNING_PLAN.md            ← Claude's phased plan
└── progress/
    └── phase-1-notes.md        ← Claude writes this as you go
```

Open `LEARNING_PLAN.md` to see the phases. Then in Claude Code, type `start phase 1` to begin learning.

---

## Then convert it to an agent

Once you've used the prompt twice and feel its rhythm, install it as a reusable agent:

```bash
mkdir -p ~/.claude/agents
cp ../../agents/learning-companion.md ~/.claude/agents/
```

Now in any folder, you can type `@learning-companion teach me X` and Claude will set up the same flow without you needing the prompt. See [agents/README.md](../../agents/README.md) for details.
