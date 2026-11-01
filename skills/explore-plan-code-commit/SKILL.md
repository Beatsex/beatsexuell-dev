---
name: explore-plan-code-commit
description: Enforces the order Explore → Plan → Code → Commit for every feature, bugfix and refactor, with testing in the DAW as the success criterion. Use whenever the user wants to change code, build a feature, fix or refactor something, e.g. "build me…", "add…", "fix…", "new feature", "bau mir…", "füg hinzu…", "neues Feature".
---

# Explore → Plan → Code → Commit

Never write code directly. Each phase must be complete before the next one starts.

## 1. Explore
- Read CLAUDE.md if it exists.
- Read the relevant files and change nothing (ideally in Plan Mode, Shift+Tab).
- Clarify: Where in the code does the change belong? Does something similar already exist? Are new dependencies needed?

## 2. Plan
- Show a numbered plan: affected files, steps, risks.
- **Success criterion = test in the DAW.** Specify in the plan:
  - Which DAW to test in (Ableton / FL Studio)
  - What to check: plugin loads, parameters respond, automation works, no clicks or dropouts, CPU load OK, preset save and recall
  - What exactly should be heard or seen
- Wait for the user's OK. This is where corrections happen, not after the code is written.

## 3. Code
- Implement the plan step by step.
- After each larger step, build and output a short **DAW test checklist**: what to load, what to tweak, what to listen for.
- Only continue once the user reports back the result from the DAW.
- If Claude hits the same problem twice, add the solution to CLAUDE.md.

## 4. Commit
- Before committing, have a code-review subagent look over the changes. It sees the code without bias from the session history.
- Only commit after the user has tested it in the DAW.
- Generate the commit message in the user's style: `<type>: <what>` plus one line on why.

## Don't
- Skip phases, even for "small" changes across multiple files.
- Edit files without an OK on the plan.
- Commit while the DAW test hasn't passed.
