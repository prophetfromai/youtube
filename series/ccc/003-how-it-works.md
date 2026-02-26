---
title: "How It Actually Works — Polling, Hooks & tmux"
series: ccc
episode: 3
status: idea
youtube_url: ""
duration_target: "10-12 min"
---

## Key Points

- The polling loop: outbound HTTPS long-poll to Telegram's getUpdates API
- The tmux layer: each Claude session runs in a named tmux session, prompts sent via send-keys
- Claude Code hooks: PreToolUse (permissions) and Stop (response forwarding)
- Transcript parsing: the Stop hook reads Claude's JSONL transcript and extracts the response

## Hook

"Your phone talks to Telegram. Telegram talks to your machine. But how does the message actually reach Claude Code? Let's trace the full path."

## Outline

### The Full Loop (0:00 - 1:30)
- Diagram: Phone → Telegram API → CCC (polling) → tmux → Claude Code → Stop hook → Telegram API → Phone
- Every arrow is outbound from your machine. That's the whole security story.

### Polling Deep Dive (1:30 - 4:00)
- `getUpdates` with 30s long-poll timeout
- HTTP client has 35s timeout (5s buffer)
- Empty response = no messages, loop again
- Message arrives = process immediately, update offset
- Show the actual Go code (commands.go listen function)

### The tmux Layer (4:00 - 6:00)
- Why tmux? Claude Code is interactive — needs a terminal
- `tmux send-keys` types the prompt into the pane
- `waitForClaude` — watches for Claude's ready indicator before sending Enter
- Session naming: `claude-<project>` — maps to Telegram topics

### Claude Code Hooks (6:00 - 9:00)
- PreToolUse hook: intercepts permission requests
  - Auto-approve mode: returns allow JSON
  - OTP mode: sends Telegram message, waits for TOTP code
- Stop hook: fires when Claude finishes responding
  - Reads the JSONL transcript file
  - Extracts last assistant turn's text blocks
  - Sends to the matching Telegram topic
- How hooks are installed in ~/.claude/settings.json

### The Telegram Active Flag (9:00 - 10:00)
- `/tmp/ccc-telegram-active-<session>` — how CCC knows if a prompt came from Telegram or local terminal
- Permission hook checks this flag to decide behavior
- Clean separation between remote and local sessions

### What's Next (10:00 - 10:30)
- Next episode: using this as a daily driver — real workflow from your phone

## Notes

- Use diagrams/animations to show the message flow
- Show actual code snippets from the Go source
- This is the "nerd episode" — go deep, assume the audience wants to understand

## Description

## Tags

claude code, ccc, architecture, polling, telegram api, tmux, hooks, developer tools, go programming
