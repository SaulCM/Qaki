# Implement Feature

## 1. Purpose

This workflow defines how an AI agent should plan, implement, test, and validate a new or extended game feature.

The objective is to transform approved requirements and design specifications into a working, maintainable, and testable implementation that integrates correctly with the existing Godot project.

The implementation must preserve established architecture, follow studio standards, and deliver the intended player-facing behavior.

## 2. Scope

Use this workflow when:

- Implementing a new gameplay feature.
- Extending an existing feature.
- Implementing an approved gameplay mechanic.
- Implementing a gameplay system from an approved specification.
- Adding UI functionality.
- Integrating new scenes, scripts, resources, or assets.
- Connecting existing gameplay systems.
- Implementing technical functionality required by an approved feature.

Do not use this workflow for:

- Designing the entire game.
- Creating or approving new gameplay requirements.
- Fixing isolated defects unrelated to the feature.
- Performing unrelated refactoring.
- Making significant architectural changes without approval.
- Implementing features that have not been sufficiently specified or authorized.

Use `fix_bug.md` for defect correction and `design_game_mechanic.md` or `design_gameplay_system.md` when gameplay behavior still needs to be designed.

## 3. Authoritative References

Before implementation, inspect applicable studio standards and project documentation.

### 3.1 Studio references

Relevant references include:

- `docs/00_studio_standards/development_philosophy.md`
- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/code_review_guidelines.md`
- `docs/00_studio_standards/branching_strategy.md`
- `docs/00_studio_standards/naming_conventions.md`
- `docs/00_studio_standards/project_structure_standards.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/00_studio_standards/documentation_standards.md`
- `docs/02_technical_standards/architecture_guidelines.md`
- `docs/02_technical_standards/engine_standards.md`
- `docs/02_technical_standards/gdscript_standards.md`
- `docs/02_technical_standards/scene_and_node_convention.md`
- `docs/02_technical_standards/resource_management.md`
- `docs/02_technical_standards/event_and_signal_guidelines.md`
- `docs/02_technical_standards/asset_pipeline.md`
- `docs/02_technical_standards/testing_strategy.md`
- `docs/02_technical_standards/performance_guidelines.md`
- `docs/04_production_standards/sprint_workflow.md`
- `docs/05_qa_standards/acceptance_criteria_guidelines.md`

Read the standards relevant to the feature rather than loading every document unnecessarily.

### 3.2 Project references

Inspect available project documents, prioritizing:

- `docs/game_design/game_concept.md`
- `docs/game_design/game_vision.md`
- `docs/game_design/core_pillars.md`
- `docs/game_design/game_design_document.md`
- Relevant gameplay system specifications.
- Relevant mechanic specifications.
- Technical design documents.
- Acceptance criteria.
- Related test plans and test cases.
- Architecture decision records.
- Relevant art and audio direction documents.

These are possible reference locations, not assumptions that every document exists.

The agent MUST inspect the actual project structure and implementation before proceeding.

## 4. Workflow Overview

Follow these stages:

1. Understand the feature request.
2. Inspect project context and existing architecture.
3. Verify requirements and acceptance criteria.
4. Assess implementation scope and dependencies.
5. Define an implementation approach.
6. Prepare the development environment and branch.
7. Implement the feature incrementally.
8. Integrate required assets and resources.
9. Generate or update tests.
10. Execute validation.
11. Review the complete change set.
12. Update relevant documentation.
13. Report completion and prepare for human review.

Adapt the workflow to the feature's complexity. Do not introduce unnecessary planning or documentation for small, straightforward changes.

## 5. Stage 1: Understand the Feature Request

Identify exactly what the user wants implemented.

Extract:

- Feature name.
- Feature purpose.
- Problem or opportunity addressed.
- Expected player-facing behavior.
- Relevant requirements.
- Acceptance criteria.
- Dependencies.
- Constraints.
- Expected deliverables.
- Known technical risks.

Determine whether the request is:

- A completely new feature.
- An extension of an existing feature.
- An implementation of an approved mechanic.
- An implementation of a gameplay system.
- A technical improvement required by another feature.

### 5.1 Verify design readiness

Determine whether sufficient design information exists to begin implementation.

Check that:

- The intended behavior is understandable.
- Important rules are defined.
- Relevant inputs and outputs are known.
- Important states and transitions are documented.
- Dependencies are identified.
- Acceptance criteria are available or can be established.

If essential design information is missing, ask the user for clarification or recommend the appropriate design workflow.

Do not silently invent significant gameplay behavior to fill specification gaps.

## 6. Stage 2: Inspect Project Context and Architecture

Understand the existing project before changing it.

Inspect:

- Project directory structure.
- Relevant feature directories.
- Existing scenes and nodes.
- Relevant GDScript files.
- Resources and configuration data.
- Autoloads and shared services.
- Signals and event connections.
- Existing tests.
- Project configuration.
- Relevant technical documentation.
- Git working tree and recent changes.

### 6.1 Identify feature ownership

Determine:

- Which feature owns the functionality.
- Whether new functionality belongs in an existing feature.
- Whether shared functionality is genuinely required.
- Whether project-wide infrastructure must be extended.
- Which other features depend on the affected functionality.

Follow the feature-oriented structure defined in:

`docs/00_studio_standards/project_structure_standards.md`

Do not introduce a new top-level directory based solely on a technical type such as `scripts/`, `scenes/`, or `managers/`.

### 6.2 Understand existing responsibilities

Before adding components:

- Identify existing functionality that can be reused.
- Understand component responsibilities.
- Check current dependency direction.
- Identify public interfaces.
- Check for existing abstractions.
- Avoid duplicating established behavior.

Do not replace working systems merely because a different implementation is preferred.

## 7. Stage 3: Verify Requirements and Acceptance Criteria

Translate the approved feature requirements into implementation tasks.

For each requirement, identify:

- Expected behavior.
- Required components.
- Relevant data.
- Dependencies.
- Acceptance criteria.
- Testing requirements.

### 7.1 Requirements traceability

Maintain a connection between:

- Feature requirements.
- Design specifications.
- Implementation components.
- Acceptance criteria.
- Automated tests.
- Manual validation where necessary.

Use existing requirement IDs or backlog references when available.

### 7.2 Resolve ambiguity

If requirements conflict or are incomplete:

1. Check authoritative project documentation.
2. Identify the unresolved decision.
3. Evaluate whether a safe implementation assumption exists.
4. Ask the user when the decision affects gameplay, architecture, persistence, or scope.

Do not reinterpret approved requirements without authorization.

## 8. Stage 4: Assess Scope and Dependencies

Determine what is necessary to deliver the feature.

Identify:

- Required scripts.
- Required scenes and nodes.
- Required resources.
- Required assets.
- Required UI elements.
- Required audio and animation.
- Required system interactions.
- Required data changes.
- Required persistence behavior.
- Required tests.
- External dependencies, if any.

### 8.1 Dependency analysis

For each significant dependency, determine:

- Why it is needed.
- Which feature owns it.
- Whether it already exists.
- How the feature will interact with it.
- Whether the dependency introduces additional risks.

Avoid circular dependencies and unnecessary coupling.

### 8.2 Scope control

Keep implementation focused on the approved feature.

Do not add unrelated improvements, speculative functionality, or unnecessary abstractions.

If implementation reveals a necessary scope change, explain its impact and obtain approval when it materially changes the requested outcome.

## 9. Stage 5: Define an Implementation Approach

Establish a practical implementation sequence.

### 9.1 Break down the feature

Divide the work into logical implementation tasks.

Examples:

- Core gameplay logic.
- State management.
- Data and resources.
- Scene and node integration.
- Player input.
- UI feedback.
- Animation and audio.
- System communication.
- Persistence.
- Automated tests.

The task breakdown should be proportional to the feature's complexity.

### 9.2 Define implementation responsibilities

For each major component, identify:

- Purpose.
- Responsibility.
- Inputs and outputs.
- Owned state.
- Dependencies.
- Relevant interfaces.

Avoid creating components with overlapping or unclear responsibilities.

### 9.3 Identify risks

Evaluate:

- Technical uncertainty.
- Architectural impact.
- Performance concerns.
- Resource loading.
- Data compatibility.
- Integration complexity.
- Testing limitations.

For significant architectural decisions, follow the project's ADR process.

For substantial technical complexity, use a technical design document before implementation.

### 9.4 Implementation sequence

Prefer an incremental approach.

Implement and validate the smallest meaningful vertical slice first, then expand the feature.

A vertical slice should demonstrate a complete and observable portion of the intended functionality rather than only isolated infrastructure.

## 10. Stage 6: Prepare the Development Environment and Branch

Before modifying project files:

1. Inspect the Git working tree.
2. Identify uncommitted user changes.
3. Confirm the current branch.
4. Check the Godot project version.
5. Verify required tools and dependencies.
6. Confirm that the project opens and existing validation commands are available.

Follow:

`docs/00_studio_standards/branching_strategy.md`

For normal feature development:

1. Start from the appropriate up-to-date `develop` branch.
2. Create a task branch using the `feature/` prefix.
3. Keep implementation changes on that branch.
4. Prepare a pull request targeting `develop` when ready.

Example branch names:

- `feature/inventory-system`
- `feature/player-interaction`
- `feature/crafting-mechanic`

The agent MUST NOT:

- Commit directly to `main` or `develop`.
- Merge into protected branches.
- Bypass branch protection.
- Discard unrelated user modifications.
- Force-push without explicit authorization.

## 11. Stage 7: Implement the Feature Incrementally

Implement the feature according to the approved specifications and implementation approach.

### 11.1 Implementation principles

The implementation MUST:

- Follow the project's feature-oriented architecture.
- Use GDScript according to studio standards.
- Respect established naming conventions.
- Maintain clear component responsibilities.
- Minimize unnecessary coupling.
- Prefer composition where appropriate.
- Use signals for suitable event-driven communication.
- Keep state ownership explicit.
- Handle errors and invalid states appropriately.
- Avoid unnecessary complexity.
- Preserve existing functionality.

### 11.2 Godot implementation

Follow applicable Godot standards for:

- Scenes and nodes.
- Node lifecycle.
- GDScript.
- Resources.
- Autoloads.
- Signals.
- Input handling.
- Physics processing.
- Animation.
- Audio.
- Resource loading.
- Scene transitions.

Use the project's selected Godot version and avoid relying on APIs unavailable in that version.

### 11.3 Incremental validation

After each meaningful implementation step:

1. Inspect the modified files.
2. Verify syntax and type correctness where applicable.
3. Run relevant tests.
4. Open affected scenes when necessary.
5. Check runtime behavior.
6. Resolve issues before building additional functionality on top of them.

Do not accumulate unvalidated changes unnecessarily.

### 11.4 Avoid premature optimization

Prioritize correctness, maintainability, and the intended player experience.

Optimize when measurements or known project constraints justify it.

Follow `docs/02_technical_standards/performance_guidelines.md`.

## 12. Stage 8: Integrate Assets and Resources

Integrate required assets and resources according to studio standards.

Consider:

- Asset ownership and location.
- File naming.
- Import settings.
- Resource references.
- Scene integration.
- Animation configuration.
- Audio integration.
- UI resources.
- Asset loading and unloading.
- Licensing and source information.

Follow:

- `docs/02_technical_standards/asset_pipeline.md`
- `docs/03_art_audio_standards/art_asset_standards.md`
- `docs/03_art_audio_standards/audio_asset_standards.md`

Read only the references relevant to the assets being integrated.

### 12.1 Asset integrity

The agent MUST:

- Preserve original source assets.
- Avoid overwriting source files without authorization.
- Use existing approved assets when appropriate.
- Verify resource references.
- Avoid adding unlicensed or undocumented external assets.
- Avoid generating placeholder assets that could be mistaken for final assets.

If required assets are unavailable, identify the missing assets and propose appropriate placeholders or alternatives for approval.

## 13. Stage 9: Generate or Update Tests

Create tests that validate the feature's expected behavior.

Follow:

- `docs/02_technical_standards/testing_strategy.md`
- `docs/05_qa_standards/test_case_guidelines.md`
- `docs/07_agent_workflows/generate_tests.md`

Consider:

- Unit tests for isolated logic.
- Integration tests for system interactions.
- Scene tests for Godot scene behavior.
- End-to-end tests for important player-facing flows.
- Regression tests for existing functionality.
- Manual validation for visual, audio, or subjective behavior.

Tests should verify acceptance criteria and important edge cases.

Avoid creating tests that merely reproduce implementation details without validating meaningful behavior.

## 14. Stage 10: Execute Validation

Run relevant validation before considering the feature ready for review.

### 14.1 Functional validation

Verify:

- Required functionality works.
- Acceptance criteria are satisfied.
- Expected player interactions behave correctly.
- State transitions are correct.
- Data is updated correctly.
- System interactions work as intended.
- Error conditions are handled.
- Existing functionality remains intact.

### 14.2 Automated validation

Run relevant:

- Unit tests.
- Integration tests.
- Scene tests.
- End-to-end tests.
- Regression tests.
- Static analysis or linting tools, when available.

Run the full test suite when practical and appropriate for the change.

### 14.3 Godot validation

Where applicable, verify:

- The project opens successfully.
- GDScript parses without errors.
- Scenes load correctly.
- Resources resolve correctly.
- Signals connect correctly.
- Relevant gameplay flows work.
- No new runtime errors or unexpected warnings appear.
- Export or build validation succeeds when relevant.

### 14.4 Manual validation

Perform manual validation when automated tests cannot adequately verify:

- Visual presentation.
- Animation behavior.
- Audio behavior.
- Player interaction feel.
- Accessibility.
- Complex gameplay sequences.

Document the checks performed and their results.

### 14.5 Validation results

Classify checks as:

- **Passed:** Executed successfully and met expectations.
- **Failed:** Executed but did not meet expectations.
- **Not Run:** Not executed.
- **Blocked:** Could not execute due to an identified limitation.
- **Not Applicable:** Not relevant to the feature.

Never claim that validation passed if it was not performed.

## 15. Stage 11: Review the Complete Change Set

Inspect the entire implementation before preparing it for review.

Check:

- Modified files.
- Added and removed files.
- Architecture and feature ownership.
- Naming and code conventions.
- Component responsibilities.
- Dependencies.
- Resource references.
- Scene and node configuration.
- Tests.
- Documentation.
- Performance implications.
- Security and data integrity.
- Unrelated modifications.

Use Git diff to inspect the actual changes.

### 15.1 Scope review

Verify that the change set contains no:

- Unrelated refactoring.
- Unrequested features.
- Temporary debugging code.
- Unused files.
- Unnecessary dependencies.
- Accidental asset modifications.
- Generated cache files.
- Hardcoded test data.
- Destructive changes to existing functionality.

### 15.2 Quality review

Check the implementation against:

`docs/00_studio_standards/definition_of_done.md`

Address identified issues before reporting the feature as ready.

## 16. Stage 12: Update Relevant Documentation

Update project documentation when implementation changes documented behavior or introduces information necessary for future development.

Potential updates include:

- Gameplay system specifications.
- Mechanic specifications.
- Technical design documents.
- Architecture decision records.
- Test cases.
- Test plans.
- Configuration documentation.
- Relevant asset or integration documentation.

Do not duplicate information unnecessarily.

Follow the project's documentation management rules and update the documentation inventory when files are created, moved, renamed, deprecated, or deleted.

The agent MUST NOT mark documentation as Approved without explicit human approval.

## 17. Pull Request Preparation

When implementation and validation are complete, prepare the changes for human review.

The pull request should include:

- Feature name.
- Purpose and context.
- Requirements or backlog references.
- Summary of implementation.
- Important architectural decisions.
- Files or components affected.
- Tests added or updated.
- Validation results.
- Screenshots or recordings when useful.
- Known limitations.
- Outstanding issues.

Follow:

`docs/00_studio_standards/code_review_guidelines.md`

The agent MAY prepare a pull request if the available tools and permissions support it.

The agent MUST NOT:

- Approve its own pull request.
- Merge its own pull request.
- Bypass required reviews.
- Mark the feature as integrated before the merge succeeds.

A human reviewer is responsible for approval and integration.

## 18. Revision Process

When review feedback or user requests require changes:

1. Read the feedback carefully.
2. Identify the affected requirements or implementation.
3. Evaluate the impact of the requested change.
4. Modify only the necessary components.
5. Update affected tests.
6. Run relevant validation again.
7. Inspect the updated diff.
8. Report the changes.

Preserve unrelated work and previously approved decisions.

If feedback conflicts with an approved design or introduces substantial scope changes, explain the conflict and request clarification.

## 19. Completion Criteria

The implementation workflow is complete when:

- The feature request is understood.
- Relevant project documentation and implementation have been inspected.
- Requirements and acceptance criteria are established.
- Scope and dependencies are identified.
- An appropriate implementation approach is defined.
- The feature is implemented according to approved requirements.
- Relevant assets and resources are integrated.
- Appropriate tests are created or updated.
- Relevant validation has been executed.
- Results and limitations are documented accurately.
- The complete change set has been reviewed.
- Relevant documentation has been updated.
- The changes are ready for human review.

Completion of this workflow does not imply pull request approval, integration, or release.

## 20. AI Agent Rules

The agent MUST:

- Inspect the project before making changes.
- Read relevant specifications and standards.
- Implement approved requirements.
- Preserve existing functionality and user modifications.
- Follow feature-oriented architecture.
- Use GDScript and the project's selected Godot version.
- Keep changes focused on the requested feature.
- Implement incrementally.
- Generate or update relevant tests.
- Execute appropriate validation.
- Report actual validation results.
- Document important assumptions and limitations.
- Request approval for significant scope or architectural changes.
- Follow Git and documentation management rules.
- Prepare a clear implementation report.

The agent MUST NOT:

- Invent significant gameplay requirements.
- Redefine approved design decisions.
- Introduce unnecessary abstractions.
- Perform unrelated refactoring.
- Introduce dependencies without justification and required approval.
- Overwrite user changes.
- Modify protected branches directly.
- Bypass tests or quality checks.
- Claim unverified functionality works.
- Approve or merge its own pull request.
- Mark its own work as approved.

## 21. Required Documentation

Before implementing a feature, consult:

- [Branching Strategy](../00_studio_standards/BRANCHING_STRATEGY.md)
- [Definition of Done](../00_studio_standards/DEFINITION_OF_DONE.md)
- [GDScript Standards](../02_technical_standards/GDSCRIPT_STANDARDS.md)
- [Architecture Guidelines](../02_technical_standards/ARCHITECTURE_GUIDELINES.md)
- [Testing Strategy](../02_technical_standards/TESTING_STRATEGY.md)

## 22. Final Report Format

After completing the workflow, provide the following report:

### Feature Implementation Report

**Feature:** [Feature name]

**Status:** Implemented / Partially Implemented / Blocked / Ready for Review

**Purpose:** [Brief description]

**Requirements:** [Relevant requirements or backlog references]

**Implementation summary:** [Description of completed functionality]

**Components created or modified:**
- [File path and purpose]

**Dependencies:** [Relevant systems, resources, or integrations]

**Tests created or updated:**
- [Test file and purpose]

**Validation results:**
- [Validation check]: Passed / Failed / Not Run / Blocked / Not Applicable

**Documentation updates:** [Updated documents or None]

**Known limitations:** [Unresolved issues or None]

**Branch:** [Feature branch name]

**Pull request:** [Reference or Not Created]

**Next step:** [Human review, additional implementation, or another appropriate action]

Do not report a feature as fully completed when required functionality or validation remains outstanding.