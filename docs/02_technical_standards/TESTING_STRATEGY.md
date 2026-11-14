# Testing Strategy

## 1. Purpose

This document establishes the studio-wide technical strategy for testing software developed with Godot.

Its purpose is to define consistent approaches for verifying functionality, detecting defects, validating integrations, and maintaining confidence in project changes.

The strategy covers:

- Testing principles and objectives.
- Testing levels and types.
- Test organization.
- Automated and manual testing.
- Unit, integration, and end-to-end testing.
- Godot-specific testing considerations.
- Testability and code design.
- Test data and fixtures.
- Regression testing.
- Test execution and reporting.
- Continuous integration.
- AI-assisted testing.

The objective is to establish a practical and maintainable testing approach appropriate for small, AI-assisted game development teams.

## 2. Scope

This strategy applies to:

- GDScript code.
- Gameplay systems.
- Feature implementations.
- Scene composition and lifecycle.
- Resource definitions and management.
- UI behavior.
- Game state and persistence.
- Cross-feature integrations.
- Game configuration.
- Technical infrastructure.
- Automated build and validation processes.

These standards primarily target Godot 4.x projects using GDScript.

Specific testing tools, frameworks, platforms, and execution environments MAY be selected at the project level.

## 3. Testing Principles

### 3.1 Quality Is Continuous

Testing MUST be integrated throughout development rather than postponed until the end of a project.

Developers SHOULD validate changes as early as practical.

### 3.2 Test According to Risk

Testing effort SHOULD reflect the potential impact and likelihood of failure.

Systems involving persistence, progression, combat calculations, economy, save data, and shared infrastructure MAY require more extensive verification than isolated presentation elements.

### 3.3 Automate Repeatable Verification

Tests that are deterministic, frequently repeated, and reasonably inexpensive SHOULD be automated.

Manual testing SHOULD remain available for exploratory evaluation, usability, visual quality, and situations where automation provides insufficient value.

### 3.4 Test Observable Behavior

Tests SHOULD verify externally observable behavior rather than depend unnecessarily on implementation details.

Tests SHOULD remain valid when internal implementations change without changing the expected behavior.

### 3.5 Keep Tests Maintainable

Tests MUST be understandable, focused, and maintainable.

Developers SHOULD avoid:

- Excessive test abstraction.
- Duplicated test setup.
- Fragile dependencies on scene-tree details.
- Unnecessary test complexity.
- Tests that validate implementation details without meaningful value.
- Tests that pass without actually verifying their intended behavior.

### 3.6 Reliable Test Results

Automated tests SHOULD produce consistent results under equivalent conditions.

Flaky tests MUST be investigated rather than routinely ignored or rerun until they pass.

### 3.7 Testing Does Not Replace Design Validation

Automated tests verify technical behavior and defined expectations.

They do not independently establish that a mechanic is enjoyable, balanced, understandable, accessible, or appropriate for the intended player experience.

Gameplay and player experience MUST also be evaluated through appropriate design validation and playtesting.

## 4. Testing Levels

The studio SHOULD use the following testing levels according to project needs.

### 4.1 Unit Testing

Unit tests verify individual functions, components, or isolated pieces of behavior.

Examples include:

- Damage calculations.
- Inventory capacity rules.
- Currency transactions.
- Resource validation.
- Progression requirements.
- State transitions.
- Utility functions.
- Input-independent gameplay calculations.

Unit tests SHOULD:

- Focus on one behavior or logical responsibility.
- Use controlled inputs.
- Verify expected outputs and state changes.
- Avoid unnecessary dependencies on the scene tree.
- Execute quickly.
- Cover relevant boundary conditions.

Pure logic SHOULD be separated from engine-dependent behavior when doing so improves testability without creating unnecessary abstractions.

### 4.2 Integration Testing

Integration tests verify that multiple components or systems work together correctly.

Examples include:

- Inventory interacting with item definitions.
- Combat interacting with health and damage components.
- Player interactions with world objects.
- UI interacting with gameplay state.
- Scene initialization with configured Resources.
- Save and load operations restoring game state.
- Signals coordinating multiple features.

Integration tests SHOULD focus on meaningful boundaries between components and features.

