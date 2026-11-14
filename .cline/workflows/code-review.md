# Code Review Workflow

## Purpose

Perform a structured code review of the requested changes, identifying correctness issues, potential defects, maintainability concerns, and violations of project or studio standards.

The review must prioritize actionable findings over stylistic preferences. It must not modify code, apply fixes, or approve changes.

## When to Use

Use this workflow when asked to:

- Review code changes before a pull request.
- Review an existing pull request or feature branch.
- Inspect recently implemented functionality.
- Identify bugs, regressions, or design problems.
- Evaluate code quality and compliance with project standards.

## Inputs

Determine the review scope from the user's request.

Possible review targets include:

- A specific file or directory.
- Uncommitted working-tree changes.
- Changes between the current branch and a target branch.
- A specific commit.
- A pull request, if its contents are accessible.

If the review target is ambiguous and cannot be determined from the repository state or request, ask the user to clarify.

Do not assume that the entire repository needs to be reviewed when the user has specified a narrower scope.

---

## Workflow

### Step 1: Establish Repository Context

Before reviewing code:

1. Inspect the repository structure.
2. Identify the current Git branch.
3. Check the working-tree status.
4. Identify the requested review target.
5. Determine the exact files and changes included in the review.
6. Identify whether there are unrelated or pre-existing modifications.

Use read-only Git commands to inspect the repository.

Do not switch branches, reset changes, stash files, modify the working tree, or alter Git history.

If the review depends on a comparison branch, verify that the branch exists and that the comparison can be performed.

### Step 2: Load Applicable Documentation

Read `docs/DOCUMENTATION_INVENTORY.md` and inspect the actual documentation structure.

Read the applicable standards before reviewing the changes.

At minimum, consult:

- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`

Load additional documentation according to the review scope.

Examples:

| Review area | Relevant documentation |
|---|---|
| GDScript implementation | `docs/02_technical_standards/GDSCRIPT_STANDARDS.md` |
| Architecture and dependencies | `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md` |
| Scenes and nodes | `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md` |
| Signals and events | `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md` |
| Performance | `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md` |
| Data persistence | `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md` |
| Resource handling | `docs/02_technical_standards/RESOURCE_MANAGEMENT.md` |
| Testing | `docs/02_technical_standards/TESTING_STRATEGY.md` |
| Asset changes | Relevant documents in `docs/03_art_audio_standards/` |
| Gameplay behavior | Relevant documents in `docs/01_game_design_guidelines/` |
| Acceptance criteria | `docs/05_qa_standards/ACCEPTANCE_CRITERIA_GUIDELINES.md` |

Also inspect relevant project-specific documentation, including technical designs, gameplay specifications, acceptance criteria, and existing architecture decisions.

Read `docs/07_agent_workflows/REVIEW_CODE.md` when it exists and is applicable.

Follow relevant documentation references and resolve relative paths from the document containing the reference.

Do not assume that a document exists because it is mentioned elsewhere. Verify its actual presence and use exact repository paths.

Do not load every document indiscriminately. Select the documents that are relevant to the requested review.

### Step 3: Understand the Intended Changes

Before judging implementation quality:

1. Read the changed files in their entirety when practical.
2. Inspect the relevant surrounding code.
3. Identify the intended behavior of the changes.
4. Review related scenes, scripts, resources, configuration, and tests.
5. Identify dependencies and interactions with existing systems.
6. Compare the implementation with relevant specifications and acceptance criteria.

Do not evaluate a code fragment in isolation when its correctness depends on surrounding functionality.

Do not assume that an implementation is incorrect merely because it differs from your preferred design.

### Step 4: Analyze the Changes

Review the implementation for the following areas, as applicable.

#### 4.1 Correctness and Functionality

Check for:

- Incorrect or incomplete behavior.
- Logical errors and incorrect assumptions.
- Incorrect calculations or state transitions.
- Missing edge-case handling.
- Invalid conditions or unreachable code.
- Incorrect initialization or execution order.
- Unexpected behavior during normal gameplay.

#### 4.2 Runtime Safety and Reliability

Check for:

- Null or invalid references.
- Invalid node paths.
- Unsafe assumptions about node availability or lifecycle.
- Unhandled errors.
- Resource loading failures.
- Invalid signal connections.
- Potential crashes or runtime exceptions.
- Incorrect cleanup or lifecycle management.

#### 4.3 Architecture and Maintainability

Check for:

- Violations of established architecture.
- Unnecessary coupling between systems.
- Responsibilities assigned to inappropriate classes or nodes.
- Duplicate logic that should reasonably be shared.
- Unnecessary abstractions or complexity.
- Inconsistent interfaces.
- Changes that introduce avoidable technical debt.

Do not request abstractions or refactoring solely to satisfy personal preferences.

#### 4.4 Godot and GDScript Practices

When applicable, check for:

- Compliance with GDScript standards.
- Appropriate use of nodes, scenes, and resources.
- Correct signal usage.
- Appropriate use of Godot lifecycle methods.
- Correct resource ownership and cleanup.
- Unnecessary scene-tree searches.
- Avoidable runtime allocations.
- Unsafe assumptions about engine behavior.
- Inappropriate use of autoloads or global state.

#### 4.5 Performance

Check for:

- Unnecessary work in `_process()` or `_physics_process()`.
- Expensive operations repeated unnecessarily.
- Inefficient scene-tree operations.
- Unnecessary object or resource creation.
- Potential memory leaks.
- Expensive operations that should be cached or executed less frequently.

Only report performance concerns when there is a reasonable basis for expecting a meaningful impact.

#### 4.6 Testing and Regression Risk

Check for:

- Missing tests for important behavior.
- Incorrect or incomplete test coverage.
- Tests that do not verify the intended behavior.
- Existing functionality potentially affected by the changes.
- Missing regression coverage for fixed defects.
- Changes that violate acceptance criteria.

Do not claim that tests pass unless they have actually been executed and their results inspected.

#### 4.7 Documentation and Consistency

Check whether:

- The implementation matches its specification.
- Relevant documentation needs updating.
- Public interfaces or configuration changes are documented where required.
- Naming and structure follow studio conventions.
- Existing documentation has become inaccurate because of the changes.

Do not request documentation updates for trivial internal changes unless the applicable standards require them.

### Step 5: Validate Potential Findings

Before reporting a finding:

1. Re-examine the relevant implementation.
2. Identify the exact affected file and line or code range.
3. Confirm that the issue is introduced by the reviewed changes or is directly relevant to their correctness.
4. Determine whether the issue is already handled elsewhere.
5. Verify that the finding is supported by actual code or documentation.
6. Consider whether the behavior is intentional.
7. Ensure the finding is actionable.

Do not report speculative problems as confirmed defects.

If a concern cannot be verified, label it as a question or an area requiring further investigation rather than presenting it as a definite bug.

Avoid duplicate findings that describe the same underlying issue.

### Step 6: Assign Severity

Use the severity definitions from `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md`.

Apply the following general interpretation when consistent with that document:

- **Critical:** A severe issue that can cause crashes, data loss, security problems, or make essential functionality unusable.
- **High:** A significant defect that breaks important functionality or creates a substantial regression.
- **Medium:** A functional or maintainability issue with a meaningful but limited impact.
- **Low:** A minor issue with limited impact that should be addressed when practical.
- **Informational:** A non-blocking observation or improvement suggestion, not a defect.

Do not inflate severity to make a finding appear more important.

### Step 7: Prepare the Review Report

Present findings first, ordered from highest to lowest severity.

Use this structure:

# Code Review Report

## Review Scope

- **Target:** Files, commit, branch comparison, or pull request reviewed.
- **Base:** Comparison branch or commit, when applicable.
- **Files reviewed:** Number of files.
- **Review type:** Full, targeted, or partial.

## Findings

For each finding, use:

### [SEVERITY] Short descriptive title

- **Location:** `path/to/file.gd:line`
- **Issue:** Explain the problem clearly.
- **Impact:** Explain the practical consequence.
- **Recommendation:** Describe the necessary correction or investigation.

Include a minimal code example only when it makes the problem or recommendation clearer.

If no actionable findings are identified, explicitly state:

**No actionable findings identified within the reviewed scope.**

## Additional Observations

Include relevant non-blocking suggestions or questions that do not qualify as defects.

Do not use this section to repeat findings.

## Validation

Report:

- Tests executed and their results.
- Static checks or other validation performed.
- Checks not performed and why.
- Limitations of the review.

Distinguish between verified results and unverified assumptions.

## Documentation Consulted

List the actual documentation files consulted.

## Overall Assessment

Provide one of the following assessments:

- **Changes require correction:** One or more blocking findings exist.
- **Changes need attention:** Non-blocking findings should be considered.
- **No actionable findings identified:** No issues were found within the reviewed scope.

This assessment is advisory. It is not a pull request approval.

---

## Review Constraints

### Read-Only Operation

This workflow is a review operation, not an implementation task.

The agent MUST NOT:

- Modify source code.
- Apply suggested fixes.
- Reformat files.
- Modify tests.
- Change project configuration.
- Modify documentation.
- Create commits.
- Push branches.
- Merge branches.
- Approve pull requests.
- Dismiss review comments.
- Change repository settings.

If a problem is identified, report it and explain the recommended correction.

Wait for an explicit user request before implementing fixes.

### Review Integrity

The agent MUST:

- Review the actual changes rather than relying only on commit messages or descriptions.
- Consider relevant surrounding code and project context.
- Follow applicable studio and project standards.
- Report only evidence-supported findings.
- Provide precise file locations.
- Distinguish defects from optional improvements.
- Disclose incomplete reviews and validation limitations.
- Never claim to have inspected files, executed tests, or verified behavior without doing so.

### Scope Control

The agent MUST NOT:

- Expand the review to unrelated files without justification.
- Report unrelated pre-existing defects as newly introduced findings.
- Treat personal coding preferences as mandatory standards.
- Suggest large refactors unrelated to the requested changes.
- Assume that missing tests automatically prove an implementation is defective.

If an important issue outside the requested scope is discovered, mention it separately as an out-of-scope observation.

### Human Authority

The user retains final authority over review outcomes.

The agent MUST NOT approve its own changes or represent its assessment as human approval.

---

## Completion Checklist

Before completing the review, verify that:

- [ ] The review scope was established.
- [ ] The actual changes were inspected.
- [ ] Applicable studio standards were consulted.
- [ ] Relevant project documentation was consulted.
- [ ] Surrounding code and dependencies were considered.
- [ ] Potential findings were validated.
- [ ] Findings have appropriate severity and precise locations.
- [ ] Defects are distinguished from optional suggestions.
- [ ] Validation results are reported accurately.
- [ ] Review limitations are disclosed.
- [ ] No files or repository state were modified.

## Final Principle

A good code review improves software quality by identifying meaningful risks and defects.

Prioritize correctness, player experience, reliability, maintainability, and compliance with established project requirements.

Be precise, objective, evidence-based, and constructive. Do not manufacture findings merely to make the review appear comprehensive.