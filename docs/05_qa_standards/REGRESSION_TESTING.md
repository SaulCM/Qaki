# Regression Testing

## 1. Purpose

This document defines the standards and procedures for regression testing across game projects.

Regression testing verifies that changes to the game do not unintentionally break existing functionality, gameplay systems, integrations, or previously corrected defects.

Its objectives are to:

- Detect unintended side effects introduced by changes.
- Preserve previously working functionality.
- Verify that bug fixes do not introduce new defects.
- Validate interactions between modified and existing systems.
- Reduce the risk of regressions reaching release builds.
- Establish consistent regression testing practices.
- Maintain confidence in the stability of the game throughout development.

Regression testing MUST be considered whenever a change could affect existing behavior.

## 2. Scope

Regression testing applies to changes involving:

- Gameplay mechanics and systems.
- Player controls and input handling.
- Character behavior and movement.
- Combat and interaction systems.
- Progression and economy.
- Inventory and resource management.
- UI and navigation.
- Save and loading systems.
- Game state and scene transitions.
- Art, animation, and visual effects.
- Audio systems.
- AI and NPC behavior.
- Performance and resource management.
- External integrations and plugins.
- Platform-specific functionality.
- Engine or dependency upgrades.
- Bug fixes and refactoring.

Regression testing MAY include automated tests, manual tests, exploratory testing, and playtesting.

The scope of each regression test effort SHOULD be proportional to the risk and impact of the changes.

## 3. Regression Testing Principles

### 3.1. Test What Could Be Affected

Regression testing SHOULD focus on functionality that may be affected directly or indirectly by a change.

Testing only the modified code is insufficient when that code interacts with other systems.

### 3.2. Risk-Based Test Selection

The number and depth of regression tests SHOULD reflect:

- Change complexity.
- Number of affected systems.
- Dependency relationships.
- Player impact.
- Historical defect patterns.
- Technical uncertainty.
- Release risk.

Critical gameplay and data integrity functionality SHOULD receive greater attention.

### 3.3. Repeatability

Regression tests SHOULD produce consistent and reproducible results.

Automated tests SHOULD use controlled conditions, deterministic inputs, and predictable expected outcomes whenever practical.

### 3.4. Automation Where Practical

Frequently executed and stable regression tests SHOULD be automated when the maintenance cost is justified.

Manual testing remains appropriate for visual quality, gameplay feel, usability, and other areas requiring human judgment.

### 3.5. Maintainable Test Coverage

Regression tests MUST be maintained as game functionality evolves.

Outdated tests SHOULD be updated or removed when their original behavior is intentionally changed.

Tests MUST NOT be modified simply to hide a regression.

### 3.6. Evidence-Based Results

Regression testing results MUST distinguish:

- Tests that passed.
- Tests that failed.
- Tests that were not executed.
- Tests that were blocked.
- Tests that are not applicable.

A successful test run does not guarantee that the entire game is free of regressions.

## 4. When Regression Testing Is Required

Regression testing SHOULD be performed after changes that could affect existing functionality.

Common triggers include:

### 4.1. Feature Changes

When adding or modifying functionality, validate:

- The new behavior.
- Existing behavior within the same feature.
- Related systems that depend on the modified functionality.
- Important player workflows.

### 4.2. Bug Fixes

After fixing a defect:

- Verify that the original defect is resolved.
- Test relevant edge cases.
- Validate nearby functionality.
- Check for unintended side effects.
- Add or update a regression test when practical.

A defect that has been fixed SHOULD have a reproducible verification procedure whenever possible.

### 4.3. Refactoring

Refactoring SHOULD preserve externally observable behavior unless an intentional behavior change has been approved.

Validate:

- Existing functionality.
- Public interfaces.
- Dependencies.
- Scene and resource references.
- Signals and event communication.
- Save compatibility.
- Relevant performance characteristics.

### 4.4. Architecture Changes

Changes to shared systems or architectural boundaries MAY affect multiple features.

Regression testing SHOULD consider all relevant dependents.

Examples include:

- Autoload modifications.
- Event or signal system changes.
- Shared resource changes.
- Input management changes.
- Scene loading changes.
- Common UI components.
- Shared gameplay utilities.

