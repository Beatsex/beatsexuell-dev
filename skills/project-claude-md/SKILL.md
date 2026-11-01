---
name: project-claude-md
description: Creates a CLAUDE.md at the start of every new project that carries the full project context, and maintains it while working. Use when a new project starts, a repo without CLAUDE.md is opened, or the user says "new project", "set up project", "create CLAUDE.md", "capture context", "neues Projekt", "CLAUDE.md anlegen", "Projekt aufsetzen", "Kontext festhalten".
---

# Project CLAUDE.md

## When
- New project or repo without a CLAUDE.md
- The user corrects Claude a second time on the same thing → add the rule to CLAUDE.md

## Steps
1. **Check:** Is there already a CLAUDE.md in the project root? If so, read it and extend it instead of overwriting.
2. **Ask briefly** (only what can't be read from the code): project goal, stack, target platform.
3. **Write the scaffold** (template below). If code already exists, run `/init` first, then refine.
4. **Keep it small:** only what Claude would otherwise get wrong. Link longer docs with `@path` instead of copying them in.
5. **Maintain it:** add recurring corrections as rules under "Conventions".

## Template

```markdown
# Project
<One sentence: what it is, who it's for, the goal>

# Stack
- <Language/framework/tools>

# Commands
- Build: `…`
- Test: `…`
- Run: `…`

# Conventions
- <Code style, folder structure, naming rules>

# Status & open items
- <What's done, what's next>

# References
- @README.md
```

## Don't
- No essays: anything Claude can read from the code itself doesn't belong here.
- No personal preferences that apply to all projects. Those go in the user-level CLAUDE.md (~/.claude/CLAUDE.md).
