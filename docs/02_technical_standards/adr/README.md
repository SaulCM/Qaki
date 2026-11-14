# Architecture Decision Records (ADR)

## 1. Purpose

This directory defines the studio-wide process for documenting significant technical and architectural decisions through Architecture Decision Records (ADRs).

ADRs provide a consistent way to record:

- Important architectural decisions.
- Technical alternatives considered.
- Reasons behind selected approaches.
- Consequences and trade-offs.
- Constraints affecting implementation.
- Historical context for future development.

The objective is to preserve architectural knowledge, reduce repeated discussions, and help developers and AI agents understand why a project is structured in a particular way.

This document establishes the ADR process. It is not a repository for individual game project decisions.

## 2. Scope

This process applies to significant technical decisions made during studio projects, including decisions involving:

- Software architecture.
- Feature boundaries and dependencies.
- Scene and node architecture.
- Data and persistence architecture.
- Resource management.
- Communication patterns.
- Third-party libraries and plugins.
- Engine capabilities and technical constraints.
- Performance architecture.
- Build and deployment infrastructure.
- Testing infrastructure.
- Security and reliability.
- Significant changes to established technical standards.

ADRs are intended for decisions with meaningful long-term consequences.

Routine implementation choices and small refactoring decisions generally do not require an ADR.

## 3. ADR Principles

### 3.1 Record Decisions, Not Every Implementation Detail

ADRs SHOULD document decisions that affect architecture, technical direction, or long-term maintainability.

They SHOULD NOT become a record of every minor coding choice.

### 3.2 Preserve Context

An ADR MUST explain why a decision was made, not merely describe the selected implementation.

Future developers should be able to understand the original problem, alternatives, constraints, and reasoning.

### 3.3 Document Trade-offs

Architectural decisions usually involve trade-offs.

ADRs SHOULD describe meaningful benefits, disadvantages, risks, and consequences.

### 3.4 Keep Decisions Discoverable

ADRs MUST use consistent numbering, naming, and organization.

Projects SHOULD maintain an index that makes relevant decisions easy to locate.

### 3.5 Decisions Are Project-Specific

Architectural decisions MUST be recorded in the repository of the project they affect.

A decision made for one game MUST NOT automatically be treated as a requirement for every other studio project.

### 3.6 Keep Records Historical

Once accepted, an ADR SHOULD remain unchanged as a historical record of the decision at the time it was made.

If the decision changes, create a new ADR that supersedes the previous one rather than silently rewriting its history.

## 4. When an ADR Is Required

An ADR MUST be created when a decision significantly affects one or more of the following:

- Overall system architecture.
- Feature boundaries or dependency direction.
- Data ownership or persistence design.
- Communication between major systems.
- Shared technical infrastructure.
- Core technology or engine integration.
- Significant third-party dependencies.
- Long-term maintainability.
- Performance constraints or architectural trade-offs.
- Security or reliability architecture.
- Established project-wide technical conventions.

An ADR SHOULD also be created when:

- Multiple reasonable approaches have meaningful trade-offs.
- A decision is difficult or expensive to reverse.
- A previous architectural decision must be changed.
- A recurring technical problem requires a standardized solution.
- A project-specific exception to a studio standard is justified.

### 4.1 Decisions That Usually Do Not Require an ADR

An ADR is generally unnecessary for:

- Routine bug fixes.
- Small implementation details.
- Local variable or function naming.
- Minor code refactoring.
- Routine scene composition.
- Standard feature configuration.
- Changes that do not affect architectural boundaries.
- Decisions already fully governed by an approved standard.

When uncertain, consider the decision's scope, reversibility, and long-term impact.

## 5. ADR Storage

### 5.1 Studio-Level Process

The studio-wide ADR process and template are maintained in:

```text
docs/
└── 02_technical_standards/
    └── adr/
        └── README.md
```

This directory defines how ADRs are managed. It does not contain the actual architectural decisions of individual games.

### 5.2 Project-Level ADRs

Each game repository MUST store its own ADRs.

Recommended structure, relative to the Godot project root (`game_project/`):

