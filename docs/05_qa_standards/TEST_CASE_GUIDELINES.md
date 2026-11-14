# Test Case Guidelines

## 1. Purpose

This document defines the standards and guidelines for creating, documenting, organizing, executing, and maintaining test cases across game projects.

The objectives are to:

- Establish a consistent test case format.
- Ensure test cases are clear, repeatable, and verifiable.
- Improve test coverage of functional and non-functional requirements.
- Support manual and automated testing.
- Improve traceability between requirements, acceptance criteria, and test results.
- Reduce ambiguity during test execution.
- Support regression testing and defect verification.
- Maintain a useful and manageable test case repository.

Test cases SHOULD provide sufficient information for another person or authorized testing tool to execute them and evaluate the results consistently.

## 2. Scope

These guidelines apply to test cases created for:

- Gameplay mechanics and systems.
- Player controls and input handling.
- Character behavior and movement.
- Combat and interactions.
- Progression and rewards.
- Economy and resource management.
- Inventory and equipment.
- User interface and navigation.
- Save and loading systems.
- Scene transitions.
- AI and NPC behavior.
- Art, animation, and visual effects.
- Audio and music.
- Performance and resource usage.
- Platform compatibility.
- Data integrity.
- Security-related behavior.
- Integrations and external dependencies.

Test cases MAY be used for unit, integration, scene, end-to-end, regression, compatibility, performance, and other testing activities.

These guidelines define how individual test cases are written and maintained. Testing strategy and execution procedures are covered in their respective documents.

## 3. Test Case Principles

### 3.1. Clear and Unambiguous

Test cases MUST use clear language.

Instructions SHOULD describe specific actions and expected outcomes rather than subjective interpretations.

Avoid instructions such as:

- "Check if the character works correctly."
- "Verify that the UI looks good."
- "Make sure the feature behaves normally."

Prefer instructions such as:

- "Move the character forward for three seconds and verify that the character moves in the configured direction."
- "Open the inventory and verify that all acquired items appear in the item list."
- "Select the Settings option and verify that the settings screen is displayed."

### 3.2. Verifiable Expected Results

Every test case MUST define an expected result that can be evaluated.

Expected results SHOULD describe observable behavior, state changes, values, or measurable conditions.

### 3.3. Repeatability

Test cases SHOULD produce consistent results when executed under the same conditions.

Document relevant preconditions, test data, environment requirements, and configuration.

### 3.4. Focused Scope

Each test case SHOULD validate a clearly defined objective.

Avoid combining unrelated scenarios into a single test case.

Related steps MAY be grouped when they form one coherent workflow.

### 3.5. Independence

Test cases SHOULD be executable independently whenever practical.

When a test depends on another test or a specific state, document that dependency explicitly.

### 3.6. Traceability

Test cases SHOULD reference relevant requirements, acceptance criteria, features, or defects.

This allows the project to identify which expected behaviors have been validated.

### 3.7. Maintainability

Test cases MUST be updated when relevant functionality, requirements, or expected behavior changes.

Obsolete test cases SHOULD be reviewed and retired rather than left misleading or unusable.

## 4. Test Case Identification

Each test case MUST have a unique and stable identifier.

### 4.1. Identifier Format

Recommended format:

`TC-XXX`

Examples:

- `TC-001`
- `TC-002`
- `TC-015`
- `TC-120`

Identifiers SHOULD remain unchanged when a test case is edited, provided its original testing objective remains the same.

A new identifier SHOULD be assigned when a test case is retired and a substantially different test is created.

### 4.2. Test Case Titles

Titles MUST briefly describe the behavior being validated.

Recommended format:

`[Feature or System] Expected behavior`

Examples:

- `[Inventory] Add an item to the inventory`
- `[Combat] Apply damage to an enemy`
- `[Save System] Restore player progress`
- `[Main Menu] Open the settings screen`
- `[Movement] Prevent movement through solid obstacles`

Titles SHOULD be concise, specific, and understandable without reading the entire test case.

## 5. Test Case Structure

Each test case SHOULD contain the following fields.

### 5.1. Required Fields

| Field | Description |
|---|---|
| Test ID | Unique test case identifier. |
| Title | Short description of the behavior being tested. |
| Objective | What the test intends to verify. |
| Preconditions | Required initial conditions. |
| Test Steps | Actions required to execute the test. |
| Expected Result | Observable outcome expected from execution. |

### 5.2. Recommended Fields

