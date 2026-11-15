# Create Technical Design — Execution Adapter

## Purpose

Adapter for technical-design authoring. It binds the always-loaded agent rules and delegates the procedure to the authoritative studio workflow.

This adapter is not a design procedure and must not be used as one.

## Authoritative Procedure

`docs/07_agent_workflows/CREATE_TECHNICAL_DESIGN.md`

Read that workflow in full and follow it. It is the single source of procedural truth for a technical design.

This adapter defines no procedure of its own. Where this adapter and the studio workflow differ, the studio workflow governs: report the difference and correct the adapter instead of following it.

If the authoritative workflow cannot be located or read, stop and report it. Do not substitute an improvised procedure.

## Binding Agent Rules

- `.cline/rules/project-context.md` — repository roots, authority order, greenfield authorship rules, engineering boundaries.
- `.cline/rules/architecture-rules.md` — architectural constraints the design must respect.
- `.cline/rules/gdscript-standards.md` — implementation expectations the design must remain compatible with.
- `.cline/rules/asset-rules.md` — asset, scene, and resource handling when the design introduces them.
- `.cline/rules/documentation-management.md` — documentation duties for the produced document, including the inventory.

## Execution Notes

- The output document path, source template, and initial status are defined in section 3 of the studio workflow. Do not choose a different destination.
- This task authorizes a design document only. It does not authorize implementation; implementation may proceed only after the required approval (studio workflow, section 9).
- When the design raises an architecture decision, follow the ADR requirement in the studio workflow (section 6, Step 16) and the ADR process in `docs/02_technical_standards/adr/ADR_PROCESS.md`.
- Routing: implementing an approved design belongs to `.clinerules/workflows/implement-feature.md`.