### 4.5. Engine and Dependency Updates

After upgrading Godot, plugins, or external dependencies, validate functionality that relies on the changed components.

This MAY include:

- Project startup.
- Resource imports.
- Scene loading.
- Script execution.
- Input handling.
- Physics behavior.
- Rendering.
- Audio playback.
- Export and build processes.
- Save and loading behavior.

### 4.6. Release Preparation

Regression testing MUST be included in release validation.

The regression scope SHOULD cover critical gameplay flows, high-risk systems, previously reported defects, and supported platform configurations.

## 5. Regression Test Scope and Selection

Regression tests SHOULD be selected according to the change impact.

### 5.1. Change Impact Analysis

Before selecting tests, identify:

1. What was changed.
2. Which features or components were affected.
3. Which systems depend on the modified functionality.
4. Which player workflows use the affected systems.
5. Which historical defects are relevant.
6. Which risks require additional validation.

Inspect the actual implementation and dependencies rather than relying only on the change description.

### 5.2. Directly Affected Functionality

Tests MUST cover the functionality directly modified by the change.

Examples:

- Changing character movement requires validating movement behavior.
- Modifying inventory operations requires validating item acquisition, removal, and storage.
- Changing a health calculation requires validating damage, healing, and death behavior.

### 5.3. Indirectly Affected Functionality

Tests SHOULD cover relevant systems that depend on the changed functionality.

Examples:

- Changing input handling may affect menus, gameplay actions, and remapping.
- Changing resource loading may affect scene initialization and asset availability.
- Changing save serialization may affect multiple systems that persist data.

### 5.4. Critical Player Workflows

Important end-to-end workflows SHOULD be included in regression coverage.

Examples:

- Starting a new game.
- Loading an existing save.
- Completing a core gameplay interaction.
- Navigating essential menus.
- Completing a representative gameplay loop.
- Transitioning between important scenes.
- Saving and restoring progress.
- Exiting and restarting the game.

### 5.5. Historical Defects

Previously fixed high-impact defects SHOULD be represented in the regression test suite whenever practical.

This reduces the likelihood of known problems returning after future changes.

## 6. Regression Testing Levels

Regression testing MAY be performed at multiple levels.

### 6.1. Unit Regression Testing

Validates individual functions, classes, or isolated components after changes.

Examples:

- Damage calculations.
- Inventory capacity calculations.
- Resource cost calculations.
- Progression requirements.
- Input mapping utilities.
- Save data conversion functions.

Unit regression tests SHOULD be fast and deterministic.

### 6.2. Integration Regression Testing

Validates interactions between related systems.

Examples:

- Inventory and equipment.
- Character health and combat.
- Quest progression and rewards.
- Save systems and gameplay state.
- UI and gameplay controllers.
- Signals and event-driven communication.

### 6.3. Scene Regression Testing

Validates scenes, nodes, and their dependencies.

Examples:

- Scene initialization.
- Node references.
- Signal connections.
- Resource loading.
- UI component behavior.
- Scene transitions.
- Node lifecycle behavior.

### 6.4. End-to-End Regression Testing

Validates complete player workflows across multiple systems.

Examples:

- Start game, play, save, exit, and reload.
- Complete an objective and receive its reward.
- Acquire an item, equip it, and verify its effects.
- Navigate menus and start a new gameplay session.

End-to-end tests SHOULD focus on important workflows because they can be slower and more sensitive to unrelated changes.

### 6.5. Manual Regression Testing

Manual regression testing is appropriate when automated tests cannot reliably evaluate the expected behavior.

Examples:

- Character movement feel.
- Animation transitions.
- Visual consistency.
- Audio behavior.
- UI presentation.
- Gameplay balance.
- Accessibility.
- Complex player interactions.

## 7. Regression Testing Categories

Regression testing SHOULD consider the following categories when relevant.

