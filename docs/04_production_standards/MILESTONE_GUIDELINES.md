# Milestone Guidelines

## 1. Purpose

This document defines the studio-wide guidelines for planning and managing development milestones.

Its purpose is to ensure that milestones:

- Represent meaningful project outcomes.
- Provide clear development objectives.
- Support progress tracking and production decisions.
- Help control project scope.
- Identify dependencies and risks.
- Establish measurable completion criteria.
- Align development activities with the intended player experience.
- Provide visibility into project readiness.

These guidelines are reusable across studio projects. Each game MUST define its own milestones according to its scope, development approach, resources, and objectives.

## 2. Scope

These guidelines apply to milestones throughout the game development lifecycle, including:

- Concept validation.
- Pre-production.
- Prototyping.
- Vertical slices.
- Feature development.
- Content production.
- Alpha.
- Beta.
- Release candidates.
- Release.
- Post-release development.

They apply to gameplay, engineering, art, audio, design, QA, production, and supporting activities.

These guidelines define milestone management practices. Project-specific milestone definitions, schedules, deliverables, and targets MUST be maintained within the corresponding game project.

## 3. Milestone Principles

### 3.1. Outcome-Oriented

A milestone MUST represent a meaningful result or state of project readiness.

It SHOULD describe what the project will achieve, not merely how many tasks will be completed.

For example:

- A playable prototype demonstrates the core gameplay loop.
- A vertical slice demonstrates the intended quality of a representative gameplay experience.
- An alpha build contains all planned major features.
- A beta build is feature-complete and undergoing stabilization.

### 3.2. Measurable Completion

Every milestone MUST have clear completion criteria.

The project owner and contributors MUST be able to determine whether those criteria have been satisfied.

Avoid vague completion conditions such as "mostly finished" or "good enough" without supporting criteria.

### 3.3. Realistic Scope

Milestone scope SHOULD reflect available development capacity, dependencies, uncertainty, and project priorities.

Avoid defining milestones around unrealistic expectations or arbitrary deadlines.

### 3.4. Incremental Progress

Milestones SHOULD represent achievable steps toward larger project objectives.

Each milestone SHOULD produce useful progress, reduce uncertainty, or establish a meaningful validation point.

### 3.5. Quality at Every Stage

Milestones MUST include appropriate quality expectations.

Work SHOULD NOT be considered milestone-ready merely because the planned features have been implemented.

Testing, integration, documentation, and validation MUST be considered according to the milestone's purpose.

### 3.6. Adaptability

Milestones MAY be revised when project conditions change.

Changes SHOULD be deliberate, documented, and communicated rather than silently modifying expectations.

## 4. Milestone Structure

Each project SHOULD organize milestones around major development outcomes.

A milestone MAY contain:

- Objectives.
- Scope.
- Deliverables.
- Related epics and features.
- Required tasks.
- Dependencies.
- Acceptance criteria.
- Target date or development period.
- Risks and assumptions.
- Validation requirements.
- Completion status.

Milestones SHOULD be sufficiently independent to support meaningful progress tracking.

### 4.1. Milestone Identifier

Each milestone SHOULD have a unique and stable identifier.

A simple convention MAY be used:

- `M0` — Initial project setup.
- `M1` — First major development objective.
- `M2` — Second major development objective.
- `M3` — Third major development objective.

Alternatively, descriptive identifiers MAY be used when they improve readability.

Identifiers SHOULD remain stable even when milestone names or target dates change.

### 4.2. Milestone Name

Milestone names SHOULD communicate their intended outcome.

Examples:

- Project Foundation.
- Core Gameplay Prototype.
- Vertical Slice.
- Feature Complete.
- Alpha.
- Beta.
- Release Candidate.
- Initial Release.

Avoid names that communicate only an arbitrary date or sprint number.

### 4.3. Milestone Description

The description SHOULD explain:

- Why the milestone exists.
- What outcome it intends to achieve.
- Which project objectives it supports.
- What will be demonstrated or validated.
- What is explicitly outside its scope.

## 5. Milestone Categories

Projects MAY use milestone categories appropriate to their development approach.

Common categories include:

### 5.1. Technical Milestones

