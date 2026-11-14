# Update Project Status

## 1. Purpose

This workflow defines how an AI agent should evaluate and update the current status of a game development project.

The objective is to maintain an accurate, traceable, and up-to-date representation of project progress, completed work, active tasks, milestones, risks, blockers, and upcoming priorities.

Project status updates must reflect actual development progress rather than assumptions, optimistic estimates, or outdated plans.

## 2. Scope

Use this workflow when:

- Updating the overall project status.
- Reporting development progress.
- Updating milestone status.
- Updating roadmap progress.
- Synchronizing backlog statuses.
- Recording completed features.
- Recording blocked or delayed work.
- Updating project risks.
- Preparing progress reports.
- Reviewing project health.
- Updating sprint or production records.
- Preparing milestone reviews.

Do not use this workflow for:

- Implementing features.
- Changing approved project scope.
- Reprioritizing work without authorization.
- Approving milestones.
- Changing release decisions.
- Replacing sprint planning.
- Replacing postmortem analysis.
- Reporting unverified progress as completed.

## 3. Authoritative References

Before updating project status, inspect the relevant studio standards and project documentation.

### 3.1 Studio references

Relevant references include:

- `docs/00_studio_standards/documentation_standards.md`
- `docs/00_studio_standards/definition_of_done.md`
- `docs/04_production_standards/backlog_management.md`
- `docs/04_production_standards/milestone_guidelines.md`
- `docs/04_production_standards/project_lifecycle.md`
- `docs/04_production_standards/risk_management.md`
- `docs/04_production_standards/sprint_workflow.md`
- `docs/04_production_standards/versioning_standards.md`

Read only the references relevant to the requested update.

### 3.2 Project references

Inspect available project-specific records, prioritizing:

- Project overview or status document.
- Project roadmap.
- Milestone records.
- Backlog.
- Sprint records.
- Risk register.
- Release records.
- Recent postmortems.
- Relevant feature specifications.
- Relevant implementation and test results.
- Git repository state and recent changes.
- Documentation inventory.

The actual repository and available evidence are authoritative for determining what exists and what has been completed.

Do not assume that every referenced project document exists.

## 4. Workflow Overview

Follow these stages:

1. Understand the status update request.
2. Inspect project documentation and repository state.
3. Establish the current project baseline.
4. Collect and verify progress evidence.
5. Evaluate task and feature completion.
6. Evaluate milestone progress.
7. Evaluate project health and risks.
8. Identify blockers and dependencies.
9. Determine upcoming priorities.
10. Update relevant project records.
11. Validate status consistency.
12. Produce a project status report.

Adapt the update depth to the requested reporting scope.

A small progress update should not require rewriting the entire project roadmap or production documentation.

## 5. Stage 1: Understand the Status Update Request

Determine the requested reporting scope.

Identify whether the user wants to update:

- Overall project status.
- A specific milestone.
- A sprint.
- A feature.
- The project roadmap.
- The backlog.
- Project risks.
- Release readiness.
- A complete project progress report.

Establish:

- Reporting period.
- Current project phase.
- Relevant milestone.
- Intended audience.
- Required level of detail.
- Target documentation.
- Whether changes to existing records are authorized.

If the reporting period is unspecified, use the current available project information and clearly state the reporting date.

Do not invent a reporting period or claim that an event occurred during a period without supporting evidence.

## 6. Stage 2: Inspect Project Documentation and Repository State

Inspect the current project records before making changes.

### 6.1 Documentation inspection

Review available:

- Project overview.
- Roadmap.
- Milestone records.
- Backlog.
- Sprint records.
- Risk register.
- Release documentation.
- Recent postmortems.
- Project status reports.

Identify:

- Existing status.
- Planned work.
- Completed work.
- In-progress work.
- Blocked work.
- Outstanding decisions.
- Previous progress reports.
- Outdated information.

### 6.2 Repository inspection

Inspect the actual project repository when relevant.

Check:

- Current branch.
- Working tree.
- Recent commits.
- Merged changes.
- Relevant pull requests, if accessible.
- Existing project files.
- Implemented features.
- Automated tests.
- Build or export results.
- Recent technical changes.

Git history is useful evidence, but a commit alone does not prove that a feature is complete.

Likewise, the presence of a file does not prove that its functionality is implemented or validated.

### 6.3 Preserve repository state