### 4.3 Scene Testing

Scene tests verify that scenes are correctly structured, initialized, and capable of performing their intended responsibilities.

Examples include:

- Scene instantiation.
- Required child nodes.
- Script attachment.
- Exported property configuration.
- Signal connections.
- Resource references.
- Node lifecycle behavior.
- Scene cleanup.

Scene tests MAY inspect the scene tree when structural correctness is part of the expected behavior.

### 4.4 End-to-End Testing

End-to-end tests verify complete workflows through multiple systems.

Examples include:

- Starting a new game.
- Completing a gameplay interaction.
- Acquiring and using an item.
- Completing a progression milestone.
- Saving and loading a game.
- Navigating between major game scenes.

End-to-end tests SHOULD focus on critical player-facing workflows.

They SHOULD NOT attempt to automate every possible gameplay interaction.

### 4.5 Manual Testing

Manual testing is appropriate when human observation or judgment is necessary.

Examples include:

- Gameplay feel.
- Visual presentation.
- Audio quality.
- UI usability.
- Accessibility.
- Difficulty and balance.
- Narrative presentation.
- Exploratory testing.
- Unusual gameplay sequences.

Manual testing SHOULD be documented when it verifies important requirements or release-critical behavior.

## 5. Testing Types

Testing levels describe the scope of verification. Testing types describe the characteristics or purpose of that verification.

### 5.1 Functional Testing

Verify that features behave according to their documented requirements.

Tests SHOULD cover:

- Expected behavior.
- Valid inputs.
- Invalid inputs.
- State changes.
- Preconditions.
- Postconditions.
- Relevant edge cases.

### 5.2 Regression Testing

Regression testing verifies that previously working behavior remains correct after changes.

Tests SHOULD prioritize:

- Previously defective behavior.
- Shared systems.
- Critical gameplay workflows.
- Persistence and progression.
- Public feature interfaces.
- Frequently modified systems.

A bug fix SHOULD include a regression test when the behavior can reasonably be automated.

### 5.3 Smoke Testing

Smoke tests provide a quick verification that a project or build is operational.

They MAY include:

- Project loading.
- Main scene initialization.
- Essential resource loading.
- Basic input handling.
- Critical scene transitions.
- Basic gameplay execution.

Smoke tests SHOULD remain small and fast enough to execute frequently.

### 5.4 Sanity Testing

Sanity tests verify that a specific change or focused area behaves as expected after implementation or modification.

They SHOULD target the affected functionality and its immediate dependencies.

### 5.5 Performance Testing

Performance testing evaluates whether the game meets its defined performance expectations.

It MAY include:

- Frame time.
- CPU utilization.
- GPU utilization.
- Memory consumption.
- Loading time.
- Physics workload.
- Scene instantiation.
- Large entity counts.

Performance tests SHOULD use representative conditions and repeatable scenarios where practical.

Refer to `docs/02_technical_standards/performance_guidelines.md`.

### 5.6 Compatibility Testing

Compatibility testing verifies behavior across supported configurations.

Depending on the project, this MAY include:

- Operating systems.
- Hardware capabilities.
- Display resolutions.
- Input devices.
- Graphics settings.
- Export configurations.
- Supported Godot versions.

Projects SHOULD define their supported configurations before establishing compatibility requirements.

### 5.7 Data and Persistence Testing

Persistence testing verifies that game data is stored and restored correctly.

It SHOULD cover:

- Save creation.
- Save loading.
- Default values.
- Missing or invalid data.
- Data version compatibility.
- Migration behavior.
- Interrupted or failed saves.
- Recovery behavior.
- Progression consistency.

Refer to `docs/02_technical_standards/data_persistence_guidelines.md`.

### 5.8 Security and Reliability Testing

When a project processes user-controlled data, external inputs, or network communication, tests SHOULD verify relevant validation and failure handling.

Examples include:

- Invalid configuration.
- Malformed save data.
- Unexpected resource references.
- Invalid network responses.
- Unauthorized operations where applicable.
- Unexpected input values.

## 6. Test Organization

### 6.1 Feature-Oriented Test Structure

Tests MUST follow the approved feature-oriented project structure.

