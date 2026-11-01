---
name: context-hygiene
description: Keeps the Claude Code context window clean and focused. Use when switching topics, when a session gets long or slow, when Claude starts forgetting earlier details, or the user says "new topic", "clean up", "compact", "neues Thema", "aufräumen", "Kontext voll".
---

# Context Hygiene

## Rules
- **New, unrelated task** → suggest `/clear`. First save anything worth keeping to CLAUDE.md.
- **Long session, same task** → suggest `/compact` with a focus hint, e.g. `/compact keep the DSP filter decisions and open bugs`.
- **Unsure how full it is** → run `/context`.
- **Large research or reading tasks** → delegate to a subagent instead of loading everything into the main context.

## Before /clear or /compact
1. Summarize decisions, open issues and next steps in 3–5 lines.
2. Add durable facts to CLAUDE.md ("Status & open items").
3. Then run the command.

## Signs it's time
- Claude repeats questions or contradicts earlier decisions
- Responses get slow or vague
- The task has changed completely
