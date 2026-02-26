---
title: "Setup from Scratch — Bot, Install, First Session"
series: ccc
episode: 2
status: idea
youtube_url: ""
duration_target: "12-15 min"
---

## Key Points

- Create a Telegram bot via BotFather
- Install CCC (clone + make install or download binary)
- Run the setup wizard — connects bot, picks permission mode, installs hooks
- Start your first remote Claude Code session and send a prompt from your phone

## Hook

"Let's go from zero to controlling Claude Code from your phone in under 15 minutes."

## Outline

### Prerequisites (0:00 - 1:00)
- Claude Code installed and working locally
- Telegram account
- Go 1.21+ (if building from source)
- tmux installed

### Create the Telegram Bot (1:00 - 3:00)
- Message @BotFather, /newbot
- Name it, get the token
- Optionally: create a Telegram group with Topics enabled for multi-session support

### Install CCC (3:00 - 5:00)
- Clone the repo, `make install`
- Or download pre-built binary from releases
- Verify with `ccc --version`

### The Setup Wizard (5:00 - 9:00)
- `ccc setup <BOT_TOKEN>`
- Choose permission mode: auto-approve vs OTP
- Send a message to the bot to link your chat ID
- Optionally link a group for topic-based sessions
- Hook installation into ~/.claude/settings.json
- Service installation (launchd on macOS, systemd on Linux)

### First Session (9:00 - 12:00)
- `cd ~/myproject && ccc` — creates a tmux session + Telegram topic
- Send a prompt from your phone
- Watch Claude respond in the terminal
- Response arrives back in Telegram
- `ccc doctor` — verify everything is healthy

### What's Next (12:00 - 12:30)
- Next episode: how it actually works under the hood — polling, hooks, tmux

## Chapters

- 0:00 What you need
- 1:00 Creating the Telegram bot
- 3:00 Installing CCC
- 5:00 The setup wizard
- 9:00 First remote session
- 12:00 What's next

## Notes

- Screen-record the entire process end to end
- Show both phone and terminal side by side where possible
- Call out any gotchas encountered during setup

## Description

## Tags

claude code, ccc, telegram bot, setup tutorial, developer tools, remote coding, claude ai
