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

`monologue.md` is this repo's rolling log of what people are thinking, asking about, and working on — captured in very few words. It gives any Claude session a sense of recent context before jumping in.

**Reading:** Scan `monologue.md` at the start of strategic or directional conversations.

**Writing:** When someone raises an idea, changes direction, or expresses intent — append a one-liner to the top of the Log section:
```
- [YYYY-MM-DD] Name: the gist in very few words — theme/feature
```

**Compaction:** The Log holds max ~20 entries. When full, distill the oldest entries into the Themes section (a few words each, merge with existing themes), then remove them from the Log. This keeps the file bounded forever.

Only capture signal: ideas, shifts in direction, decisions. Skip routine implementation chatter.

For the portfolio-level monologue (cross-product ideas and themes), see `/Users/qualitydrivensoftwareltd/git/director/monologue.md`.