Technical milestones validate infrastructure, architecture, or important engineering capabilities.

Examples:

- Godot project foundation established.
- Feature-oriented architecture implemented.
- Save and load functionality validated.
- Automated build pipeline operational.
- Performance targets demonstrated.

### 5.2. Gameplay Milestones

Gameplay milestones validate player-facing functionality and gameplay systems.

Examples:

- Core gameplay loop playable.
- Player movement and interaction implemented.
- Combat prototype validated.
- Progression system integrated.
- Representative gameplay scenario completed.

### 5.3. Content Milestones

Content milestones track the production and integration of game content.

Examples:

- Initial environment set completed.
- Character content integrated.
- Required audio assets produced.
- First playable level completed.
- Planned content set integrated.

### 5.4. Quality Milestones

Quality milestones focus on product stability, usability, and validation.

Examples:

- Critical gameplay defects resolved.
- Alpha validation completed.
- Beta regression testing completed.
- Performance requirements validated.
- Release readiness established.

### 5.5. Release Milestones

Release milestones represent significant delivery stages.

Examples:

- Release candidate approved.
- Initial public release.
- Post-release update completed.

A milestone MAY combine multiple categories when they contribute to one coherent project outcome.

## 6. Milestone Planning

Milestones SHOULD be planned before their associated work begins.

Planning MUST consider the project's current understanding, available resources, and known constraints.

### 6.1. Define the Objective

Every milestone MUST have a clear objective.

The objective SHOULD describe the expected project state after completion.

It SHOULD answer:

- What will be achieved?
- Why is it important?
- What will it enable?
- How will success be demonstrated?

### 6.2. Define Scope

Milestone scope MUST identify:

- Included features or capabilities.
- Required deliverables.
- Relevant quality expectations.
- Important dependencies.
- Explicit exclusions.

Scope SHOULD be achievable without introducing unnecessary work.

### 6.3. Identify Dependencies

Dependencies SHOULD be identified before committing to milestone expectations.

Consider:

- Technical prerequisites.
- Design decisions.
- External resources.
- Art and audio production.
- Integration requirements.
- Other milestones.
- Engine or platform constraints.

Dependencies that threaten milestone completion SHOULD be visible and actively managed.

### 6.4. Estimate Effort

Projects MAY estimate milestone effort using:

- Task estimates.
- Relative effort.
- Historical development data.
- Available development capacity.
- Risk and uncertainty assessments.

Milestone estimates SHOULD account for implementation, integration, testing, review, and documentation.

Avoid estimating milestones solely by summing optimistic implementation estimates.

### 6.5. Establish a Target

A milestone MAY have a target date or development period.

Targets SHOULD reflect realistic expectations and known dependencies.

When uncertainty is high, use a development range or relative planning window instead of an artificially precise date.

A target date is a planning commitment, not proof that the milestone will be completed by that date.

## 7. Milestone Deliverables

Deliverables are the concrete results expected from a milestone.

Depending on its purpose, deliverables MAY include:

- Playable builds.
- Implemented features.
- Integrated content.
- Technical infrastructure.
- Design specifications.
- Architecture documentation.
- Art and audio assets.
- Test results.
- Performance measurements.
- Validation reports.
- Release packages.

### 7.1. Deliverable Quality

Deliverables MUST satisfy the quality requirements appropriate to their intended use.

For example, a prototype may use temporary assets, while a release candidate requires production-ready content and validated integration.

### 7.2. Demonstrable Results

Milestone deliverables SHOULD be demonstrable or independently verifiable.

Examples:

- A playable build demonstrates gameplay functionality.
- A test report demonstrates validation results.
- A benchmark report demonstrates measured performance.
- A completed asset set demonstrates content readiness.

### 7.3. Deliverable Traceability

Deliverables SHOULD reference relevant backlog items, specifications, and validation records.

This makes it easier to understand what contributed to the milestone and whether its objectives were satisfied.

## 8. Milestone Acceptance Criteria

Every milestone MUST define acceptance criteria.

Acceptance criteria describe the conditions required to consider the milestone complete.

They SHOULD be:

- Specific.
- Measurable or verifiable.
- Relevant to the milestone objective.
- Consistent with the approved scope.
- Appropriate to the milestone's development stage.

