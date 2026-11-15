# Review Code

## 1. Purpose

This workflow defines how an AI agent should inspect and review code changes in the game project.

The objective is to identify defects, architectural problems, maintainability issues, security risks, performance concerns, and missing validation before changes are approved and integrated.

The review should provide actionable feedback supported by evidence from the actual code and project requirements.

## 2. Scope

Use this workflow when:

- Reviewing a pull request.
- Reviewing a feature implementation.
- Reviewing a bug fix.
- Reviewing a refactoring change.
- Reviewing technical improvements.
- Reviewing AI-generated code.
- Evaluating whether changes follow project standards.
- Performing a focused review of specific files or components.

Do not use this workflow for:

- Implementing new features.
- Fixing defects directly without authorization.
- Replacing automated testing.
- Performing a complete security audit.
- Approving architectural decisions on behalf of the user.
- Replacing the formal human review and approval process.

If a review identifies defects, report them and recommend the appropriate corrective workflow.

## 3. Authoritative References

Before reviewing code, inspect the relevant studio standards and project documentation.

### 3.1 Studio references

Relevant references include:

- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/BRANCHING_STRATEGY.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`
- `docs/02_technical_standards/ENGINE_STANDARDS.md`
- `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md`
- `docs/02_technical_standards/RESOURCE_MANAGEMENT.md`
- `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md`
- `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md`
- `docs/02_technical_standards/TESTING_STRATEGY.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`

Read only the references relevant to the changes being reviewed.

### 3.2 Project references

Inspect available project documents, prioritizing:

- The feature or bug-fix request.
- Acceptance criteria.
- Relevant gameplay specifications.
- Relevant technical design documents.
- Existing architecture decisions.
- Related automated tests.
- Previous review feedback.
- Relevant project-specific implementation standards.

These are possible reference locations, not assumptions that every document exists.

The agent MUST inspect the actual project structure and code changes before forming review conclusions.

## 4. Workflow Overview

Follow these stages:

1. Understand the review request.
2. Inspect the repository and review context.
3. Identify the scope of changes.
4. Understand the intended behavior.
5. Review correctness and functional behavior.
6. Review architecture and code quality.
7. Review Godot and GDScript conventions.
8. Review tests and validation.
9. Review performance, security, and data integrity.
10. Review documentation and repository hygiene.
11. Classify and report findings.
12. Provide an overall review assessment.

Adapt the review depth to the size, complexity, and risk of the changes.

## 5. Stage 1: Understand the Review Request

Identify what needs to be reviewed.

Determine:

- Review target.
- Related feature or bug.
- Intended behavior.
- Requirements and acceptance criteria.
- Relevant pull request or task.
- Expected review depth.
- Known risks or concerns.
- Required validation.

Clarify whether the review concerns:

- A complete pull request.
- A specific commit.
- A set of changed files.
- A particular implementation concern.
- A previously identified issue.

Do not review code in isolation when relevant requirements or design decisions are available.

## 6. Stage 2: Inspect the Repository and Review Context

Inspect the repository before evaluating changes.

Check:

- Current branch.
- Git working tree.
- Relevant commits.
- Base and target branches.
- Changed files.
- Added and deleted files.
- Project structure.
- Existing tests.
- Relevant documentation.
- Recent related changes.

### 6.1 Determine the actual diff

Use the appropriate Git comparison to identify the changes being reviewed.

For pull requests, compare the source branch against the intended target branch.

Inspect:

- Added code.
- Modified code.
- Deleted code.
- Renamed files.
- Configuration changes.
- Asset changes.
- Test changes.
- Documentation changes.

Review the complete relevant diff rather than relying exclusively on a summary or commit message.

### 6.2 Preserve repository state

The agent MUST NOT:

- Modify files during a review unless explicitly requested.
- Discard uncommitted changes.
- Reset branches.
- Rebase or rewrite commits.
- Merge branches.
- Modify protected branches.
- Change the pull request without authorization.

The review should be read-only unless the user explicitly requests corrections.

## 7. Stage 3: Identify the Scope of Changes

Determine what the changes are intended to accomplish.

Identify:

- Features or systems affected.
- Components modified.
- New dependencies.
- Public interfaces changed.
- Data structures changed.
- Scenes and resources affected.
- Tests added or modified.
- Documentation affected.
- Potentially impacted features.

### 7.1 Scope consistency

Verify that the implementation matches the stated purpose.

Identify:

- Unrelated changes.
- Unrequested functionality.
- Unexpected refactoring.
- Missing implementation components.
- Changes outside the expected feature boundaries.
- Unnecessary dependencies.

Do not automatically classify every additional change as a defect. Evaluate whether it is justified and relevant.

## 8. Stage 4: Understand Intended Behavior

Before judging implementation correctness, establish what the code is supposed to do.

Use:

- Approved requirements.
- Acceptance criteria.
- Gameplay specifications.
- Technical design documents.
- Existing contracts and interfaces.
- Established project behavior.

Identify:

- Expected inputs.
- Expected outputs.
- State changes.
- Side effects.
- Failure conditions.
- Dependencies.
- Relevant edge cases.

If intended behavior is ambiguous, identify the ambiguity instead of assuming the implementation is incorrect.

Do not recommend changes that contradict approved design decisions.

## 9. Stage 5: Review Correctness and Functional Behavior

Evaluate whether the implementation behaves correctly.

### 9.1 Logic and correctness

Inspect for:

- Incorrect conditions.
- Incorrect calculations.
- Invalid assumptions.
- Incorrect state transitions.
- Missing validation.
- Incorrect return values.
- Unexpected side effects.
- Incorrect execution order.
- Incorrect handling of repeated operations.
- Potential null or invalid references.

### 9.2 Edge cases

Consider:

- Empty collections.
- Missing resources.
- Invalid inputs.
- Boundary values.
- Unexpected state combinations.
- Repeated calls.
- Interrupted operations.
- Scene transitions.
- Initialization order.
- Resource loading failures.
- Save/load behavior.

### 9.3 Error handling

Verify that:

- Errors are handled appropriately.
- Invalid states do not silently corrupt data.
- Failures are communicated clearly.
- Recovery behavior is reasonable.
- Important failures are not suppressed.
- Error handling does not hide underlying defects.

Report only findings supported by actual code or reproducible evidence.

## 10. Stage 6: Review Architecture and Code Quality

Evaluate the implementation against the project's architectural standards.

### 10.1 Feature boundaries

Verify that:

- Functionality belongs to the correct feature.
- Shared functionality is genuinely reusable.
- Infrastructure contains project-wide technical concerns.
- Feature ownership is clear.
- Dependencies follow the established architecture.
- Circular dependencies are avoided.
- Cross-feature references to `res://features/...` target only a `class_name` type or an `_api.gd` facade; scene-path coupling between features is absent or explicitly justified.

