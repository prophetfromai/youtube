# YouTube

@/Users/qualitydrivensoftwareltd/git/claude.md/CLAUDE.md

## What This Project Is

Content planning and scripts for the ProphetFromAI YouTube channel — developer-focused video series showing real builds, tools, and workflows.

## Summary

This repo is the single source of truth for all YouTube content. Each series lives in its own folder under `series/`, with one markdown file per episode containing the outline, script, key points, and metadata. The top-level `series.yaml` is the registry of all series and episodes — same pattern as `repos.yaml` in director.

**No product code lives here** — only content planning, scripts, and notes. Code for projects featured in videos lives in their own repos.

**First series:** Implementing [CCC (Claude Code Controller)](https://github.com/kidandcat/ccc) — a Telegram-based remote control for Claude Code that uses safe polling instead of exposing your machine to inbound connections.

## Structure

```
series.yaml              # registry of all series + episodes (source of truth)
templates/episode.md     # skeleton for new episodes
series/
  <series-name>/
    series.yaml           # series-level metadata
    001-<slug>.md         # one file per episode
```

## Workflow

**New series:** Create a folder under `series/`, add a `series.yaml` inside it, plan episodes as numbered markdown files, register everything in the top-level `series.yaml`.

**New episode:** Copy `templates/episode.md`, fill in the frontmatter and outline, add the entry to the top-level `series.yaml`.

**Episode statuses:** `idea` → `outlining` → `scripting` → `recorded` → `editing` → `published`

## Commands

```bash
# No build commands — this is a content repo
# Use grep/search to find episodes by status, topic, etc.
```

## Monologue

`monologue.md` is this repo's rolling log of ideas, direction, and intent. Scan it at the start of strategic conversations. See `topics/conventions/` in the central repo for the full protocol.
