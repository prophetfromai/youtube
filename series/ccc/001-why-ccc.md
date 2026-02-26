---
title: "Why CCC? Remote Claude Code Without the Risk"
series: ccc
episode: 1
status: outlining
youtube_url: ""
duration_target: "10-12 min"
---

## Key Points

- Claude Code is powerful but locked to your terminal — what if you're away from your desk?
- The obvious solution (expose a webhook/port) is a security nightmare for a tool that runs shell commands
- CCC solves this with outbound-only polling via the Telegram API — your machine is never reachable from the internet
- No ngrok, no port forwarding, no relay servers — just your machine talking to Telegram

## Hook

"What if you could send Claude Code a prompt from your phone — and it just worked? Without exposing your machine to the internet?"

## Outline

### The Problem (0:00 - 2:00)
- Claude Code runs locally, has full shell access, can read/write files
- You're on the bus, you have an idea, you want Claude to start working on it
- Or Claude is mid-task and asks a permission question — you need to respond
- Currently: you're stuck. You need your terminal.

### The Dangerous Solutions (2:00 - 4:00)
- **Webhooks / exposed ports** — your machine listens for inbound connections. A tool with shell access is now internet-reachable. Terrible idea.
- **ngrok / tunneling** — same problem with extra steps. Your local machine has a public URL.
- **Cloud relay servers** — your prompts and code go through someone else's server. Trust issues.
- **SSH** — works but clunky from a phone. No notifications, no async.

### Why Polling Wins (4:00 - 6:00)
- CCC makes outbound HTTPS requests to the Telegram API — asks "any new messages?"
- Your machine initiates all connections. No ports open. No public URL. Invisible from outside.
- Telegram handles message delivery, notifications, media — battle-tested infrastructure
- Your bot token + your chat ID = only you can send commands

### What CCC Actually Does (6:00 - 9:00)
- Live demo: send a prompt from phone, watch Claude work, get the response back
- Multi-session support — one Telegram topic per project
- Permission handling — approve tool use from your phone (with OTP if you want)
- Bonus features: voice messages, image analysis, file transfer, remote shell

### The Architecture in 60 Seconds (9:00 - 10:00)
- Phone → Telegram API → CCC polls → tmux send-keys → Claude Code → Stop hook → Telegram API → Phone
- All outbound. Your machine is a client, never a server.

### What's Next (10:00 - 10:30)
- Next episode: setting it up from scratch — Telegram bot, install, first session
- Subscribe if you want to control Claude from your phone without the risk

## Chapters

- 0:00 The problem with Claude Code
- 2:00 The dangerous solutions
- 4:00 Why polling wins
- 6:00 Live demo
- 9:00 Architecture in 60 seconds
- 10:00 What's next

## Notes

- Compare briefly with other remote Claude solutions if any exist at time of recording
- Keep the security argument concrete — show what "exposed port" actually means
- The demo should be punchy — phone on screen, terminal visible, message goes in, response comes back

## Description

Claude Code is incredibly powerful — but it's stuck on your terminal. What happens when you want to send it a prompt from your phone?

Most solutions (webhooks, ngrok, tunnels) expose your machine to the internet. For a tool with full shell access, that's a terrible idea.

CCC (Claude Code Controller) takes the opposite approach: it polls the Telegram API using outbound-only connections. Your machine is never reachable from the outside. No ports open, no public URLs, no relay servers.

In this video, we look at why this matters and how CCC works.

CCC repo: https://github.com/kidandcat/ccc

## Tags

claude code, claude code controller, ccc, telegram bot, remote coding, ai coding, claude ai, developer tools, security, polling vs webhooks