```text
game_project/
└── docs/
    └── technical/
        └── adr/
            ├── README.md
            ├── 0001-use-feature-oriented-architecture.md
            ├── 0002-use-godot-signals-for-event-notifications.md
            └── 0003-define-save-data-versioning-strategy.md
```

Project-level ADRs MUST be stored under `game_project/docs/technical/adr/`.

They MUST NOT be stored under repository-root `docs/`, which contains only the studio-level ADR process and template.

The project-level `README.md` SHOULD serve as an index of the project's ADRs.

### 5.3 Project Independence

Project ADRs MUST remain within the repository they govern.

Shared studio standards MAY be referenced by project ADRs, but project-specific decisions SHOULD NOT be moved into the studio standards repository.

## 6. ADR Numbering and Naming

### 6.1 Numbering

ADRs MUST use sequential, four-digit identifiers.

Examples:

- `0001`
- `0002`
- `0003`
- `0004`

Identifiers MUST NOT be reused, including when an ADR is rejected or superseded.

### 6.2 File Naming

ADR filenames MUST follow:

```text
NNNN-short-descriptive-title.md
```

Examples:

```text
0001-use-feature-oriented-architecture.md
0002-adopt-godot-signals-for-event-notifications.md
0003-use-json-for-save-data.md
```

Rules:

- Use four-digit numbering.
- Use lowercase kebab-case.
- Use a concise, descriptive title.
- Use the `.md` extension.
- Avoid vague names such as `architecture-decision.md`.

### 6.3 Titles

The document title SHOULD clearly communicate the decision topic.

The title MAY use a different wording from the filename when necessary for readability.

## 7. ADR Status

Every ADR MUST have one of the following statuses:

| Status | Meaning |
|---|---|
| Proposed | The decision is documented and awaiting review or approval. |
| Accepted | The decision has been approved and is the current project direction. |
| Rejected | The proposed decision was evaluated but not adopted. |
| Superseded | A newer ADR replaces this decision. |
| Deprecated | The decision is no longer recommended or applicable. |

### 7.1 Proposed

A proposed ADR documents a decision under consideration.

Implementation MUST NOT treat a proposed ADR as an approved architectural requirement unless the project owner explicitly authorizes a temporary implementation.

### 7.2 Accepted

An accepted ADR represents an approved project decision.

Implementation SHOULD follow the accepted decision unless an approved change supersedes it.

### 7.3 Rejected

A rejected ADR MUST remain available as a historical record.

Its rationale SHOULD explain why the proposal was not adopted.

### 7.4 Superseded

A superseded ADR MUST identify the ADR that replaces it.

The replacement ADR MUST reference the decision it supersedes.

### 7.5 Deprecated

A deprecated ADR is no longer applicable or recommended.

It SHOULD explain why it is deprecated and identify a replacement when one exists.

## 8. ADR Document Structure

Every ADR MUST use the following structure.

```markdown
# NNNN - Decision Title

- **Status:** Proposed
- **Date:** YYYY-MM-DD
- **Decision Owner:** Project Owner
- **Related ADRs:** None

## 1. Context

Describe the problem, requirement, or situation that requires a decision.

Include relevant constraints, technical context, and existing conditions.

## 2. Decision Drivers

List the important factors influencing the decision.

Examples:
- Maintainability.
- Performance.
- Simplicity.
- Compatibility.
- Development effort.
- Long-term flexibility.

## 3. Considered Options

Describe the reasonable alternatives considered.

### Option 1: Name

Describe the approach, advantages, and disadvantages.

### Option 2: Name

Describe the approach, advantages, and disadvantages.

## 4. Decision

Clearly state the selected approach.

Explain why it was selected and how it addresses the decision drivers.

## 5. Consequences

Describe the expected consequences of the decision.

### Positive Consequences

- Benefits and improvements.

### Negative Consequences and Trade-offs

- Limitations and disadvantages.

### Risks and Mitigations

- Relevant risks and how they will be managed.

## 6. Implementation Notes

Describe important implementation considerations, constraints, or migration requirements.

This section SHOULD remain focused on information necessary to implement the decision.

## 7. References

List relevant documentation, standards, technical resources, or related ADRs.
```

### 8.1 Required Sections

The following sections MUST be present:

- Context.
- Decision Drivers.
- Considered Options.
- Decision.
- Consequences.

