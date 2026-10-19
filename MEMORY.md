# Project memory

Last reviewed: 2026-10-19.
Scope: this skill collection. Read this file at session entry.

## User preferences

- Date: 2026-10-19. Source: explicit user request in the record-continuity session.
  Maintain dedicated project memory after each completed task through review of the full available session.
  Preserve useful lessons, supported habits, and preferences for agents in later sessions.
  Reuse condition: tasks in this project. Current instructions take precedence.
- Date: 2026-10-19. Source: user-provided global AGENTS.md instructions.
  Use orchestrate for implementation and three-loop-workflow for non-trivial changes and pre-landing reviews.
  Use the smallest suitable execution structure. Delegation is not mandatory for every task.
  Reuse condition: implementation work under those defaults, subject to host restrictions.

## Project lessons

- Date: 2026-10-19. Source: README.md and inspected Git submodules.
  Each skill has a separate repository. Root Git diffs do not show complete submodule file changes.
  Reuse condition: inspect each changed submodule when reviewing skill edits.
- Date: 2026-10-19. Source: skills/three-loop-workflow/CLAUDE.md.
  Skill rule changes require Deep review. The existing release gate checks prose limits and package contents.
  Reuse condition: read current project instructions before changing shipped workflow rules.

- Date: 2026-10-19. Source: record-continuity validation and independent review.
  The generic skill validator rejects three-loop's existing compatibility key, although its repository release gate passes.
  Reuse condition: report these results separately. Do not remove supported metadata merely to satisfy a narrower validator.
- Date: 2026-10-19. Source: record-continuity independent review.
  Standalone memory guidance also needs concurrent-write reconciliation and an explicit unavailable-memory report.
  Reuse condition: review both standalone and coordinated paths when shared workflow rules change.

- Date: 2026-10-19. Source: archive-cleanup dependency scan and independent review.
  Current release checks consume test fixtures and measurement evidence. Historical figures read tagged trees.
  Reuse condition: inspect consumers before deleting documentation or tests. Retired checkout archives can remain in Git history.

- Date: 2026-10-19. Source: release-memory installation inventory and release workflows.
  Both skills have installed copies under ~/.agents/skills and ~/.claude/skills.
  Reuse condition: when the user requests local updates, inspect both locations and preserve backups before synchronization.
- Date: 2026-10-19. Source: the three-loop release workflow and this session's release checks.
  A pushed version tag triggers the three-loop release archive workflow. Version metadata must match that tag.
  Reuse condition: publish the skill commits before the parent repository's updated submodule references.

## Maintenance

The task owner maintains this file. During coordinated work, only the parent writes it.
Review the full available session after each completed task. Disclose missing context.
Keep sourced reusable lessons. Merge duplicates and remove obsolete guidance.
Do not store secrets, raw transcripts, unsupported habits, or temporary task status.
Before updates, reread this file and preserve other sessions' changes.
If no useful lesson exists, update the review date and record that outcome.
