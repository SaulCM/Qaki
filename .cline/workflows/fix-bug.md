# Fix Bug Workflow

## Purpose

Systematically investigate and resolve a software defect in the Godot project.

The workflow ensures that fixes address the actual root cause, minimize unintended changes, preserve existing functionality, and include appropriate validation.

The agent must understand the defect before modifying code. It must not hide symptoms with superficial workarounds when the underlying cause can be identified and corrected.

## When to Use

Use this workflow when:

- A gameplay feature behaves incorrectly.
- A script produces an error or unexpected result.
- A scene or node does not behave as intended.
- A resource fails to load or is incorrectly managed.
- A regression is introduced by a recent change.
- A system fails under specific conditions.
- An existing bug report requires investigation and resolution.

Do not use this workflow for new feature development or broad refactoring unrelated to a defect.

## Inputs

Identify the available information from the user's request and repository.

Potential inputs include:

- Bug description.
- Steps to reproduce.
- Expected behavior.
- Actual behavior.
- Error messages or stack traces.
- Screenshots, recordings, or logs.
- Affected scenes, scripts, or resources.
- Relevant bug report.
- Related feature or gameplay specifications.
- Recent commits or changes that may have introduced the defect.

If essential reproduction information is missing, investigate the available evidence first.

Ask the user for clarification only when the missing information prevents meaningful investigation.

Do not invent reproduction steps or claim a defect has been reproduced when it has not.

---

## Workflow

### Step 1: Establish Repository Context

Before investigating:

1. Inspect the repository structure.
2. Identify the current Git branch.
3. Check the working-tree status.
4. Identify the affected files and related systems.
5. Inspect recent relevant changes when useful.
6. Identify existing project conventions and architecture.

Use read-only Git commands during investigation.

Do not switch branches, reset changes, stash files, or modify Git history.

Preserve unrelated user changes. Never overwrite or discard existing work.

If the working tree contains uncommitted changes, determine whether they overlap with the proposed fix. Avoid modifying user-owned changes.

### Step 2: Load Applicable Documentation

Read `docs/DOCUMENTATION_INVENTORY.md` and inspect the actual documentation structure.

