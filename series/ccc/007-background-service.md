---
title: "Always On — Running CCC as a Background Service"
series: ccc
episode: 7
status: idea
youtube_url: ""
duration_target: "6-8 min"
---

## Key Points

- launchd on macOS, systemd on Linux — automatic startup
- The lock file — only one listener runs at a time
- Self-update via /update command in Telegram
- Monitoring and troubleshooting the service

## Hook

"CCC should be running before you even think about using it. Here's how to make it permanent."

## Outline

### Why a Service? (0:00 - 1:00)
- Without it: you have to manually run `ccc listen` every time
- With it: CCC starts on boot, restarts on crash, always polling

### macOS: launchd (1:00 - 3:00)
- Setup wizard creates ~/Library/LaunchAgents/com.ccc.plist
- `launchctl load/unload` — start/stop the service
- Logs and stdout/stderr paths
- Show the plist file

### Linux: systemd (3:00 - 4:30)
- ~/.config/systemd/user/ccc.service
- `systemctl --user enable/start/status ccc`
- Journalctl for logs

### Self-Update (4:30 - 6:00)
- `/update` in Telegram — downloads latest binary from GitHub releases
- Validates, backs up old binary, replaces, codesigns on macOS
- Service manager restarts it automatically
- Demo: run /update, watch the version change

### Troubleshooting (6:00 - 7:00)
- `ccc doctor` — checks everything
- Lock file issues (~/.ccc.lock)
- Common problems: stale tmux sessions, hook misconfiguration

### What's Next (7:00 - 7:30)
- Next: reading the Go codebase — for those who want to hack on it

## Notes

- Keep this practical — show real terminal output
- macOS focus for the demo, mention Linux equivalents

## Description

## Tags

claude code, ccc, launchd, systemd, background service, devops, automation, self-update
