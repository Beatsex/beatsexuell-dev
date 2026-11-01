# beatsexuell-dev

Claude Code plugin for building audio plugins and music apps, based on the Claude Academy course Claude Code 101.

## Skills
| Skill | What it does |
|---|---|
| project-claude-md | Creates and maintains a CLAUDE.md per project |
| explore-plan-code-commit | Explore → Plan → Code → Commit, DAW test as success criterion |
| prompt-builder | Turns rough ideas into precise prompts, picks the mode |
| code-review-triage | /diff, /code-review, sort findings into fix / ask / leave |
| correction-to-rule | Turns repeated corrections into CLAUDE.md rules |
| context-hygiene | /clear, /compact, /context at the right time |
| subagent-delegation | When and how to hand work to subagents |
| subagent-builder | Creates custom subagents |
| hook-setup | Hooks for formatting, blocking, notifications |
| mcp-setup | Connect MCP servers with the right scope |
| skill-check | Reviews skills for triggering and structure |

## Agent
- dsp-reviewer: read-only review of audio/DSP code for real-time safety

## Install
Push this folder to a GitHub repo, then in Claude Code:
```
/plugin marketplace add <github-user>/beatsexuell-dev
/plugin install beatsexuell-dev@beatsexuell
```
Local test: `claude --plugin-dir ./beatsexuell-dev`