Tests SHOULD be colocated with the feature or shared functionality they verify.

Example:

```text
features/
├── inventory/
│   ├── scenes/
│   ├── scripts/
│   ├── resources/
│   └── tests/
│       ├── unit/
│       └── integration/
│
├── combat/
│   ├── scenes/
│   ├── scripts/
│   └── tests/
│       ├── unit/
│       └── integration/
│
shared/
└── tests/
    └── unit/

tests/
└── integration/
```

This structure is illustrative. Projects SHOULD create only the test directories they actually need.

### 6.2 Test Ownership

Each feature SHOULD own the tests that verify its internal behavior.

Cross-feature integration tests MAY be placed in the project-level `tests/integration/` directory.

Shared functionality SHOULD have tests within its owning shared area.

### 6.3 Test File Naming

Test files MUST follow the project's naming conventions.

Test filenames SHOULD clearly identify the behavior or component being tested.

Examples:

```text
test_health_component.gd
test_inventory_operations.gd
test_save_manager.gd
test_damage_calculation.gd
```

### 6.4 Test Separation

Production code and test code SHOULD remain distinguishable.

Test-only helpers, fixtures, and mock implementations MUST NOT become accidental production dependencies.

### 6.5 Test Discoverability

Test organization SHOULD make it straightforward to identify:

- What is being tested.
- Which feature owns the test.
- How the test is executed.
- What dependencies are required.

## 7. Test Design and Quality

### 7.1 Arrange, Act, Assert

Tests SHOULD use a clear structure:

1. Arrange: establish the required state and inputs.
2. Act: execute the behavior being tested.
3. Assert: verify the expected result.

Each test SHOULD communicate its intent without requiring unnecessary interpretation.

### 7.2 One Primary Behavior

A test SHOULD verify one primary behavior.

Additional assertions MAY be included when they describe the same behavior or its direct consequences.

### 7.3 Meaningful Assertions

Assertions MUST verify meaningful expectations.

Tests SHOULD NOT merely execute code without checking the resulting behavior.

### 7.4 Positive and Negative Cases

Important functionality SHOULD be tested using:

- Valid inputs.
- Invalid inputs.
- Boundary values.
- Missing dependencies.
- Unexpected state.
- Repeated operations where relevant.

### 7.5 Boundary Testing

Tests SHOULD consider values at and around important limits.

Examples include:

- Minimum and maximum health.
- Empty and full inventories.
- Zero and negative quantities.
- Resource limits.
- Progression thresholds.
- Invalid identifiers.
- Empty collections.

### 7.6 Determinism

Tests SHOULD avoid unnecessary dependence on:

- Random number generation.
- Wall-clock time.
- External network services.
- User-specific settings.
- Uncontrolled scene state.
- Execution order.
- Machine-specific assumptions.

When randomness is relevant, use controlled seeds or injectable random sources where practical.

### 7.7 Test Independence

Tests SHOULD be independently executable.

A test MUST NOT depend on another test having executed first unless an explicitly managed integration scenario requires shared setup.

Tests SHOULD restore or isolate state to prevent unintended interference.

## 8. Godot-Specific Testing Practices

### 8.1 Testing GDScript

GDScript tests SHOULD verify:

- Function outputs.
- State changes.
- Signal emissions.
- Error handling.
- Type and value constraints.
- Component behavior.
- Relevant lifecycle behavior.

### 8.2 Testing Nodes

Node-dependent tests SHOULD create the required nodes and add them to an appropriate scene tree before testing behavior that depends on tree membership or lifecycle callbacks.

Tests SHOULD clean up instantiated nodes and resources appropriately.

### 8.3 Testing Scenes

Scene tests MAY instantiate a `PackedScene` and inspect its resulting node hierarchy.

Example:

```gdscript
var scene: PackedScene = preload(
    "res://features/player/scenes/player.tscn"
)


func test_player_scene_can_be_instantiated() -> void:
    var player := scene.instantiate()

    assert_not_null(player)

    player.free()
```

The example illustrates the concept. Actual test syntax and assertion methods MUST match the selected testing framework.

### 8.4 Testing Signals

Signal tests SHOULD verify:

- Whether the expected signal is emitted.
- Whether it is emitted at the correct time.
- Whether the payload is correct.
- Whether it is emitted the expected number of times.

### 8.5 Testing Asynchronous Behavior

Tests involving deferred calls, timers, coroutines, or asynchronous resource loading MUST wait for the relevant operation to complete before asserting its result.

Tests SHOULD use bounded waiting conditions and fail clearly when expected events do not occur.

### 8.6 Testing Physics

Physics-dependent tests SHOULD account for physics frame execution and engine timing.

They SHOULD avoid assumptions that physics calculations complete immediately after an operation is requested.

### 8.7 Testing Input

Input-dependent tests SHOULD use controlled input simulation where supported.

Gameplay logic SHOULD be separated from direct input polling when that separation improves testability.

### 8.8 Testing Resources

Tests SHOULD verify:

- Resource loading.
- Default values.
- Configuration validity.
- Resource sharing behavior.
- Independent copies when required.
- Expected behavior when references are missing.

### 8.9 Engine Compatibility

Tests MUST use APIs and test framework capabilities supported by the project's configured Godot version.

## 9. Testability and Code Design

### 9.1 Testable Architecture

Production code SHOULD be designed so important behavior can be tested without unnecessarily starting the entire game.

### 9.2 Separation of Responsibilities

Logic that can be tested independently SHOULD be separated from unrelated presentation, input, and scene orchestration responsibilities when doing so improves maintainability.

### 9.3 Dependency Management

External dependencies SHOULD be explicit.

Where appropriate, dependencies MAY be supplied through initialization methods, exported properties, or other clear interfaces.

### 9.4 Avoid Excessive Global State

Tests SHOULD avoid depending on mutable global state.

Autoloads and global services SHOULD expose behavior that can be tested without requiring extensive project-wide setup.

### 9.5 Testability Versus Abstraction

Developers MUST NOT introduce unnecessary abstractions solely to make code easier to mock.

Testing requirements SHOULD inform design decisions without overriding simplicity and maintainability.

## 10. Test Data, Fixtures, and Mocks

### 10.1 Test Data

Test data SHOULD be small, explicit, and representative of the behavior being verified.

Tests SHOULD avoid depending on mutable production data or unrelated game content.

### 10.2 Fixtures

Reusable fixtures MAY provide common setup for tests.

Fixtures SHOULD remain focused and understandable.

### 10.3 Mocks and Stubs

Mocks and stubs MAY be used to isolate dependencies.

They SHOULD only simulate behavior relevant to the test.

Mocks MUST NOT replace verification of important integration behavior.

### 10.4 Test Isolation

Tests SHOULD use temporary or isolated data when modifying files, save data, configuration, or persistent state.

Test execution MUST NOT unintentionally overwrite real user data.

### 10.5 Randomized Test Data

Randomized test data MAY be used when it provides meaningful additional coverage.

Randomized tests SHOULD use reproducible seeds and report sufficient information to reproduce failures.

## 11. Test Frameworks and Tools

### 11.1 Framework Selection

Projects MAY use Godot's built-in capabilities or an external testing framework.

The selection SHOULD consider:

- Godot version compatibility.
- GDScript support.
- Unit and integration testing capabilities.
- Scene and node testing.
- Signal testing.
- Headless execution.
- CI compatibility.
- Maintenance and documentation.
- Setup complexity.

### 11.2 Avoid Unnecessary Tooling

The studio SHOULD prefer the simplest testing setup that provides sufficient coverage and reliable results.

Additional frameworks SHOULD only be introduced when their benefits justify their maintenance costs.

### 11.3 Tool Configuration

Project-specific testing tools, dependencies, configuration, and execution commands MUST be documented in the game repository.

### 11.4 Tool Changes

Significant changes to the testing framework or execution environment SHOULD be documented and reviewed.

## 12. Regression and Defect Prevention

### 12.1 Regression Tests

When a defect is discovered, developers SHOULD determine whether an automated regression test is practical.

When practical, the test SHOULD reproduce the defect before verifying the correction.

### 12.2 Shared Systems

Changes to shared functionality SHOULD trigger appropriate regression testing of its consumers.

### 12.3 Critical Workflows