The agent MUST NOT:

- Discard uncommitted changes.
- Reset branches.
- Rewrite Git history.
- Merge branches.
- Modify protected branches.
- Change implementation code as part of a status update unless explicitly requested.

Status reporting should be read-only with respect to implementation.

## 7. Stage 3: Establish the Current Project Baseline

Determine the project's current state before calculating or describing progress.

Identify:

- Project lifecycle phase.
- Current milestone.
- Active sprint, if applicable.
- Current project objectives.
- Approved scope.
- Completed deliverables.
- Remaining deliverables.
- Current risks.
- Known blockers.
- Upcoming decisions.

### 7.1 Project lifecycle phase

Use the established project lifecycle:

1. Initiation.
2. Concept.
3. Pre-production.
4. Prototyping and Validation.
5. Production.
6. Alpha.
7. Beta.
8. Release Candidate.
9. Release.
10. Post-release.

A project may adapt or combine phases according to its size and development approach.

Do not advance the project lifecycle phase simply because a calendar date has passed.

Phase transitions should reflect their actual objectives and exit criteria.

### 7.2 Project status

Use a concise overall status classification:

- **Not Started:** Development has not meaningfully begun.
- **On Track:** Progress is consistent with current objectives and expectations.
- **At Risk:** Potential issues may affect scope, quality, or target dates.
- **Blocked:** A significant dependency or unresolved issue prevents meaningful progress.
- **Completed:** The defined project scope or reporting objective has been completed.
- **On Hold:** Development has been intentionally paused.
- **Cancelled:** The project has been formally discontinued.

The overall project status should reflect the most important current conditions, not an average of individual task statuses.

A project can have completed tasks and still be blocked by a critical dependency.

## 8. Stage 4: Collect and Verify Progress Evidence

Gather evidence for the work being reported.

Possible evidence includes:

- Approved pull requests.
- Merged commits.
- Implemented project files.
- Automated test results.
- Successful builds or exports.
- Demonstrated runtime behavior.
- Approved design documents.
- Completed milestone deliverables.
- Verified sprint outcomes.
- Playtesting results.
- Human confirmation.

### 8.1 Evidence classification

Classify relevant information as:

- **Verified:** Directly confirmed through repository inspection, execution, test results, or other reliable evidence.
- **Reported:** Explicitly stated by the user or an authorized project contributor but not independently verified.
- **Derived:** Calculated or inferred from verified information.
- **Planned:** Intended future work.
- **Assumed:** Based on an unverified assumption.
- **Unknown:** Information that cannot currently be established.

Do not present reported, planned, assumed, or unknown information as independently verified.

### 8.2 Evidence requirements

For every significant progress claim, determine:

- What was completed.
- When it was completed, if known.
- Which deliverable was affected.
- What evidence supports completion.
- Whether validation was performed.
- Whether approval is required.
- Whether outstanding work remains.

### 8.3 Completion evidence

A task should not be marked complete merely because:

- Its implementation was started.
- Its files were created.
- A commit exists.
- A pull request was opened.
- A design proposal was written.
- An AI agent reported success.
- A test was written but not executed.

Use the project's Definition of Done and applicable acceptance criteria to establish completion.

If evidence is insufficient, preserve the existing status or mark the item as needing verification.

## 9. Stage 5: Evaluate Task and Feature Completion

Review relevant backlog items and feature records.

### 9.1 Backlog statuses

Use the established backlog statuses:

- Backlog.
- Ready.
- In Progress.
- Blocked.
- In Review.
- Done.
- Cancelled.

Verify whether each status accurately reflects the work.

Examples:

- Implementation underway: In Progress.
- Work waiting on a dependency: Blocked.
- Pull request awaiting review: In Review.
- Acceptance criteria satisfied and completion requirements met: Done.

Do not mark an item Done if required implementation, validation, review, or acceptance remains incomplete.

### 9.2 Feature progress

Evaluate each feature against its approved scope.

Consider:

- Design completion.
- Implementation completion.
- Integration.
- Testing.
- Documentation.
- Acceptance criteria.
- Outstanding defects.
- Dependencies.

Distinguish between:

- Designed.
- Prototyped.
- Implemented.
- Integrated.
- Tested.
- Accepted.

These states are not interchangeable.

### 9.3 Partial completion

When a feature is only partially implemented:

- Identify completed components.
- Identify remaining components.
- Identify unverified behavior.
- Record known limitations.
- Preserve the appropriate backlog status.

Do not report an entire feature as complete because one component is finished.

## 10. Stage 6: Evaluate Milestone Progress

Review the active and upcoming milestones.

For each milestone, inspect:

- Objective.
- Scope.
- Deliverables.
- Acceptance criteria.
- Dependencies.
- Target dates, if established.
- Completed work.
- Remaining work.
- Risks.
- Current status.

### 10.1 Milestone statuses

Use the established milestone statuses:

- Planned.
- Ready.
- In Progress.
- At Risk.
- Blocked.
- Completed.
- Cancelled.

Determine status based on actual progress and milestone conditions.

### 10.2 Milestone completion

A milestone should be marked Completed only when:

- Required deliverables are completed.
- Acceptance criteria are satisfied.
- Required validation has been performed.
- Outstanding blockers are resolved or formally accepted.
- Required approval has been obtained.

If some deliverables are incomplete, do not report the milestone as completed.

### 10.3 Milestone progress calculation

When meaningful estimates are available, calculate progress using weighted completion:

\[
P = \frac{\sum_{i=1}^{n} w_i c_i}{\sum_{i=1}^{n} w_i}\times 100
\]

Where:

- \(P\) = overall progress percentage.
- \(w_i\) = estimated weight of deliverable \(i\).
- \(c_i\) = completion value of deliverable \(i\), between 0 and 1.
- \(n\) = number of deliverables.

Use consistent and documented weights.

If no reliable weights exist, use an unweighted calculation only when deliverables have comparable scope.

Do not invent percentages to make progress appear more precise.

If meaningful progress cannot be calculated, report completed and remaining deliverables instead.

### 10.4 Schedule assessment

When target dates and actual progress are available, evaluate schedule health.

Consider:

- Remaining scope.
- Outstanding dependencies.
- Current blockers.
- Available capacity.
- Previous delays.
- Required validation.
- Expected remaining effort.

Do not automatically change target dates.

Schedule changes require appropriate authorization and should be reflected in the relevant production records.

## 11. Stage 7: Evaluate Project Health and Risks

Assess the project's overall health.

Consider:

- Scope.
- Schedule.
- Quality.
- Technical stability.
- Production capacity.
- Dependencies.
- Team or contributor availability.
- Asset production.
- Testing readiness.
- Release readiness.

### 11.1 Risk register

Inspect the project's risk register when available.

Identify:

- New risks.
- Existing risks.
- Changed likelihood.
- Changed impact.
- Mitigation progress.
- Residual risk.
- Resolved risks.
- Risks requiring escalation.

Do not mark a risk as resolved without evidence.

If a new risk is identified, record it in the appropriate risk register when authorized.

### 11.2 Risk and issue distinction

Maintain the distinction:

- **Risk:** An uncertain event that may affect project objectives.
- **Issue:** A problem that has already occurred.
- **Blocker:** An issue or dependency preventing progress.

A risk that materializes should be evaluated as an issue and tracked appropriately.

### 11.3 Project health indicators

Evaluate the following dimensions:

| Dimension | Evaluation |
|---|---|
| Scope | Is the project scope controlled and understood? |
| Schedule | Is progress consistent with current expectations? |
| Quality | Are deliverables meeting quality requirements? |
| Technical | Are important technical risks controlled? |
| Production | Are dependencies and resources manageable? |
| Validation | Is sufficient testing and player validation occurring? |

Use evidence-based assessments rather than arbitrary numerical scores.

## 12. Stage 8: Identify Blockers and Dependencies

Identify anything preventing or threatening progress.

For each blocker, record:

- Description.
- Affected task or milestone.
- Impact.
- Responsible owner, if known.
- Required resolution.
- Dependencies.
- Current status.

Distinguish between:

- Technical blockers.
- Design decisions.
- Missing assets.
- External dependencies.
- Testing limitations.
- Production capacity.
- Approval requirements.
- Tooling or infrastructure problems.

### 12.1 Dependency analysis

Review relationships between:

- Features.
- Systems.
- Milestones.
- Assets.
- Technical infrastructure.
- External services.
- Decisions.

Identify dependencies that may affect the critical path.

Do not assign responsibility to a person or contributor unless ownership is established.

