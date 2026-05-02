---
title: "Agents — Build Your Own (and reference ours)"
permalink: /agents/
---

# Agents — Build Your Own

The most important idea in this whole kit: **you don't download agents — you have Claude build them for you.**

Once you've used Claude with a long prompt and it worked well, you ask Claude to turn that prompt into a permanent agent. No code, no curl, no copying our files. Claude writes the agent based on what just worked between the two of you.

---

## What is an agent?

An agent is just a `.md` file in `~/.claude/agents/` that tells Claude how to behave when you call it.

It has two parts:
1. **Frontmatter** — a few lines at the top: `name`, `description` (when to use it)
2. **System prompt** — the instructions for how it should behave

That's it. No servers, no deployment, nothing to compile. **It's text.**

---

## The recipe (works for any workflow)

```
1. Get Claude to do the thing once (with a long prompt — see any of the scenarios)
2. Ask Claude: "make this into a reusable agent at ~/.claude/agents/<name>.md"
3. Restart Claude → invoke as @<name> forever
```

That's the meta-skill. Apply it to anything in your life:

| Something you do repeatedly | Build the agent |
|---|---|
| Write a great cover letter | `@cover-letter-writer` |
| Review code or PRs | `@code-reviewer` |
| Prep for board / leadership meetings | `@meeting-prepper` |
| Triage your inbox | `@email-triager` |
| Plan a trip | `@trip-planner` |
| Research a company before a sales call | `@account-researcher` |
| Write LinkedIn posts in your voice | `@post-drafter` |
| Summarize long reads | `@reading-summarizer` |

You don't need to be a programmer. You need to know what "good" looks like — and let Claude do the encoding.

---

## How to ask Claude to build an agent

After you've successfully used Claude on a task, paste something like this:

```
Turn what we just did into a reusable Claude Code agent.

Write the agent definition to ~/.claude/agents/<NAME>.md with:
- YAML frontmatter with `name: <name>` and a clear `description` of when to invoke it
- A system prompt that captures how you handled my request — the steps you took, the tone you used, any rules about what to do or refuse
- Use the standard Claude Code agent format

Read the file back to me when you're done.
```

Replace `<NAME>` with whatever you want to call it (kebab-case, e.g., `email-writer`).

Claude will:
1. Reflect on the conversation we just had
2. Distill it into a system prompt
3. Write the file
4. Show you what it wrote

**Restart Claude Code** (`/exit`, then `claude`) and the agent is live. Use it as `@<name>` in any folder, anywhere.

---

## How to use an agent (once you have one)

In any folder, after starting `claude`:

```
@learning-companion teach me about ETF investing
@data-analyst what's the story in this folder?
@interview-coach prep me — my files are here
```

The `@` triggers the agent. Claude loads the agent's instructions and behaves accordingly. The agent persists across sessions and folders — once installed, it's available everywhere.

---

## Polished reference agents (to compare your build against)

After Claude writes an agent for you, you might want to see how a more polished version looks. Here are three reference agents we built. **Don't install these blindly** — use them to compare with what Claude built for you, borrow ideas, and edit yours.

| Agent | View / read it |
|---|---|
| `@learning-companion` | [agents/learning-companion.md](https://github.com/evolveML/claude-code-jumpstart/blob/main/agents/learning-companion.md) |
| `@data-analyst` | [agents/data-analyst.md](https://github.com/evolveML/claude-code-jumpstart/blob/main/agents/data-analyst.md) |
| `@interview-coach` | [agents/interview-coach.md](https://github.com/evolveML/claude-code-jumpstart/blob/main/agents/interview-coach.md) |

If you want to skip building your own and just install one of these as a starting point, you can — open the file on GitHub, click "Raw," copy the contents, and save it to `~/.claude/agents/<name>.md` on your machine. (Or use `curl` if you're terminal-comfortable — see the bottom of this page.)

But the **better** path: have Claude write yours first. Then read ours. You'll learn more about how the file works, and yours will be more attuned to your specific style.

---

## Tips for editing an agent file

You'll iterate. The first agent Claude writes you is rarely perfect. Open `~/.claude/agents/<name>.md` in VSCode and:

- **One agent, one job.** Don't bolt new tasks onto an existing agent — build a new one.
- **Description matters.** Claude reads it to decide *whether to invoke* the agent. Be specific. "Use when..." beats "for general use."
- **Iterate based on usage.** Use the agent for a week. Notice what's annoying. Edit the prompt. Test again.
- **Be explicit about tone.** Agents inherit Claude's default behaviors unless you override them. If you want it terse, say "be terse." If you want it to push back, say "challenge me before agreeing."
- **Share with friends.** Agent files are just `.md` — email them, paste them in Slack, post them in a gist. People can drop them in their own `~/.claude/agents/` folder.

---

## If you really want to install ours via the command line

For folks comfortable with terminal — these one-liners install our reference agents directly:

```bash
mkdir -p ~/.claude/agents && curl -fsSL https://raw.githubusercontent.com/evolveML/claude-code-jumpstart/main/agents/learning-companion.md -o ~/.claude/agents/learning-companion.md
```

```bash
mkdir -p ~/.claude/agents && curl -fsSL https://raw.githubusercontent.com/evolveML/claude-code-jumpstart/main/agents/data-analyst.md -o ~/.claude/agents/data-analyst.md
```

```bash
mkdir -p ~/.claude/agents && curl -fsSL https://raw.githubusercontent.com/evolveML/claude-code-jumpstart/main/agents/interview-coach.md -o ~/.claude/agents/interview-coach.md
```

Restart Claude. They're live.

---

## Where to learn more

- Anthropic's [official agent docs](https://docs.claude.com/en/docs/claude-code/agents.md)
- The [Claude Code GitHub](https://github.com/anthropics/claude-code) for more examples

---

← [Back to Claude Code Jumpstart home]({{ "/" | relative_url }}) · [Scenario 1]({{ "/scenarios/01-learning-companion/" | relative_url }}) · [Scenario 2]({{ "/scenarios/02-data-to-dashboard/" | relative_url }}) · [Scenario 3]({{ "/scenarios/03-interview-prep/" | relative_url }})
