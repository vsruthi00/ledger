# Flow: shard-selection

Given a task description, choose which shards to load. Used by orient and by council when feeding subagents.

Steps:
1. Load `.ledger/INDEX.md` only (never load all shards by default).
2. Match the task description against each shard's hook (the text after the dash).
3. Select shards whose hook is relevant to the task. When unsure, prefer including a borderline shard over missing context, but cap at the smallest set that covers the task.
4. Return the selected shard paths. For council, return per-role selections (e.g., Security gets auth and data shards; Designer gets ui-flow shards).
5. If no shard matches, return none and note that the task may be new territory worth a fresh shard at handoff.

Token rule: the index is always loaded; shard bodies are loaded only when selected.