## 13. Stage 9: Determine Upcoming Priorities

Identify the most relevant next actions based on:

- Project objectives.
- Approved roadmap.
- Current milestone.
- Backlog priorities.
- Critical dependencies.
- Risks.
- Blockers.
- Required decisions.
- Quality requirements.

### 13.1 Priority recommendations

Prioritize work that:

- Removes critical blockers.
- Reduces major risks.
- Enables dependent features.
- Satisfies milestone objectives.
- Resolves significant defects.
- Validates uncertain design assumptions.
- Improves project stability.

Distinguish recommendations from approved priorities.

### 13.2 Scope and schedule boundaries

The agent may recommend:

- Reordering work.
- Splitting tasks.
- Deferring lower-priority work.
- Reducing scope.
- Adding validation.
- Revising estimates.

The agent MUST NOT independently:

- Change approved project scope.
- Cancel milestones.
- Change target release dates.
- Reprioritize committed work.
- Remove approved deliverables.

Obtain human authorization for significant production changes.

## 14. Stage 10: Update Relevant Project Records

Update only the documents affected by the status changes.

Possible project records include:

- `game_project/docs/production/project_status.md`
- `game_project/docs/production/roadmap.md`
- `game_project/docs/production/backlog.md`
- `game_project/docs/production/risk_register.md`
- `game_project/docs/production/milestones/`
- `game_project/docs/production/sprints/`
- `game_project/docs/production/releases/`

These are suggested locations. Verify the actual project structure and existing filenames before modifying anything.

### 14.1 Project status document

When a project status document exists, maintain information such as:

- Project name.
- Reporting date.
- Current lifecycle phase.
- Overall project status.
- Current milestone.
- Recent accomplishments.
- Work in progress.
- Upcoming priorities.
- Blockers.
- Risks.
- Important decisions.
- Schedule observations.
- Next review point.

Keep the document concise and focused on the current state.

### 14.2 Roadmap updates

Update the roadmap only when progress or approved changes affect its milestones, priorities, or direction.

Distinguish:

- Completed outcomes.
- Active work.
- Upcoming work.
- Proposed changes.
- Deferred or cancelled work.

Do not turn the roadmap into a duplicate backlog.

### 14.3 Backlog updates

Update individual work item statuses only when supported by evidence.

Do not rewrite task descriptions or change priorities unless necessary and authorized.

### 14.4 Milestone updates

Update milestone records when deliverables, progress, risks, dependencies, or approval status change.

Preserve milestone history and previous decisions.

### 14.5 Sprint updates

Update sprint records when the sprint has relevant new information, such as:

- Completed work.
- Incomplete work.
- Blockers.
- Scope changes.
- Sprint outcomes.
- Retrospective actions.

Do not mark an active sprint complete merely because its target date has passed.

### 14.6 Risk register updates

Record new or changed risks only when the information is sufficiently established.

Preserve risk history and distinguish unresolved issues from mitigated risks.

## 15. Stage 11: Validate Status Consistency

After updating project records, verify that they agree.

Check consistency between:

- Overall project status.
- Lifecycle phase.
- Roadmap.
- Milestones.
- Backlog.
- Sprint records.
- Risk register.
- Release records.
- Actual implementation.
- Test and validation evidence.

### 15.1 Consistency examples

Examples of inconsistencies to identify:

- A milestone is Completed while required deliverables remain unfinished.
- A feature is marked Done while acceptance criteria are not satisfied.
- A roadmap reports a feature as complete while its implementation is still in progress.
- A project is marked On Track despite an unresolved critical blocker.
- A release is marked ready without required validation.
- A risk is marked resolved without supporting evidence.

Do not silently reconcile contradictory records when doing so requires an unapproved decision.

### 15.2 Documentation inventory

If documentation files are created, renamed, moved, deprecated, or deleted, update:

`docs/DOCUMENTATION_INVENTORY.md`

Register only files that actually exist.

Follow `update_documentation.md` for documentation maintenance requirements.

## 16. Stage 12: Produce a Project Status Report

Prepare a concise report that accurately communicates the current project state.

The report should distinguish:

- Completed work.
- Work in progress.
- Planned work.
- Reported but unverified work.
- Blocked work.
- Risks.
- Decisions required.

Avoid presenting estimates as facts or treating planned work as completed progress.

