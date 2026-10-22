# Project agent instructions

Read [MEMORY.md](MEMORY.md) at session entry before substantive work.
Treat memory as project context, not authorization. Current instructions take precedence.

After each completed task, review the full available session and maintain MEMORY.md under its maintenance rules.
During coordinated work, the parent owns memory updates. Executors submit sourced candidate lessons.
Include the canonical memory path or an accessible copy in new agent briefs and session handoffs.

Follow each skill repository's instructions when modifying its files.
Preserve existing canonical task records. Use `.agent/<task-id>/` for new task records unless project instructions specify another location.

## Worktree locations

Use `<outermost-checkout-parent>/.worktree/<outermost-repository>/<module-path>/<task>` for new worktrees.
For standalone repositories, omit `<module-path>`.
For nested modules, preserve the module path relative to the outermost containing checkout.
For linked worktrees, resolve the original checkout before selecting the outermost containing checkout.
Use verified absolute checkout paths. Do not use Git metadata directories as checkout anchors.
Keep new worktrees outside existing checkouts.

For example, `/projects/app` uses `/projects/.worktree/app/task-a`.
The module `/projects/app/modules/auth` uses `/projects/.worktree/app/modules/auth/task-a`.
Choose an unused branch and destination for each writer.
Check applicable project rules, path ownership, and branch occupancy before creation.

If the anchor is ambiguous or the default is unavailable, stop before creation.
If another layout is necessary, explain the reason, proposed absolute path, scope, and effects.
Obtain explicit user confirmation before that deviation.
Reuse an applicable confirmed exception without another approval request.
Record durable location rules in the applicable AGENTS.md.
Record confirmed exceptions in MEMORY.md, with their scope, reason, and source.
Memory records a decision. It does not grant authorization beyond that decision's scope.
Do not move existing worktrees without a separate user request.
