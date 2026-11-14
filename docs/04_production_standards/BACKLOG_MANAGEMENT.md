# Backlog Management

## 1. Purpose

This document defines the studio-wide standards for managing development backlogs.

Its purpose is to ensure that development work is:

- Clearly defined and understandable.
- Prioritized according to project goals.
- Broken down into manageable tasks.
- Traceable to project requirements and objectives.
- Maintained as project needs evolve.
- Ready for implementation when selected.
- Visible to the project owner and contributors.

These standards establish a reusable backlog management approach without requiring a specific project management tool or methodology.

## 2. Scope

These standards apply to:

- Features.
- User stories.
- Tasks and subtasks.
- Bugs and defects.
- Technical improvements.
- Refactoring.
- Research and investigation.
- Testing activities.
- Documentation work.
- Art and audio production.
- Technical infrastructure.
- Maintenance and production activities.

Each game project MUST maintain its own backlog.

The backlog SHOULD reflect the current project scope, approved design decisions, production priorities, and known development work.

## 3. Backlog Management Principles

### 3.1. Single Source of Truth

Each project MUST have an identifiable authoritative backlog.

Work items SHOULD NOT be independently maintained across multiple systems without a clear synchronization process.

Supporting documents, technical specifications, and discussions MAY provide additional context, but they SHOULD reference the authoritative work item when one exists.

### 3.2. Transparency

The backlog SHOULD provide a clear view of:

- Planned work.
- Current priorities.
- Work in progress.
- Blocked items.
- Completed work.
- Known defects.
- Outstanding decisions.

Work status MUST reflect actual progress.

### 3.3. Value-Driven Prioritization

Work SHOULD be prioritized according to its contribution to the project.

Consider:

- Player experience.
- Core gameplay requirements.
- Project milestones.
- Technical dependencies.
- Risk reduction.
- Quality improvements.
- Production constraints.
- Available resources.

Priority SHOULD NOT be determined solely by how interesting or technically attractive a task appears.

### 3.4. Manageable Work Items

Work items SHOULD be sufficiently small and clear to support estimation, implementation, review, and validation.

Large items SHOULD be decomposed when their scope makes progress difficult to track or completion difficult to verify.

### 3.5. Continuous Refinement

The backlog is an evolving planning artifact.

Items MAY be added, modified, reprioritized, split, or removed as project understanding changes.

Backlog changes SHOULD preserve relevant decisions and historical traceability.

### 3.6. Practicality

Backlog management MUST remain proportional to project size.

Avoid excessive administrative overhead, unnecessary classifications, and artificial precision in estimates.

## 4. Backlog Structure

A project backlog SHOULD organize work using a hierarchy appropriate to its size and complexity.

A recommended structure is:

1. **Epic:** A large area of functionality or a significant project objective.
2. **Feature:** A cohesive gameplay, technical, production, or content capability.
3. **User Story:** A player- or user-oriented requirement describing a desired outcome.
4. **Task:** A specific unit of work required to implement, validate, or support an outcome.
5. **Subtask:** A smaller activity within a task when additional breakdown is useful.

Not every project requires every level.

A solo developer MAY manage small features directly as tasks without introducing unnecessary hierarchy.

### 4.1. Epic

An epic represents a substantial objective that requires multiple related work items.

Examples:

- Player progression.
- Inventory system.
- Procedural environment generation.
- Combat system.
- Save and load system.
- Audio implementation.

An epic SHOULD define:

- Objective.
- Expected outcome.
- Scope.
- Major dependencies.
- Relevant features or work items.
- Completion criteria.

### 4.2. Feature

A feature represents a cohesive capability of the game or its development infrastructure.

Examples:

- Equipment management.
- Character movement.
- Dialogue interactions.
- Resource gathering.
- Enemy behavior.
- Settings interface.

Features SHOULD be organized according to the project's feature-oriented architecture where applicable.

### 4.3. User Story

A user story describes a desired outcome from the perspective of a player or another relevant stakeholder.

Recommended format:

**As a** [type of user or player],  
**I want** [capability or action],  
**so that** [benefit or intended outcome].

