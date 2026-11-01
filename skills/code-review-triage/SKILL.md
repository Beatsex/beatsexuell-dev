---
name: code-review-triage
description: Reviews Claude's changes before they are kept: read the real diff, get a clean-context second opinion, sort every finding into fix now / ask why / leave it. Use after Claude finished a coding task, before a commit, or when the user says "review", "check the changes", "what did you change", "prüf die Änderungen", "was hast du geändert".
---

# Code Review Triage

## 1. Read the actual diff
- Use `/diff` (requires git). Don't trust the summary alone.
- Flag in particular:
  - Changes the user didn't ask for (config values, rewritten helpers)
  - Tests that were skipped, deleted or loosened
  - New dependencies and hard-coded values (URLs, keys, magic numbers, sample rates, buffer sizes)
- Whole change wrong → `/rewind`, choose "Restore code and conversation". Note: changes from shell commands (e.g. package installs) are not rolled back.

## 2. Second opinion from a clean context
- Run `/code-review` (`low` = fewer false alarms, `high` = wider net). It reports only and edits nothing.
- Worth it for: changes too big to hold in your head, sensitive or destructive changes (audio thread, file I/O, presets), anything before release.

## 3. Sort each finding
| Pile | Meaning | Action |
|---|---|---|
| Fix now | Real and important | Fix, then run the build/tests and show the output |
| Ask why | Can't verify or seems off | Quote the finding back and ask Claude to check again |
| Leave it | Real but minor | Collect for a later cleanup session |

## 4. Close the loop
- Same finding keeps coming back → turn it into a CLAUDE.md rule (correction-to-rule).
- A fix that grew large → review again.
- Then: DAW test, then commit.

Source: Claude Academy, Claude Code 101, "Code review".
