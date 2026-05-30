# Prompt: kickoff-generator

Input: this session's changes, updated ROADMAP, the next task.
Produce a copy-pasteable kickoff prompt for the next session that minimizes token and exploration cost:
- Name the project and where the ledger lives (.ledger/).
- State the next task in one line.
- List the exact shards to load for it.
- Note any blocker or open decision.
Output as a single fenced block the user can copy. No emojis, no em dashes.