Example:

As a player, I want to save my current progress so that I can continue playing later.

User stories SHOULD focus on outcomes rather than prescribing unnecessary implementation details.

Not all technical or production work naturally fits the user story format. Technical tasks MAY use a direct objective statement instead.

### 4.4. Task

A task describes a specific piece of work.

Examples:

- Implement player movement input.
- Create the inventory item resource.
- Add validation for save data.
- Create the inventory interface scene.
- Add automated tests for equipment selection.
- Configure the export pipeline.

Tasks SHOULD have clear expected results and appropriate completion criteria.

### 4.5. Subtask

Subtasks MAY be used when a task contains several independently trackable activities.

Avoid excessive decomposition that creates more administrative work than practical value.

## 5. Work Item Types

Projects SHOULD use a consistent set of work item types.

Recommended types include:

| Type | Purpose |
|---|---|
| Epic | Groups substantial related objectives |
| Feature | Represents a cohesive capability |
| User Story | Describes a desired player or stakeholder outcome |
| Task | Tracks specific implementation or production work |
| Bug | Tracks behavior that does not meet requirements |
| Technical Debt | Tracks known maintainability or architectural problems |
| Research | Tracks investigation or uncertainty reduction |
| Documentation | Tracks documentation creation or maintenance |
| Test | Tracks testing work not already included in another item |
| Chore | Tracks maintenance and supporting development activities |

Projects MAY simplify or extend this list when justified.

A work item SHOULD have one primary type.

## 6. Work Item Requirements

Every actionable backlog item SHOULD contain enough information for someone to understand its purpose and expected outcome.

### 6.1. Required Information

An actionable work item MUST have:

- Unique identifier.
- Clear title.
- Work item type.
- Description or objective.
- Current status.
- Priority.

### 6.2. Recommended Information

When applicable, include:

- Parent epic or feature.
- Acceptance criteria.
- Dependencies.
- Relevant design or technical documents.
- Related work items.
- Estimated effort.
- Risk or uncertainty.
- Target milestone.
- Assignee.
- Labels or categories.
- Validation requirements.

Fields SHOULD be included only when they provide useful planning or execution information.

### 6.3. Title

Titles MUST be concise and describe the work clearly.

Prefer action-oriented titles for implementation tasks.

Examples:

- Implement inventory item selection.
- Add player damage feedback.
- Validate save file compatibility.
- Create enemy detection behavior.

Avoid vague titles such as:

- Improve gameplay.
- Fix things.
- Work on UI.
- Update system.

### 6.4. Description

Descriptions SHOULD explain:

- What needs to be done.
- Why the work is necessary.
- Relevant context.
- Expected behavior or outcome.
- Important constraints.

Descriptions SHOULD NOT duplicate entire technical specifications or design documents.

Reference authoritative documents when additional detail is required.

### 6.5. Acceptance Criteria

Acceptance criteria define the conditions that must be satisfied for a work item to be accepted.

They SHOULD be:

- Specific.
- Observable.
- Verifiable.
- Relevant to the intended outcome.
- Independent of unnecessary implementation details.

Example:

**Task:** Implement inventory item selection.

Acceptance criteria:

- The player can select an available inventory item.
- The selected item is visually distinguishable.
- Selecting another item updates the selection.
- Invalid selections are rejected safely.
- Selection state is correctly reflected by the interface.

Acceptance criteria SHOULD describe expected behavior rather than merely list implementation activities.

## 7. Backlog Prioritization

The project owner is responsible for establishing and approving backlog priorities.

Prioritization SHOULD consider value, urgency, dependencies, risk, and effort.

### 7.1. Priority Levels

Projects SHOULD use a simple priority scale.

| Priority | Meaning |
|---|---|
| Critical | Requires immediate attention because it blocks essential work, threatens project integrity, or causes a severe defect |
| High | Important for current project objectives or upcoming milestones |
| Medium | Valuable work that should be addressed after higher-priority items |
| Low | Optional improvement or work with limited immediate impact |