| Category | Validation Focus |
|---|---|
| Functional | Existing features still behave correctly. |
| Gameplay | Core mechanics and player workflows remain functional. |
| UI/UX | Navigation, interaction, layout, and feedback remain correct. |
| Integration | Connected systems continue communicating correctly. |
| Data integrity | Save data and persistent state remain valid. |
| Performance | Changes do not introduce unacceptable performance degradation. |
| Compatibility | Supported platforms and configurations remain functional. |
| Visual | Rendering, animation, and presentation remain consistent. |
| Audio | Playback, mixing, triggers, and audio transitions remain correct. |
| Security | Changes do not introduce relevant security or data-handling weaknesses. |

Not every change requires every category. Select the categories that are relevant to the change and its risks.

## 8. Regression Test Design

### 8.1. Test Case Structure

Regression test cases SHOULD contain enough information to execute and evaluate them consistently.

Recommended fields:

| Field | Description |
|---|---|
| Test ID | Unique test identifier. |
| Title | Short description of the behavior being validated. |
| Feature | Related feature or system. |
| Objective | What the test verifies. |
| Preconditions | Required initial state. |
| Test Data | Relevant inputs or data. |
| Steps | Actions to execute. |
| Expected Result | Required observable behavior. |
| Priority | Importance of the test. |
| Automation Status | Automated, Manual, or Candidate for Automation. |
| Related Requirement | Requirement or acceptance criterion. |
| Related Defect | Previously reported defect, if applicable. |

### 8.2. Test Case Quality

Regression test cases SHOULD:

- Have a clear objective.
- Verify observable behavior.
- Be repeatable.
- Avoid unnecessary dependencies.
- Include relevant preconditions.
- Define expected results.
- Identify important edge cases.
- Remain independent where practical.

### 8.3. Positive and Negative Scenarios

Regression coverage SHOULD include relevant positive and negative scenarios.

Examples:

- Valid player input.
- Invalid player input.
- Missing resources.
- Empty inventory.
- Maximum inventory capacity.
- Interrupted interactions.
- Invalid save data.
- Unexpected scene transitions.

### 8.4. Boundary Conditions

Boundary conditions SHOULD be considered when a change affects limits, thresholds, or calculations.

Examples:

- Minimum and maximum health.
- Zero available resources.
- Maximum inventory capacity.
- Progression thresholds.
- Timer expiration.
- Maximum supported values.
- Empty or unusually large collections.

## 9. Regression Test Prioritization

Regression tests SHOULD be prioritized to maximize useful coverage while keeping execution time manageable.

### 9.1. Priority Levels

| Priority | Description | Execution Guidance |
|---|---|---|
| Critical | Protects essential game functionality or data integrity. | Execute whenever relevant changes occur. |
| High | Covers important gameplay systems and major workflows. | Execute for relevant feature and integration changes. |
| Medium | Covers supporting functionality and common interactions. | Execute when related systems change or during broader regression runs. |
| Low | Covers isolated or lower-impact functionality. | Execute during appropriate comprehensive validation. |

### 9.2. Prioritization Factors

Consider:

- Player impact.
- Feature importance.
- Failure likelihood.
- Dependency count.
- Historical defect frequency.
- Difficulty of detecting failures.
- Recovery cost.
- Release implications.

### 9.3. Critical Regression Suite

Each project SHOULD maintain a small critical regression suite covering the most important functionality.

Depending on the game, it MAY include:

- Project startup.
- Main menu navigation.
- New game creation.
- Core gameplay interaction.
- Player movement and controls.
- Essential progression.
- Save and loading.
- Scene transitions.
- Game shutdown and restart.

The suite SHOULD remain small enough to execute frequently.

## 10. Automated Regression Testing

Automation SHOULD be used for repeatable checks that provide meaningful value.

### 10.1. Automation Candidates

Good candidates include:

- Unit tests.
- Deterministic calculations.
- Data serialization and deserialization.
- Save data validation.
- Inventory rules.
- Progression calculations.
- State transitions.
- API or integration behavior.
- Critical gameplay logic.
- Build and resource validation.

### 10.2. Automation Requirements

Automated regression tests SHOULD:

- Have clear assertions.
- Use controlled test data.
- Avoid unnecessary external dependencies.
- Produce useful failure messages.
- Clean up temporary state.
- Avoid reliance on execution order.
- Be repeatable across supported environments.
- Be maintained with the implementation.

### 10.3. Godot-Specific Considerations

For Godot projects:

