---
name: subagent-delegation
description: Decides when to hand work to a subagent to keep the main context clean, and defines the return format. Use for large codebase searches, reading long docs (e.g. RNBO, JUCE, VST SDK), research, or code review, or when the user says "research", "look through", "review", "recherchier", "durchsuch", "review mal".
---

# Subagent Delegation

## Delegate when
- Searching a large codebase for usages, patterns or causes
- Reading long documentation or specs
- Web research with many sources
- Code review before a commit (fresh eyes, no session bias)

## Keep in the main agent
- Decisions, planning and writing the actual code
- Anything that needs the conversation history

## Task for the subagent
- One clear question, the relevant paths or sources, what to ignore
- Read only, no file changes, unless explicitly part of the task

## Return format
- Answer in max. 10 lines
- Relevant files/lines as `path:line`
- Open questions or uncertainties at the end