### 8.1. Acceptance Criteria Examples

For a core gameplay prototype:

- The primary gameplay loop is playable.
- The player can perform the essential gameplay actions.
- The main systems interact correctly.
- Feedback communicates important gameplay events.
- The prototype can be built and executed reliably.
- Relevant gameplay assumptions have been evaluated.

For an alpha milestone:

- All planned major features are implemented.
- Major gameplay systems are integrated.
- The game can be completed through its intended primary progression.
- Critical defects have been addressed.
- Remaining known issues are documented.
- Required validation has been performed.

Acceptance criteria MUST reflect the actual milestone rather than copying generic criteria from another development stage.

## 9. Milestone Status Management

Projects SHOULD use a consistent status model.

A recommended model is:

| Status | Meaning |
|---|---|
| Planned | Milestone identified but detailed planning may be incomplete |
| Ready | Scope, objectives, and completion criteria are sufficiently defined |
| In Progress | Work contributing to the milestone is actively underway |
| At Risk | A significant issue threatens the expected outcome or target |
| Blocked | A major unresolved dependency prevents meaningful progress |
| Completed | Acceptance criteria have been satisfied and completion approved |
| Cancelled | Milestone is no longer part of the project plan |

Projects MAY adapt this model to their production workflow.

### 9.1. Status Accuracy

Milestone status MUST reflect the actual state of its objectives and deliverables.

A milestone MUST NOT be marked Completed simply because its target date has passed or all associated tasks have been closed.

### 9.2. At-Risk Milestones

A milestone SHOULD be marked At Risk when there is a meaningful possibility that its objectives, quality requirements, or target will not be achieved.

The risk SHOULD be documented with:

- The underlying issue.
- Potential impact.
- Affected deliverables.
- Proposed mitigation.
- Decisions or support required.

### 9.3. Blocked Milestones

A milestone SHOULD be marked Blocked when an unresolved issue prevents meaningful progress toward its objectives.

The blocking condition and required resolution MUST be identified.

### 9.4. Status Changes

Significant milestone status changes SHOULD be communicated to the project owner.

Changes to Completed or Cancelled status MUST be supported by the corresponding decision or acceptance outcome.

## 10. Milestone Tracking

Milestone progress SHOULD be tracked using the authoritative project backlog and relevant development records.

### 10.1. Progress Measurement

Progress SHOULD be evaluated using meaningful indicators, such as:

- Accepted deliverables.
- Satisfied acceptance criteria.
- Completed features.
- Resolved dependencies.
- Validation results.
- Remaining high-priority work.

Task completion percentages MAY provide supporting information but MUST NOT be treated as the sole measure of milestone progress.

A milestone with many completed minor tasks may still be far from achieving its primary objective.

### 10.2. Progress Reviews

Milestone progress SHOULD be reviewed periodically.

Review frequency SHOULD reflect milestone duration, risk, and project needs.

During reviews, consider:

- Current status.
- Completed deliverables.
- Outstanding work.
- Changes in scope.
- New dependencies.
- Risks and blockers.
- Target date.
- Required decisions.

### 10.3. Progress Reporting

Progress reports SHOULD be concise and communicate the milestone's actual condition.

They SHOULD identify:

- Current status.
- Achievements.
- Remaining work.
- Important risks.
- Blockers.
- Changes to expectations.
- Next actions.

Avoid reporting optimistic progress that is not supported by demonstrable results.

## 11. Milestone Changes and Scope Control

Milestones MAY change as the project evolves.

Changes SHOULD preserve the milestone's purpose and maintain visibility into their impact.

### 11.1. Scope Changes

A scope change SHOULD identify:

- What is changing.
- Why the change is necessary.
- Which deliverables are affected.
- Impact on dependencies.
- Impact on effort and timing.
- Impact on quality or project objectives.

Significant scope changes MUST receive project owner approval.

### 11.2. Target Date Changes

Target dates MAY be revised when estimates, dependencies, or project priorities change.

Changes SHOULD be based on updated information rather than repeatedly moving dates without addressing the underlying problem.

### 11.3. Milestone Splitting

