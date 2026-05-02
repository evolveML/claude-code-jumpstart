# Workshop Takeaway — One Page

You learned how to use Claude Code today. Here's how to keep going.

---

## The 3 patterns you saw

| Pattern | When to use it | Where to find it |
|---|---|---|
| **Learning Companion** | Anytime you want to learn something | `scenarios/01-learning-companion/` |
| **Data → Dashboard** | When you have a CSV, screenshot, or messy data | `scenarios/02-data-to-dashboard/` |
| **Interview Coach** | Before any interview | `scenarios/03-interview-prep/` |

Each scenario is a **prompt template + sample data**. Open the folder, follow the README, paste the prompt.

---

## The agents you can install right now

```bash
mkdir -p ~/.claude/agents
cp agents/*.md ~/.claude/agents/
```

Then in any folder:
- `@learning-companion teach me about [anything]`
- `@data-analyst what's the story in this folder?`
- `@interview-coach prep me — files are here`

---

## The 5 commands you actually need

```bash
claude                 # Start Claude in any folder
/exit                  # Close Claude
@agent-name [task]     # Invoke an agent
/clear                 # Reset conversation (start fresh)
/help                  # See everything you can do
```

---

## The 3 most useful keyboard shortcuts (in Claude Code)

- `Esc` once → interrupt the current task
- `Ctrl+C` → fully cancel
- Up arrow → recall your last message

---

## Build your own agent in 60 seconds

1. Create `~/.claude/agents/my-agent.md`
2. Paste this template:
```markdown
---
name: my-agent
description: When to use this agent (be specific).
---

You are an expert at [thing]. When invoked:
1. [First thing you do]
2. [Second thing]

Always [behavior]. Never [bad behavior].
```
3. Save. Restart Claude. `@my-agent [task]` and you're live.

---

## What to try this week

- [ ] Use the Learning Companion on a topic you've been putting off
- [ ] Drop a CSV into the Data Analyst (your bank statement, fitness data, anything)
- [ ] Build ONE agent of your own — anything, even silly
- [ ] Show one friend or coworker what you learned

---

## Where to keep learning

- The repo you cloned today: `github.com/evolveML/claude-code-jumpstart`
- Anthropic's docs: [docs.claude.com/en/docs/claude-code](https://docs.claude.com/en/docs/claude-code)
- The official Claude Code GitHub: [github.com/anthropics/claude-code](https://github.com/anthropics/claude-code)

---

## When something breaks

90% of issues are one of:
1. `claude: command not found` → close + reopen terminal
2. Auth failed → `claude /logout` then `claude` again
3. Transcript download failed → use `notegpt.io` or the sample we provided
4. Something else → see `TROUBLESHOOTING.md` in the repo

---

**The bigger idea**: AI is just instructions written in plain English. You don't need to be a programmer to build with it. The 3 things you did today, you can repeat 50 times this year.

Built with care by [EvolveML](https://evolveml.io).
