---
title: "Locking It Down — OTP Mode & Permission Control"
series: ccc
episode: 5
status: idea
youtube_url: ""
duration_target: "8-10 min"
---

## Key Points

- Auto-approve vs OTP mode — what each means
- Setting up TOTP (Google Authenticator / Authy)
- How OTP IPC works between the hook and listener
- The Telegram-active flag — local sessions stay unaffected
- Security considerations: what to be careful about

## Hook

"CCC gives Claude Code remote shell access from your phone. What stops someone else from using it?"

## Outline

### The Trust Model (0:00 - 2:00)
- Auto-approve: Claude gets full autonomy on remote sessions
- Your bot token + chat ID = the only auth layer
- If someone gets your bot token, they control Claude
- This might be fine for personal use — but OTP adds a real second factor

### Setting Up OTP (2:00 - 4:00)
- Choose OTP during setup (or switch later)
- QR code appears in terminal — scan with authenticator app
- TOTP secret saved to ~/.ccc.json (file permissions 0600)

### How OTP Works in Practice (4:00 - 6:00)
- Claude wants to use a tool → PreToolUse hook fires
- Hook checks the Telegram-active flag — is this a remote session?
- If remote: writes a request file to /tmp, sends a Telegram message asking for the code
- You enter the 6-digit code in Telegram
- Listener validates, writes response file, hook reads it
- Grant lasts 5 minutes — parallel tool calls don't each need a code

### What to Be Careful About (6:00 - 8:00)
- `/c <cmd>` runs arbitrary shell commands — no OTP check on this
- One-shot queries use `--dangerously-skip-permissions`
- The relay server for large files — deployable yourself if you don't trust the default
- Config file security — 0600 permissions, keep your bot token safe

### What's Next (8:00 - 8:30)
- Next: voice, images, and file transfer — the extra features

## Notes

- Show a real OTP flow on screen
- Don't be preachy about security — present the facts, let viewers decide their comfort level

## Description

## Tags

claude code, ccc, security, otp, totp, two-factor, permissions, telegram bot, developer tools
