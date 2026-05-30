# Flow: handoff

Run at session end.

Steps:
1. Append a session entry to `.ledger/log/sessions.md` using the session-log entry format (date DD.Month.YYYY, what changed, shards updated, safe-to-close, next kickoff pointer).
2. Update only the shards that changed this session. Edit in place; do not rewrite unrelated shards. Bump each touched shard's `last_updated`. Create a new shard only for genuinely new territory (use `schema/shard.template.md`), and add its line to INDEX.md.
3. Update `.ledger/ROADMAP.md`: increment cumulative sessions, update status, launch-readiness %, ETA, and the "Next up" list.
4. Invoke `prompts/kickoff-generator.md` to produce a pre-filled, copy-pasteable next-session kickoff prompt.
5. Report "safe to close?" with a yes/no and print the kickoff prompt.

Touch the minimum set of files. The index changes only when a shard is added or removed.
