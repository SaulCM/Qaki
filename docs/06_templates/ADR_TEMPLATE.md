# Architecture Decision Record (ADR) Template

> Use this template to document a significant architectural or technical decision.
>
> Replace the placeholder content with project-specific information. Remove instructional comments before accepting the ADR.

## ADR-[NUMBER]: [DECISION TITLE]

| Field | Value |
|---|---|
| **Status** | Proposed |
| **Date** | YYYY-MM-DD |
| **Decision Owner** | [Name or role] |
| **Decision Contributors** | [Names or roles, if applicable] |
| **Related ADRs** | [ADR references or None] |
| **Related Requirements** | [Requirement references or None] |

## 1. Context

Describe the problem, situation, or technical requirement that requires a decision.

Include relevant information such as:

- Current system architecture or implementation.
- The problem or limitation being addressed.
- Relevant project requirements and constraints.
- Technical or operational circumstances.
- Why a decision is necessary now.
- Consequences of leaving the issue unresolved.

Focus on the information necessary to understand the decision.

## 2. Decision Drivers

List the factors that influence the decision.

Examples:

- Maintainability.
- Performance.
- Scalability.
- Reliability.
- Development complexity.
- Integration with Godot.
- Compatibility with supported platforms.
- Testing requirements.
- Development time and available resources.
- Long-term maintenance costs.
- Consistency with existing architecture.
- Compatibility with approved studio standards.

Prioritize the drivers when some considerations are more important than others.

## 3. Considered Options

Document the realistic alternatives evaluated.

### Option 1: [Option Name]

**Description:**

Describe the proposed approach.

**Advantages:**

- [Advantage]
- [Advantage]

**Disadvantages:**

- [Disadvantage]
- [Disadvantage]

**Risks and Considerations:**

- [Risk or consideration]

### Option 2: [Option Name]

**Description:**

Describe the proposed approach.

**Advantages:**

- [Advantage]
- [Advantage]

**Disadvantages:**

- [Disadvantage]
- [Disadvantage]

**Risks and Considerations:**

- [Risk or consideration]

### Option 3: [Option Name] (Optional)

**Description:**

Describe the proposed approach.

**Advantages:**

- [Advantage]

**Disadvantages:**

- [Disadvantage]

**Risks and Considerations:**

- [Risk or consideration]

Add or remove options as necessary.

If an alternative was considered but rejected early, briefly explain why it was not evaluated further.

## 4. Decision

**Selected Option:** [Chosen option]

Describe the selected approach clearly and precisely.

Explain:

- What will be implemented or adopted.
- How the solution addresses the decision drivers.
- Which important design or architectural principles will be followed.
- Any constraints or conditions associated with the decision.

The decision MUST be specific enough to guide implementation.

## 5. Consequences

Document the expected effects of adopting the decision.

### 5.1. Positive Consequences

- [Expected benefit]
- [Expected benefit]

### 5.2. Negative Consequences and Trade-offs

- [Expected limitation or cost]
- [Expected limitation or cost]

### 5.3. Risks and Mitigations

| Risk | Potential Impact | Mitigation |
|---|---|---|
| [Risk description] | [Impact] | [Mitigation] |

### 5.4. Implementation Implications

Describe relevant implementation changes, such as:

- Systems or components affected.
- Dependencies introduced or removed.
- Required migrations or refactoring.
- Changes to project structure.
- Testing requirements.
- Documentation updates.
- Operational or maintenance considerations.

## 6. Implementation Plan (Optional)

Use this section when the decision requires multiple implementation steps.

| Step | Description | Expected Outcome |
|---|---|---|
| 1 | [Implementation task] | [Outcome] |
| 2 | [Implementation task] | [Outcome] |
| 3 | [Implementation task] | [Outcome] |

Related implementation tasks SHOULD be tracked in the project's backlog.

An ADR documents the decision; it does not replace implementation planning or task tracking.

## 7. Validation and Verification (Optional)

Describe how the implementation or adoption of the decision will be validated.

Potential validation activities include:

- Automated tests.
- Integration tests.
- Performance measurements.
- Prototype evaluation.
- Compatibility checks.
- Code review.
- Runtime validation.
- Architectural review.

Define measurable success criteria when practical.

## 8. References

List relevant resources supporting or explaining the decision.

Examples:

- Related ADRs.
- Game design documents.
- Technical specifications.
- Godot documentation.
- External technical references.
- Relevant source code or implementation discussions.

References:

- [Reference title or description] — [Link or repository path]
- [Reference title or description] — [Link or repository path]

## 9. Decision History

Record significant changes to the ADR's status or decision.

| Date | Status | Description | Approved By |
|---|---|---|---|
| YYYY-MM-DD | Proposed | Initial decision proposal. | [Name or role] |
| YYYY-MM-DD | Accepted | Decision approved. | [Name or role] |

Do not rewrite historical decisions in a way that removes their original context.

If an accepted decision is replaced, create a new ADR and reference the previous record.

---

## ADR Review Checklist

Before submitting this ADR for approval:

- [ ] The problem and context are clearly explained.
- [ ] The decision drivers are identified.
- [ ] Relevant alternatives have been considered.
- [ ] Advantages and disadvantages are documented.
- [ ] The selected option is explicit.
- [ ] Consequences and trade-offs are understood.
- [ ] Significant risks have been identified.
- [ ] Implementation implications are considered.
- [ ] Validation requirements are defined where applicable.
- [ ] Related documentation and ADRs are referenced.
- [ ] The ADR follows the project's naming and numbering conventions.

## Approval

| Role | Name | Decision | Date |
|---|---|---|---|
| Project Owner | [Name] | Pending | YYYY-MM-DD |

**Approval Status:** Pending Project Owner Review