# Flow: init

Sets up `.ledger/` in the current project.

Steps:
1. Confirm the working directory is the project root. If a `.ledger/` already exists, stop and report it; do not overwrite.
2. Create `.ledger/`, `.ledger/shards/`, `.ledger/log/`.
3. Write `.ledger/INDEX.md` from `schema/index.template.md`.
4. Write `.ledger/ROADMAP.md` from `schema/roadmap.template.md`, filling project name and today's date.
5. Write `.ledger/log/sessions.md` from `schema/session-log.template.md`.
6. If the project has an existing handoff file or README worth seeding, invoke `prompts/shard-split.md` to split it into concern-based shards and add a line per shard to INDEX.md. Otherwise leave shards empty.
7. Report what was created and the next step (run orient).

Never overwrite an existing `.ledger/`. All file writes use the project's date format DD.Month.YYYY.