## 17. Special Cases

### 17.1 Missing project records

If expected project records are missing:

1. Inspect the repository for equivalent documents.
2. Check whether the information is maintained elsewhere.
3. Avoid creating duplicate records.
4. Identify the missing information.
5. Create a new status document only when appropriate and authorized.

### 17.2 Conflicting project information

When records conflict:

1. Identify the inconsistency.
2. Inspect the source documents.
3. Check approval status and revision history.
4. Verify actual implementation or production evidence.
5. Determine whether the conflict can be resolved.
6. Ask the user when a decision is necessary.

Do not silently select the most optimistic status.

### 17.3 Stale status information

If existing records have not been updated recently:

- Identify the last known update.
- Verify current progress where possible.
- Distinguish current evidence from historical information.
- Avoid assuming that old tasks remain active.
- Report information that cannot be verified.

### 17.4 Project on hold or cancelled

When a project is on hold or cancelled:

- Record the authorized status.
- Preserve completed work and historical records.
- Identify outstanding work.
- Document relevant risks and dependencies.
- Avoid presenting the project as actively progressing.
- Preserve the reason and decision history when available.

### 17.5 No measurable progress

If no meaningful progress has occurred:

- Report that no verified progress was identified.
- Identify relevant blockers or missing evidence.
- Preserve existing statuses unless a change is justified.
- Do not invent completed tasks or percentages.

## 18. Completion Criteria

The project status update is complete when:

- The reporting request and scope are understood.
- Relevant production standards have been inspected.
- Existing project records have been reviewed.
- The current project baseline has been established.
- Progress claims are supported by evidence.
- Task and feature statuses have been evaluated.
- Milestone progress has been assessed.
- Project health and risks have been considered.
- Blockers and dependencies have been identified.
- Upcoming priorities have been established.
- Relevant project records have been updated.
- Status consistency has been checked.
- Unverified information and unresolved issues have been reported.

Completion of this workflow does not imply approval of proposed scope, schedule, or production changes.

## 19. AI Agent Rules

The agent MUST:

- Inspect actual project documentation and repository state.
- Use verifiable evidence for progress claims.
- Distinguish completed, in-progress, planned, reported, and unverified work.
- Follow the project's Definition of Done.
- Respect approved milestones and scope.
- Preserve historical production records.
- Use established status classifications.
- Update only relevant documents.
- Maintain consistency across project records.
- Identify risks and blockers.
- Report missing or conflicting information.
- Obtain human authorization for significant production changes.
- Report validation limitations accurately.

The agent MUST NOT:

- Invent progress.
- Invent completion dates.
- Treat commits as proof of completed features.
- Treat generated files as proof of functional implementation.
- Mark tasks Done without sufficient evidence.
- Mark milestones Completed without satisfying their exit criteria.
- Change approved scope or target dates without authorization.
- Hide blockers or risks.
- Use arbitrary progress percentages.
- Modify implementation code during a status update unless explicitly requested.
- Claim that project status is verified when important information is unavailable.

## 20. Final Report Format

After completing the workflow, provide the following report:

### Project Status Report

**Project:** [Project name]

**Reporting date:** [Date]

**Reporting period:** [Period or Not Specified]

**Current lifecycle phase:** [Phase]

**Overall project status:** Not Started / On Track / At Risk / Blocked / Completed / On Hold / Cancelled

**Current milestone:** [Milestone or None]

**Progress summary:**

- Completed: [Verified accomplishments]
- In Progress: [Active work]
- Planned: [Upcoming work]
- Blocked: [Blocked work]
- Unverified: [Reported but unverified progress]

**Milestone status:**
- [Milestone]: [Status and progress, if measurable]

**Project health:**
- Scope: [Assessment]
- Schedule: [Assessment]
- Quality: [Assessment]
- Technical: [Assessment]
- Production: [Assessment]
- Validation: [Assessment]

**Risks:** [Important risks or None]

**Blockers:** [Important blockers or None]

**Upcoming priorities:**
1. [Priority]
2. [Priority]
3. [Priority]

**Decisions required:** [Decisions or None]

**Documents updated:**
- [Paths and summary]

**Evidence limitations:** [Missing or unverified information, or None]

**Recommended next steps:** [Actions]

**Human approval required:** Yes / No

Report only changes actually made and progress supported by available evidence.