Implementation Notes and References SHOULD be included when relevant.

### 8.2 Metadata

Every ADR MUST identify:

- Its status.
- Its creation date.
- Its decision owner.
- Related ADRs, when applicable.

The decision owner is normally the project owner or an explicitly authorized decision-maker.

### 8.3 Decision Clarity

The Decision section MUST state the selected approach directly.

Avoid ambiguous statements that describe alternatives without identifying which one was chosen.

## 9. ADR Creation Process

The following process SHOULD be followed when introducing a significant architectural decision.

### Step 1: Identify the Decision

Determine whether the technical issue requires an architectural decision.

Evaluate its scope, impact, reversibility, and relationship to existing standards.

### Step 2: Investigate the Context

Review:

- Existing architecture.
- Relevant project documentation.
- Current implementation.
- Existing ADRs.
- Applicable studio standards.
- Technical constraints.
- Relevant alternatives.

### Step 3: Identify Alternatives

Consider reasonable approaches.

At least one alternative to the proposed approach SHOULD be evaluated when meaningful alternatives exist.

The evaluation SHOULD consider maintainability, complexity, performance, compatibility, and implementation cost as applicable.

### Step 4: Draft the ADR

Create a new ADR using the required template.

Assign the next available sequential identifier.

Set its initial status to `Proposed`.

### Step 5: Review the Proposal

Review the proposal for:

- Correctness.
- Completeness.
- Consistency with existing architecture.
- Alignment with studio standards.
- Technical feasibility.
- Long-term consequences.
- Unaddressed risks.

### Step 6: Approve or Reject

The project owner MUST explicitly approve or reject the decision.

AI agents MUST NOT independently approve architectural decisions.

### Step 7: Update the Status

After the decision:

- Set the ADR to `Accepted` if approved.
- Set it to `Rejected` if not adopted.

Record relevant approval context when useful.

### Step 8: Implement and Validate

Implement the accepted decision according to its documented requirements.

Update affected architecture documentation and implementation references when necessary.

### Step 9: Maintain the ADR Index

Update the project-level ADR index to reflect the new record and its current status.

## 10. ADR Review and Approval

### 10.1 Decision Authority

The project owner is the final authority for project-specific architectural decisions.

The project owner MAY delegate review responsibilities but retains final approval authority unless explicitly stated otherwise.

### 10.2 Technical Review

Proposed ADRs SHOULD be reviewed for:

- Technical feasibility.
- Architectural consistency.
- Maintainability.
- Compatibility with project constraints.
- Implementation complexity.
- Consequences and risks.
- Alternatives and trade-offs.

### 10.3 Approval Requirements

An ADR MUST NOT be marked `Accepted` without explicit project owner approval.

A review comment, implementation attempt, or AI-generated recommendation does not constitute approval.

### 10.4 Changes After Approval

When an accepted decision needs to change, a new ADR SHOULD be created.

The new ADR MUST identify the previous decision and explain why the change is necessary.

## 11. Changing and Superseding Decisions

### 11.1 New Decision

When an accepted decision becomes unsuitable, create a new ADR.

The new ADR SHOULD explain:

- The limitations of the previous decision.
- The new requirements or circumstances.
- Alternatives considered.
- Why the replacement is preferable.
- Migration or compatibility implications.

### 11.2 Superseding Relationships

When a new ADR replaces an existing one:

- The new ADR MUST reference the previous ADR.
- The previous ADR MUST reference the new ADR.
- The previous ADR MUST change to `Superseded`.
- The new ADR MUST become `Accepted` after approval.

### 11.3 Historical Integrity

Accepted ADRs MUST NOT be silently rewritten to represent a different decision.

Minor corrections to spelling, formatting, or broken links MAY be made without changing the historical meaning.

Changes that alter the original reasoning or decision MUST be documented through a new ADR.

## 12. ADR Index Maintenance

Every project-level ADR directory SHOULD contain a `README.md` index.

The index SHOULD list:

- ADR identifier.
- Decision title.
- Current status.
- Decision date.
- Link to the ADR.

Example:

```markdown
# Architecture Decision Records

This directory contains architectural decisions for this project.

| ID | Decision | Status | Date |
|---|---|---|---|
| 0001 | Use feature-oriented architecture | Accepted | 2026-01-10 |
| 0002 | Use signals for event notifications | Accepted | 2026-01-12 |
| 0003 | Introduce a custom networking layer | Rejected | 2026-01-15 |
```

The example is illustrative. Projects MUST use their actual ADR records and dates.

### 12.1 Index Accuracy

The ADR index MUST reflect the actual files and statuses in the directory.

### 12.2 Index Updates

The index SHOULD be updated whenever an ADR is:

- Created.
- Accepted.
- Rejected.
- Superseded.
- Deprecated.

### 12.3 No Duplicate Sources of Truth

The ADR document is the authoritative source for its decision.

The index provides discoverability and MUST NOT replace the ADR's detailed content.

## 13. Relationship with Studio Standards

ADRs and studio standards serve different purposes.

### 13.1 Studio Standards

Studio standards establish reusable practices and expectations across projects.

Examples include:

- Architecture guidelines.
- GDScript standards.
- Resource management guidelines.
- Scene and node conventions.
- Performance guidelines.
- Data persistence guidelines.

### 13.2 Project ADRs

Project ADRs record decisions made for a particular game.

They MAY:

- Select among approaches permitted by studio standards.
- Define project-specific technical constraints.
- Establish justified exceptions.
- Record project-specific architectural patterns.
- Document decisions that are not covered by existing standards.

### 13.3 Exceptions to Studio Standards

A project MAY require an exception to a studio standard.

Such an exception MUST:

- Explain why the standard is unsuitable.
- Document the alternative approach.
- Identify affected systems.
- Explain consequences and risks.
- Receive project owner approval.
- Reference the relevant studio standard.

An ADR does not automatically modify or override the studio-wide standard for other projects.

If a reusable studio standard itself needs to change, that change MUST be reviewed and approved through the studio documentation governance process.

## 14. AI-Assisted ADR Management

AI agents MAY assist with researching, drafting, reviewing, and maintaining ADRs.

AI agents MUST:

- Read relevant existing ADRs before proposing a new decision.
- Inspect the current architecture and implementation.
- Review applicable studio standards.
- Identify meaningful alternatives.
- Explain technical trade-offs.
- Distinguish verified facts from assumptions.
- Use the required ADR structure.
- Assign the next available identifier after inspecting the project ADR directory.
- Set new ADRs to `Proposed`.
- Update the ADR index when creating or changing records.
- Preserve historical decisions.
- Identify affected documentation and implementation areas.

AI agents MUST NOT:

- Approve their own architectural decisions.
- Mark an ADR as `Accepted` without explicit owner approval.
- Invent technical constraints or evidence.
- Create duplicate ADRs without evaluating existing records.
- Silently modify the meaning of accepted ADRs.
- Treat a project-specific decision as a studio-wide requirement.
- Implement a significant architectural change solely because an ADR proposal exists.

AI agents SHOULD request owner approval before implementing proposed architectural decisions that materially affect project structure, feature boundaries, or shared technical infrastructure.

## 15. ADR Review Checklist

Before submitting an ADR for approval, verify:

- [ ] The decision has meaningful architectural or long-term technical impact.
- [ ] The problem and context are clearly explained.
- [ ] Decision drivers are identified.
- [ ] Relevant existing standards and ADRs have been reviewed.
- [ ] Reasonable alternatives have been considered.
- [ ] The selected decision is explicit.
- [ ] Benefits and disadvantages are documented.
- [ ] Risks and mitigations are considered.
- [ ] Implementation implications are identified.
- [ ] Related ADRs are referenced.
- [ ] The filename and identifier follow conventions.
- [ ] The initial status is correct.
- [ ] The project ADR index is updated.
- [ ] Approval authority is clear.

## 16. Maintenance

This ADR process SHOULD be reviewed when:

- The studio changes its architecture governance practices.
- Project experience reveals recurring ADR management problems.
- New technical standards require additional decision documentation.
- AI-assisted development workflows change significantly.
- The existing ADR template becomes insufficient.

Changes to this process MUST preserve the distinction between studio-wide standards and project-specific architectural decisions.