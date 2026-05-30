# Prompt: shard-split

Input: an existing handoff file or README.
Split it into concern-based shards (one concern per shard, kebab-case area name). For each:
- Write `.ledger/shards/<area>.md` from shard.template.md with the concern's content.
- Add a line to INDEX.md: `- [Title](shards/<area>.md) - hook`.
Do not duplicate content across shards. Prefer 5-12 focused shards over one large dump or dozens of tiny ones.
