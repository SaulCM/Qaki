# Refactor Code — Execution Adapter

## Purpose

Adapter for behavior-preserving refactoring tasks. It binds the always-loaded agent rules and delegates the procedure to the authoritative studio workflow.

This adapter is not a refactoring procedure and must not be used as one.

## Authoritative Procedure

`docs/07_agent_workflows/REFACTOR_CODE.md`

Read that workflow in full and follow it. It is the single source of procedural truth for a refactor.

This adapter defines no procedure of its own. Where this adapter and the studio workflow differ, the studio workflow governs: report the difference and correct the adapter instead of following it.

If the authoritative workflow cannot be located or read, stop and report it. Do not substitute an improvised procedure.

## Binding Agent Rules

- `.cline/rules/project-context.md` — repository roots, authority order, engineering boundaries.
- `.cline/rules/architecture-rules.md` — architectural constraints the refactor must preserve.
- `.cline/rules/gdscript-standards.md` — coding requirements.
- `.cline/rules/asset-rules.md` — asset, scene, and resource handling when files move.
- `.cline/rules/git-workflow.md` — branch, commit, and repository-safety requirements.
- `.cline/rules/documentation-management.md` — documentation and inventory duties.

## Execution Notes

- Branch and integration requirements come from `docs/00_studio_standards/BRANCHING_STRATEGY.md`, `docs/00_studio_standards/GIT_CONVENTIONS.md`, and `.cline/rules/git-workflow.md`. This adapter does not define them.
- The baseline and behavior-preservation evidence required by the studio workflow (sections 6 and 7) are mandatory. Do not begin editing without them.
- Routing: a change that alters observable behavior belongs to `.clinerules/workflows/implement-feature.md` or `.clinerules/workflows/fix-bug.md`; a structural design decision belongs to `.clinerules/workflows/create-technical-design.md`; an independent review belongs to `.clinerules/workflows/code-review.md`.
