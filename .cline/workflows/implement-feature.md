# Implement Feature Workflow

## Purpose

Implement an approved game feature or technical capability in the Godot project.

The workflow ensures that implementation follows confirmed requirements, approved designs, existing architecture, and studio standards.

The agent must understand the intended behavior before writing code, implement the feature incrementally, validate its functionality, and preserve existing systems.

This workflow authorizes implementation within the scope of the user's request. It does not authorize unrelated features, architectural changes, or unapproved design decisions.

## When to Use

Use this workflow when:

- Implementing a new gameplay feature.
- Implementing an approved gameplay mechanic.
- Developing a new technical system.
- Extending an existing system with approved functionality.
- Integrating a feature with existing scenes, scripts, or resources.
- Implementing a feature based on an approved technical design.
- Completing an implementation task from the project backlog.

Do not use this workflow for:

- Isolated bug fixes; use `fix-bug.md`.
- Code review; use `code-review.md`.
- Creating a technical design without implementation; use `create-technical-design.md`.
- General refactoring without a feature requirement.

## Inputs

Identify the available information from the user's request and repository.

Potential inputs include:

- Feature description.
- Approved gameplay system specification.
- Approved mechanic specification.
- Game Design Document.
- Game Vision.
- Core game pillars.
- Approved technical design.
- Relevant ADRs.
- Acceptance criteria.
- Backlog item or user story.
- Existing source code and project architecture.
- UI, art, audio, and asset requirements.
- Testing requirements.

Use authoritative project documentation to establish the intended behavior.

Do not assume that a proposed feature, design decision, or backlog item has been approved.

If essential requirements are missing, contradictory, or ambiguous, identify the issue and ask the user for clarification before making decisions that could materially affect the feature.

---

## Workflow

### Step 1: Establish Repository Context

Before implementation:

1. Inspect the repository structure.
2. Identify the current Git branch.
3. Check the working-tree status.
4. Identify the feature's affected systems and files.
5. Inspect the existing architecture and implementation patterns.
6. Identify the Godot version and relevant project configuration.
7. Identify existing tests and validation tools.

Determine whether the working tree contains uncommitted changes.

Preserve unrelated user modifications. Never overwrite, discard, or silently incorporate unrelated work.

Follow `.cline/rules/git-workflow.md` and the studio branching strategy.

If the task requires a new branch, follow the established branch naming conventions and obtain any required approval before creating it.

Never work directly on protected branches or bypass branch protection.

### Step 2: Load Applicable Documentation

Read `docs/DOCUMENTATION_INVENTORY.md` and inspect the actual documentation structure.

