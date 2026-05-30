# Flow: orient

Run at session start.

Steps:
1. Load `.ledger/INDEX.md` and `.ledger/ROADMAP.md`.
2. Determine today's task: from the user, from cadence, or from ROADMAP "Next up".
3. Run `flow/shard-selection.md` with that task to pick relevant shards, and load them.
4. Gather recent git changes: `git log --oneline -10` and `git status --short` if the project is a git repo.
5. Invoke `prompts/you-are-here.md` to produce a "you are here" summary plus a launch-readiness line from ROADMAP.
6. Present the summary. Do not modify any ledger file during orient (read-only).
