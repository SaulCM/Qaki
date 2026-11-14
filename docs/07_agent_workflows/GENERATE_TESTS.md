# Generate Tests

## 1. Purpose

This workflow defines how an AI agent should analyze, design, generate, and validate tests for the game project.

The objective is to create meaningful, maintainable, and reliable tests that verify expected behavior, detect regressions, and provide confidence in the quality of the implementation.

Generated tests must validate actual requirements and behavior rather than merely increase test counts or code coverage.

## 2. Scope

Use this workflow when:

- Creating tests for a new feature or gameplay system.
- Adding tests for an existing implementation.
- Increasing coverage of important gameplay behavior.
- Creating regression tests for previously reported defects.
- Testing interactions between gameplay systems.
- Validating scene and node behavior.
- Testing data persistence and resource management.
- Improving existing test coverage.
- Creating automated tests for critical game flows.

Do not use this workflow for:

- Fixing implementation defects without a testing request.
- Replacing the studio's testing strategy.
- Creating a complete project test plan.
- Conducting human playtesting sessions.
- Writing bug reports.
- Implementing unrelated production functionality.

If test execution reveals defects, document the findings and recommend using `fix_bug.md` to investigate and correct them.

## 3. Authoritative References

Before generating tests, inspect the relevant studio standards and project documentation.

### 3.1 Studio references

Relevant references include:

- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/code_review_guidelines.md`
- `docs/02_technical_standards/gdscript_standards.md`
- `docs/02_technical_standards/architecture_guidelines.md`
- `docs/02_technical_standards/testing_strategy.md`
- `docs/05_qa_standards/acceptance_criteria_guidelines.md`
- `docs/05_qa_standards/test_case_guidelines.md`
- `docs/05_qa_standards/regression_testing.md`
- `docs/06_templates/test_plan_template.md`

Read only the references relevant to the testing task.

### 3.2 Project references

Inspect available project documentation, prioritizing:

- Relevant gameplay system specifications.
- Relevant mechanic specifications.
- Acceptance criteria.
- Existing test cases.
- Existing automated tests.
- Technical design documents.
- Relevant architecture decisions.
- Bug reports associated with the functionality.
- Project-specific testing instructions.

These are possible reference locations, not assumptions that every document exists.

The agent MUST inspect the actual project structure and existing tests before generating new ones.

## 4. Workflow Overview

Follow these stages:

1. Understand the testing request.
2. Inspect project context and implementation.
3. Identify testing objectives and scope.
4. Analyze requirements and expected behavior.
5. Identify test scenarios.
6. Select appropriate test levels and techniques.
7. Design test cases and test data.
8. Generate automated tests.
9. Execute and validate the tests.
10. Review test quality and maintainability.
11. Report the results.

Adapt the level of detail to the complexity and risk of the functionality being tested.

## 5. Stage 1: Understand the Testing Request

Identify what the user wants to test.

Extract the available information:

- Feature, mechanic, or system under test.
- Expected behavior.
- Relevant requirements.
- Acceptance criteria.
- Known defects or risks.
- Required test levels.
- Existing test coverage.
- Target platform or environment.
- Testing tools and framework.
- Constraints or limitations.

Determine whether the request involves:

- New automated tests.
- Additional test coverage.
- Regression tests.
- Unit tests.
- Integration tests.
- Scene tests.
- End-to-end tests.
- Performance tests.
- Data persistence tests.
- Test refactoring or maintenance.

If the request is ambiguous, ask focused questions when the missing information materially affects test design.

Do not invent expected behavior.

## 6. Stage 2: Inspect Project Context and Implementation

Examine the project before creating tests.

Inspect:

- Project directory structure.
- Existing test directories.
- Test framework and configuration.
- Related GDScript files.
- Related scenes and nodes.
- Resources and configuration data.
- Relevant autoloads.
- Signals and event connections.
- Existing fixtures and test utilities.
- Related test cases.
- CI workflows and test execution commands.

### 6.1 Understand the implementation

Determine:

- Which feature owns the functionality.
- Which components are responsible for the behavior.
- Which methods and signals are involved.
- Which state and data are relevant.
- What dependencies are required.
- Which behaviors can be tested in isolation.
- Which behaviors require multiple components or scenes.

Do not generate tests based solely on filenames or class names. Understand the actual behavior being tested.

### 6.2 Inspect existing coverage

Before creating a test:

- Search for existing tests covering the same behavior.
- Identify reusable fixtures and helpers.
- Check whether an existing test can be extended.
- Identify missing scenarios.
- Avoid duplicate test coverage without a clear reason.

Prefer improving existing tests over creating redundant ones.

## 7. Stage 3: Identify Testing Objectives and Scope

Define what the tests should establish.

Examples include:

- A function produces the expected result.
- A mechanic follows its documented rules.
- A system transitions between states correctly.
- Invalid operations are rejected.
- Resources are consumed or generated correctly.
- Signals are emitted under the correct conditions.
- Components interact correctly.
- Data persists across save and load operations.
- Previously fixed defects do not return.

### 7.1 Define scope

Identify:

- Functionality included in testing.
- Functionality excluded from testing.
- Relevant dependencies.
- Required test environments.
- Required test data.
- Expected validation results.

Prioritize behavior that is critical to gameplay, data integrity, stability, and player experience.

## 8. Stage 4: Analyze Requirements and Expected Behavior

Translate requirements into observable and verifiable conditions.

Use authoritative sources such as:

- Approved acceptance criteria.
- Approved gameplay specifications.
- Technical design documents.
- Established implementation contracts.
- Explicit user instructions.

For each requirement, identify:

- Expected input.
- Preconditions.
- Expected behavior.
- Expected output.
- State changes.
- Side effects.
- Failure conditions.
- Relevant constraints.

### 8.1 Resolve ambiguity

If a requirement does not define expected behavior sufficiently:

1. Identify the ambiguity.
2. Determine whether existing approved documentation resolves it.
3. Inspect established implementation behavior when appropriate.
4. Ask the user if the expected result remains unclear.

Do not encode an assumption into a test and treat it as an approved requirement.

### 8.2 Test traceability

Where practical, associate tests with:

- Requirement IDs.
- Acceptance criteria.
- Test case IDs.
- Bug IDs.
- Feature or system names.

This makes it easier to understand why a test exists and what behavior it protects.

## 9. Stage 5: Identify Test Scenarios

Identify scenarios that provide meaningful coverage of the expected behavior.

Consider the following categories.

### 9.1 Positive scenarios

Verify that valid operations work correctly.

Examples:

- Valid inputs produce expected results.
- Valid actions are accepted.
- Required state transitions occur.
- Resources are updated correctly.
- Expected events are emitted.

### 9.2 Negative scenarios

Verify that invalid operations are handled correctly.

Examples:

- Invalid inputs are rejected.
- Missing dependencies are handled safely.
- Insufficient resources prevent an operation.
- Invalid state transitions are prevented.
- Invalid references do not cause unexpected crashes.

### 9.3 Boundary scenarios

Test relevant limits and boundaries.

Examples:

- Minimum and maximum values.
- Empty collections.
- Single-element collections.
- Zero values.
- Maximum capacity.
- Values immediately outside permitted ranges.

### 9.4 State transition scenarios

Verify:

- Valid transitions.
- Invalid transitions.
- Repeated transitions.
- Interrupted operations.
- Recovery behavior.
- State consistency after transitions.

### 9.5 Integration scenarios

Verify interactions between relevant components.

Examples:

- Inventory and crafting.
- Combat and character health.
- Quest progression and rewards.
- Player input and interaction systems.
- Save systems and gameplay state.

### 9.6 Regression scenarios

Include tests for previously fixed defects and important existing behavior.

Refer to `docs/05_qa_standards/regression_testing.md`.

### 9.7 Edge cases

Consider:

- Missing or invalid references.
- Unexpected execution order.
- Repeated calls.
- Simultaneous events.
- Scene changes.
- Resource loading failures.
- Initialization problems.
- Save/load interruptions.
- Unexpected runtime states.

Prioritize scenarios based on risk and relevance rather than attempting to test every theoretically possible combination.

## 10. Stage 6: Select Appropriate Test Levels

Choose the test level that best validates the intended behavior.

### 10.1 Unit tests

Use unit tests to validate isolated logic.

Examples:

- Calculations.
- Validation functions.
- State rules.
- Inventory operations.
- Resource calculations.
- Data transformations.

Prefer unit tests when dependencies can be isolated without losing the behavior being tested.

### 10.2 Integration tests

Use integration tests to validate interactions between components.

Examples:

- Two gameplay components exchanging information.
- A system reacting to a signal.
- Inventory and crafting interactions.
- Character attributes affecting combat calculations.

### 10.3 Scene tests

Use scene tests to validate:

- Scene initialization.
- Node configuration.
- Scene dependencies.
- Node interactions.
- Signal connections.
- Scene lifecycle behavior.

### 10.4 End-to-end tests

Use end-to-end tests for important player-facing workflows.

Examples:

- Starting a new game.
- Completing an interaction sequence.
- Acquiring and using an item.
- Completing a quest objective.
- Saving and loading a game.

Use them selectively because they generally require more setup and are more sensitive to environmental changes.

### 10.5 Performance tests

Use performance tests when the behavior has meaningful performance requirements.

Examples:

- Large collections.
- Frequent system updates.
- Entity processing.
- Resource loading.
- Complex calculations.

Use measurable thresholds when project requirements define them.

### 10.6 Manual testing

Some behaviors require human evaluation.

Examples:

- Visual quality.
- Animation smoothness.
- Audio presentation.
- Subjective gameplay feel.
- Accessibility and usability.
- Complex player experience.

When automation is unsuitable, document the required manual validation rather than creating unreliable automated tests.

## 11. Stage 7: Design Test Cases and Test Data

Before writing automated tests, define the important test cases.

### 11.1 Test case structure

Each meaningful test case should identify:

- Test ID, when required.
- Test title.
- Objective.
- Related requirement or acceptance criterion.
- Preconditions.
- Input or test data.
- Execution steps.
- Expected result.
- Relevant cleanup requirements.

Follow `docs/05_qa_standards/test_case_guidelines.md`.

Do not create separate documentation for every trivial automated test unless the project's QA process requires it.

### 11.2 Test data

Choose data that validates meaningful behavior.

Consider:

- Typical valid data.
- Minimum and maximum values.
- Invalid data.
- Empty data.
- Boundary values.
- Special cases.
- Different game states.
- Different player progression levels.

Use deterministic data whenever possible.

Avoid depending on:

- Random values without controlled seeds.
- External services without isolation.
- Existing player save files.
- Machine-specific paths.
- Uncontrolled system time.
- Unstable network conditions.

### 11.3 Test isolation

Tests should be independent whenever practical.

Ensure that:

- Each test establishes its own required state.
- Tests do not depend on execution order.
- Temporary resources are cleaned up.
- Shared state is reset.
- Test data does not leak between tests.
- Tests do not modify real player data.

Use fixtures and reusable helpers when they improve clarity and reduce duplication.

## 12. Stage 8: Generate Automated Tests

Generate tests using the project's existing testing framework and conventions.

Do not introduce a new testing framework without justification and human approval.

### 12.1 Test organization

Follow the project's feature-oriented structure.

Place tests close to the functionality they validate.

For example:

```text
features/
└── inventory/
    ├── scripts/
    ├── scenes/
    └── tests/
        ├── test_inventory.gd
        └── test_item_stacking.gd
