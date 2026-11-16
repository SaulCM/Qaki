# Sprint Workflow

## 1. Purpose

This document defines the standard workflow for planning, executing, reviewing, and improving development sprints.

It establishes:

- Sprint structure and objectives.
- Sprint planning practices.
- Work selection and prioritization.
- Sprint execution and progress tracking.
- Daily coordination.
- Sprint reviews.
- Sprint retrospectives.
- Sprint completion criteria.
- AI-assisted sprint management.

The objective is to maintain a predictable development rhythm, deliver incremental value, identify problems early, and continuously improve the development process.

## 2. Scope

These guidelines apply to game development projects that organize work into time-boxed iterations.

The workflow is inspired by Scrum but is intentionally lightweight and adaptable to solo development and small teams.

Projects MAY adjust sprint duration, ceremonies, roles, and tracking practices according to their needs.

These guidelines do not require strict adherence to the complete Scrum framework.

## 3. Sprint Principles

### 3.1. Outcome-Oriented Work

Each sprint MUST have a clear objective.

The sprint objective SHOULD describe the intended outcome rather than simply list activities.

### 3.2. Incremental Development

Each sprint SHOULD produce a demonstrable increment of the game or a meaningful reduction in project uncertainty.

An increment MAY include:

- A playable feature.
- An integrated gameplay system.
- A validated technical prototype.
- Completed game content.
- A meaningful quality improvement.
- A resolved technical risk.

### 3.3. Realistic Commitment

Sprint scope SHOULD reflect available capacity, task complexity, dependencies, and uncertainty.

The objective is to establish a realistic plan, not maximize the number of tasks selected.

### 3.4. Continuous Validation

Work SHOULD be validated throughout the sprint rather than postponed until its final day.

Testing, integration, review, and documentation SHOULD be included in normal sprint work.

### 3.5. Transparency

Sprint progress, blockers, scope changes, and incomplete work MUST be visible.

Work MUST NOT be reported as complete without satisfying its acceptance criteria.

### 3.6. Continuous Improvement

Each sprint SHOULD provide opportunities to identify problems and improve the development workflow.

Process improvements SHOULD be practical, specific, and actionable.

## 4. Sprint Structure

### 4.1. Sprint Definition

A sprint is a fixed development period during which selected work is performed toward a defined objective.

Each sprint SHOULD have:

- A unique identifier.
- A start date.
- An end date.
- A sprint objective.
- A selected backlog.
- Defined capacity.
- Expected deliverables.
- Completion criteria.

### 4.2. Sprint Duration

The recommended duration is one or two weeks.

Projects MAY use longer sprints when their work requires additional investigation, integration, or validation.

Sprint duration SHOULD remain reasonably consistent to support planning and progress evaluation.

### 4.3. Sprint Boundaries

A sprint begins with sprint planning and ends with sprint review and retrospective activities.

Work MAY be prepared before a sprint begins, but selected sprint work SHOULD be evaluated against the sprint objective.

### 4.4. Sprint Identification

Use a consistent sprint identifier.

Recommended format:

`SPRINT-001`

Examples:

- `SPRINT-001`
- `SPRINT-002`
- `SPRINT-003`

Sprint identifiers MUST NOT be reused.

## 5. Sprint Roles and Responsibilities

The workflow MAY use formal Scrum roles or simplified responsibilities.

### 5.1. Project Owner

The project owner is responsible for:

- Defining and maintaining project direction.
- Establishing priorities.
- Approving significant scope changes.
- Reviewing sprint outcomes.
- Resolving priority conflicts.
- Accepting or rejecting important deliverables.
- Approving significant process changes.

In solo development, the developer and project owner MAY be the same person.

### 5.2. Developer

The developer is responsible for:

- Estimating and selecting work.
- Implementing assigned tasks.
- Following technical and design standards.
- Testing completed work.
- Reporting progress and blockers.
- Updating work item statuses.
- Participating in sprint reviews and retrospectives.

In a solo project, the developer performs all development responsibilities.

### 5.3. AI Agents

AI agents MAY assist with:

- Backlog refinement.
- Task breakdown.
- Sprint planning proposals.
- Technical investigation.
- Implementation.
- Test creation.
- Documentation.
- Progress summaries.
- Sprint review preparation.
- Retrospective analysis.

AI agents MUST follow approved project documentation and workflow rules.

They MUST NOT independently redefine sprint objectives, approve significant scope changes, or declare unverified work complete.

## 6. Backlog Preparation

Sprint planning depends on having a sufficiently refined backlog.

### 6.1. Backlog Readiness

Before selecting work, backlog items SHOULD have:

- A clear title.
- A description or objective.
- Acceptance criteria.
- Relevant dependencies.
- Priority.
- An appropriate level of detail.

Additional information MAY include:

- Estimates.
- Technical notes.
- Related features.
- Design references.
- Risks.
- Testing requirements.

### 6.2. Definition of Ready

A backlog item is considered ready for sprint selection when:

- Its objective is understood.
- Its scope is sufficiently clear.
- Acceptance criteria are defined.
- Dependencies are identified.
- Required references are available.
- The work can be reasonably estimated or investigated.

Not every item needs a detailed implementation plan before entering a sprint.

Research and investigation tasks MAY be selected specifically to resolve uncertainty.

### 6.3. Backlog Refinement

Backlog refinement SHOULD occur continuously or before sprint planning.

Activities MAY include:

- Clarifying requirements.
- Splitting oversized items.
- Reviewing priorities.
- Identifying dependencies.
- Estimating effort.
- Adding acceptance criteria.
- Identifying risks.
- Removing obsolete work.

Backlog refinement is not a separate mandatory ceremony. Its purpose is to keep upcoming work understandable and actionable.

## 7. Sprint Planning

### 7.1. Objective

Sprint planning establishes what will be worked on and how the sprint objective will be achieved.

### 7.2. Planning Inputs

Sprint planning SHOULD consider:

- Project objectives.
- Current milestones.
- Backlog priorities.
- Available capacity.
- Previous sprint outcomes.
- Outstanding defects.
- Technical dependencies.
- Identified risks.
- Required maintenance work.

### 7.3. Define the Sprint Objective

The sprint objective MUST describe the primary outcome expected by the end of the sprint.

A good objective is:

- Clear.
- Focused.
- Meaningful.
- Verifiable.
- Realistic within the sprint duration.

Example:

"Implement and validate the player's basic inventory interaction, including item pickup, storage, and removal."

Avoid objectives that only describe activity.

Weak example:

"Work on inventory tasks."

### 7.4. Select Backlog Items

Select work that contributes to the sprint objective.

Consider:

- Priority.
- Dependencies.
- Estimated effort.
- Available capacity.
- Technical uncertainty.
- Required testing.
- Work carried over from previous sprints.

Do not select work solely to fill available capacity.

### 7.5. Estimate Capacity

Sprint capacity represents the amount of work realistically available during the sprint.

Consider:

- Available development time.
- Other responsibilities.
- Expected interruptions.
- Investigation and debugging.
- Testing and review.
- Documentation.
- Maintenance activities.

For solo development, capacity SHOULD reflect actual available working time rather than an assumed full-time schedule.

### 7.6. Task Breakdown

Large backlog items SHOULD be divided into manageable tasks when useful.

Tasks SHOULD be small enough to:

- Understand their expected outcome.
- Track their progress.
- Validate their completion.
- Identify blockers.

Avoid creating unnecessary subtasks for trivial work.

### 7.7. Sprint Commitment

The selected sprint scope represents the current plan, not an unconditional guarantee.

The project owner and development team SHOULD make a realistic commitment based on available evidence.

The sprint objective SHOULD remain the primary focus even when individual tasks change.

## 8. Sprint Execution

### 8.1. Work Execution

During the sprint:

- Work SHOULD follow the established priority order.
- Tasks SHOULD be implemented incrementally.
- Dependencies SHOULD be addressed early.
- Completed work SHOULD be validated.
- Blockers SHOULD be reported promptly.
- Documentation SHOULD be updated when necessary.
- Changes SHOULD follow the approved development workflow.

### 8.2. Work in Progress

Projects SHOULD limit excessive work in progress.

Prefer completing existing work before starting unrelated tasks.

For solo development, avoid simultaneously implementing too many unfinished features.

For small teams, WIP limits MAY be established for specific workflow stages.

### 8.3. Work Item Status

Use the project's established backlog statuses.

Recommended workflow:

`Backlog → Ready → In Progress → Blocked → In Review → Done`

The Blocked and In Review statuses are conditional and do not need to occur for every task.

Additional statuses such as Cancelled MAY be used when appropriate.

### 8.4. Task Completion

A task MUST satisfy its acceptance criteria and applicable Definition of Done requirements before being marked Done.

Completion SHOULD include:

- Implementation.
- Relevant validation.
- Required review.
- Documentation updates.
- Integration into the appropriate branch.

A task is not complete merely because its code has been written.

### 8.5. Integration

Changes SHOULD be integrated continuously through the established Git workflow.

Avoid accumulating large amounts of unintegrated work until the end of the sprint.

All branch protection and pull request requirements MUST be respected.

