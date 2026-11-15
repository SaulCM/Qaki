# Implement Feature — Execution Adapter

## Purpose

Adapter for feature-implementation tasks. It binds the always-loaded agent rules and delegates the procedure to the authoritative studio workflow.

This adapter is not an implementation procedure and must not be used as one.

## Authoritative Procedure

`docs/07_agent_workflows/IMPLEMENT_FEATURE.md`

Read that workflow in full and follow it. It is the single source of procedural truth for feature implementation.

This adapter defines no procedure of its own. Where this adapter and the studio workflow differ, the studio workflow governs: report the difference and correct the adapter instead of following it.

If the authoritative workflow cannot be located or read, stop and report it. Do not substitute an improvised procedure.

## Binding Agent Rules

- `.cline/rules/project-context.md` — repository roots, authority order, greenfield authorship rules, engineering boundaries.
- `.cline/rules/architecture-rules.md` — architectural constraints on the implementation.
- `.cline/rules/gdscript-standards.md` — coding requirements.
- `.cline/rules/asset-rules.md` — asset, scene, and resource handling.
- `.cline/rules/git-workflow.md` — branch, commit, and repository-safety requirements.
- `.cline/rules/documentation-management.md` — documentation duties.

## Execution Notes

- Branch preparation, pull-request target, and integration requirements come from `docs/00_studio_standards/BRANCHING_STRATEGY.md`, `docs/00_studio_standards/GIT_CONVENTIONS.md`, and `.cline/rules/git-workflow.md`. This adapter does not define them.
- Requirements that are missing or not yet approved are handled under `.cline/rules/project-context.md`, section 5.1. Do not invent design decisions to fill the gap.
- Routing: isolated defects belong to `.clinerules/workflows/fix-bug.md`; design-only work belongs to `.clinerules/workflows/create-technical-design.md`; an independent review belongs to `.clinerules/workflows/code-review.md`.