Consult the applicable studio standards:

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/BRANCHING_STRATEGY.md`
- `docs/00_studio_standards/GIT_CONVENTIONS.md`

Load additional documentation according to the feature.

Examples:

| Implementation area | Relevant documentation |
|---|---|
| Architecture | `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md` |
| Godot engine practices | `docs/02_technical_standards/ENGINE_STANDARDS.md` |
| GDScript | `docs/02_technical_standards/GDSCRIPT_STANDARDS.md` |
| Scene and node structure | `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md` |
| Signals and events | `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md` |
| Data persistence | `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md` |
| Resource management | `docs/02_technical_standards/RESOURCE_MANAGEMENT.md` |
| Performance | `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md` |
| Asset integration | `docs/02_technical_standards/ASSET_PIPELINE.md` |
| Testing | `docs/02_technical_standards/TESTING_STRATEGY.md` |
| Acceptance criteria | `docs/05_qa_standards/ACCEPTANCE_CRITERIA_GUIDELINES.md` |
| Regression testing | `docs/05_qa_standards/REGRESSION_TESTING.md` |

Also consult relevant:

- Game design guidelines in `docs/01_game_design_guidelines/`.
- Art and audio standards in `docs/03_art_audio_standards/`.
- Production standards in `docs/04_production_standards/`.
- QA standards in `docs/05_qa_standards/`.
- Project-specific specifications and technical designs.
- Relevant ADRs.

Read `docs/07_agent_workflows/IMPLEMENT_FEATURE.md` when it exists and is applicable.

Follow relevant documentation references and resolve relative paths from the document containing the reference.

Verify that referenced documents exist. Do not assume that all documents in the inventory are relevant to the current task.

### Step 3: Understand the Feature Requirements

Establish exactly what must be implemented.

Identify:

- The problem the feature solves.
- Its intended player-facing or system-facing behavior.
- Functional requirements.
- Non-functional requirements.
- Acceptance criteria.
- Dependencies on existing systems.
- Required scenes, nodes, scripts, and resources.
- UI and input requirements, if applicable.
- Data and persistence requirements, if applicable.
- Performance constraints.
- Testing and validation expectations.
- Explicit exclusions and out-of-scope behavior.

Distinguish between:

- **Confirmed:** Explicitly established by the user or authoritative project documentation.
- **Derived:** A necessary or reasonable implication of confirmed requirements.
- **Proposed:** A recommendation introduced during implementation.
- **Undecided:** A question requiring clarification or approval.
- **Not Applicable:** A requirement that does not apply.

Do not silently convert proposals or assumptions into confirmed requirements.

### Step 4: Inspect Existing Systems

Before designing or writing implementation code:

1. Locate existing components related to the feature.
2. Read relevant scripts and scenes.
3. Identify existing interfaces and dependencies.
4. Inspect resource and data structures.
5. Understand initialization and lifecycle behavior.
6. Identify relevant signals and event flows.
7. Inspect existing tests.
8. Identify functionality that can be reused or extended.

Determine whether the feature requires:

- New components.
- Extensions to existing components.
- Changes to existing interfaces.
- New scenes or resources.
- Integration with other systems.

Follow the existing architecture unless an approved design explicitly changes it.

Do not duplicate functionality that can reasonably be reused.

### Step 5: Confirm the Implementation Approach

Use the approved technical design when one exists.

If no technical design exists:

- Use the existing architecture and applicable standards for straightforward implementation.
- Do not create unnecessary design documentation for trivial features.
- For significant features requiring architectural decisions, stop and use the `create-technical-design.md` workflow before implementation.

Confirm:

- Component responsibilities.
- Data ownership.
- Dependencies.
- Communication patterns.
- Scene and node organization.
- Resource lifecycle.
- Error handling.
- Testing approach.

If implementation reveals a significant conflict with the approved design, stop and present the issue before changing the design.

Do not silently replace approved architectural decisions.

### Step 6: Define the Implementation Plan

Break the feature into small, logically ordered implementation steps.

A typical plan may include:

1. Create or update required resources and data structures.
2. Implement core system logic.
3. Implement component interactions.
4. Integrate with existing systems.
5. Implement scenes and UI, if applicable.
6. Add input handling, if applicable.
7. Implement persistence, if applicable.
8. Add tests.
9. Perform integration and regression validation.
10. Update relevant documentation.

Identify dependencies between steps.

Prefer incremental implementation over large, unrelated changes.

For substantial features, present the implementation plan to the user before proceeding if the scope or design decisions require approval.

### Step 7: Implement the Feature

Implement the feature according to the confirmed requirements and approved design.

Follow these principles:

#### 7.1 Architecture

- Follow the established project structure.
- Keep responsibilities clear.
- Respect component boundaries.
- Avoid unnecessary coupling.
- Reuse existing systems where appropriate.
- Avoid introducing unnecessary global state.
- Keep dependencies explicit and manageable.

#### 7.2 GDScript

- Follow `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`.
- Use GDScript consistently.
- Follow naming and typing conventions.
- Use appropriate Godot classes and engine APIs.
- Avoid unnecessary dynamic behavior.
- Handle invalid states and references appropriately.
- Keep scripts focused and maintainable.

Do not introduce C# into the project unless explicitly authorized by the user.

#### 7.3 Scenes and Nodes

- Follow scene and node conventions.
- Keep scene hierarchies understandable.
- Assign responsibilities appropriately.
- Avoid unnecessary node dependencies.
- Respect node lifecycle and ownership.
- Use signals and references consistently with established architecture.

#### 7.4 Resources and Assets

- Follow resource-management and asset-pipeline standards.
- Use appropriate resource types.
- Avoid unnecessary duplication.
- Respect asset naming and directory conventions.
- Ensure referenced resources exist.
- Handle resource loading and cleanup correctly.

Do not fabricate or substitute production art or audio assets without authorization.

If required assets are missing, identify the dependency and use an approved placeholder only when appropriate.

#### 7.5 Gameplay Behavior

- Follow approved gameplay specifications.
- Preserve established game rules.
- Respect core game pillars and intended player experience.
- Implement only the behavior within the feature's scope.
- Avoid introducing unapproved gameplay mechanics or balance changes.

#### 7.6 Incremental Changes

Implement and validate logically independent parts of the feature.

After meaningful implementation steps:

- Inspect the affected code.
- Check for obvious errors.
- Run relevant validation when practical.
- Ensure the project remains consistent.

Do not wait until the entire feature is implemented to discover fundamental integration problems.

### Step 8: Implement Tests

Create or update tests according to the feature's behavior and complexity.

Consider:

- Unit tests for isolated logic.
- Integration tests for interactions between systems.
- Scene-level tests for node and lifecycle behavior.
- Gameplay tests for player-facing functionality.
- Regression tests for existing behavior affected by the feature.

Tests should verify observable requirements and acceptance criteria.

Include important edge cases, invalid inputs, and state transitions.

Follow `docs/02_technical_standards/TESTING_STRATEGY.md` and applicable QA standards.

Do not:

- Remove valid existing tests to make the implementation pass.
- Weaken assertions without justification.
- Write tests that only duplicate implementation details.
- Claim test coverage that has not been established.

If automated tests are not practical, document the required manual validation steps.

### Step 9: Validate the Implementation

Perform validation appropriate to the feature.

When supported by the project environment:

1. Run relevant automated tests.
2. Run available static checks.
3. Run Godot project validation or headless checks where appropriate.
4. Verify affected scenes and resources load correctly.
5. Verify the feature's expected behavior.
6. Validate important edge cases.
7. Check integration with dependent systems.
8. Run regression tests for affected functionality.
9. Inspect runtime output for relevant errors and warnings.

Validate each applicable acceptance criterion.

Distinguish between:

- Passed checks.
- Failed checks.
- Checks not executed.
- Checks unavailable in the current environment.
- Manual validation completed.
- Manual validation still required.

Do not claim that a feature works merely because the project compiles or the scripts contain no syntax errors.

### Step 10: Review the Changes

Inspect the complete implementation diff.

Verify that:

- All changes belong to the requested feature.
- The implementation matches confirmed requirements.
- The approved technical design was followed.
- Existing functionality remains intact.
- No unnecessary abstractions were introduced.
- No temporary debugging code remains.
- No duplicate or unused files were introduced.
- Naming and project structure follow standards.
- Tests cover important behavior.
- No unrelated user changes were overwritten.

If significant issues are identified, correct them before reporting completion.

For an independent code review, use the `code-review.md` workflow when requested or required by the project's review process.

The implementing agent must not approve its own changes.

### Step 11: Update Documentation

Determine which project-specific documents need updating.

Update relevant documentation when the implementation changes or establishes:

- Gameplay behavior.
- System responsibilities.
- Technical interfaces.
- Architecture.
- Data structures.
- Configuration.
- Persistence behavior.
- Testing procedures.
- Player-facing instructions.

Possible documents include:

- Gameplay system specifications.
- Mechanic specifications.
- Technical design documents.
- Technical overview.
- ADRs.
- Test plans.
- Other affected project documentation.

Use the applicable templates and documentation-management rules.

Do not modify shared studio standards to describe project-specific implementation details.

Do not create redundant documentation or update unrelated files.

If an implementation requires a significant architectural decision, document it through the ADR process and obtain approval where required.

### Step 12: Verify Definition of Done

Evaluate the implementation against:

`docs/00_studio_standards/DEFINITION_OF_DONE.md`

Confirm that all applicable completion criteria are satisfied.

If any criteria remain incomplete:

- Identify the outstanding work.
- Explain why it remains incomplete.
- Do not report the feature as fully complete.
- Identify any user action or approval required.

Passing tests alone does not automatically mean the feature is complete.

### Step 13: Report the Implementation

Present a concise implementation report.

Use the following structure:

# Feature Implementation Report

## Summary

Describe the implemented feature and its intended behavior.

## Requirements Implemented

List the confirmed requirements and acceptance criteria addressed.

Identify any requirements that remain incomplete.

## Changes Made

List the important files created or modified and explain their responsibilities.

## Architecture and Integration

Summarize the main components, dependencies, and integration points.

Mention any deviations from the approved technical design.

## Tests and Validation

Report:

- Tests created or modified.
- Tests executed and their results.
- Project validation performed.
- Manual checks completed.
- Regression checks performed.
- Validation not performed and why.

## Documentation

List project documents updated, if any.

## Remaining Work and Risks

Identify incomplete requirements, known limitations, unresolved risks, or required manual checks.

## Git Status

Report:

- Current branch.
- Working-tree status.
- Commits created, if explicitly authorized.
- Whether changes are ready for review.

Do not claim a commit, push, merge, or pull request was created unless it actually happened.

## Final Status

Choose the appropriate status:

- **Implemented and validated:** Applicable requirements are implemented and validation succeeded.
- **Implemented, validation incomplete:** Implementation is complete, but some required validation remains.
- **Partially implemented:** Some requirements remain incomplete.
- **Blocked:** Implementation cannot proceed without clarification, access, dependencies, or approval.

Do not report a feature as fully complete when required acceptance criteria remain unmet.

---

## Constraints

### Scope Control

The agent MUST:

- Implement only the requested and approved functionality.
- Preserve existing behavior unless a change is required.
- Avoid unrelated refactoring.
- Avoid speculative features.
- Respect established gameplay rules and specifications.
- Preserve unrelated user modifications.
- Request approval before expanding scope.

### Technical Quality

The agent MUST:

- Follow applicable studio and project standards.
- Follow the approved technical design.
- Use GDScript for project implementation.
- Prefer simple, maintainable solutions.
- Reuse existing functionality when appropriate.
- Keep responsibilities and dependencies clear.
- Handle relevant edge cases.
- Add appropriate tests.
- Validate the implementation honestly.

### Documentation

The agent MUST:

- Read the documentation inventory before documentation changes.
- Follow the documentation-management rules.
- Update relevant project-specific documentation.
- Never modify shared templates to store project-specific information.
- Never claim that documentation was updated when it was not.

### Git Safety

The agent MUST:

- Follow `.cline/rules/git-workflow.md`.
- Follow the studio branching strategy.
- Respect protected branches.
- Preserve uncommitted user changes.
- Never rewrite Git history.
- Never bypass branch protection or review requirements.
- Never commit, push, merge, or create pull requests without the required authorization.

### Human Approval

The user retains authority over significant design and implementation decisions.

The agent MUST request approval before:

- Changing approved requirements.
- Making significant architectural changes.
- Introducing new dependencies.
- Changing save-data formats or compatibility behavior.
- Modifying unrelated systems.
- Making destructive changes.
- Expanding the implementation scope.

An explicit request to implement an approved feature authorizes necessary implementation within that scope. It does not authorize unrelated changes.

---

## Completion Checklist

Before reporting completion, verify that:

- [ ] Repository structure and working-tree status were inspected.
- [ ] Applicable documentation was consulted.
- [ ] Feature requirements and acceptance criteria were identified.
- [ ] Existing systems and dependencies were inspected.
- [ ] An approved technical design was followed, when applicable.
- [ ] The implementation plan was established.
- [ ] The feature was implemented within scope.
- [ ] GDScript and architecture standards were followed.
- [ ] Required scenes, scripts, and resources were integrated.
- [ ] Appropriate tests were created or updated.
- [ ] Available validation was performed.
- [ ] Regression risks were considered.
- [ ] The final diff was inspected.
- [ ] Relevant project documentation was updated.
- [ ] Definition of Done criteria were evaluated.
- [ ] Incomplete work and limitations were reported.
- [ ] Unrelated user changes were preserved.
- [ ] Git operations followed studio rules.
- [ ] The final status accurately reflects the implementation.

## Final Principle

A feature is not complete simply because its code has been written.

It is complete when the approved behavior is implemented, integrated with the project, validated against its acceptance criteria, and consistent with studio standards.

Implement incrementally, keep changes focused, validate continuously, and preserve the intended player experience.