# Fix Bug

## 1. Purpose

This workflow defines how an AI agent should investigate, diagnose, fix, and validate software defects in the game project.

The objective is to resolve bugs systematically while minimizing regressions, preserving existing functionality, and maintaining the project's architectural and quality standards.

A bug fix must address the underlying cause whenever reasonably possible rather than merely hiding its symptoms.

## 2. Scope

Use this workflow when:

- Fixing a confirmed software defect.
- Investigating unexpected game behavior.
- Resolving runtime errors or crashes.
- Correcting incorrect gameplay logic.
- Fixing UI or interaction defects.
- Resolving scene, resource, or asset loading problems.
- Fixing save/load or data persistence defects.
- Correcting performance regressions.
- Resolving integration problems between gameplay systems.
- Addressing defects discovered through automated tests or playtesting.

Do not use this workflow for:

- Implementing new features.
- Making unrelated refactors.
- Changing intended gameplay behavior without authorization.
- Performing general code cleanup.
- Redesigning a system to address a problem that has not been confirmed.

If an issue is actually a feature request, design change, or improvement rather than a defect, explain the distinction and recommend the appropriate workflow.

## 3. Authoritative References

Before investigating or modifying the project, inspect the relevant studio standards.

### 3.1 Studio references

Relevant references include:

- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/code_review_guidelines.md`
- `docs/00_studio_standards/branching_strategy.md`
- `docs/00_studio_standards/development_philosophy.md`
- `docs/00_studio_standards/documentation_standards.md`
- `docs/02_technical_standards/architecture_guidelines.md`
- `docs/02_technical_standards/gdscript_standards.md`
- `docs/02_technical_standards/testing_strategy.md`
- `docs/02_technical_standards/performance_guidelines.md`
- `docs/02_technical_standards/resource_management.md`
- `docs/05_qa_standards/bug_reporting.md`
- `docs/05_qa_standards/regression_testing.md`

Read only the references relevant to the defect.

### 3.2 Project references

Inspect available project documentation, prioritizing:

- The bug report or issue description.
- Relevant gameplay system specifications.
- Relevant mechanic specifications.
- Technical design documents.
- Existing test cases.
- Related automated tests.
- Relevant architecture decisions.
- Previous bug fixes or documented workarounds.

The agent MUST inspect the actual project structure and existing implementation before making changes.

## 4. Workflow Overview

Follow these stages:

1. Understand the bug report.
2. Inspect project context.
3. Reproduce the defect.
4. Investigate and identify the root cause.
5. Determine the appropriate fix.
6. Implement the fix.
7. Create or update regression tests.
8. Validate the changes.
9. Review the changes for unintended consequences.
10. Report the results.

Do not skip reproduction or validation without documenting why they are not possible.

The investigation effort should be proportional to the defect's severity, complexity, and risk.

## 5. Stage 1: Understand the Bug Report

Read the available bug report and extract the relevant information.

Identify:

- Bug ID, if available.
- Bug title.
- Description.
- Expected behavior.
- Actual behavior.
- Reproduction steps.
- Frequency and reproducibility.
- Affected feature or system.
- Affected platform or environment.
- Build or project version.
- Severity and priority.
- Screenshots, videos, logs, or other evidence.
- Relevant recent changes.

### 5.1 Clarify expected behavior

Determine what the game should do.

Use the following sources in order of relevance:

1. Approved gameplay and technical specifications.
2. Approved acceptance criteria.
3. Existing automated tests and documented expected behavior.
4. Established behavior in the current implementation.
5. User-provided clarification.

Do not assume that unexpected behavior is necessarily a bug. It may be intentional behavior that is poorly documented.

If the intended behavior is ambiguous, ask the user before making a potentially significant gameplay or architectural change.

### 5.2 Assess impact

Understand the defect's potential consequences.

Consider:

- Player experience.
- Gameplay progression.
- Save data integrity.
- Crashes and application stability.
- Other affected systems.
- Performance.
- Security or data exposure.
- Frequency and reproducibility.
- Availability of workarounds.

Respect the severity and priority recorded in the bug report. Do not silently change its classification.

## 6. Stage 2: Inspect Project Context

Examine the relevant source code and project structure.

Inspect:

- Related GDScript files.
- Related scenes and nodes.
- Resources and configuration data.
- Autoloads and shared services.
- Signals and event connections.
- Relevant feature dependencies.
- Existing tests.
- Git history when useful.
- Recent changes affecting the behavior.

### 6.1 Understand the implementation

Determine:

- Which feature owns the affected functionality.
- Which components participate in the behavior.
- Where relevant state is stored.
- How data flows through the system.
- Which methods or signals trigger the behavior.
- Whether the behavior depends on scene lifecycle or resource loading.
- Whether the issue crosses feature boundaries.

Do not modify files before understanding their responsibilities.

### 6.2 Check recent changes

When appropriate, inspect:

- Recent commits.
- Changes to affected files.
- Recent refactors.
- Configuration changes.
- Dependency or engine version changes.
- Changes to related tests.

Use Git history as investigation evidence, not as proof of causation.

## 7. Stage 3: Reproduce the Defect

Attempt to reproduce the reported behavior.

Follow the original reproduction steps as closely as possible.

Record:

- Preconditions.
- Test environment.
- Actions performed.
- Expected result.
- Actual result.
- Error messages or logs.
- Reproduction frequency.

### 7.1 Reproduction status

Classify the result:

- **Reproduced:** The reported defect occurred.
- **Partially Reproduced:** Related behavior occurred, but the exact defect was not reproduced.
- **Not Reproduced:** The reported defect did not occur.
- **Blocked:** Required information, environment, assets, or dependencies are unavailable.
- **Not Applicable:** Reproduction is unnecessary for the particular change, with justification.

### 7.2 When reproduction fails

If the defect cannot be reproduced:

1. Verify the reproduction steps.
2. Check project and engine versions.
3. Examine available logs and evidence.
4. Check environment-specific conditions.
5. Inspect relevant code paths.
6. Identify missing information.

Do not invent a reproduction result.

If the evidence is insufficient to identify the problem safely, request additional information rather than implementing a speculative fix.

## 8. Stage 4: Investigate and Identify the Root Cause

Investigate the defect systematically.

Consider possible causes such as:

- Incorrect conditions or calculations.
- Invalid assumptions.
- Incorrect state transitions.
- Unexpected null or missing references.
- Incorrect signal connections.
- Lifecycle or initialization problems.
- Resource loading failures.
- Incorrect node paths.
- Scene ownership problems.
- Data serialization or deserialization errors.
- Race conditions or timing problems.
- Incorrect input handling.
- Unexpected interactions between systems.
- Performance bottlenecks.
- Engine-specific behavior.
- Configuration or platform differences.

### 8.1 Root cause analysis

Establish a connection between the observed symptom and the underlying cause.

Use appropriate investigation techniques:

- Debugger inspection.
- Breakpoints.
- Logging.
- Assertions.
- Test isolation.
- Input and state tracing.
- Git history.
- Minimal reproduction projects.
- Performance profiling.
- Data inspection.

For complex defects, consider a minimal reproduction or a sequence of hypotheses and experiments.

### 8.2 Root cause documentation

Record:

- Observed symptom.
- Identified root cause.
- Evidence supporting the diagnosis.
- Affected components.
- Conditions that trigger the defect.
- Potential consequences.
- Remaining uncertainty.

If the root cause cannot be established, explicitly state what remains unknown.

Do not present an unverified hypothesis as a confirmed root cause.

## 9. Stage 5: Determine the Appropriate Fix

Before modifying the project, define the proposed correction.

Consider:

- The smallest change that correctly resolves the defect.
- Whether the fix belongs in the affected feature.
- Whether other components are affected.
- Whether existing functionality must be preserved.
- Whether data migration or compatibility is necessary.
- Whether the fix introduces additional dependencies.
- Whether a regression test is needed.
- Whether documentation requires an update.

### 9.1 Fix principles

Prefer fixes that:

- Address the root cause.
- Preserve existing intended behavior.
- Respect feature ownership.
- Minimize unrelated changes.
- Follow established coding conventions.
- Maintain clear responsibilities.
- Include appropriate tests.
- Avoid introducing unnecessary abstractions.

Do not use broad refactoring as a substitute for a targeted bug fix.

### 9.2 High-risk changes

Request human approval before proceeding when a fix would:

- Change approved gameplay rules.
- Modify save data formats or migration behavior.
- Change public interfaces used by multiple systems.
- Introduce significant architectural changes.
- Modify shared infrastructure with broad impact.
- Remove existing functionality.
- Affect security or sensitive data handling.
- Require significant changes outside the reported defect.

A small code change can still have significant system-wide consequences.

## 10. Stage 6: Implement the Fix

Implement the approved correction.

### 10.1 Implementation requirements

The agent MUST:

- Modify only files necessary for the fix.
- Follow GDScript and architecture standards.
- Preserve existing naming conventions.
- Respect feature boundaries.
- Maintain clear ownership of state and behavior.
- Handle relevant error conditions.
- Avoid hardcoded workarounds unless explicitly justified.
- Keep changes focused and understandable.
- Preserve unrelated user changes.

### 10.2 Code quality

Verify that the implementation:

- Resolves the identified root cause.
- Does not introduce duplicate logic.
- Does not create unnecessary coupling.
- Does not introduce circular dependencies.
- Uses appropriate types and validation.
- Handles relevant edge cases.
- Does not generate avoidable runtime warnings or errors.

Do not suppress errors or warnings merely to make the output appear clean.

### 10.3 Preserve existing work

Before editing:

- Inspect the Git working tree.
- Identify uncommitted user changes.
- Avoid overwriting unrelated modifications.
- Do not discard or reset user work.
- Do not perform destructive Git operations without explicit authorization.

Keep the fix isolated from unrelated changes.

## 11. Stage 7: Create or Update Regression Tests

Add or update tests to prevent the defect from returning.

### 11.1 Test requirements

When practical, create a test that:

1. Establishes the conditions that previously triggered the defect.
2. Executes the relevant behavior.
3. Verifies the expected result.
4. Fails against the defective implementation.
5. Passes after the correction.

Prefer a focused test that directly validates the root cause.

### 11.2 Test selection

Choose appropriate test levels:

- **Unit tests:** Validate isolated functions, calculations, and rules.
- **Integration tests:** Validate interactions between components or systems.
- **Scene tests:** Validate scene initialization, node behavior, and scene-level interactions.
- **End-to-end tests:** Validate important player-facing flows.
- **Manual tests:** Validate behavior that cannot be adequately automated.

Follow `docs/02_technical_standards/testing_strategy.md` and `docs/05_qa_standards/regression_testing.md`.

### 11.3 Test limitations

If a regression test cannot reasonably be automated:

- Explain why.
- Identify the manual validation steps.
- Document the expected result.
- Report the remaining testing limitation.

Do not claim regression coverage without evidence.

## 12. Stage 8: Validate the Changes

Run the appropriate validation procedures.

### 12.1 Functional validation

Verify:

- The original defect no longer occurs.
- Expected behavior is restored.
- Related functionality still works.
- Important edge cases behave correctly.
- The fix does not introduce new defects.

### 12.2 Automated validation

Run relevant:

- Unit tests.
- Integration tests.
- Scene tests.
- End-to-end tests.
- Regression tests.
- Static analysis or linting tools, when available.

### 12.3 Godot validation

Where applicable, verify:

- The project opens successfully.
- GDScript parses without errors.
- Scenes load correctly.
- Resources resolve correctly.
- Relevant gameplay flows work.
- No new runtime errors or unexpected warnings appear.
- Export or build validation succeeds when relevant.

Use the project's configured Godot version and testing tools.

### 12.4 Performance validation

For performance-related defects, compare behavior before and after the fix when a baseline is available.

Check relevant:

- CPU usage.
- GPU usage.
- Memory consumption.
- Frame time.
- Loading time.
- Physics processing.
- Resource allocation.

Avoid claiming a performance improvement without measurements or reproducible evidence.

### 12.5 Validation results

Report each relevant check as:

- **Passed:** Executed successfully.
- **Failed:** Executed and did not meet expectations.
- **Not Run:** Not executed.
- **Blocked:** Could not execute due to an identified limitation.
- **Not Applicable:** Not relevant to the fix.

Never report a test as passed if it was not executed.

## 13. Stage 9: Review for Regressions and Unintended Changes

Inspect the complete change set.

Check:

- Modified files.
- Added or removed files.
- Unrelated changes.
- Public interface changes.
- Feature dependencies.
- Data ownership.
- Resource references.
- Scene and node references.
- Test coverage.
- Documentation updates.
- Potential performance impact.

Run `git diff` and inspect the changes before declaring the fix ready.

### 13.1 Regression review

Determine whether the fix affects:

- Other mechanics.
- Other gameplay systems.
- Existing player progression.
- Save compatibility.
- Input behavior.
- UI interactions.
- Scene transitions.
- Resource loading.
- Other platforms.

Run additional regression tests when the change has broader impact.

### 13.2 Scope review

Ensure the implementation does not contain:

- Unrelated refactoring.
- Unrequested feature work.
- Temporary debugging code.
- Unused files.
- Unnecessary configuration changes.
- Accidental asset modifications.
- Hardcoded test data.
- Generated files that should not be committed.

## 14. Stage 10: Report the Results

Present a concise bug-fix report.

Include:

- Bug ID and title.
- Original symptoms.
- Reproduction result.
- Root cause.
- Implemented correction.
- Modified files.
- Tests added or updated.
- Validation results.
- Regression risks.
- Remaining limitations.
- Recommended next steps.

If the bug report is tracked in the project's issue management process, provide the information needed to update its status.

Do not close the bug automatically unless the user has authorized that action and the issue management workflow supports it.

## 15. Git and Branching Requirements

Follow:

`docs/00_studio_standards/branching_strategy.md`

For normal bug fixes:

1. Start from the appropriate up-to-date `develop` branch.
2. Create a task branch using the `fix/` or `bugfix/` prefix.
3. Implement the correction.
4. Run the relevant validation.
5. Review the complete diff.
6. Prepare a pull request targeting `develop`.

Example branch names:

- `fix/inventory-duplicate-items`
- `bugfix/player-fall-through-floor`
- `fix/save-data-corruption`

The agent MUST NOT:

- Commit directly to `main` or `develop`.
- Merge into protected branches.
- Bypass branch protection.
- Force-push without explicit authorization.
- Delete branches containing unmerged work.
- Include unrelated changes in the bug-fix branch.

A human reviewer is responsible for approving and merging the pull request.

## 16. Documentation and Bug Record Updates

Update documentation only when the fix changes documented behavior or reveals an important missing requirement.

Potential updates include:

- Bug report status and resolution details.
- Relevant gameplay specifications.
- Technical documentation.
- Test cases.
- Known issue records.
- Architecture decision records, when a significant decision is involved.

Do not create documentation solely to describe trivial code changes.

Follow `docs/00_studio_standards/documentation_standards.md` and the project's documentation management rules.

If the fix changes approved design behavior, obtain the required approval before updating the authoritative specification.

## 17. Completion Criteria

The bug-fix workflow is complete when:

- The bug report has been understood.
- Expected behavior has been established.
- The defect has been reproduced or the reproduction limitation documented.
- The root cause has been identified or remaining uncertainty documented.
- An appropriate correction has been implemented.
- Relevant regression tests have been added or updated when practical.
- Applicable automated and manual validation has been performed.
- Results have been reported accurately.
- The change set has been reviewed for unintended modifications.
- Relevant documentation has been updated when necessary.
- The fix is ready for human review.

Completion of this workflow does not imply pull request approval, integration, or release.

## 18. AI Agent Rules

The agent MUST:

- Inspect project context before changing code.
- Understand expected behavior before implementing a fix.
- Preserve user changes and unrelated work.
- Investigate the root cause.
- Prefer minimal, targeted corrections.
- Follow project architecture and GDScript standards.
- Add or update regression tests when practical.
- Run relevant validation.
- Report actual test results.
- Identify unverified assumptions and limitations.
- Follow the established Git workflow.
- Request approval for high-risk changes.
- Provide a clear completion report.

The agent MUST NOT:

- Guess expected behavior when requirements are ambiguous.
- Hide symptoms without addressing the underlying cause.
- Modify unrelated functionality.
- Perform broad refactoring without authorization.
- Remove tests merely because they fail.
- Disable validation to make a fix appear successful.
- Ignore new errors or warnings.
- Claim tests passed when they were not executed.
- Discard user modifications.
- Modify protected branches directly.
- Merge its own pull request.
- Mark its own work as approved.

## 19. Final Report Format

After completing the workflow, provide the following report:

### Bug Fix Report

**Bug ID:** [Bug ID or Not Assigned]

**Title:** [Short bug description]

**Status:** Fixed / Partially Fixed / Blocked / Unable to Reproduce

**Severity:** [Reported severity]

**Reproduction:** Reproduced / Partially Reproduced / Not Reproduced / Blocked

**Root cause:** [Identified cause or remaining uncertainty]

**Fix implemented:** [Description of the correction]

**Modified files:**
- [File path and reason for modification]

**Regression tests:**
- [Test added or updated]
- [Or explain why no automated test was added]

**Validation results:**
- [Validation check]: Passed / Failed / Not Run / Blocked / Not Applicable

**Regression risks:** [Potential impact or None identified]

**Documentation updates:** [Updated documents or None]

**Branch:** [Task branch name]

**Remaining limitations:** [Unresolved issues or None]

**Next step:** [Human review, additional investigation, or another appropriate action]

Do not report a bug as fully fixed when validation has not established that the original defect is resolved.