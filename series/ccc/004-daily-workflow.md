---
title: "Daily Driver — Real Workflow from Your Phone"
series: ccc
episode: 4
status: idea
youtube_url: ""
duration_target: "8-10 min"
---

## Key Points

- Starting sessions from phone vs terminal
- Multi-session topics — one project per thread
- Handoff between phone and terminal
- One-shot queries for quick questions
- When to use remote vs local

## Hook

"I've been running CCC for a week. Here's what actually works — and what doesn't."

## Outline

### Starting Sessions (0:00 - 2:00)
- From terminal: `cd project && ccc`
- From phone: `/new myproject` in Telegram
- Both create a tmux session + Telegram topic

### Multi-Session Management (2:00 - 4:00)
- Each project gets its own Telegram topic (thread)
- Switch between projects by switching threads
- `/delete` to clean up finished sessions

### The Handoff (4:00 - 5:30)
- Start on phone, continue on terminal (or vice versa)
- tmux session persists — attach from anywhere
- Responses go to both Telegram and the terminal

### One-Shot Queries (5:30 - 7:00)
- Quick questions in private chat (no session needed)
- Uses `claude -p` under the hood
- Good for: "what does this error mean?", quick code snippets

### Practical Tips (7:00 - 8:30)
- What works well: fire-and-forget tasks, monitoring progress, quick approvals
- What doesn't: heavy back-and-forth (use a terminal for that)
- Battery/data: polling is lightweight, minimal impact

### What's Next (8:30 - 9:00)
- Next: security deep dive — OTP mode and permission control

## Notes

- This should feel like a real "day in the life" — show genuine usage, not staged demos
- Include at least one real task done entirely from phone

## Description

## Tags

claude code, ccc, workflow, remote coding, telegram, developer productivity, mobile coding