Priority levels SHOULD represent relative importance, not implementation order alone.

### 7.2. Prioritization Factors

Consider the following factors:

**Player and project value**
- Does the work improve the core experience?
- Is it required for an important feature?
- Does it support a project milestone?

**Dependencies**
- Does other work depend on this item?
- Is it blocking implementation or validation?
- Must it be completed before another feature can proceed?

**Risk**
- Does it reduce technical or production uncertainty?
- Does it address a major quality concern?
- Could postponing it create significant rework?

**Effort**
- Is the expected benefit proportional to the effort?
- Can the work be divided into smaller deliverables?
- Is a simpler solution available?

**Timing**
- Is the work required for the current sprint or milestone?
- Does it depend on external resources or decisions?
- Is there a deadline?

### 7.3. Priority Review

Priorities SHOULD be reviewed when:

- Project objectives change.
- New dependencies are discovered.
- Important defects are identified.
- A milestone approaches.
- Technical risks become clearer.
- Previously planned work loses relevance.

Do not change priorities arbitrarily without considering the impact on existing commitments.

## 8. Backlog Refinement

Backlog refinement is the process of improving work items so they are understandable, appropriately scoped, and ready for future execution.

Refinement SHOULD be continuous and proportional to the project's needs.

### 8.1. Refinement Activities

During refinement:

1. Review the item's purpose and relevance.
2. Confirm that its scope is understandable.
3. Clarify expected outcomes.
4. Define acceptance criteria where appropriate.
5. Identify dependencies.
6. Identify risks and unknowns.
7. Estimate effort when useful.
8. Split oversized items.
9. Remove obsolete or duplicate work.
10. Confirm its priority.

### 8.2. Refinement Timing

Projects MAY refine the backlog:

- During sprint planning.
- Before starting a new feature.
- When new requirements emerge.
- During technical investigation.
- When existing items become unclear.

Do not require every backlog item to be fully specified in advance.

### 8.3. Refinement Ownership

The project owner is responsible for confirming scope, priorities, and intended outcomes.

Contributors and AI agents MAY suggest improvements, identify missing information, and propose task decomposition.

Significant scope changes require project owner approval.

## 9. Definition of Ready

A work item is considered ready for implementation when it contains enough information to begin work without significant unresolved ambiguity.

A ready item SHOULD satisfy the applicable criteria:

- [ ] Its objective is clear.
- [ ] Its scope is understood.
- [ ] Required context is available.
- [ ] Acceptance criteria are defined where appropriate.
- [ ] Important dependencies are identified.
- [ ] Known constraints are documented.
- [ ] Required design or technical decisions are available.
- [ ] Its priority is established.
- [ ] Its estimated effort is reasonable when estimation is used.
- [ ] It can be implemented and validated independently or as part of a clearly defined group of tasks.

Not every item requires every criterion.

Research tasks MAY be ready even when the implementation details are unknown, provided the investigation objective and expected deliverable are clear.

The Definition of Ready is a planning aid, not an additional approval process.

## 10. Work Item Estimation

Projects MAY estimate work items to support planning and capacity management.

Estimation SHOULD be used to improve decisions rather than create false precision.

### 10.1. Estimation Approaches

Possible approaches include:

- Relative effort.
- Story points.
- T-shirt sizes.
- Time estimates.
- No formal estimation for sufficiently small tasks.

The project SHOULD select an approach appropriate to its workflow.

Avoid mixing estimation systems without a clear reason.

### 10.2. Estimation Considerations

Estimates SHOULD consider:

- Implementation complexity.
- Dependencies.
- Technical uncertainty.
- Testing effort.
- Integration effort.
- Required documentation.
- Potential rework.

### 10.3. Uncertainty

When the implementation approach is unclear, create a research or investigation item before committing to a detailed implementation estimate.

Estimates SHOULD be revised when new information materially changes the expected effort.

### 10.4. Estimation and AI

AI agents MAY suggest estimates but MUST identify assumptions and uncertainty.

AI-generated estimates MUST NOT be treated as guaranteed completion times.

## 11. Dependencies and Blockers

