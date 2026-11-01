---
name: correction-to-rule
description: Turns repeated corrections into permanent rules in CLAUDE.md. Use when the user corrects Claude on something already corrected before, or says "always…", "never…", "remember this", "save as rule", "immer…", "nie…", "merk dir das", "als Regel speichern".
---

# Correction → Rule

## When
- The user corrects the same thing a second time
- The user states a general rule ("always use…", "never…")
- A code review flags the same issue repeatedly

## Steps
1. Phrase the correction as a short, positive rule: what to do, not just what not to do.
2. Decide where it belongs:
   - Applies only to this project → project CLAUDE.md, section "Conventions"
   - Applies to all projects → user-level ~/.claude/CLAUDE.md
   - Must happen every time without exception → suggest a hook instead (see hook-setup)
3. Show the rule and target file, wait for OK, then add it.
4. Check for duplicates or contradictions with existing rules; merge instead of appending.

## Don't
- Write rules for one-off decisions that only concern the current task.
- Let CLAUDE.md grow unchecked; condense when it gets long.