## 9. Daily Progress Tracking

### 9.1. Objective

Daily progress tracking helps identify blockers, maintain focus, and keep the sprint objective visible.

It SHOULD be lightweight and proportional to the development setup.

### 9.2. Daily Review

At the beginning or end of a development session, review:

- What was completed.
- What remains in progress.
- What should be worked on next.
- Whether any blockers exist.
- Whether the sprint objective remains achievable.

A solo developer MAY perform this review independently.

### 9.3. Progress Updates

Work item statuses SHOULD be updated when meaningful progress occurs.

Updates SHOULD communicate actual outcomes rather than vague activity descriptions.

Example:

Weak update:

"Worked on inventory."

Better update:

"Implemented item pickup and inventory insertion. Removal behavior remains incomplete."

### 9.4. Blockers

A blocker is an issue preventing meaningful progress on a work item.

When a blocker is identified:

1. Record the blocker.
2. Describe its impact.
3. Identify the required action or dependency.
4. Assign responsibility when applicable.
5. Reassess the sprint plan if necessary.

Blockers SHOULD be resolved or escalated as early as practical.

## 10. Scope Changes During a Sprint

### 10.1. General Rule

Sprint scope SHOULD remain reasonably stable.

Minor adjustments MAY be made when they do not compromise the sprint objective.

### 10.2. Adding Work

New work MAY be added when:

- It is necessary to achieve the sprint objective.
- It addresses a critical defect.
- It resolves an important dependency.
- The project owner approves the change.
- Available capacity permits the additional work.

When new work is added, existing work SHOULD be reconsidered if the sprint capacity is exceeded.

### 10.3. Removing Work

Work MAY be removed or deferred when:

- It is no longer necessary.
- New information invalidates its original assumptions.
- Its dependencies are unavailable.
- It cannot reasonably be completed within the sprint.
- Higher-priority work requires attention.

Removed work MUST return to the backlog or receive an appropriate alternative status.

### 10.4. Changing the Sprint Objective

The sprint objective SHOULD remain stable.

If significant changes make the objective irrelevant or unachievable, the project owner MAY redefine it or terminate the sprint.

The reason for a significant change SHOULD be documented.

### 10.5. Emergency Work

Critical defects, data integrity problems, security concerns, or urgent technical incidents MAY interrupt planned sprint work.

Emergency work SHOULD be prioritized according to its impact.

The effect on the sprint objective MUST be evaluated.

## 11. Testing and Quality During a Sprint

Quality activities MUST be integrated into sprint execution.

### 11.1. Continuous Testing

Developers SHOULD validate work as it is implemented.

Depending on the feature, validation MAY include:

- Unit tests.
- Integration tests.
- Scene tests.
- Manual gameplay testing.
- Regression tests.
- Performance checks.
- Save and loading validation.

### 11.2. Code Review

Changes MUST follow applicable code review requirements.

AI-generated code MUST receive appropriate human or authorized review before integration.

### 11.3. Defect Handling

Defects discovered during the sprint SHOULD be:

- Recorded.
- Evaluated.
- Prioritized.
- Assigned or scheduled.
- Linked to the affected feature when practical.

Critical defects SHOULD be addressed before continuing dependent work.

### 11.4. Quality Expectations

Sprint completion MUST follow the studio Definition of Done.

Sprint deadlines MUST NOT justify silently bypassing required validation or quality standards.

## 12. Sprint Review

### 12.1. Objective

The sprint review evaluates the actual results of the sprint and determines what those results mean for the project.

It focuses on the increment produced, not merely the number of completed tasks.

### 12.2. Review Activities

During the sprint review:

- Demonstrate completed work.
- Compare outcomes with the sprint objective.
- Evaluate acceptance criteria.
- Review incomplete work.
- Discuss significant defects.
- Review technical or design discoveries.
- Collect feedback.
- Identify necessary backlog changes.

### 12.3. Demonstration

When practical, completed features SHOULD be demonstrated in the actual game or a representative development build.

A demonstration SHOULD show the implemented behavior rather than rely exclusively on descriptions or screenshots.

### 12.4. Incomplete Work

Incomplete work MUST NOT be reported as completed.

It SHOULD be returned to the backlog or rescheduled according to its priority and remaining work.

Partially completed work MAY be retained when its current state is useful, but its limitations MUST be clear.

### 12.5. Sprint Review Outcomes

The review SHOULD identify:

- Completed deliverables.
- Incomplete work.
- Sprint objective status.
- Important discoveries.
- Defects requiring attention.
- Feedback.
- Recommended backlog changes.
- Risks affecting upcoming work.