A milestone SHOULD be split when its scope becomes too large or contains multiple independently valuable outcomes.

Each resulting milestone SHOULD have its own objectives and acceptance criteria.

### 11.4. Milestone Cancellation

A milestone MAY be cancelled when:

- Its objective is no longer relevant.
- Project direction changes.
- Its scope is absorbed into another milestone.
- Its expected value no longer justifies the effort.

The reason for cancellation SHOULD be documented.

### 11.5. Historical Integrity

When milestones are revised, preserve meaningful historical information.

Do not silently rewrite completed milestone records to make past plans appear consistent with later decisions.

## 12. Milestone Dependencies and Risks

Milestones SHOULD be planned with awareness of project dependencies and risks.

### 12.1. Dependency Management

A milestone MAY depend on:

- Another milestone.
- A major feature.
- External resources.
- Technical validation.
- Content production.
- Project owner decisions.

Dependencies SHOULD be visible in the milestone plan.

### 12.2. Risk Identification

Important risks SHOULD be identified early.

Examples include:

- Unproven technical approaches.
- Unclear gameplay requirements.
- Performance uncertainty.
- Asset production delays.
- Integration complexity.
- External tool or service limitations.
- Insufficient testing capacity.
- Uncontrolled scope growth.

### 12.3. Risk Mitigation

High-impact risks SHOULD have a mitigation strategy.

Mitigation MAY include:

- Technical prototypes.
- Research tasks.
- Early integration.
- Reduced scope.
- Alternative implementation approaches.
- Additional validation.
- Revised milestone sequencing.

### 12.4. Uncertainty Reduction

Milestones SHOULD be used to reduce important uncertainty.

A research or prototype milestone MAY be valuable even when it does not produce a finished player-facing feature.

Its completion criteria SHOULD describe the knowledge or validation outcome expected.

## 13. Milestone Reviews and Completion

A milestone SHOULD undergo a review before being considered complete.

### 13.1. Completion Review

The review SHOULD verify:

- Milestone objectives have been achieved.
- Required deliverables exist.
- Acceptance criteria are satisfied.
- Relevant integration work is complete.
- Required validation has been performed.
- Outstanding issues are documented.
- Relevant project documentation is updated.
- Follow-up work has been identified.

### 13.2. Completion Approval

The project owner is responsible for approving milestone completion.

AI agents and other contributors MAY prepare evidence, validate criteria, and recommend completion, but MUST NOT independently approve significant milestone outcomes.

### 13.3. Incomplete Criteria

If acceptance criteria remain unsatisfied, the milestone MUST NOT be marked Completed.

The project owner SHOULD determine whether to:

- Complete the remaining work.
- Revise the milestone scope.
- Split the remaining work into a follow-up milestone.
- Cancel the affected deliverable.

Any scope revision MUST be explicit and justified.

### 13.4. Milestone Retrospective

A retrospective SHOULD be performed when a milestone provides meaningful learning opportunities.

Consider:

- What went well?
- What took longer than expected?
- Which assumptions were incorrect?
- What technical or production risks emerged?
- What quality issues were discovered?
- What should change in the next milestone?

Record only lessons that are useful for future decisions.

## 14. Relationship to the Development Lifecycle

Milestones SHOULD align with the project's development lifecycle.

The following examples illustrate possible milestone outcomes.

| Lifecycle Stage | Example Milestone Outcome |
|---|---|
| Concept | Game concept and core vision validated |
| Pre-production | Key design and technical risks understood |
| Prototyping | Core gameplay loop demonstrated |
| Production | Major gameplay systems and content implemented |
| Alpha | Feature-complete game available for broad testing |
| Beta | Content and features stabilized, release-focused validation underway |
| Release Candidate | Candidate build meets release requirements |
| Release | Approved game build delivered |
| Post-release | Initial release issues reviewed and follow-up priorities established |

These examples are not mandatory milestones.

Projects MAY combine, split, rename, or omit stages according to their scope and development model.

A lifecycle stage describes a broader development phase. A milestone represents a specific, verifiable outcome within or across those phases.

## 15. Milestone Documentation Template

Projects SHOULD use a consistent milestone format.

