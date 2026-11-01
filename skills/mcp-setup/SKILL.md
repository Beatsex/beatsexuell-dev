---
name: mcp-setup
description: Connects Claude Code to external tools and docs via MCP servers, picks the right scope, and keeps context costs low. Use when the user wants to connect a tool, needs current docs for a library (JUCE, RNBO, Web Audio), or says "connect", "MCP", "add server", "too many tools", "verbinde", "MCP-Server hinzufügen".
---

# MCP Setup

## 1. Check first
- Is there a CLI (e.g. `gh` for GitHub)? CLIs are more context-efficient than MCP; prefer them, optionally wrapped in a skill.
- Is there an official connector? See claude.com/connectors.

## 2. Add
- Remote service → HTTP server: `claude mcp add --transport http <name> <url>`
- Local process → stdio server: `claude mcp add <name> -- <command>`
- Useful for you: a docs server (e.g. Context7) for current JUCE/RNBO/library docs, GitHub, your task tool.

## 3. Pick the scope
| Scope | Applies to | Where |
|---|---|---|
| Local | this project, only you | default |
| User | all your projects | `--scope user` |
| Project | everyone on the repo | `.mcp.json`, committed |

## 4. Keep context lean
- Every connected server costs context, even unused.
- Check with `/mcp`, disable what you don't need right now.
- Pair an often-used server with a skill that explains how to use its tools well.

## Output
- The exact `claude mcp add` command, the chosen scope with one line why, and how to verify with `/mcp`.

Source: Claude Academy, Claude Code 101, "MCP".
