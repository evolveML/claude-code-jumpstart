# Convert Any Workflow Into a Reusable Agent

Once you've run a prompt twice and you like how it works, **stop pasting it** — turn it into an agent. One file, one folder, infinite re-use.

---

## What is an agent?

An agent is just a `.md` file in `~/.claude/agents/` that tells Claude how to behave when you call it.

It has two parts:
1. **Frontmatter** — a few lines at the top that say "this agent is named X, here's when to use it, here are its tools"
2. **System prompt** — the instructions for how it should behave

That's it. No code, no servers, nothing to deploy.

---

## How to install an agent

```bash
# Make sure the agents folder exists
mkdir -p ~/.claude/agents

# Copy the agent file from this repo
cp learning-companion.md ~/.claude/agents/
cp data-analyst.md ~/.claude/agents/
cp interview-coach.md ~/.claude/agents/
```

That's it. Restart Claude Code and the agents are live.

---

## How to use an agent

In any folder, after starting `claude`:

```
@learning-companion teach me about ETF investing
```

```
@data-analyst what's the story in this folder?
```

```
@interview-coach prep me — my files are here
```

The `@` triggers the agent. Claude will load the agent's instructions and behave accordingly. The agent persists across sessions — once installed, it's available everywhere.

---

## Agents in this kit

| Agent | When to invoke | What it does |
|---|---|---|
| **`@learning-companion`** | Anytime you want to learn something | Builds phased learning plans with TODOs, teaches alongside you |
| **`@data-analyst`** | When you have a data file or screenshot | Reads it, finds the story, writes analysis (and optionally a dashboard HTML) |
| **`@interview-coach`** | Before an interview | Reads your resume + JD + interviewers' info, builds prep doc, runs mock interviews |

---

## Building your own agent

Once you understand the pattern, you can write your own. Pick any prompt you've used twice and want to reuse, and:

1. Create a new file: `~/.claude/agents/[your-agent-name].md`
2. Use this template:

```markdown
---
name: your-agent-name
description: When to use this agent. Be specific — Claude reads this to decide whether to route to you.
---

You are an expert at [thing]. When the user invokes you, you should:

1. [First thing you do]
2. [Second thing]
...

Always [behavior they want consistently].
Never [behavior they don't want].

[Any other context, examples, or guardrails.]
```

Save the file. Restart Claude. `@your-agent-name [request]` and it works.

---

## Pro tips

- **One agent, one job.** Don't build a "do everything" agent — build small focused ones and chain them.
- **Description matters.** Claude uses the description to decide *whether to call* an agent. Make it clear when to use it.
- **Iterate on the prompt.** First version is rarely perfect. Use the agent for a week, notice what's annoying, edit the file.
- **Share your agents.** A `.md` file is portable. Email it to a friend, paste it in a doc, fork this repo and PR it.

---

## Where to learn more

- Anthropic's [official agent docs](https://docs.claude.com/en/docs/claude-code/agents.md)
- The [Claude Code GitHub](https://github.com/anthropics/claude-code) for examples
