# Code Review — Execution Adapter

## Purpose

Adapter for code review tasks. It selects the review scope, binds the always-loaded agent rules, and delegates the procedure to the authoritative studio workflow.

This adapter is not a review procedure and must not be used as one.

## Authoritative Procedure

`docs/07_agent_workflows/REVIEW_CODE.md`

Read that workflow in full and follow it. It is the single source of procedural truth for a code review.

This adapter defines no procedure of its own. Where this adapter and the studio workflow differ, the studio workflow governs: report the difference and correct the adapter instead of following it.

If the authoritative workflow cannot be located or read, stop and report it. Do not substitute an improvised procedure.

## Binding Agent Rules

- `.cline/rules/project-context.md` — repository roots, authority order, engineering boundaries.
- `.cline/rules/architecture-rules.md` — architectural review expectations.
- `.cline/rules/gdscript-standards.md` — GDScript review expectations.
- `.cline/rules/git-workflow.md` — read-only repository inspection; no state-changing Git operations.
- `.cline/rules/documentation-management.md` — documentation duties when the review affects documentation.

## Execution Notes

- This task is advisory and read-only. The agent MUST NOT approve, merge, or otherwise represent its own assessment as approval (`docs/07_agent_workflows/REVIEW_CODE.md`, section 16.1).
- Review only the scope the user requested. When the review target is ambiguous, ask instead of assuming the whole repository is in scope.
- Report findings. Change the reviewed code only on a separate, explicit request.
- Routing: defect correction belongs to `.clinerules/workflows/fix-bug.md`; new functionality belongs to `.clinerules/workflows/implement-feature.md`.