Dependencies MUST be identified when they materially affect implementation order or feasibility.

### 11.1. Dependency Types

Examples include:

- Feature dependencies.
- Technical dependencies.
- Asset dependencies.
- Design decisions.
- External tools or services.
- Other work items.
- Platform or engine requirements.

### 11.2. Dependency Management

Work items SHOULD reference their relevant dependencies.

Avoid creating unnecessary dependency relationships between unrelated tasks.

### 11.3. Blocked Work

A blocked item SHOULD:

- Have its status updated.
- Identify the blocking condition.
- Reference the blocking work item or decision when applicable.
- Describe the action required to unblock it.

Blocked work MUST NOT be reported as actively progressing when no meaningful work can continue.

### 11.4. Dependency Changes

When a dependency changes, review affected work items and their priorities.

Significant dependency changes SHOULD be communicated to the project owner.

## 12. Backlog Status Management

Projects SHOULD use a consistent workflow to communicate work item progress.

A recommended lightweight workflow is:

| Status | Meaning |
|---|---|
| Backlog | Identified work not yet prepared for implementation |
| Ready | Sufficiently refined and available for selection |
| In Progress | Active implementation or production work |
| Blocked | Cannot progress due to an unresolved dependency or issue |
| In Review | Awaiting required review or validation |
| Done | Meets its completion and acceptance requirements |
| Cancelled | Intentionally removed from active scope |

Projects MAY use additional statuses when necessary.

### 12.1. Status Accuracy

Work item status MUST reflect actual progress.

Do not move an item to `Done` merely because implementation has started or code has been written.

Completion MUST follow the applicable acceptance criteria and `definition_of_done.md`.

### 12.2. Status Transitions

Status changes SHOULD reflect meaningful progress.

Typical transitions include:

- Backlog → Ready.
- Ready → In Progress.
- In Progress → Blocked.
- Blocked → In Progress.
- In Progress → In Review.
- In Review → In Progress.
- In Review → Done.
- Backlog or Ready → Cancelled.

Not every item requires every transition.

### 12.3. Reopened Work

A completed item MAY be reopened when:

- Acceptance criteria were not actually satisfied.
- A regression is discovered.
- Required work was omitted.
- New information invalidates the original result.

When appropriate, create a separate bug or follow-up task instead of reopening unrelated completed work.

## 13. Sprint and Milestone Planning

Projects using iterative development MAY select backlog items for sprints or development iterations.

### 13.1. Sprint Selection

Sprint work SHOULD be selected according to:

- Project priorities.
- Available capacity.
- Dependencies.
- Item readiness.
- Current milestone objectives.
- Risk and uncertainty.

Avoid committing to more work than can reasonably be completed.

### 13.2. Sprint Scope

Once a sprint begins, its scope SHOULD remain reasonably stable.

Changes MAY be necessary when:

- Critical defects are discovered.
- Important assumptions become invalid.
- Dependencies prevent planned work.
- Project priorities materially change.

Significant scope changes SHOULD be reviewed with the project owner.

### 13.3. Sprint Completion

At the end of an iteration:

- Review completed work.
- Identify incomplete work.
- Update item statuses.
- Reassess priorities.
- Record relevant findings.
- Return unfinished work to the appropriate backlog state.
- Carry forward only work that remains relevant.

Incomplete items SHOULD NOT be automatically marked as complete or copied into a new sprint without review.

### 13.4. Milestone Alignment

Backlog items SHOULD reference project milestones when this improves planning.

Milestones SHOULD represent meaningful project outcomes rather than arbitrary collections of tasks.

## 14. Bug and Defect Management

Bugs MUST be recorded with enough information to understand and investigate the problem.

### 14.1. Bug Report Requirements

A bug report SHOULD include:

- Clear title.
- Description of the problem.
- Expected behavior.
- Actual behavior.
- Reproduction steps.
- Relevant environment or engine version.
- Supporting logs, screenshots, or recordings when useful.
- Severity.
- Priority.
- Related feature or work item.

### 14.2. Severity and Priority

Severity describes the impact of the defect.