### 12.6. Sprint Objective Evaluation

Use one of the following outcomes:

- **Achieved:** The sprint objective was successfully achieved.
- **Partially Achieved:** Meaningful progress was made, but important parts remain incomplete.
- **Not Achieved:** The intended outcome was not achieved.

An objective MAY be achieved even when some secondary tasks remain incomplete, provided the objective's intended outcome has been delivered and validated.

## 13. Sprint Retrospective

### 13.1. Objective

The retrospective evaluates how the sprint was executed and identifies practical improvements for future work.

It focuses on the development process rather than only the delivered product.

### 13.2. Review Areas

Consider:

**What went well?**

- Effective workflows.
- Successful technical decisions.
- Productive collaboration.
- Useful automation.
- Effective testing.
- Good planning.

**What did not go well?**

- Unexpected blockers.
- Unclear requirements.
- Incorrect estimates.
- Excessive context switching.
- Rework.
- Integration problems.
- Incomplete testing.
- Ineffective AI-assisted workflows.

**What should improve?**

- Planning.
- Task breakdown.
- Documentation.
- Development practices.
- Testing.
- Tooling.
- Automation.
- Communication.
- Risk management.

### 13.3. Improvement Actions

Retrospectives SHOULD produce a small number of actionable improvements.

Each significant improvement action SHOULD define:

- Description.
- Expected benefit.
- Priority.
- Responsible owner.
- Target sprint or review date.

Improvement actions SHOULD be added to the backlog when they require meaningful work.

### 13.4. Retrospective Principles

Retrospectives MUST focus on learning and improvement rather than blame.

Observations SHOULD be based on actual events and evidence.

Avoid creating improvement actions that are too broad, vague, or difficult to evaluate.

## 14. Sprint Completion

A sprint is considered complete when its review and retrospective activities have been performed and its records have been updated.

### 14.1. Completion Requirements

Before closing a sprint:

- The sprint objective has been evaluated.
- Completed work satisfies its acceptance criteria.
- Applicable Definition of Done requirements are met.
- Incomplete work has been identified.
- Work item statuses are updated.
- Defects and blockers are recorded.
- Sprint outcomes are documented.
- Improvement actions are captured.
- The next development priorities are understood.

### 14.2. Carryover Work

Incomplete work MUST NOT automatically be considered complete or silently transferred.

It SHOULD be returned to the product backlog and reconsidered during the next planning session.

Carryover work SHOULD be reviewed to understand why it was not completed.

Possible causes include:

- Incorrect estimates.
- Unclear requirements.
- Unexpected complexity.
- External dependencies.
- Insufficient capacity.
- Scope changes.
- Technical blockers.

### 14.3. Sprint Closure

A closed sprint SHOULD preserve its historical record.

Completed sprint records MUST NOT be rewritten to make the sprint appear more successful than it was.

Corrections MAY be made when necessary, but historical outcomes SHOULD remain accurate.

## 15. Sprint Metrics

Metrics MAY help identify trends and improve planning.

They MUST NOT become substitutes for product quality, meaningful progress, or player experience.

### 15.1. Recommended Metrics

**Sprint objective completion**

Indicates whether the intended sprint outcome was achieved.

**Planned versus completed work**

Helps identify planning and capacity issues.

**Carryover work**

Shows how much selected work remained incomplete.

**Blocked work**

Helps identify dependencies and recurring obstacles.

**Defect trends**

Helps evaluate quality and stability.

**Cycle time**

Measures the time between starting and completing work.

**Rework**

Helps identify unclear requirements, design problems, or implementation issues.

### 15.2. Metric Usage

Metrics SHOULD be interpreted in context.

Avoid:

- Comparing individual productivity using raw task counts.
- Treating story points as a direct measure of value.
- Increasing estimates to manipulate velocity.
- Prioritizing task closure over quality.
- Using sprint metrics as the sole basis for performance evaluation.

### 15.3. Solo Development

Solo projects MAY use only a small set of useful indicators.

The sprint objective, completed outcomes, carryover work, and recurring blockers are often sufficient.

## 16. Sprint Documentation

Each sprint SHOULD have a concise record.

Recommended location:

`game_project/docs/production/sprints/`

Recommended filename:

`sprint-001.md`

Use lowercase kebab-case for sprint record filenames.

A sprint record SHOULD contain:

- Sprint identifier.
- Start and end dates.
- Sprint objective.
- Selected backlog items.
- Completed work.
- Incomplete work.
- Sprint review results.
- Retrospective findings.
- Improvement actions.

Detailed implementation notes, test reports, and technical decisions SHOULD remain in their appropriate project documents.

