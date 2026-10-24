# Project agent instructions

## Entry and selective reads

Read only the selector in [MEMORY.md](MEMORY.md#read-selector) at entry.
Read a selected detail section only when its reuse condition matches the current task.
Current instructions take precedence. Memory records context, not authorization.
Follow each skill repository's instructions when modifying its files.

For new work, do not scan `.agent/` or read previous task records.
For resumed work, read only the identified task's HANDOFF.md first.
Follow its next-action references as needed. A link alone does not require a read.
Read complete artifacts when required by checks or independent review.

## Record lifecycle and cleanup policy

Use `.agent/<task-id>/` for new task records. Keep existing canonical paths when reconciling a current task.
Apply orchestrate continuity rules for coordination and three-loop writing rules for standalone implementation.
Keep one authoritative location per fact. Admit only facts that change unfinished work or safe recovery.
Replace changed state instead of appending updates. Keep accepted work only while unfinished dependencies need it.

Close tasks only after acceptance and resolved or transferred obligations. Confirm that modifying commands stopped.
Unknown process state or an unassigned obligation prevents closure.
For closed tasks, keep STATE.md as a result and evidence receipt.
Keep existing TODO.md and HANDOFF.md paths as empty-queue and closed markers, without automatic read instructions.
Remove closed tasks from active selectors. Do not maintain a closed-task index.
Retain plans and evidence in place for explicit historical questions. Do not create per-update archives.
Physical deletion of historical evidence requires a separate scope check. Leaving default context does not require deletion.

## Memory maintenance

After task completion, review available session information for qualifying memory changes, including removals.
A review need not change a file. Do not append review outcomes or update dates merely to record review.
Keep only sourced, reusable information absent from current instructions and maintained project documentation.
Give each entry reuse and invalidation conditions. Remove obsolete entries and their selector pointers.
Keep the selector limited to conditions and pointers. Do not include task history or lesson summaries there.

During coordinated work, only the parent writes shared memory. Executors return sourced candidates.
Before writing, reread affected entries and reconcile concurrent changes. Disclose relevant missing context.
Give new agents only applicable memory sections or accessible references, with the canonical path when needed.

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