Projects SHOULD identify critical workflows and maintain sufficient test coverage for them.

Examples MAY include:

- New game initialization.
- Save and load.
- Player progression.
- Inventory transactions.
- Combat resolution.
- Scene transitions.
- Major gameplay interactions.

### 12.4 Regression Scope

Regression testing SHOULD be proportional to the scope and risk of a change.

Changes to foundational systems MAY require broader validation than isolated feature changes.

## 13. Test Execution Strategy

### 13.1 During Development

Developers SHOULD execute focused tests while implementing or modifying functionality.

The smallest relevant test scope SHOULD be executed first.

### 13.2 Before Integration

Before submitting changes for integration, developers SHOULD:

- Run relevant unit tests.
- Run relevant integration tests.
- Execute applicable static validation.
- Verify affected scenes.
- Check for runtime errors.
- Review test results.

### 13.3 Continuous Integration

Automated tests SHOULD be integrated into CI workflows when practical.

CI SHOULD prioritize reliable, repeatable validation.

Depending on project requirements, CI MAY execute:

- GDScript static analysis.
- Project import validation.
- Headless test execution.
- Unit tests.
- Integration tests.
- Smoke tests.
- Export or build validation.

### 13.4 Release Validation

Before a release, projects SHOULD execute the relevant regression suite and validate critical workflows in representative target environments.

### 13.5 Test Execution Order

A typical execution order SHOULD prioritize fast feedback:

1. Static checks and parsing.
2. Focused unit tests.
3. Feature integration tests.
4. Broader integration tests.
5. Scene and smoke tests.
6. End-to-end workflows.
7. Performance and compatibility validation where required.

The actual order MAY be adapted to project architecture and tooling.

## 14. Test Results and Reporting

### 14.1 Test Results

Test execution SHOULD produce clear and reviewable results.

Reports SHOULD identify:

- Tests executed.
- Tests passed.
- Tests failed.
- Tests skipped.
- Execution environment.
- Relevant errors.
- Known limitations.

### 14.2 Failure Investigation

Failed tests MUST be investigated.

Developers SHOULD distinguish between:

- Production defects.
- Test defects.
- Environment problems.
- Unstable tests.
- Invalid assumptions.
- Unsupported configurations.

### 14.3 Skipped Tests

Tests SHOULD NOT be skipped without justification.

Skipped tests SHOULD include an explanation and, where appropriate, a plan to restore coverage.

### 14.4 Flaky Tests

Flaky tests MUST NOT be treated as reliable validation.

They SHOULD be investigated, corrected, or explicitly quarantined with documented justification.

### 14.5 Honest Reporting

Developers and AI agents MUST report test execution accurately.

Tests that were not executed MUST NOT be reported as passed.

## 15. Test Coverage

### 15.1 Coverage Purpose

Coverage metrics MAY be used to identify untested code and areas requiring additional verification.

Coverage MUST NOT be treated as the sole measure of software quality.

### 15.2 Meaningful Coverage

Testing SHOULD prioritize important behavior and risk rather than pursuing arbitrary coverage percentages.

### 15.3 Coverage Expectations

Projects MAY define coverage targets for critical systems.

Such targets SHOULD be justified by project risk and maintainability requirements.

### 15.4 Coverage Gaps

Important untested behavior SHOULD be documented when it represents a known quality risk.

## 16. Performance and Scalability of Tests

### 16.1 Execution Cost

Tests SHOULD execute efficiently enough to support frequent use.

Slow tests SHOULD be reviewed for unnecessary setup, excessive dependencies, or avoidable engine initialization.

### 16.2 Test Suite Growth

As the test suite grows, projects SHOULD organize tests so that focused tests can be executed independently from broader validation suites.

### 16.3 Parallel Execution

Parallel test execution MAY be introduced when supported by the selected tooling and when tests are sufficiently isolated.

Tests MUST NOT share mutable state in ways that cause unpredictable results during parallel execution.

### 16.4 Resource Cleanup

Tests SHOULD release instantiated nodes, temporary files, and other resources when no longer needed.

## 17. Manual Testing and Playtesting

### 17.1 Purpose

Manual testing complements automated verification.