| Field | Description |
|---|---|
| Feature | Related game feature or system. |
| Test Type | Functional, integration, regression, usability, etc. |
| Priority | Importance of executing the test. |
| Test Data | Inputs and data required for execution. |
| Requirements | Related requirements or acceptance criteria. |
| Dependencies | Other systems, tests, or conditions required. |
| Environment | Required platform, build, or configuration. |
| Automation Status | Manual, Automated, or Candidate for Automation. |
| Related Defects | Relevant defect identifiers. |
| Notes | Additional information or limitations. |

Projects MAY adapt this structure to their test management tools, provided the essential information remains available.

## 6. Writing Test Objectives

The objective explains what the test case verifies.

It SHOULD:

- Focus on one primary behavior.
- Describe the intended validation.
- Avoid implementation details unless technically necessary.
- Be consistent with approved requirements.
- Identify the relevant system or interaction.

Example:

**Weak objective:**

"Test the inventory."

**Improved objective:**

"Verify that the inventory correctly stores an item acquired by the player."

The objective describes the intended behavior, while the test steps describe how to validate it.

## 7. Writing Preconditions

Preconditions describe the state that must exist before executing a test.

They MAY include:

- Game state.
- Player state.
- Inventory contents.
- Character attributes.
- Available resources.
- Quest or progression state.
- Scene or level.
- Active configuration.
- Required permissions.
- Save data.
- External dependencies.

Example:

```markdown
### Preconditions

- The game is running.
- The player is in the inventory-enabled gameplay scene.
- The inventory has at least one available slot.
- The player does not already possess the test item.
```

Preconditions SHOULD be minimal.

Do not include unnecessary setup requirements that do not affect the test objective.

## 8. Writing Test Steps

Test steps MUST describe the actions needed to execute the test.

### 8.1. Step Structure

Each step SHOULD:

- Have a clear sequence.
- Describe one logical action.
- Use specific controls or interactions.
- Avoid ambiguous language.
- Include necessary values or inputs.
- Be understandable without additional explanation.

Example:

```markdown
### Test Steps

1. Start the game.
2. Load the specified test save.
3. Open the inventory.
4. Select the test item.
5. Use the item.
6. Observe the player's health value.
```

### 8.2. Action Specificity

Prefer specific instructions over assumptions.

Weak:

"Use the item."

Improved:

"Select the Health Potion in the inventory and activate the Use command."

### 8.3. Avoid Excessive Steps

Test cases SHOULD remain focused.

If a test becomes too long or validates several unrelated behaviors, consider splitting it into multiple test cases.

### 8.4. Setup and Cleanup

When a test modifies game state, document any required cleanup.

Examples include:

- Restoring player attributes.
- Removing test inventory items.
- Resetting progression.
- Deleting temporary save files.
- Returning to the initial scene.
- Restoring configuration settings.

Cleanup SHOULD prevent one test from interfering with another.

## 9. Writing Expected Results

Expected results define what must happen when the test is executed successfully.

They MUST be observable and sufficiently specific.

### 9.1. Expected Result Quality

Weak:

"The item works correctly."

Improved:

"The player's health increases by the configured healing amount, and the potion is removed from the inventory."

Weak:

"The character moves correctly."

Improved:

"The character moves in the requested direction and does not pass through solid collision objects."

### 9.2. Multiple Expected Conditions

A test MAY contain multiple expected conditions when they are part of the same objective.

Example:

After using a health potion:

- The player's health increases by the configured amount.
- Health does not exceed the maximum health value.
- The potion is removed from the inventory.
- The inventory displays the updated item quantity.

Each condition SHOULD be independently verifiable.

### 9.3. Avoid Subjective Language

Terms such as "smooth," "good," "fast," and "correct" SHOULD be replaced with measurable or observable criteria when possible.

Subjective evaluations MAY be used for playtesting and artistic review when accompanied by defined evaluation criteria.

## 10. Test Case Types

Test cases SHOULD be classified according to their validation purpose.

### 10.1. Functional Test Cases

Verify that a feature behaves according to its requirements.

Examples:

- Adding an item to inventory.
- Opening a menu.
- Applying damage.
- Completing a quest.
- Activating an interaction.

### 10.2. Positive Test Cases

Verify expected behavior when valid inputs and conditions are provided.

Examples:

- Using an available health potion.
- Equipping a compatible weapon.
- Loading a valid save file.
- Completing an available objective.

### 10.3. Negative Test Cases

Verify that invalid actions or conditions are handled appropriately.

Examples:

- Attempting to use an item that does not exist.
- Equipping an incompatible item.
- Loading corrupted save data.
- Performing an interaction outside its valid conditions.

