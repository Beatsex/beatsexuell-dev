---
name: subagent-builder
description: Creates custom Claude Code subagents as Markdown files with frontmatter, including a ready-made read-only DSP/audio code reviewer. Use when the user wants a specialized helper, "create a subagent", "build me a reviewer", "agent for X", "erstell einen Subagenten", "bau mir einen Reviewer".
---

# Subagent Builder

A subagent runs in its own context window with its own system prompt and returns only a summary. Its intermediate work is discarded, which keeps the main context clean.

## Steps
1. Clarify: job, when it should be called, which tools (read-only?), project or all projects.
2. Location: `.claude/agents/<name>.md` (this project) or `~/.claude/agents/<name>.md` (all projects).
3. Write the file: `name`, a `description` that says when to call it, `tools`, then the system prompt. Optional: `skills` to preload.
4. Restart Claude Code if the folder is new, then test with one real task.

## Built-ins first
- `Explore`: fast codebase search
- `Plan`: research in Plan Mode
- `general-purpose`: multi-step tasks
Only build your own when these don't fit.

## Template: DSP reviewer

```markdown
---
name: dsp-reviewer
description: Reviews audio/DSP code (JUCE, RNBO export, C++) for real-time safety and sound bugs. Use before committing audio changes or when the user asks for a DSP review.
tools: Read, Grep, Glob
---

You review audio plugin code. Read only, never edit.

Check:
- Audio thread: no allocation, locks, file/network I/O or logging in processBlock
- Denormals, NaN/Inf, clipping, DC offset
- Parameter smoothing (no zipper noise), thread-safe parameter access
- Sample rate and buffer size changes handled, nothing hard-coded
- Latency reporting, bypass, state save/recall

Return max. 10 findings as `path:line – problem – fix`, each tagged
fix now / ask why / leave it. End with what to listen for in the DAW test.
```

Source: Claude Academy, Claude Code 101, "Subagents".