- Use the project's selected Godot version.
- Validate GDScript parsing and project startup.
- Test relevant scenes and nodes.
- Verify signal connections.
- Validate Resource loading.
- Check autoload behavior.
- Test scene transitions.
- Validate InputMap behavior where relevant.
- Test persistence through the appropriate user data paths.
- Consider headless execution for suitable automated tests.

The project MAY use GUT, GdUnit4, or another suitable testing framework. The selected framework MUST be documented in the game project.

### 10.4. Test Environment

Automated regression tests SHOULD execute in a controlled environment.

Document relevant dependencies such as:

- Godot version.
- Plugins.
- Test framework version.
- Required project configuration.
- Test data.
- Platform or runtime assumptions.

### 10.5. CI Integration

Where CI is configured, automated regression tests SHOULD be integrated into the appropriate pipeline stages.

Recommended execution:

- Fast unit regression tests during frequent development checks.
- Relevant integration tests before merging changes.
- Critical regression suite during integration validation.
- Broader regression suite before release candidates.

A failing mandatory regression check MUST be investigated before the affected change is considered ready for integration.

## 11. Manual Regression Testing

Manual regression testing SHOULD follow documented procedures for important workflows.

### 11.1. Preparation

Before execution:

- Identify the build or version.
- Review the changes being validated.
- Select relevant test cases.
- Prepare required test data.
- Establish preconditions.
- Confirm the test environment.
- Identify known limitations.

### 11.2. Execution

During execution:

- Follow the documented steps.
- Record actual results.
- Capture relevant evidence.
- Report unexpected behavior.
- Record blocked or skipped tests.
- Avoid modifying the test environment without documenting it.

### 11.3. Exploratory Regression Testing

Exploratory testing MAY supplement predefined regression cases.

It is particularly useful when:

- The change affects complex interactions.
- Requirements do not describe every possible behavior.
- The affected system has a history of defects.
- Unexpected behavior is suspected.
- Manual observation provides additional confidence.

Exploratory testing SHOULD record meaningful findings rather than relying only on informal impressions.

## 12. Regression Testing Workflow

The following workflow SHOULD be used when a change requires regression testing.

### Step 1: Review the Change

Understand the purpose and scope of the modification.

Identify changed files, systems, interfaces, resources, and dependencies.

### Step 2: Perform Impact Analysis

Determine which existing functionality could be affected directly or indirectly.

Identify high-risk dependencies and critical player workflows.

### Step 3: Select Regression Tests

Choose relevant tests based on:

- Change impact.
- Test priority.
- Historical defects.
- System dependencies.
- Risk level.
- Available validation time.

### Step 4: Prepare the Test Environment

Confirm that the correct build, configuration, test data, and dependencies are available.

### Step 5: Execute Regression Tests

Run selected automated and manual tests.

Record actual outcomes and relevant evidence.

### Step 6: Analyze Failures

For each failure:

- Determine whether it is a new regression.
- Check whether the failure is reproducible.
- Identify affected functionality.
- Review logs and relevant evidence.
- Compare against previous known behavior.
- Report confirmed defects.

Do not assume every failed test is caused by the latest change. Investigate environmental failures, outdated tests, and unrelated defects.

### Step 7: Fix and Retest

After a defect is corrected:

- Verify the original failure.
- Execute the relevant regression test.
- Validate nearby functionality.
- Expand testing when the fix affects additional systems.

### Step 8: Evaluate Results

Determine whether the selected regression scope passed and whether unresolved issues affect the change.

### Step 9: Report Completion

Communicate:

- Build or version tested.
- Changes evaluated.
- Tests executed.
- Passed and failed tests.
- Blocked and skipped tests.
- Defects discovered.
- Remaining risks.
- Overall regression testing result.

## 13. Handling Regression Failures

### 13.1. Failure Classification

A failed regression test SHOULD be classified as one of the following:

- **Confirmed Regression:** Previously working behavior has been broken by a change.
- **Existing Defect:** The behavior was already incorrect before the current change.
- **Test Defect:** The test case, assertion, or test data is incorrect.
- **Environment Failure:** The test environment prevents valid execution.
- **Unrelated Failure:** The failure is not caused by the change under evaluation.
- **Inconclusive:** Available evidence is insufficient to determine the cause.

