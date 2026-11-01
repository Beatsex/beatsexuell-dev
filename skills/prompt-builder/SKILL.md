---
name: prompt-builder
description: Turns a rough idea into a descriptive Claude Code prompt and picks the right permission mode. Use when the user gives a vague request for a feature, says "write me a prompt", "how do I ask Claude Code…", "schreib mir einen Prompt", "wie formuliere ich das".
---

# Prompt Builder

## Build the prompt
A good prompt states:
1. **Goal:** what should exist afterwards
2. **Where:** files, modules, plugin part (DSP, UI, presets)
3. **Constraints:** what must not change, existing style or theme to match
4. **Done when:** the DAW test or check that proves it works
5. **Open questions:** invite Claude to ask instead of guessing

## Pick the mode (Shift+Tab)
- **Plan Mode:** multi-step features, unclear approach, safe code review. Default for anything non-trivial.
- **Manual:** sensitive areas (audio thread, file handling), when you want to approve every step.
- **Auto-accept:** small, well-understood edits.
- **Auto:** longer runs with background safety check.

## Output
- The finished prompt in a code block, ready to paste
- Recommended mode in one line

Source: Claude Academy, Claude Code 101, "Your first prompt".
