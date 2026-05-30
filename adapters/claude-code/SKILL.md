---
name: ledger
description: Use to set up and run a project's sharded handoff memory. Invoke "ledger init" to create the library, "ledger orient" at session start to load only relevant context, and "ledger handoff" at session end to update shards and produce a next-session kickoff prompt. Use whenever starting or ending a working session on a project, when a single handoff file has grown too large, or when a subagent or council role needs only its relevant shards injected rather than the whole project.
---

# ledger

A sharded project memory: a thin always-loaded index plus one-concern-per-file shards, so each session and each subagent loads only what it needs.

## Commands

- `init` - run `core/flow/init.md`
- `orient` - run `core/flow/orient.md`
- `handoff` - run `core/flow/handoff.md`

Shard selection (used by orient and by external callers like council) is defined in `core/flow/shard-selection.md`.

## Rules

- The index is the only file loaded by default; shard bodies load only when selected.
- Never overwrite an existing `.ledger/` on init.
- handoff touches the minimum set of files and always updates the roadmap and session log.
- Dates use DD.Month.YYYY. No emojis, no em dashes.
- Path base: paths in this file are relative to the repo root (so `core/flow/init.md`). Paths inside `core/flow/*.md` and `core/prompts/*.md` are relative to `core/` (so `schema/shard.template.md` means `core/schema/shard.template.md`, and `prompts/shard-split.md` means `core/prompts/shard-split.md`).

Read the relevant `core/flow/*.md` and `core/prompts/*.md` and follow them exactly.
