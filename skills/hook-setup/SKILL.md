---
name: hook-setup
description: Sets up Claude Code hooks for things that must happen every time without exception: auto-formatting, blocking dangerous commands, notifications. Use when the user says "always do X automatically", "block…", "never allow…", "notify me when done", "hook", "immer automatisch", "blockier…", "benachrichtige mich".
---

# Hook Setup

Rule of thumb: if something must happen every time without fail, it doesn't belong in a prompt or CLAUDE.md. It belongs in a hook.

## Events
- `PreToolUse`: before a tool call, can block it
- `PostToolUse`: after a tool call, e.g. formatting, logging
- `UserPromptSubmit`: when a prompt is submitted
- `Stop`: when Claude finishes responding
- `Notification`: when Claude sends a notification

## Steps
1. Clarify what should happen, on which event, for which tools (matcher, e.g. `Edit|Write` or `Bash`).
2. Write the script into the project (e.g. `.claude/hooks/`), reference it via `$CLAUDE_PROJECT_DIR`.
3. Add the hook to `.claude/settings.json` (project, can be committed) or the user settings (all projects).
4. Show the config, wait for OK, then write it.
5. Check with `/hooks` that it is listed, then test once.

## Blocking (PreToolUse)
- The hook gets tool name and input as JSON on stdin.
- Exit `0` = proceed, exit `2` = block (stderr goes back to Claude as the reason), other codes = non-blocking error.

## Useful starters
- Auto-format C++/JUCE with clang-format after `Edit|Write`
- Block `rm -rf`, force pushes, and commits to `main`
- Block writes to release/installer folders or sample libraries
- Desktop notification on `Stop`, so you can return to the DAW while Claude works

Source: Claude Academy, Claude Code 101, "Hooks".