Sprint records SHOULD reference those documents rather than duplicate their contents.

## 17. Sprint Record Template

# SPRINT-001: Sprint Name

## Overview

- **Start Date:** YYYY-MM-DD
- **End Date:** YYYY-MM-DD
- **Status:** Planned / Active / Completed / Cancelled
- **Owner:** Project Owner

## Sprint Objective

Describe the primary outcome expected from this sprint.

## Selected Work

| ID | Work Item | Priority | Status |
|---|---|---|---|
| ITEM-001 | Example work item | High | Ready |

## Capacity and Planning

- Available capacity:
- Important dependencies:
- Known risks:
- Planning notes:

## Execution Summary

Describe significant progress, blockers, and scope changes.

## Completed Work

List the work completed and validated.

## Incomplete Work

List unfinished work and explain its current status.

## Sprint Review

- **Objective Status:** Achieved / Partially Achieved / Not Achieved
- **Demonstrated Increment:**
- **Feedback:**
- **Important Findings:**

## Sprint Retrospective

### What Went Well?

- 

### What Did Not Go Well?

- 

### What Should Improve?

- 

## Improvement Actions

| Action | Priority | Owner | Target |
|---|---|---|---|
| Example action | Medium | Project Owner | Next sprint |

## Risks and Blockers

List significant risks and blockers identified or updated during the sprint.

## References

Link relevant features, technical documents, test reports, and project records.

## 18. AI-Assisted Sprint Management

AI agents MAY assist throughout the sprint workflow.

### 18.1. Sprint Planning Assistance

AI agents MAY:

- Analyze backlog readiness.
- Suggest task breakdowns.
- Identify dependencies.
- Estimate complexity.
- Identify risks.
- Propose sprint scope.
- Draft sprint objectives.

All proposals MUST be reviewed before being adopted.

### 18.2. Execution Assistance

AI agents MAY:

- Implement selected work items.
- Generate tests.
- Investigate defects.
- Update documentation.
- Summarize implementation progress.
- Identify blockers.
- Report deviations from approved requirements.

Agents MUST work within the assigned task scope and established repository rules.

### 18.3. Progress Reporting

AI-generated progress reports MUST distinguish:

- Completed and verified work.
- Implemented but unvalidated work.
- Work in progress.
- Blocked work.
- Work not started.
- Unverified assumptions.

Agents MUST NOT infer task completion from the existence of code or generated files alone.

### 18.4. Sprint Review Assistance

AI agents MAY:

- Compare completed work with acceptance criteria.
- Summarize changes.
- Identify incomplete deliverables.
- Review validation results.
- Prepare sprint summaries.

### 18.5. Retrospective Assistance

AI agents MAY:

- Identify recurring blockers.
- Analyze carryover patterns.
- Compare planned and actual outcomes.
- Suggest workflow improvements.
- Identify opportunities for automation.

AI-generated observations SHOULD be checked against actual sprint records.

### 18.6. Approval and Authority

AI agents MUST NOT:

- Independently redefine sprint objectives.
- Change project priorities without authorization.
- Mark unverified work as Done.
- Approve their own significant architectural decisions.
- Modify protected branches outside the approved workflow.
- Close sprints without authorized review.
- Invent sprint metrics or historical results.

The project owner retains responsibility for sprint commitments, scope changes, and final decisions.

## 19. Exceptions

Projects MAY adapt the sprint workflow according to:

- Team size.
- Development methodology.
- Project complexity.
- Experimental work.
- Available capacity.
- Production constraints.

Solo projects MAY combine planning, review, and retrospective activities into a single personal review session.

The purpose of the workflow is to improve delivery and learning, not to create unnecessary administrative work.

Significant deviations SHOULD be documented when they affect project planning or accountability.

## 20. Related Documents

- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/BRANCHING_STRATEGY.md`
- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/GAME_DEVELOPMENT_LIFECYCLE.md`
- `docs/04_production_standards/BACKLOG_MANAGEMENT.md`
- `docs/04_production_standards/MILESTONE_GUIDELINES.md`
- `docs/04_production_standards/PROJECT_LIFECYCLE.md`
- `docs/04_production_standards/RISK_MANAGEMENT.md`
- `docs/04_production_standards/POSTMORTEM_GUIDELINES.md`

## 21. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- Sprint workflows change.
- Development methodologies evolve.
- Recurring planning problems are identified.
- New tools improve sprint tracking.
- Retrospectives reveal opportunities for improvement.

Changes MUST preserve the distinction between reusable studio sprint practices and project-specific sprint plans.

The project owner is responsible for approving changes to these guidelines.