### 10.2 Component responsibilities

Review:

- Class and component responsibilities.
- Cohesion.
- Coupling.
- Separation of concerns.
- State ownership.
- Public interfaces.
- Reusability where justified.
- Testability.

Identify components that have unnecessary or overlapping responsibilities.

### 10.3 Maintainability

Inspect for:

- Unnecessary complexity.
- Duplicated logic.
- Dead code.
- Unused variables or functions.
- Excessive nesting.
- Unclear naming.
- Unexplained magic values.
- Fragile dependencies.
- Excessive abstraction.
- Unnecessary inheritance.
- Poor separation of configuration and runtime state.

Prefer specific, actionable improvements over subjective style preferences.

### 10.4 Responsibilities and design contracts

Consider the following when evaluating the implementation:

- **Single responsibility:** each script, scene, and component has one cohesive reason to change.
- **Composition over inheritance:** inheritance is used only for a genuine, stable type relationship.
- **Signal and public-method contracts:** consumers depend on declared signals and public methods, not on another component's internals.
- **Dependency direction:** dependencies point toward stable, lower-level code and do not form cycles.
- **Justified abstraction:** an abstraction exists because a requirement justifies it, not to satisfy a pattern.

Do not force every principle into every component.

Simple and understandable solutions are preferable to unnecessary abstractions.

## 11. Stage 7: Review Godot and GDScript Conventions

Evaluate implementation against the project's Godot and GDScript standards.

### 11.1 GDScript

Check:

- Naming conventions.
- Type annotations where appropriate.
- Function responsibilities.
- Variable and constant declarations.
- Signal definitions.
- Resource references.
- Error handling.
- Code formatting.
- Documentation comments where useful.

### 11.2 Scenes and nodes

Check:

- Scene ownership.
- Node hierarchy.
- Node naming.
- Node responsibilities.
- Scene dependencies.
- Node lifecycle.
- Signal connections.
- Appropriate use of instantiation.
- Unnecessary node references.

### 11.3 Resources

Check:

- Resource ownership.
- Resource loading.
- Shared resource behavior.
- Runtime modifications.
- Resource duplication.
- Reference validity.
- Resource lifecycle.

### 11.4 Signals and events

Check:

