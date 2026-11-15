# Architecture Decision Records

This directory holds the studio-wide Architecture Decision Record (ADR) process. It does not contain the architectural decisions of individual games.

## Documents

| Document | Purpose |
|---|---|
| `ADR_PROCESS.md` | The authoritative studio-wide ADR process: when an ADR is required, its structure, numbering, status lifecycle, review, approval, and maintenance. Read this before writing an ADR. |
| `docs/06_templates/ADR_TEMPLATE.md` | The template used to instantiate an ADR. |

## Where project decisions live

Game-specific ADRs MUST be stored under `game_project/docs/technical/adr/` and MUST NOT be stored in this directory (`ADR_PROCESS.md`, section 5.2). Each project ADR directory SHOULD contain a `README.md` index listing its ADRs (`ADR_PROCESS.md`, section 12).

## Adding an ADR

1. Confirm that the decision meets the criteria in `ADR_PROCESS.md`, section 4.
2. Copy `docs/06_templates/ADR_TEMPLATE.md` into the project ADR directory.
3. Follow the numbering, naming, and status rules in `ADR_PROCESS.md`, sections 6 and 7.
4. Set the new ADR to `Proposed` and request project owner approval.
5. Update the project ADR index.

This index does not restate the process. `ADR_PROCESS.md` governs.