### 10.4. Boundary Test Cases

Verify behavior at important limits or thresholds.

Examples:

- Minimum and maximum health.
- Empty inventory.
- Maximum inventory capacity.
- Zero available resources.
- Progression threshold boundaries.
- Timer expiration.

### 10.5. Integration Test Cases

Verify that related systems work together correctly.

Examples:

- Combat updates player health.
- Inventory changes are reflected in the UI.
- Quest completion grants the configured reward.
- Save and loading preserve equipment.
- Scene transitions preserve required player state.

### 10.6. Regression Test Cases

Verify that previously working behavior remains functional after changes.

Examples:

- A previously fixed inventory defect does not return.
- A movement update does not break collision behavior.
- A UI refactor does not break navigation.
- A save system modification does not invalidate existing supported saves.

### 10.7. Performance Test Cases

Verify that the game meets defined performance expectations.

Examples:

- Scene loading completes within the project-defined target.
- Memory usage remains within the configured budget.
- Frame time remains within the required threshold under a representative workload.

Performance test cases MUST specify relevant hardware, configuration, workload, and measurement conditions.

### 10.8. Compatibility Test Cases

Verify functionality under supported platform or configuration variations.

Examples:

- Keyboard and controller input.
- Supported screen resolutions.
- Supported operating systems.
- Graphics configuration changes.
- Platform-specific save behavior.

### 10.9. Usability and Accessibility Test Cases

Verify that interactions and information presentation meet defined usability or accessibility requirements.

Examples:

- Menus can be navigated using supported input methods.
- Important text meets readability requirements.
- Relevant accessibility settings are applied consistently.
- UI feedback communicates interaction results.

### 10.10. Exploratory Testing

Exploratory testing does not always require predefined step-by-step test cases.

When useful findings emerge, they SHOULD be converted into reproducible test cases or defect reports.

## 11. Test Case Design Techniques

The following techniques MAY be used to improve test coverage.

### 11.1. Equivalence Partitioning

Divide input data into groups expected to behave similarly.

Example: A health potion may accept valid healing values within a defined range and reject invalid values outside that range.

Test representative values from each relevant group rather than testing every possible value.

### 11.2. Boundary Value Analysis

Test values at and around important boundaries.

For an inventory capacity of 20 items, relevant test values may include:

- 0 items.
- 1 item.
- 19 items.
- 20 items.
- An attempted 21st item.

### 11.3. Decision Table Testing

Use decision tables when behavior depends on combinations of conditions.

Example:

| Player Has Key | Door Is Locked | Expected Result |
|---|---|---|
| Yes | Yes | Door unlocks if the key is valid. |
| No | Yes | Door remains locked. |
| Yes | No | Door can be opened without unlocking. |
| No | No | Door can be opened. |

### 11.4. State Transition Testing

Use state transition scenarios when functionality depends on the current state.

Examples:

- Idle to attacking.
- Alive to dead.
- Locked to unlocked.
- Quest active to completed.
- Unsaved to saved.

Tests SHOULD verify valid transitions and prevent invalid transitions.

### 11.5. Use Case Testing

Design tests around realistic player workflows.

Examples:

- Start a new game and complete the initial objective.
- Acquire equipment and verify its effect.
- Complete a quest and collect its reward.
- Save progress, restart the game, and continue.

### 11.6. Pairwise Testing

When multiple configuration variables exist, pairwise testing MAY help reduce the number of combinations while still covering interactions between pairs of values.

Use it when exhaustive testing is impractical and the risk justifies combinatorial coverage.

## 12. Test Data Management

Test data MUST be controlled and appropriate for the test objective.

### 12.1. Test Data Requirements

Document relevant data such as:

- Player attributes.
- Inventory contents.
- Equipment.
- Resource quantities.
- Quest states.
- Save files.
- Configuration values.
- Level or scene identifiers.
- Random seeds.

### 12.2. Data Isolation

Tests SHOULD avoid modifying normal player data or unrelated development files.

Use dedicated test saves, fixtures, temporary resources, or isolated environments when practical.

### 12.3. Data Reproducibility

When random behavior affects test results, use controlled random seeds or deterministic test configurations when supported.

Document any randomness that cannot be controlled.

### 12.4. Sensitive Data

Do not include passwords, personal information, private credentials, or production secrets in test cases or test data.

## 13. Test Case Priority

Test cases SHOULD be prioritized according to their importance.