- Appropriate use of signals.
- Correct connection and disconnection.
- Clear event ownership.
- Appropriate payloads.
- Avoidance of unnecessary global event communication.
- Potential duplicate connections.
- Lifecycle-related connection problems.

### 11.5 Engine compatibility

Verify that:

- The implementation uses APIs supported by the project's Godot version.
- Project configuration remains consistent.
- Engine-specific behavior is handled correctly.
- No unsupported or deprecated API is introduced without justification.

Do not assume that an API is available merely because it exists in another Godot version.

## 12. Stage 8: Review Tests and Validation

Evaluate whether the changes have adequate test coverage.

### 12.1 Test quality

Check whether tests:

- Validate intended behavior.
- Cover relevant acceptance criteria.
- Include important positive scenarios.
- Include negative and boundary scenarios where relevant.
- Validate important state transitions.
- Cover relevant integrations.
- Include regression coverage for bug fixes.
- Use meaningful assertions.

### 12.2 Test reliability

Inspect for:

- Uncontrolled randomness.
- Timing-dependent assertions.
- Shared mutable state.
- Execution-order dependencies.
- Inadequate cleanup.
- External dependencies without isolation.
- Tests that modify real player data.
- Flaky behavior.

### 12.3 Validation evidence

Determine whether appropriate validation was performed.

Where possible, run relevant tests and inspect their results.

Consider:

- GDScript parsing.
- Automated tests.
- Scene loading.
- Runtime behavior.
- Integration behavior.
- Performance checks.
- Export or build validation.

Do not claim that validation succeeded if it was not executed.

Classify checks as:

- **Passed:** Executed successfully.
- **Failed:** Executed but did not meet expectations.
- **Not Run:** Not executed.
- **Blocked:** Could not execute due to a known limitation.
- **Not Applicable:** Not relevant to the changes.

A missing test is not automatically a defect. Evaluate the risk and importance of the untested behavior.

## 13. Stage 9: Review Performance, Security, and Data Integrity

Evaluate risks introduced by the changes.

### 13.1 Performance

Consider:

- Expensive operations in `_process()` or `_physics_process()`.
- Unnecessary object creation.
- Excessive scene instantiation.
- Unnecessary resource loading.
- Repeated calculations.
- Expensive loops.
- Excessive signal emissions.
- Unnecessary physics queries.
- Large collections or data structures.
- Memory retention and resource lifecycle.
- Rendering and UI performance.

Do not report hypothetical performance concerns as confirmed regressions without evidence.

Recommend profiling when actual impact cannot be established through code inspection.

### 13.2 Security

Check for:

- Unsafe file operations.
- Unvalidated external input.
- Unsafe deserialization.
- Sensitive information in logs.
- Insecure external integrations.
- Unnecessary permission exposure.
- Unsafe handling of player-controlled data.

### 13.3 Data integrity

Review:

- Save/load behavior.
- Data validation.
- Serialization compatibility.
- Resource references.
- State consistency.
- Duplicate or missing data.
- Error recovery.
- Migration requirements.

Changes to save formats or persistent data deserve particular attention.

## 14. Stage 10: Review Documentation and Repository Hygiene

Verify that the changes include appropriate documentation updates.

Consider:

- Gameplay specifications.
- Technical design documents.
- Architecture decision records.
- Test cases.
- Test plans.
- Configuration documentation.
- Asset documentation.
- Relevant development instructions.

Documentation should reflect actual approved behavior.

### 14.1 Repository hygiene

Check for:

- Generated cache files.
- Temporary debugging files.
- Unused assets.
- Accidental configuration changes.
- Unnecessary dependencies.
- Duplicate resources.
- Incorrect file locations.
- Naming convention violations.
- Missing or broken references.

Verify that generated Godot cache files, such as `.godot/`, are not unintentionally included in source control.

### 14.2 Documentation inventory

If documentation files are created, moved, renamed, deprecated, or deleted, verify that the documentation inventory is updated according to the project's documentation management rules.

Do not register files that do not exist.

## 15. Stage 11: Classify and Report Findings

Classify findings according to their severity.

### 15.1 Severity levels

Use the studio's established severity classification:

- **Critical:** A serious defect causing crashes, data corruption, security exposure, or a major failure that prevents essential functionality.
- **High:** A significant defect affecting important gameplay or system behavior, with no reasonable workaround.
- **Medium:** A defect affecting limited functionality or producing incorrect behavior with a reasonable workaround.
- **Low:** A minor defect with limited functional impact.
- **Suggestion:** A non-blocking improvement to readability, maintainability, or design quality.

