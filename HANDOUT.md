---
title: "Workshop Takeaway"
permalink: /handout/
---

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

## How to build your own agents (the meta-skill)

The most powerful pattern in this kit. The recipe is always:

1. **Use Claude to do the thing once** (with a long prompt — see any scenario)
2. **Ask Claude**: "turn what we just did into a reusable agent at `~/.claude/agents/<name>.md`"
3. **Restart Claude** → use it forever as `@<name>` in any folder

You don't write code. Claude writes the agent for you, based on the conversation you just had.

Example agents you can build by talking:
- **learning-companion** — teach me anything
- **data-analyst** — find the story in any data
- **interview-coach** — prep me for any interview
- **email-writer, code-reviewer, meeting-prepper** — anything you do more than twice

To invoke any of them: in plain English, just say *"Hey [agent-name] — [what you want]"*. Works in VSCode or terminal. (Terminal users can also use `@agent-name` as a shortcut.)

[Full guide on the agents page]({{ "/agents/" | relative_url }})

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
4. Something else → [Troubleshooting]({{ "/troubleshooting/" | relative_url }})

---

**The bigger idea**: AI is just instructions written in plain English. You don't need to be a programmer to build with it. The 3 things you did today, you can repeat 50 times this year.

Built with care by [EvolveML](https://evolveml.io).

---

← [Back to home]({{ "/" | relative_url }}) · [Scenario 1: Learning Companion]({{ "/scenarios/01-learning-companion/" | relative_url }}) · [Scenario 2: Data → Dashboard]({{ "/scenarios/02-data-to-dashboard/" | relative_url }}) · [Scenario 3: Interview Prep]({{ "/scenarios/03-interview-prep/" | relative_url }}) · [Agents]({{ "/agents/" | relative_url }})