| Priority | Description | Examples |
|---|---|---|
| Critical | Essential functionality or data integrity. | Game startup, save and loading, core gameplay loop. |
| High | Important functionality with significant player impact. | Combat, inventory, progression, essential navigation. |
| Medium | Supporting functionality with moderate impact. | Optional interactions, secondary UI features. |
| Low | Isolated or lower-impact functionality. | Minor cosmetic behavior or optional presentation details. |

Priority MUST reflect the importance of executing the test, not the severity of a defect discovered during execution.

## 14. Test Case Execution

### 14.1. Execution Preparation

Before executing a test case:

- Confirm the correct build or version.
- Review the test objective.
- Verify preconditions.
- Prepare required test data.
- Confirm the test environment.
- Identify dependencies.
- Review relevant known issues.

### 14.2. Execution Results

Each execution SHOULD record one of the following statuses:

| Status | Meaning |
|---|---|
| Passed | Actual behavior matches the expected result. |
| Failed | Actual behavior does not match the expected result. |
| Blocked | Execution cannot proceed because of an external dependency or condition. |
| Skipped | The test was intentionally not executed. |
| Not Run | The test has not been executed. |
| Not Applicable | The test does not apply to the evaluated build or configuration. |

A test MUST NOT be marked as Passed when its expected result was not verified.

### 14.3. Recording Results

Execution records SHOULD include:

- Test ID.
- Build or version.
- Execution date.
- Tester or execution agent.
- Environment.
- Actual result.
- Status.
- Evidence when relevant.
- Related defect ID when failed.

### 14.4. Failure Handling

When a test fails:

1. Record the actual behavior.
2. Capture relevant evidence.
3. Determine whether the failure is reproducible.
4. Compare the result with the expected behavior.
5. Report a defect when appropriate.
6. Link the defect to the test case.
7. Retest after a correction.

Do not modify the expected result to match unexpected behavior unless the requirement has intentionally changed and has been approved.

## 15. Test Case Automation

Test cases MAY be automated when automation provides sufficient value.

### 15.1. Automation Candidates

Good candidates include:

- Deterministic calculations.
- Repeated validation scenarios.
- Data serialization and deserialization.
- Inventory rules.
- Progression logic.
- State transitions.
- Save and loading.
- Stable integration workflows.
- Critical regression checks.

### 15.2. Automation Suitability

Before automating a test, consider:

- Execution frequency.
- Test stability.
- Maintenance cost.
- Technical feasibility.
- Reliability of assertions.
- Test data requirements.
- Value of automated feedback.

Not every manual test should be automated.

### 15.3. Automation Status

Recommended values:

- Manual.
- Automated.
- Candidate for Automation.
- Automation Not Practical.

### 15.4. Automated Test Quality

Automated test cases SHOULD:

- Use clear assertions.
- Avoid unnecessary dependencies.
- Produce actionable failure messages.
- Be repeatable.
- Isolate test data.
- Clean up temporary state.
- Avoid relying on execution order.
- Be maintained alongside the tested functionality.

## 16. Test Case Organization

Test cases SHOULD be organized by feature, system, or testing objective.

Recommended project-specific structure:

```text
docs/qa/test_cases/
├── README.md
├── gameplay/
│   ├── movement.md
│   ├── combat.md
│   └── inventory.md
├── ui/
│   └── navigation.md
├── progression/
│   └── quest_system.md
├── persistence/
│   └── save_and_load.md
├── integration/
└── compatibility/
```

Projects MAY organize test cases directly in a test management tool instead of Markdown files.

The selected location or tool SHOULD be documented in the game project.

### 16.1. Organization Rules

- Group test cases logically.
- Avoid duplicate test definitions.
- Keep test identifiers unique.
- Maintain references to related requirements.
- Separate reusable test cases from execution reports.
- Keep project-specific test cases within the game project.
- Do not duplicate studio-wide QA standards in project documentation.

## 17. Test Case Templates

### 17.1. Standard Test Case Template

```markdown
# [TC-XXX] [Feature] Expected Behavior

## Information

- **Test ID:** TC-XXX
- **Feature:** 
- **Test Type:** 
- **Priority:** 
- **Automation Status:** 
- **Related Requirement:** 
- **Related Defect:** 

## Objective

Describe what this test case verifies.

## Preconditions

- Condition 1
- Condition 2

## Test Data

- Input or data required for execution.

## Test Steps

1. First action.
2. Second action.
3. Third action.

## Expected Result

Describe the expected observable behavior.

## Cleanup

Describe any required cleanup or state restoration.

## Notes

Additional information, dependencies, or limitations.
```