Severity should reflect impact, not personal preference.

### 15.2 Finding requirements

Each finding should include:

- Severity.
- Short descriptive title.
- Relevant file and location.
- Description of the problem.
- Why it matters.
- Reproduction conditions or supporting evidence.
- Recommended correction.

### 15.3 Finding quality

A useful finding must:

- Identify a specific problem.
- Be supported by code or evidence.
- Explain the practical impact.
- Suggest an actionable correction.
- Avoid speculative claims.
- Avoid duplicating another finding.

Use precise file references and line numbers when available.

Do not report a style preference as a defect unless it violates an established project standard or creates a meaningful maintenance problem.

### 15.4 Prioritize findings

Present findings in descending severity:

1. Critical.
2. High.
3. Medium.
4. Low.
5. Suggestions.

Avoid overwhelming the user with minor observations when more important issues exist.

## 16. Stage 12: Provide an Overall Review Assessment

After evaluating the changes, provide an overall assessment.

Use one of these outcomes:

- **Changes Required:** One or more significant findings must be addressed before approval.
- **Review Passed:** No blocking findings were identified within the reviewed scope.
- **Review Incomplete:** Important areas could not be inspected or validated.
- **Needs Clarification:** Intended behavior or requirements are insufficiently defined.

A review passing does not guarantee the absence of defects.

### 16.1 Approval boundaries

The agent may provide a technical assessment and recommendations.

The agent MUST NOT:

- Approve its own implementation.
- Mark a pull request as approved without authorization.
- Merge the pull request.
- Bypass required human reviews.
- Modify the reviewed implementation without an explicit request.
- Claim that the entire project is defect-free based on a limited review.

The user or authorized human reviewer remains responsible for final approval.

## 17. Revision and Re-review Process

When the author submits corrections:

1. Inspect the updated diff.
2. Identify which previous findings were addressed.
3. Verify each relevant correction.
4. Check whether new problems were introduced.
5. Re-run relevant validation when appropriate.
6. Report unresolved findings.
7. Provide an updated review assessment.

Do not assume a finding is resolved merely because the author states it was fixed.

Preserve the original review context and avoid reopening findings that have been demonstrably resolved unless new evidence warrants it.

## 18. Completion Criteria

The code review workflow is complete when:

- The review request is understood.
- Relevant project standards and requirements have been inspected.
- The actual change set has been examined.
- Intended behavior has been established.
- Correctness and edge cases have been evaluated.
- Architecture and code quality have been reviewed.
- Godot and GDScript conventions have been checked.
- Tests and validation evidence have been evaluated.
- Performance, security, and data integrity risks have been considered.
- Documentation and repository hygiene have been reviewed.
- Findings have been classified and documented.
- An overall review assessment has been provided.

Completion of this workflow does not imply human approval or integration.

## 19. AI Agent Rules

The agent MUST:

- Inspect the actual code changes.
- Understand requirements before evaluating correctness.
- Follow applicable studio and project standards.
- Review the implementation objectively.
- Support findings with evidence.
- Use accurate file references.
- Prioritize meaningful defects.
- Distinguish confirmed defects from potential risks.
- Identify missing validation.
- Preserve the repository state.
- Avoid modifying reviewed code unless explicitly requested.
- Provide actionable recommendations.
- Respect human approval responsibilities.

The agent MUST NOT:

- Approve its own work.
- Modify the code during a read-only review.
- Invent defects.
- Report unsupported performance or security claims.
- Demand unnecessary abstractions.
- Treat personal style preferences as defects.
- Ignore approved requirements.
- Hide significant findings.
- Claim tests passed without execution.
- Merge or approve its own pull request.

## 20. Final Report Format

After completing the review, provide the following report:

### Code Review Report

**Review target:** [Pull request, commit, branch, or files]

**Related feature/bug:** [Reference or None]

**Review scope:** [Areas inspected]

**Overall assessment:** Changes Required / Review Passed / Review Incomplete / Needs Clarification

**Findings:**

#### Critical
- [Finding or None]

#### High
- [Finding or None]

#### Medium
- [Finding or None]

#### Low
- [Finding or None]

#### Suggestions
- [Suggestion or None]

**Validation performed:**
- [Check]: Passed / Failed / Not Run / Blocked / Not Applicable

**Areas not validated:** [Areas or None]

**Documentation issues:** [Issues or None]

**Additional risks:** [Relevant risks or None]

**Recommended next steps:** [Actions required]

**Human approval:** Required / Pending / Not Applicable

Do not report a review as passed when significant areas remain uninspected or required validation is incomplete.