Priority describes how urgently the defect should be addressed.

These concepts SHOULD NOT be treated as interchangeable.

A minor visual issue may have low severity but high priority if it affects an imminent release. A severe issue in an unused experimental feature may have high severity but lower immediate priority.

### 14.3. Bug Resolution

Before marking a bug as Done:

- The reported behavior has been investigated.
- The fix has been implemented.
- Relevant regression testing has been performed.
- Acceptance criteria are satisfied.
- Related documentation is updated when necessary.

Bug management SHOULD follow the project's QA standards.

## 15. Technical Debt and Maintenance Work

Technical debt SHOULD be visible in the backlog when it requires future attention.

Examples include:

- Architectural limitations.
- Duplicated logic.
- Fragile implementations.
- Missing automated tests.
- Performance problems.
- Outdated dependencies.
- Incomplete documentation.
- Temporary workarounds.

Technical debt items SHOULD describe:

- The current problem.
- Its impact.
- The affected area.
- Recommended improvement.
- Risks of postponement.

Avoid using technical debt as a generic label for every code improvement.

Refactoring SHOULD have a clear purpose and preserve expected behavior unless the work explicitly changes it.

## 16. Backlog Hygiene

The backlog SHOULD remain relevant, understandable, and manageable.

### 16.1. Duplicate Items

Duplicate work items SHOULD be consolidated or linked.

Preserve relevant references and historical context when consolidating items.

### 16.2. Obsolete Items

Items that no longer contribute to project objectives SHOULD be cancelled or removed according to the project's tracking system.

Cancelled items SHOULD retain a brief reason when the decision provides useful historical context.

### 16.3. Stale Items

Items that have remained untouched for a long period SHOULD be reviewed.

Determine whether they should be:

- Kept.
- Reprioritized.
- Refined.
- Split.
- Deferred.
- Cancelled.

Do not automatically delete work merely because it is old.

### 16.4. Scope Control

New work SHOULD be evaluated against current project priorities and available capacity.

Avoid uncontrolled backlog growth caused by speculative ideas, unnecessary polish, or unvalidated feature requests.

Ideas MAY be recorded separately from actionable work until they are sufficiently understood.

### 16.5. Backlog Size

Keep the immediately actionable backlog manageable.

Detailed refinement SHOULD focus on upcoming work rather than every possible future task.

## 17. Backlog Traceability

Work items SHOULD maintain useful relationships with relevant project information.

Examples include:

- Game design specifications.
- Technical specifications.
- Architecture Decision Records.
- Feature documentation.
- Test cases.
- Defect reports.
- Pull requests.
- Commits.
- Milestones.
- Related backlog items.

Traceability SHOULD help contributors understand why work exists and how it relates to other project decisions.

Avoid unnecessary linking that creates maintenance overhead without improving understanding.

## 18. Backlog Tools and Data Management

Projects MAY use issue trackers, project management tools, structured Markdown files, or other suitable systems.

The chosen tool MUST support the project's actual workflow.

### 18.1. Tool Selection

Consider:

- Ease of use.
- Search and filtering.
- Work item relationships.
- Status management.
- Priority management.
- Version control integration.
- Automation support.
- Collaboration requirements.
- Data export and portability.

Avoid introducing complex tooling for a backlog that can be managed more simply.

### 18.2. Structured Backlog Data

When backlog information is stored in structured files or consumed by automation, maintain consistent identifiers and field definitions.

Data SHOULD be validated before automated processing.

### 18.3. Data Integrity

Backlog changes SHOULD preserve:

- Unique identifiers.
- Parent-child relationships.
- Dependency references.
- Status validity.
- Historical context where relevant.

Automated tools MUST NOT silently discard existing work items or overwrite unrelated changes.

### 18.4. Version Control

When backlog files are stored in Git:

- Changes MUST follow the project's Git workflow.
- Work item identifiers SHOULD remain stable.
- Concurrent changes MUST be handled carefully.
- Generated data SHOULD be distinguishable from authoritative source data.
- Large automated updates SHOULD be reviewed before integration.