### 17.2. Test Execution Record Template

```markdown
# Test Execution Record

## Execution Information

- **Test ID:**
- **Build / Version:**
- **Branch / Commit:**
- **Execution Date:**
- **Executed By:**
- **Environment:**

## Preconditions

Record the actual initial conditions.

## Execution Results

| Step | Action | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| 1 | First action | Expected behavior | Observed behavior | Passed |
| 2 | Second action | Expected behavior | Observed behavior | Failed |

## Overall Status

- [ ] Passed
- [ ] Failed
- [ ] Blocked
- [ ] Skipped
- [ ] Not Run
- [ ] Not Applicable

## Evidence

Attach or reference relevant screenshots, videos, logs, or other evidence.

## Related Defects

List relevant defect identifiers.

## Notes

Additional observations or limitations.
```

## 18. AI-Assisted Test Case Creation and Maintenance

AI agents MAY assist with:

- Analyzing requirements.
- Identifying test scenarios.
- Generating test cases.
- Suggesting edge cases.
- Reviewing test coverage.
- Identifying duplicate tests.
- Converting manual tests into automated tests.
- Updating test cases after implementation changes.
- Preparing test execution records.

AI agents MUST:

1. Read relevant project requirements and QA standards.
2. Inspect existing test cases before creating new ones.
3. Avoid duplicating existing test coverage.
4. Use approved terminology and identifiers.
5. Ensure expected results are supported by approved requirements.
6. Distinguish requirements from assumptions.
7. Include relevant negative and boundary scenarios.
8. Avoid inventing behavior that has not been approved.
9. Preserve existing test identifiers when editing existing test cases.
10. Report missing requirements or ambiguous expected behavior.

AI agents MUST NOT:

- Change approved expected behavior without authorization.
- Mark unexecuted tests as passed.
- Remove failing tests to hide defects.
- Claim complete coverage without evidence.
- Modify unrelated test cases.
- Use production or personal save data without authorization.

Generated test cases SHOULD be reviewed before being treated as authoritative project QA documentation.

## 19. Test Case Review Checklist

Use this checklist when creating or reviewing test cases.

### Test Definition

- [ ] The test has a unique identifier.
- [ ] The title describes the intended behavior.
- [ ] The objective is clear.
- [ ] Preconditions are documented.
- [ ] Required test data is identified.
- [ ] Steps are specific and understandable.
- [ ] Expected results are observable.
- [ ] Cleanup requirements are documented when necessary.

### Test Coverage

- [ ] Relevant positive scenarios are covered.
- [ ] Relevant negative scenarios are considered.
- [ ] Boundary conditions are considered.
- [ ] Important state transitions are covered.
- [ ] Relevant dependencies are considered.
- [ ] Important player workflows are represented.

### Test Quality

- [ ] The test is repeatable.
- [ ] The test has a focused objective.
- [ ] The test avoids unnecessary dependencies.
- [ ] Requirements and acceptance criteria are referenced.
- [ ] Priority is appropriate.
- [ ] Automation suitability is considered.

### Maintenance

- [ ] The test follows project organization conventions.
- [ ] Duplicate coverage has been considered.
- [ ] Existing identifiers are preserved when appropriate.
- [ ] Obsolete information has been removed.
- [ ] Related documentation is updated when necessary.

## 20. Exceptions

Projects MAY adapt test case formats and organization according to their tools and development needs.

Exceptions SHOULD preserve the essential qualities of a test case:

- Clear objective.
- Defined preconditions.
- Reproducible execution.
- Verifiable expected result.
- Traceability when applicable.

Significant deviations from mandatory studio QA practices MUST be reviewed and approved by the project owner.

## 21. Related Documents

- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/02_technical_standards/testing_strategy.md`
- `docs/04_production_standards/backlog_management.md`
- `docs/05_qa_standards/qa_strategy.md`
- `docs/05_qa_standards/acceptance_criteria_guidelines.md`
- `docs/05_qa_standards/bug_reporting.md`
- `docs/05_qa_standards/playtesting_guidelines.md`
- `docs/05_qa_standards/regression_testing.md`

## 22. Maintenance

This document SHOULD be reviewed periodically and updated when:

- Testing practices evolve.
- New testing tools are adopted.
- Test management workflows change.
- Project requirements introduce new testing needs.
- Repeated test execution reveals weaknesses in test case design.
- AI-assisted test generation introduces new considerations.

The project owner is responsible for approving changes to this standard.