### 13.2. Defect Reporting

Confirmed regressions MUST be documented using the project's bug reporting process.

The report SHOULD identify:

- Affected functionality.
- Expected behavior.
- Actual behavior.
- Reproduction steps.
- Affected build or version.
- Relevant evidence.
- Related change or commit, when known.
- Severity and priority.

### 13.3. Fix Verification

A regression MUST NOT be considered resolved solely because the implementation was modified.

The original failure MUST be retested.

Relevant surrounding functionality SHOULD also be validated.

### 13.4. Regression Test Updates

When a confirmed regression is discovered:

- Add an automated test when practical.
- Otherwise, document a repeatable manual test.
- Update affected test cases.
- Review whether other related workflows require additional coverage.

The goal is to reduce the likelihood of the same defect returning.

## 14. Regression Test Suite Maintenance

Regression suites MUST evolve with the game.

### 14.1. Test Updates

Update tests when:

- Requirements change.
- Gameplay behavior changes intentionally.
- Interfaces are modified.
- Systems are refactored.
- Dependencies change.
- Defects reveal missing coverage.

### 14.2. Removing Tests

A test MAY be removed when:

- The tested functionality no longer exists.
- The behavior is intentionally replaced.
- The test is obsolete.
- Equivalent coverage is provided elsewhere.
- The test cannot provide meaningful validation.

Removal SHOULD be justified.

Do not remove a test merely because it repeatedly fails.

### 14.3. Flaky Tests

Flaky tests produce inconsistent results without a corresponding change in the system under test.

They SHOULD be investigated and corrected.

Potential causes include:

- Timing dependencies.
- Uncontrolled random behavior.
- Shared mutable state.
- Improper cleanup.
- External dependencies.
- Race conditions.
- Unreliable scene initialization.

A flaky test SHOULD NOT silently be treated as passing.

If a test must be temporarily quarantined, document the reason, impact, and follow-up action.

### 14.4. Test Data and Environment Maintenance

Test data SHOULD be isolated from normal player data.

Tests SHOULD avoid modifying personal saves, production data, or unrelated project state.

Temporary files and resources SHOULD be cleaned up after execution.

## 15. Regression Testing and Release Readiness

Regression testing MUST contribute to release validation.

Before a release candidate is approved, the project SHOULD validate:

- Critical gameplay workflows.
- Important feature integrations.
- Previously fixed high-impact defects.
- Save and loading behavior.
- Scene transitions.
- Supported platform configurations.
- Performance-sensitive functionality.
- Known high-risk areas.
- Relevant automated test suites.

Release readiness MUST consider both regression results and outstanding defects.

A release MUST NOT be considered safe solely because automated regression tests pass.

The project owner is responsible for evaluating remaining risks and approving release decisions.

## 16. Regression Testing Records

Projects SHOULD maintain regression testing records when traceability or repeatability is important.

Recommended project-specific location:

`docs/qa/regression/`

Suggested structure:

```text
docs/qa/regression/
├── README.md
├── test_suites/
│   ├── critical_regression_suite.md
│   └── gameplay_regression_suite.md
└── reports/
    ├── regression-report-template.md
    └── release-regression/
```

Projects MAY use a test management system or issue tracker instead, provided it remains the authoritative source.

### 16.1. Test Identification

Suggested identifier format:

- `REG-001`: Individual regression test.
- `REG-SUITE-001`: Regression test suite.
- `REG-RUN-001`: Regression execution record.

Identifiers SHOULD remain stable when test descriptions or implementation details change.

### 16.2. Regression Execution Report Template