```

For shared functionality:

```text
shared/
└── tests/
    └── test_shared_utility.gd
```

Project-level integration tests may be organized separately when they validate interactions across multiple features.

Follow the actual project structure rather than forcing this example onto an existing repository.

### 12.2 GDScript requirements

Generated tests MUST:

- Follow the project's GDScript standards.
- Use clear and descriptive test names.
- Use explicit assertions.
- Validate observable behavior.
- Avoid unnecessary implementation coupling.
- Use appropriate test setup and teardown.
- Clean up temporary objects and resources.
- Avoid modifying production code solely to simplify tests unless justified.

### 12.3 Assertion quality

Use assertions that clearly communicate expected behavior.

Prefer:

- Exact comparisons for deterministic values.
- Approximate comparisons for floating-point calculations.
- Explicit state assertions.
- Collection size and content assertions.
- Signal emission assertions.
- Error or failure condition assertions where supported.

Avoid assertions that merely verify an object exists when the actual behavior needs validation.

### 12.4 Test framework conventions

Use the testing framework already configured in the project.

If GUT or GdUnit4 is installed, follow its established conventions and version-specific APIs.

If no testing framework exists:

1. Inspect the project's testing requirements.
2. Identify suitable options.
3. Explain the tradeoffs.
4. Request approval before introducing a dependency or changing project configuration.

Do not assume that a testing framework is installed.

### 12.5 Godot-specific testing

Consider relevant Godot behavior:

- Scene instantiation.
- Node lifecycle.
- `_ready()`, `_process()`, and `_physics_process()`.
- Signal connections.
- Deferred calls.
- Resource loading.
- Autoload initialization.
- Scene tree dependencies.
- Timers and asynchronous operations.
- Input handling.
- Physics interactions.

Tests should account for engine execution order and lifecycle requirements.

Avoid arbitrary delays when a deterministic signal, condition, or synchronization mechanism can be used.

## 13. Stage 9: Execute and Validate the Tests

Run the generated tests using the project's configured commands and environment.

### 13.1 Execution requirements

Verify:

- Tests are discovered by the test framework.
- Test scripts parse successfully.
- Required scenes and resources load.
- Tests execute without unexpected runtime errors.
- Assertions evaluate correctly.
- Cleanup executes successfully.
- Results are reported accurately.

### 13.2 Test failures

When a test fails:

1. Inspect the failure message.
2. Identify the failing assertion or execution step.
3. Determine whether the test or implementation is incorrect.
4. Check the expected behavior against authoritative documentation.
5. Investigate environmental or setup problems.
6. Correct the test if its assumptions are wrong.
7. Report implementation defects separately.

Do not modify production code automatically just to make generated tests pass.

If the test exposes a confirmed defect, document it and recommend the `fix_bug.md` workflow.

### 13.3 Existing test suite

Run relevant existing tests to detect regressions.

For broader changes, run the full test suite when practical.

If the full suite cannot be executed, identify the tests that were run and explain the limitation.

### 13.4 Execution results

Classify each validation result as:

- **Passed:** Executed successfully and met expectations.
- **Failed:** Executed but did not meet expectations.
- **Not Run:** Not executed.
- **Blocked:** Could not execute due to an identified limitation.
- **Not Applicable:** Not relevant to the testing task.

Never claim that tests passed if they were not executed.

## 14. Stage 10: Review Test Quality and Maintainability

Review the generated tests before presenting them.

### 14.1 Correctness

Verify that:

- Tests validate documented behavior.
- Expected results are correct.
- Preconditions are established.
- Assertions are meaningful.
- Negative cases are handled.
- Boundary cases are covered where relevant.
- Tests do not encode unsupported assumptions.

### 14.2 Reliability

Verify that:

- Tests produce deterministic results.
- Tests do not depend on execution order.
- Time-dependent behavior is controlled.
- Random behavior is controlled where possible.
- External dependencies are isolated.
- Cleanup is reliable.
- Tests do not modify real player data.

### 14.3 Maintainability

Verify that:

- Test names describe the behavior.
- Setup is understandable.
- Assertions are clear.
- Helpers are reusable where appropriate.
- Duplication is minimized.
- Tests avoid unnecessary implementation details.
- Test organization follows project conventions.

### 14.4 Coverage quality

Determine whether the tests cover:

- Important expected behavior.
- Critical failure conditions.
- Relevant boundaries.
- Important system interactions.
- Previously reported defects.
- High-risk gameplay behavior.

Code coverage can help identify untested code, but it does not prove that behavior is adequately tested.

Do not optimize for coverage percentages at the expense of meaningful assertions.

## 15. Stage 11: Report the Results

Present a concise testing report.

Include:

- Tested feature or system.
- Testing objectives.
- Test files created or modified.
- Test scenarios covered.
- Test framework used.
- Execution commands.
- Execution results.
- Existing tests executed.
- Defects discovered.
- Known limitations.
- Remaining testing gaps.

Clearly distinguish generated tests from tests that were successfully executed.

## 16. Documentation and Traceability

Update project documentation when the testing work materially changes test coverage or testing requirements.

Potential updates include:

- Test case documentation.
- Test plans.
- Requirement-to-test references.
- Regression test records.
- QA reports.
- Relevant technical or gameplay specifications.

Follow the project's documentation management rules.

Do not create unnecessary documentation for every small test addition.

If test generation reveals ambiguous or contradictory requirements, report the issue rather than silently changing authoritative documentation.

## 17. Completion Criteria

The workflow is complete when:

- The testing request is understood.
- Relevant project documentation and implementation have been inspected.
- Testing objectives and scope are defined.
- Expected behavior is established.
- Relevant test scenarios are identified.
- Appropriate test levels are selected.
- Test cases and data are designed.
- Automated tests are generated when applicable.
- Generated tests are executed when the environment permits.
- Results and failures are reported accurately.
- Test quality and maintainability are reviewed.
- Relevant existing tests are executed when practical.
- Testing limitations and uncovered risks are documented.

Completion of this workflow does not imply that the tested implementation is defect-free.

## 18. AI Agent Rules

The agent MUST:

- Inspect existing tests before generating new ones.
- Use authoritative requirements and expected behavior.
- Follow the project's testing framework and conventions.
- Respect feature-oriented test organization.
- Generate meaningful and deterministic tests.
- Include relevant positive, negative, and boundary scenarios.
- Use appropriate assertions.
- Isolate test data and dependencies.
- Clean up temporary resources.
- Execute tests when the environment permits.
- Report actual results.
- Distinguish test failures from implementation defects.
- Identify testing gaps and limitations.
- Preserve existing production behavior.
- Request approval before introducing testing dependencies or changing project configuration.

The agent MUST NOT:

- Invent expected behavior.
- Create redundant tests without justification.
- Generate tests solely to increase coverage percentages.
- Modify production code merely to satisfy incorrect tests.
- Remove or weaken assertions to make tests pass.
- Disable failing tests without authorization.
- Depend on uncontrolled randomness or timing.
- Modify real player save data.
- Claim tests passed without execution.
- Hide discovered defects.
- Mark its own work as approved.

## 19. Final Report Format

After completing the workflow, provide the following report:

### Test Generation Report

**Feature/System:** [Name]

**Status:** Completed / Partially Completed / Blocked

**Testing objectives:** [What the tests are intended to validate]

**Test framework:** [Framework and version, if known]

**Test files created:**
- [File path and purpose]

**Test files modified:**
- [File path and reason, or None]

**Test scenarios covered:**
- [Scenario]
- [Scenario]

**Execution commands:**
- [Command used]

**Execution results:**
- Passed: [Number]
- Failed: [Number]
- Not Run: [Number]
- Blocked: [Number]

**Defects discovered:** [Description or None]

**Coverage gaps:** [Uncovered important behavior or None identified]

**Validation limitations:** [Limitations or None]

**Documentation updates:** [Updated documents or None]

**Next step:** [Additional testing, bug investigation, human review, or another appropriate action]

Do not report tests as successful unless their execution results support that conclusion.