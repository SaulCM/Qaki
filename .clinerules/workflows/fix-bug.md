# Fix Bug — Execution Adapter

## Purpose

Adapter for defect-correction tasks. It binds the always-loaded agent rules and delegates the procedure to the authoritative studio workflow.

This adapter is not a bug-fix procedure and must not be used as one.

## Authoritative Procedure

`docs/07_agent_workflows/FIX_BUG.md`

Read that workflow in full and follow it. It is the single source of procedural truth for a bug fix.

This adapter defines no procedure of its own. Where this adapter and the studio workflow differ, the studio workflow governs: report the difference and correct the adapter instead of following it.

If the authoritative workflow cannot be located or read, stop and report it. Do not substitute an improvised procedure.

## Binding Agent Rules

- `.cline/rules/project-context.md` — repository roots, authority order, engineering boundaries.
- `.cline/rules/architecture-rules.md` — architectural constraints on the correction.
- `.cline/rules/gdscript-standards.md` — coding requirements for the correction.
- `.cline/rules/asset-rules.md` — asset, scene, and resource handling when the defect involves them.
- `.cline/rules/git-workflow.md` — branch, commit, and repository-safety requirements.
- `.cline/rules/documentation-management.md` — documentation duties when the fix changes documented behavior.

## Execution Notes

- Branch and integration requirements come from `docs/00_studio_standards/BRANCHING_STRATEGY.md`, `docs/00_studio_standards/GIT_CONVENTIONS.md`, and `.cline/rules/git-workflow.md`. This adapter does not define them.
- Report validation honestly. A fix is not complete merely because an error disappeared (`docs/00_studio_standards/DEFINITION_OF_DONE.md`, section 6.4).
- Preserve unrelated user changes in the working tree.
- Routing: new or changed functionality belongs to `.clinerules/workflows/implement-feature.md`; an independent review belongs to `.clinerules/workflows/code-review.md`.