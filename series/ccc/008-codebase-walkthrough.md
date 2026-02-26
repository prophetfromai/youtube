---
title: "Under the Hood — Reading the Go Codebase"
series: ccc
episode: 8
status: idea
youtube_url: ""
duration_target: "12-15 min"
---

## Key Points

- File-by-file walkthrough of the CCC Go codebase
- How to build from source and contribute
- Key design decisions and patterns
- Where to add your own features

## Hook

"CCC is ~3000 lines of Go. Let's read every file and understand exactly how it works."

## Outline

### The Source Map (0:00 - 2:00)
- main.go — CLI entry point, type definitions
- commands.go — the listen loop, setup wizard, all Telegram command handlers
- telegram.go — Telegram API wrappers
- hooks.go — Claude Code hook handlers, transcript parsing
- session.go — session lifecycle
- tmux.go — tmux abstraction
- config.go — config loading/saving
- otp.go — TOTP implementation
- relay.go — file relay server
- service.go — OS service installation
- whisper.go — voice transcription

### Key Design Decisions (2:00 - 5:00)
- Why Go? Single binary, easy cross-compilation, good concurrency
- Why tmux? Claude Code needs an interactive terminal
- Why file-based IPC for OTP? Hook processes are short-lived, can't hold connections
- Why JSONL transcript parsing? Claude Code's native format, no alternative

### The Listen Loop (5:00 - 7:00)
- Walk through the actual polling code
- Message routing: how updates map to handlers
- Offset tracking: Telegram's cursor-based pagination

### Hook Implementation (7:00 - 9:00)
- How hooks plug into ~/.claude/settings.json
- PreToolUse: the permission flow
- Stop: transcript extraction and response forwarding
- The deduplication logic for streaming entries

### Building and Contributing (9:00 - 11:00)
- `go build` / `make install`
- Build tags (voice support)
- Adding a new Telegram command
- Adding a new hook type
- Where to file issues / PRs

### Wrap-Up (11:00 - 12:00)
- What we built across the series
- The core insight: outbound polling = safe remote control
- Where to go from here

## Notes

- This is for developers who want to understand or contribute
- Use VS Code / editor view to walk through files
- Highlight the clever parts: transcript parsing, Telegram-active flag, OTP IPC

## Description

## Tags

claude code, ccc, go, golang, open source, code review, codebase walkthrough, contributing