The following template MAY be copied into project-specific planning documentation:

```markdown
# Milestone: [Milestone Name]

## 1. Overview

- **ID:** [Milestone ID]
- **Status:** [Planned / Ready / In Progress / At Risk / Blocked / Completed / Cancelled]
- **Target Date:** [Date or TBD]
- **Category:** [Technical / Gameplay / Content / Quality / Release]
- **Owner:** [Responsible person]

## 2. Objective

[Describe the intended outcome and why this milestone matters.]

## 3. Scope

### Included

- [Deliverable or capability]
- [Deliverable or capability]

### Excluded

- [Explicitly excluded work]

## 4. Deliverables

- [Expected deliverable]
- [Expected deliverable]

## 5. Acceptance Criteria

- [ ] [Verifiable condition]
- [ ] [Verifiable condition]

## 6. Dependencies

- [Dependency or prerequisite]

## 7. Risks and Assumptions

- [Known risk or assumption]

## 8. Related Work

- [Backlog items, features, or specifications]

## 9. Progress

- **Completed:** [Summary]
- **Remaining:** [Summary]
- **Blockers:** [Summary]

## 10. Completion Review

- **Outcome:** [Completed / Not Completed]
- **Validation Evidence:** [Builds, test results, reports, etc.]
- **Outstanding Issues:** [Known issues]
- **Approval:** [Project owner decision]
- **Completion Date:** [Date]
```

Projects MAY simplify this template for smaller milestones.

## 16. AI-Assisted Milestone Management

AI agents MAY assist with milestone planning, decomposition, tracking, risk identification, progress reporting, and completion reviews.

AI agents MUST:

1. Read the existing milestone plan and relevant project documentation.
2. Respect approved project objectives and scope.
3. Use the authoritative backlog to identify related work.
4. Identify dependencies and risks.
5. Distinguish verified progress from assumptions.
6. Report incomplete or blocked deliverables.
7. Preserve milestone identifiers and historical records.
8. Request approval for significant scope or target changes.
9. Provide evidence when recommending milestone completion.
10. Update project documentation only when authorized.

AI agents MUST NOT:

- Invent milestone achievements.
- Mark milestones complete without satisfying acceptance criteria.
- Change approved project objectives without authorization.
- Hide delays or unresolved risks.
- Treat completed task counts as proof of milestone success.
- Independently approve milestone completion.
- Silently delete or rewrite historical milestone information.

## 17. Milestone Review Checklist

Before approving a milestone, verify the applicable requirements:

- [ ] The milestone objective is clear.
- [ ] Scope and exclusions are documented.
- [ ] Required deliverables are available.
- [ ] Acceptance criteria are satisfied.
- [ ] Dependencies have been addressed.
- [ ] Relevant features are integrated.
- [ ] Required testing and validation are complete.
- [ ] Important defects and limitations are documented.
- [ ] Project documentation is updated.
- [ ] Follow-up work is recorded.
- [ ] Completion evidence is available.
- [ ] Project owner approval has been obtained.

## 18. Exceptions

Projects MAY adapt these guidelines to their development model, scope, and available resources.

Exceptions SHOULD be justified when they:

- Simplify production management.
- Support iterative or experimental development.
- Address changing project constraints.
- Reduce unnecessary administrative effort.
- Better represent the project's actual delivery process.

Exceptions MUST NOT compromise milestone traceability, acceptance criteria, or the accuracy of progress reporting.

Significant changes to the milestone management process require project owner approval.

## 19. Related Documents

- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/game_development_lifecycle.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/04_production_standards/backlog_management.md`

Project-specific milestone plans SHOULD reference relevant:

- Game design specifications.
- Technical specifications.
- Architecture Decision Records.
- Backlog items.
- Sprint plans.
- QA plans and validation reports.
- Release documentation.

## 20. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- Studio production practices change.
- Milestone planning becomes unnecessarily complex.
- Recurring planning or delivery problems are identified.
- New project management practices are adopted.
- AI-assisted production workflows evolve.
- Improvements to milestone tracking and validation are identified.

Changes MUST preserve the distinction between reusable studio guidelines and project-specific milestone plans.

The project owner is responsible for approving changes to these guidelines.