Consult the applicable studio standards:

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`

Load additional documentation according to the affected system.

Examples:

| Bug area | Relevant documentation |
|---|---|
| GDScript behavior | `docs/02_technical_standards/GDSCRIPT_STANDARDS.md` |
| Architecture | `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md` |
| Scene and node behavior | `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md` |
| Signals and events | `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md` |
| Data persistence | `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md` |
| Resource loading | `docs/02_technical_standards/RESOURCE_MANAGEMENT.md` |
| Performance | `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md` |
| Testing | `docs/02_technical_standards/TESTING_STRATEGY.md` |
| Bug reporting | `docs/05_qa_standards/BUG_REPORTING.md` |
| Regression testing | `docs/05_qa_standards/REGRESSION_TESTING.md` |
| Acceptance criteria | `docs/05_qa_standards/ACCEPTANCE_CRITERIA_GUIDELINES.md` |

Also inspect relevant project-specific specifications, existing tests, and ADRs.

Read `docs/07_agent_workflows/FIX_BUG.md` when it exists and is applicable.

Follow relevant documentation references and resolve relative paths from the document containing the reference.

Verify that referenced documents exist. Do not assume that every document in the inventory is relevant to the current bug.

### Step 3: Understand the Defect

Establish the difference between expected and actual behavior.

Identify:

- What is supposed to happen?
- What actually happens?
- Under what conditions does the problem occur?
- Which system or component is involved?
- Is the defect reproducible?
- Does it occur consistently or intermittently?
- Is there evidence of a recent regression?
- What is the expected behavior according to authoritative project documentation?

Record the defect in a concise problem statement.

If the expected behavior is unclear or contradictory, do not invent the intended behavior. Consult the relevant specification or ask the user.

### Step 4: Reproduce the Bug

Attempt to reproduce the defect using the available project environment.

When possible:

1. Identify the required initial state.
2. Follow the reported reproduction steps.
3. Execute the relevant gameplay or system behavior.
4. Observe the actual result.
5. Capture relevant errors, logs, or stack traces.
6. Determine whether the behavior is consistent.

Use the project's existing test infrastructure and Godot execution tools where appropriate.

If reproduction requires unavailable external services, user interaction, assets, or runtime conditions, document the limitation.

Classify the reproduction status:

- **Reproduced:** The reported defect was observed.
- **Partially reproduced:** Related behavior was observed, but the exact defect was not confirmed.
- **Not reproduced:** The defect could not be observed.
- **Unable to test:** Required tools, environment, or information were unavailable.

Do not claim successful reproduction without evidence.

### Step 5: Investigate the Root Cause

Inspect the affected implementation and its dependencies.

Consider:

- Incorrect conditions or calculations.
- Invalid assumptions about state.
- Initialization and execution order.
- Node lifecycle and scene-tree timing.
- Invalid or missing references.
- Incorrect signal connections.
- Resource loading and ownership.
- Unexpected state transitions.
- Data serialization and deserialization.
- Race conditions or timing-dependent behavior.
- Incorrect input handling.
- Interactions between systems.
- Recent changes that may have introduced a regression.

Trace the execution path from the observed behavior to the responsible implementation.

Check whether the defect originates in the reported file or in another dependency.

Do not assume that the location of an error message is necessarily the root cause.

### Step 6: Identify the Root Cause and Proposed Fix

Before editing code, establish:

1. The most likely root cause.
2. The evidence supporting that conclusion.
3. The affected components.
4. The smallest reasonable correction.
5. Potential side effects.
6. Required regression coverage.

Prefer a targeted fix that addresses the underlying problem.

Avoid:

- Hiding errors without correcting their cause.
- Adding unnecessary defensive code.
- Introducing unrelated refactoring.
- Replacing working systems unnecessarily.
- Duplicating existing functionality.
- Changing intended gameplay behavior without approval.

If multiple solutions exist and the choice has significant architectural or gameplay consequences, present the alternatives and ask the user before proceeding.

### Step 7: Implement the Fix

After the root cause is sufficiently understood:

1. Modify only the necessary files.
2. Follow existing architecture and coding conventions.
3. Preserve public interfaces unless a change is required.
4. Keep the correction focused.
5. Handle relevant edge cases.
6. Add or update tests when appropriate.
7. Preserve unrelated user changes.

Use the smallest implementation that reliably resolves the defect.

Do not silently expand the task into a refactor or feature enhancement.

If the fix requires an architectural change beyond the original scope, stop and request approval.

### Step 8: Add or Update Tests

Add or update tests that verify the corrected behavior.

Select an appropriate test level:

- **Unit tests:** Validate isolated logic and calculations.
- **Integration tests:** Validate interactions between components.
- **Scene-level tests:** Validate node, scene, and lifecycle behavior.
- **Gameplay tests:** Validate player-facing behavior.
- **Regression tests:** Ensure the original defect does not return.

Tests should verify observable behavior rather than merely reproduce the implementation.

Include relevant edge cases.

When automated testing is impractical, document the manual validation steps required.

Do not weaken or remove existing tests simply to make the suite pass.

### Step 9: Validate the Fix

Perform validation appropriate to the scope of the change.

At minimum, when supported by the environment:

1. Run the relevant tests.
2. Run relevant static checks or project validation.
3. Verify that the affected scene or system loads.
4. Confirm that the original defect is resolved.
5. Check relevant edge cases.
6. Run regression tests for affected functionality.
7. Inspect the final diff for unintended changes.

If the defect was reproduced before the fix, repeat the same reproduction steps after implementation.

Distinguish between:

- Tests executed successfully.
- Tests executed with failures.
- Tests not executed.
- Tests unavailable in the current environment.
- Manual checks completed.
- Manual checks still required.

Do not claim that a bug is fixed solely because the code was changed.

### Step 10: Review the Changes

Inspect the final diff.

Verify that:

- Only relevant files were changed.
- The fix addresses the identified root cause.
- No unrelated behavior was modified.
- No temporary debugging code remains.
- No unnecessary comments or abstractions were introduced.
- Tests cover the corrected behavior where appropriate.
- Naming and architecture follow studio standards.
- Documentation remains accurate.

Check that the implementation does not introduce new defects or regressions.

### Step 11: Update Documentation When Necessary

Determine whether the fix requires documentation changes.

Update relevant documentation only when the correction changes or clarifies:

- System behavior.
- Technical interfaces.
- Architecture.
- Configuration.
- Usage instructions.
- Known constraints.
- Testing procedures.

Do not create documentation for every minor bug fix.

If the fix reveals an inaccurate specification or unresolved design decision, identify the discrepancy and request clarification when necessary.

Follow the documentation-management rules when creating or modifying documents.

### Step 12: Report the Result

Present a concise bug-fix report.

Use the following structure:

# Bug Fix Report

## Summary

Describe the defect and the implemented correction.

## Root Cause

Explain why the defect occurred.

Include the relevant file and code location.

If the root cause could not be confirmed, state that explicitly.

## Changes Made

List the modified files and explain the purpose of each change.

## Tests and Validation

Report:

- Tests added or modified.
- Tests executed and results.
- Manual validation performed.
- Regression checks performed.
- Validation not performed and why.

## Remaining Risks

Identify unresolved concerns, limitations, or additional validation required.

If none were identified, state that explicitly.

## Documentation

List documentation files updated, if any.

## Final Status

Choose the appropriate status:

- **Fixed and validated:** The defect was reproduced or otherwise confirmed, corrected, and successfully validated.
- **Fixed, validation incomplete:** A correction was implemented, but some validation remains outstanding.
- **Unable to confirm fix:** The implementation was changed, but the defect could not be reliably reproduced or verified.
- **Investigation incomplete:** The root cause or required correction remains unresolved.
- **Blocked:** Additional information, access, or approval is required.

Do not report a defect as fixed and validated when its correction has not been verified.

---

## Constraints

### Scope Control

The agent MUST:

- Focus on the reported defect.
- Preserve existing functionality.
- Avoid unrelated refactoring.
- Avoid speculative changes.
- Respect existing project specifications.
- Ask for approval before changing intended gameplay behavior.
- Preserve unrelated user modifications.

### Code Quality

The agent MUST:

- Follow applicable GDScript and architecture standards.
- Address the root cause rather than only the symptom.
- Use the simplest reliable correction.
- Add appropriate regression coverage.
- Avoid unnecessary dependencies and abstractions.
- Keep the change understandable and maintainable.

### Git Safety

The agent MUST:

- Follow `.cline/rules/git-workflow.md` and the studio branching strategy.
- Never commit, push, merge, or change protected branches unless separately authorized.
- Never discard unrelated working-tree changes.
- Never rewrite Git history.
- Never bypass branch protection or review requirements.

### Human Approval

The agent MUST request approval before:

- Making significant architectural changes.
- Changing intended gameplay behavior.
- Modifying unrelated systems.
- Introducing new dependencies.
- Changing save-data formats or compatibility behavior.
- Performing destructive operations.
- Expanding the task beyond the reported defect.

A user request to fix a bug authorizes the necessary, scoped correction. It does not authorize unrelated changes.

---

## Completion Checklist

Before reporting completion, verify that:

- [ ] The repository context was inspected.
- [ ] The working-tree state was checked.
- [ ] Applicable documentation was consulted.
- [ ] Expected and actual behavior were identified.
- [ ] Reproduction was attempted or its limitations documented.
- [ ] The root cause was investigated.
- [ ] The proposed fix addresses the underlying issue.
- [ ] Only necessary files were modified.
- [ ] Relevant tests were added or updated.
- [ ] Available validation was performed.
- [ ] Regression risks were considered.
- [ ] The final diff was inspected.
- [ ] Documentation was updated when necessary.
- [ ] Unresolved risks and limitations were reported.
- [ ] No unrelated user changes were overwritten.
- [ ] The final status accurately reflects the evidence.

## Final Principle

A successful bug fix does more than make an error disappear.

It corrects the underlying defect, preserves intended behavior, reduces regression risk, and provides evidence that the correction works.

Investigate carefully, change minimally, validate honestly, and report transparently.