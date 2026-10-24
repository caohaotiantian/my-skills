# Project memory

## Read selector

| Reuse condition | Detail |
| --- | --- |
| A generic skill validator rejects three-loop frontmatter | [Validator compatibility](#validator-compatibility) |
| An authorized task updates existing local skill installations | [Installed copies](#installed-copies) |

## Validator compatibility

Observation date: 2026-10-19. Scope: validation of the existing three-loop skill package.
The generic skill validator rejected the existing `compatibility` key while the repository release gate passed.
Report those outcomes separately. Check current validator support before changing supported metadata.
Source: [.agent/record-continuity/evidence/checks.md](.agent/record-continuity/evidence/checks.md).
Invalidation: the validator accepts that key, or the package metadata contract changes.

## Installed copies

Observation date: 2026-10-24. Scope: authorized local installation updates for this collection.
Only `~/.agents/skills/orchestrate` and `~/.agents/skills/three-loop-workflow` exist in the inspected roots.
The matching paths under `~/.codex/skills` and `~/.claude/skills` are absent.
Inspect current targets rather than treating that inventory as permanent.
Keep verified backups outside skill discovery roots, under `~/.local/state/my-skills/backups/`.
Compare installed file sets and bytes with the selected source after synchronization.
Source: [.agent/release-context-writing/evidence/installation-inventory.json](.agent/release-context-writing/evidence/installation-inventory.json).
Invalidation: an installation inventory or explicit user choice changes the targets or backup policy.