## 19. AI-Assisted Backlog Management

AI agents MAY assist with backlog creation, refinement, prioritization suggestions, task decomposition, dependency analysis, and status reporting.

AI-assisted backlog operations MUST preserve project owner authority.

### 19.1. Context and Source of Truth

Before creating or modifying work items, agents MUST:

1. Inspect the existing backlog.
2. Read relevant project documentation.
3. Identify existing related work items.
4. Check for duplicate or conflicting work.
5. Respect approved project decisions.
6. Follow the established backlog structure and naming conventions.

### 19.2. Work Item Creation

Agents MAY draft new work items when requested.

New items SHOULD include:

- Clear titles.
- Relevant descriptions.
- Appropriate types.
- Acceptance criteria where applicable.
- Identified dependencies.
- Suggested priority.
- References to relevant documentation.

Agents SHOULD distinguish confirmed requirements from assumptions and recommendations.

### 19.3. Prioritization

Agents MAY recommend priorities based on available project context.

They MUST explain important assumptions and trade-offs.

Agents MUST NOT independently change approved project priorities when the change materially affects scope, milestones, or commitments.

### 19.4. Task Decomposition

Agents MAY break down large work items into smaller tasks.

Decomposition MUST preserve the original objective and acceptance criteria.

Avoid producing excessive subtasks that do not improve execution or tracking.

### 19.5. Status Updates

Agents MAY update work item statuses when the corresponding work has actually reached the relevant state and the agent is authorized to modify the backlog.

Agents MUST NOT:

- Mark unvalidated work as Done.
- Invent progress.
- Assume a pull request has been approved.
- Close defects without appropriate validation.
- Remove existing items without authorization.
- Rewrite backlog history without justification.

### 19.6. Reporting

After backlog modifications, agents SHOULD report:

- Items created.
- Items modified.
- Items reprioritized.
- Dependencies identified.
- Items cancelled or consolidated.
- Outstanding questions.
- Decisions requiring project owner approval.

## 20. Backlog Review Checklist

During backlog reviews, verify the applicable requirements:

- [ ] The backlog reflects current project objectives.
- [ ] Work items have clear titles and descriptions.
- [ ] Actionable items have appropriate acceptance criteria.
- [ ] Priorities reflect current needs.
- [ ] Dependencies are identified.
- [ ] Blocked items explain their blocking conditions.
- [ ] Work items have accurate statuses.
- [ ] Oversized items are appropriately decomposed.
- [ ] Duplicate and obsolete items are addressed.
- [ ] Technical debt is visible where necessary.
- [ ] Relevant documentation is referenced.
- [ ] Upcoming work is sufficiently refined.
- [ ] Milestone and sprint assignments remain relevant.
- [ ] No work has been marked complete without validation.

## 21. Exceptions

Projects MAY adapt these standards to their size, workflow, and tooling.

Exceptions SHOULD be justified when they:

- Reduce unnecessary administrative effort.
- Support a more effective development process.
- Address limitations of the selected tooling.
- Accommodate experimental or research-driven work.

Exceptions MUST NOT compromise the accuracy of work status, ownership of project decisions, or traceability of important requirements.

Significant changes to the backlog management process require project owner approval.

## 22. Related Documents

- `docs/00_studio_standards/branching_strategy.md`
- `docs/00_studio_standards/code_review_guidelines.md`
- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/documentation_standards.md`
- `docs/00_studio_standards/game_development_lifecycle.md`
- `docs/04_production_standards/`

Project-specific references SHOULD point to the corresponding game repository documents, including design specifications, technical specifications, sprint plans, milestone plans, and QA records.

## 23. Maintenance

These standards SHOULD be reviewed periodically and updated when:

- Studio production practices change.
- Backlog management becomes unnecessarily complex.
- Recurring planning or tracking problems are identified.
- New tools or automation workflows are adopted.
- AI-assisted development practices evolve.
- Improvements to work item organization or prioritization are identified.

Changes MUST preserve the distinction between reusable studio standards and project-specific planning decisions.

The project owner is responsible for approving changes to these standards.