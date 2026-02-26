---
title: "Voice, Images & File Transfer — The Extras"
series: ccc
episode: 6
status: idea
youtube_url: ""
duration_target: "8-10 min"
---

## Key Points

- Voice messages: speak a prompt, auto-transcribed via Whisper/Groq/OpenAI
- Image support: send images to Claude for analysis
- File transfer: `ccc send` to get files from your machine to your phone
- Remote shell: `/c <cmd>` for quick commands without a Claude session

## Hook

"You can talk to Claude Code. Literally. Send a voice note, and it becomes a prompt."

## Outline

### Voice Messages (0:00 - 3:00)
- Send a voice note in Telegram → CCC transcribes it → sends as text to Claude
- Transcription options: built-in whisper.cpp, Groq API, OpenAI API
- Build tags: `voice` tag for built-in, stub fallback for external
- Demo: dictate a coding task from your phone

### Image Support (3:00 - 5:00)
- Send an image in Telegram → forwarded to Claude for analysis
- Use cases: screenshot of an error, photo of a whiteboard, UI mockup
- Demo: send a screenshot, get Claude's analysis

### File Transfer (5:00 - 7:00)
- `ccc send <file>` — sends a file from your machine to Telegram
- Files under 50MB: direct Telegram upload
- Files over 50MB: streaming relay server (self-hostable)
- Use case: grab a build artifact, log file, or export without SSH

### Remote Shell (7:00 - 8:00)
- `/c <cmd>` — execute any shell command from Telegram
- 2-minute timeout, runs in a login shell
- Quick checks: git status, disk space, process list
- Caveat: no OTP on this — be aware

### What's Next (8:00 - 8:30)
- Next: running CCC as a persistent background service

## Notes

- Each feature gets a live demo
- Voice is the wow factor — lead with it in the hook

## Description

## Tags

claude code, ccc, voice messages, whisper, image analysis, file transfer, remote shell, telegram