It is particularly important for evaluating player-facing qualities that cannot be adequately established through assertions.

### 17.2 Exploratory Testing

Exploratory testing SHOULD be used to investigate unexpected behavior, complex interactions, and scenarios not covered by existing test cases.

### 17.3 Gameplay Playtesting

Playtesting SHOULD evaluate:

- Mechanic clarity.
- Player feedback.
- Gameplay flow.
- Difficulty.
- Balance.
- Progression.
- Player motivation.
- Usability.
- Frustration and recovery.

### 17.4 Manual Test Documentation

Important manual testing activities SHOULD record:

- Objective.
- Build or version tested.
- Relevant configuration.
- Steps or scenario.
- Expected behavior.
- Observed behavior.
- Issues discovered.

Detailed playtesting practices SHOULD be maintained in the applicable QA and game design documentation.

## 18. AI-Assisted Testing

AI agents MUST treat testing as part of implementation rather than an optional final step.

Agents MUST:

- Inspect existing tests before adding new ones.
- Follow the project's selected testing framework.
- Add or update tests when behavior changes.
- Prefer tests that verify observable behavior.
- Include relevant boundary and failure cases.
- Avoid unnecessary test dependencies.
- Execute applicable tests when tools and environments permit.
- Investigate failures rather than silently ignoring them.
- Report exactly which tests were executed.
- Identify tests that could not be executed and explain why.

Agents MUST NOT:

- Claim tests passed without executing them.
- Delete or weaken tests merely to make a change pass.
- Modify expected results without validating the intended behavior.
- Introduce arbitrary coverage targets.
- Hide flaky tests.
- Treat mocked behavior as proof of integration correctness.
- Modify production code solely to satisfy a flawed test without evaluating the underlying requirement.

Agents SHOULD request owner approval before making significant changes to the project's testing framework, test infrastructure, or established quality gates.

## 19. Testing Strategy Review Checklist

Before completing testing-related work, verify:

- [ ] Testing requirements are understood.
- [ ] The appropriate testing level has been selected.
- [ ] Tests follow feature-oriented organization.
- [ ] Test names and structure are clear.
- [ ] Tests verify meaningful behavior.
- [ ] Relevant positive and negative cases are covered.
- [ ] Important boundary conditions are considered.
- [ ] Tests are sufficiently isolated.
- [ ] Test data is controlled.
- [ ] Godot lifecycle behavior is handled correctly.
- [ ] Scene and Resource dependencies are validated.
- [ ] Regression tests are added when appropriate.
- [ ] Relevant tests have been executed.
- [ ] Failures have been investigated.
- [ ] Test results are reported accurately.
- [ ] Known limitations are documented.

## 20. Exceptions

Exceptions MAY be introduced when project-specific requirements justify alternative testing practices.

Exceptions SHOULD:

- Have a clear justification.
- Identify affected systems or workflows.
- Explain the associated quality risks.
- Define compensating validation where appropriate.
- Receive project owner approval when they affect established quality gates or critical workflows.
- Be documented when they establish a reusable exception.

## 21. Related Documents

This strategy SHOULD be used alongside:

- `docs/00_studio_standards/development_philosophy.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/code_review_guidelines.md`
- `docs/00_studio_standards/project_structure_standards.md`
- `docs/02_technical_standards/architecture_guidelines.md`
- `docs/02_technical_standards/gdscript_standards.md`
- `docs/02_technical_standards/scene_and_node_convention.md`
- `docs/02_technical_standards/resource_management.md`
- `docs/02_technical_standards/data_persistence_guidelines.md`
- `docs/02_technical_standards/performance_guidelines.md`
- `docs/02_technical_standards/event_and_signal_guidelines.md`
- Applicable documents in `docs/05_qa_standards/`

## 22. Maintenance

This strategy SHOULD be reviewed when:

- The studio adopts a different testing framework.
- Godot introduces relevant testing capabilities.
- CI workflows change significantly.
- Repeated defects reveal gaps in the testing approach.
- Project complexity requires additional testing levels.
- Existing testing practices become unnecessarily expensive or difficult to maintain.

Changes MUST preserve the purpose of this document as a reusable studio-wide technical standard.