```markdown
# Regression Testing Report

## 1. Execution Information

- Report ID:
- Project:
- Build / Version:
- Branch / Commit:
- Execution Date:
- Environment:
- Executed By:

## 2. Change Summary

Describe the changes evaluated.

## 3. Impact Analysis

- Directly affected systems:
- Indirectly affected systems:
- Critical workflows:
- Identified risks:

## 4. Test Scope

- Selected test suites:
- Automated tests:
- Manual tests:
- Excluded tests and reasons:

## 5. Execution Results

| Test ID | Test Name | Priority | Result | Notes |
|---|---|---|---|---|
| REG-001 | Example test | Critical | Passed | No issues found |
| REG-002 | Example test | High | Failed | Unexpected behavior |

## 6. Summary

- Total Tests:
- Passed:
- Failed:
- Blocked:
- Skipped:
- Not Executed:

## 7. Defects and Findings

List confirmed regressions, related defects, and relevant evidence.

## 8. Remaining Risks

Describe unresolved issues and untested areas.

## 9. Overall Result

- [ ] Passed
- [ ] Passed with Conditions
- [ ] Failed
- [ ] Blocked

## 10. Follow-up Actions

List required fixes, additional testing, or risk reviews.
```

## 17. AI-Assisted Regression Testing

AI agents MAY assist with regression testing activities.

Permitted activities include:

- Analyzing code changes.
- Identifying affected systems.
- Suggesting regression test cases.
- Generating automated tests.
- Executing authorized test commands.
- Reviewing test failures.
- Identifying missing coverage.
- Preparing regression reports.

AI agents MUST:

1. Inspect the relevant implementation and project documentation before proposing tests.
2. Base impact analysis on actual dependencies and code changes.
3. Preserve existing test conventions and framework choices.
4. Avoid modifying unrelated tests or implementation.
5. Never weaken assertions merely to make tests pass.
6. Distinguish confirmed regressions from suspected causes.
7. Report tests that were not executed.
8. Preserve test data and user-owned files.
9. Report environmental limitations.
10. Request human approval when a significant behavior or testing requirement must change.

AI-generated regression tests MUST be reviewed and validated like other project code.

AI agents MUST NOT claim that regression testing passed when required checks were skipped or their results were inconclusive.

## 18. Regression Testing Checklist

### Planning

- [ ] The change has been reviewed.
- [ ] Directly affected functionality has been identified.
- [ ] Indirect dependencies have been considered.
- [ ] Relevant historical defects have been reviewed.
- [ ] Regression tests have been selected according to risk.

### Preparation

- [ ] The correct build or version is available.
- [ ] The test environment is configured.
- [ ] Required test data is available.
- [ ] Preconditions are established.

### Execution

- [ ] Relevant automated tests have been executed.
- [ ] Relevant manual tests have been completed.
- [ ] Critical workflows have been validated.
- [ ] Test results have been recorded.
- [ ] Failures have been investigated.
- [ ] Blocked and skipped tests have been documented.

### Defect Handling

- [ ] Confirmed regressions have been reported.
- [ ] Defect severity and priority have been evaluated.
- [ ] Fixes have been retested.
- [ ] Relevant regression coverage has been added or updated.

### Completion

- [ ] Results have been summarized.
- [ ] Remaining risks have been documented.
- [ ] Required follow-up actions have been identified.
- [ ] Regression testing status has been communicated.

## 19. Exceptions

Regression testing scope MAY be reduced when:

- A change is isolated and demonstrably low risk.
- The project is producing a temporary prototype.
- Testing is blocked by unavailable infrastructure.
- Time constraints require prioritization.

Exceptions SHOULD document:

- What was not tested.
- Why testing was reduced.
- Potential impact.
- Remaining risks.
- Required follow-up validation.

Critical functionality and data integrity SHOULD NOT be excluded without explicit project owner review.

## 20. Related Documents

- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/00_studio_standards/code_review_guidelines.md`
- `docs/02_technical_standards/testing_strategy.md`
- `docs/04_production_standards/risk_management.md`
- `docs/04_production_standards/release_process.md`
- `docs/05_qa_standards/qa_strategy.md`
- `docs/05_qa_standards/acceptance_criteria_guidelines.md`
- `docs/05_qa_standards/bug_reporting.md`
- `docs/05_qa_standards/playtesting_guidelines.md`

## 21. Maintenance

This document SHOULD be reviewed periodically and updated when:

- Testing practices evolve.
- New automation capabilities are introduced.
- The Godot version or testing framework changes.
- Recurring regressions reveal coverage gaps.
- New platforms or configurations are supported.
- Postmortems identify improvements to regression testing.

The project owner is responsible for approving changes to this standard.