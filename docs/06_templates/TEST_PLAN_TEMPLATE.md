# Test Plan Template

> **Purpose:** This template defines the structure for project-specific test plans.
>
> A test plan describes what will be tested, why testing is necessary, how testing will be performed, what resources are required, and how results will be evaluated.
>
> A test plan establishes the testing approach and scope. Individual test cases, execution records, bug reports, and regression suites should be maintained separately when appropriate.
>
> This template is intended for features, systems, milestones, integrations, and releases. Remove sections that do not apply to the testing scope.

---

## 1. Document Information

| Field | Value |
|---|---|
| Test Plan ID | TP-XXX |
| Title | [Test plan title] |
| Project | [Project name] |
| Target Feature / System | [Feature, system, milestone, or release] |
| Build / Version | [Build or version identifier] |
| Status | Draft |
| Test Plan Owner | [Responsible person] |
| Author | [Author or AI-assisted] |
| Created Date | [YYYY-MM-DD] |
| Last Updated | [YYYY-MM-DD] |
| Planned Start | [YYYY-MM-DD] |
| Planned Completion | [YYYY-MM-DD] |
| Related Documents | [Links] |

### 1.1 Test Plan Summary

[Provide a concise overview of the testing effort, its objectives, scope, and expected outcome.]

### 1.2 Testing Purpose

Explain why this testing effort is necessary.

Examples:

- Validate a newly implemented feature.
- Verify integration between gameplay systems.
- Detect regressions after code changes.
- Validate a milestone before acceptance.
- Evaluate performance and stability.
- Verify release readiness.

### 1.3 Test Plan Type

Select the applicable type:

- [ ] Feature testing.
- [ ] System testing.
- [ ] Integration testing.
- [ ] Regression testing.
- [ ] Milestone validation.
- [ ] Release testing.
- [ ] Performance testing.
- [ ] Compatibility testing.
- [ ] Data persistence testing.
- [ ] Security testing.
- [ ] Exploratory testing.
- [ ] Other: [Specify]

---

## 2. Test Objectives

### 2.1 Primary Objectives

Describe what the testing effort must establish.

| Objective ID | Objective | Expected Result |
|---|---|---|
| OBJ-01 | [Objective] | [Expected result] |
| OBJ-02 | [Objective] | [Expected result] |

### 2.2 Quality Objectives

Identify the relevant quality characteristics.

- Functional correctness.
- Gameplay behavior.
- Reliability and stability.
- Performance.
- Usability.
- Accessibility.
- Data integrity.
- Compatibility.
- Visual and audio consistency.
- Security.

Only include quality areas relevant to the testing scope.

### 2.3 Success Criteria

Define measurable or verifiable conditions for considering the testing effort successful.

Examples:

- All critical test cases pass.
- No unresolved critical defects remain.
- Required integration scenarios work correctly.
- Performance requirements are satisfied.
- Save/load behavior is validated.
- Acceptance criteria are satisfied.

---

## 3. Test Scope

### 3.1 Features and Systems Under Test

List the features, components, or systems included in the testing effort.

| ID | Feature / System | Description | Priority |
|---|---|---|---|
| SCOPE-01 | [Feature] | [Description] | [Critical / High / Medium / Low] |
| SCOPE-02 | [System] | [Description] | [Priority] |

### 3.2 In-Scope Functionality

Describe the functionality that must be tested.

- [Functionality]
- [Functionality]

### 3.3 Out-of-Scope Functionality

Explicitly identify what will not be tested.

| Item | Reason for Exclusion | Potential Impact |
|---|---|---|
| [Item] | [Reason] | [Impact] |

Out-of-scope items should not be interpreted as validated or defect-free.

### 3.4 Testing Boundaries

Define relevant boundaries.

Consider:

- Feature boundaries.
- Integration boundaries.
- Supported platforms.
- Supported input methods.
- Supported save formats.
- Relevant game states.
- Content or progression limits.

---

## 4. Requirements and Acceptance Criteria

### 4.1 Source Requirements

Identify the documents or requirements that define expected behavior.

| Requirement ID | Description | Source Document |
|---|---|---|
| REQ-01 | [Requirement] | [Reference] |
| REQ-02 | [Requirement] | [Reference] |

### 4.2 Acceptance Criteria

List the conditions that must be satisfied.

| AC ID | Acceptance Criterion | Verification Method |
|---|---|---|
| AC-01 | [Criterion] | [Test / Inspection / Other] |
| AC-02 | [Criterion] | [Verification method] |

### 4.3 Requirement Traceability

Ensure that important requirements have corresponding validation coverage.

| Requirement | Related Test Case IDs | Coverage Status |
|---|---|---|
| REQ-01 | [TC-001, TC-002] | [Covered / Partial / Not Covered] |
| REQ-02 | [TC-003] | [Status] |

### 4.4 Requirement Clarifications

Record unclear, contradictory, or incomplete requirements that affect testing.

| ID | Question / Ambiguity | Impact | Resolution |
|---|---|---|---|
| Q-01 | [Description] | [Impact] | [Pending / Resolved] |

Do not invent expected behavior when the source requirements are ambiguous.

---

## 5. Test Strategy and Approach

### 5.1 Overall Testing Strategy

Describe the general approach for validating the scope.

Explain:

- Which test levels will be used.
- Which test types are required.
- What will be automated.
- What requires manual validation.
- Which areas receive priority.
- How test results will be evaluated.

### 5.2 Test Levels

| Test Level | Purpose | Planned Coverage | Execution Method |
|---|---|---|---|
| Unit Testing | Validate isolated logic | [Scope] | [Automated / Manual] |
| Integration Testing | Validate component interactions | [Scope] | [Method] |
| Scene / Feature Testing | Validate complete feature behavior | [Scope] | [Method] |
| End-to-End Testing | Validate player workflows | [Scope] | [Method] |
| Manual Testing | Validate behavior requiring human evaluation | [Scope] | [Method] |

### 5.3 Test Types

Select applicable testing types:

- [ ] Functional testing.
- [ ] Positive testing.
- [ ] Negative testing.
- [ ] Boundary testing.
- [ ] State transition testing.
- [ ] Integration testing.
- [ ] Regression testing.
- [ ] Smoke testing.
- [ ] Sanity testing.
- [ ] Performance testing.
- [ ] Compatibility testing.
- [ ] Usability testing.
- [ ] Accessibility testing.
- [ ] Persistence testing.
- [ ] Security testing.
- [ ] Exploratory testing.
- [ ] Visual testing.
- [ ] Audio testing.
- [ ] Playtesting.

### 5.4 Risk-Based Testing

Prioritize testing according to:

- Player impact.
- Functional criticality.
- Complexity.
- Frequency of use.
- Integration dependencies.
- Historical defect patterns.
- Data integrity.
- Performance sensitivity.
- Uncertainty in implementation.

| Area | Risk | Testing Priority | Reason |
|---|---|---|---|
| [Area] | [Risk] | [Critical / High / Medium / Low] | [Reason] |

### 5.5 Automation Strategy

Describe which tests should be automated and why.

Consider:

- Repeatability.
- Execution frequency.
- Regression value.
- Deterministic behavior.
- Maintenance cost.
- Available testing tools.

Identify manual-only scenarios and explain why automation is unsuitable.

---

## 6. Test Environment

### 6.1 Environment Configuration

| Component | Configuration |
|---|---|
| Operating System | [OS and version] |
| Godot Version | [Version] |
| Project Build | [Build identifier] |
| Rendering Method | [Renderer] |
| Display Resolution | [Resolution] |
| Input Devices | [Keyboard / Mouse / Controller / Other] |
| Target Platform | [Platform] |
| Required Plugins | [Plugins] |

Use the actual project configuration. Do not assume an engine version or platform that has not been established.

### 6.2 Hardware Requirements

Specify relevant hardware configurations.

| Component | Minimum Configuration | Test Configuration |
|---|---|---|
| CPU | [Specification] | [Specification] |
| GPU | [Specification] | [Specification] |
| RAM | [Specification] | [Specification] |
| Storage | [Specification] | [Specification] |

### 6.3 Test Environment Setup

Describe the steps required to prepare the environment.

Include:

- Build installation.
- Project configuration.
- Required plugins or dependencies.
- Test data preparation.
- Save file preparation.
- Debug or logging configuration.
- Network or external service requirements, if applicable.

### 6.4 Environment Limitations

Document known environment limitations that may affect test results.

---

## 7. Test Data and Preconditions

### 7.1 Test Data Requirements

Identify the data required for testing.

| Data ID | Description | Purpose | Preparation Method |
|---|---|---|---|
| DATA-01 | [Data] | [Purpose] | [Method] |
| DATA-02 | [Data] | [Purpose] | [Method] |

### 7.2 Test Data Categories

Consider:

- Default data.
- Valid data.
- Invalid data.
- Boundary values.
- Empty or missing data.
- Large data sets.
- Previously saved data.
- Different player progression states.
- Different world states.

### 7.3 Preconditions

List conditions that must be satisfied before execution.

Examples:

- Required build is available.
- Dependencies are installed.
- Test data is prepared.
- Required player progression is available.
- Relevant features are implemented.
- Environment configuration is correct.

### 7.4 Test Data Isolation

Describe how tests avoid unintended interference.

Consider:

- Independent save files.
- Reset procedures.
- Temporary test data.
- Unique test identifiers.
- Cleanup procedures.

### 7.5 Sensitive Data

Do not use real credentials, private user information, or sensitive production data in test environments unless explicitly authorized and appropriately protected.

---

## 8. Test Scenarios and Coverage

### 8.1 Scenario Overview

Summarize the main scenarios that will be validated.

| Scenario ID | Scenario | Objective | Priority |
|---|---|---|---|
| TS-01 | [Scenario] | [Objective] | [Priority] |
| TS-02 | [Scenario] | [Objective] | [Priority] |

### 8.2 Functional Scenarios

Describe important expected behaviors and their validation.

### 8.3 Negative Scenarios

Identify invalid actions, unsupported conditions, and failure situations that must be tested.

### 8.4 Boundary Scenarios

Identify relevant limits and boundary conditions.

### 8.5 Integration Scenarios

Describe interactions between the target feature and other project systems.

### 8.6 Regression Scenarios

Identify existing functionality that may be affected by the changes.

### 8.7 Gameplay Scenarios

When applicable, describe player-facing scenarios.

Consider:

- Normal gameplay flow.
- Unusual player behavior.
- Interruptions.
- Failure and recovery.
- Progression.
- Player choices.
- Repeated interactions.
- Edge cases.

### 8.8 Coverage Summary

| Coverage Area | Planned Coverage | Status |
|---|---|---|
| Functional Requirements | [Description] | [Planned / Complete / Partial] |
| Integration Points | [Description] | [Status] |
| Error Handling | [Description] | [Status] |
| Persistence | [Description] | [Status] |
| Performance | [Description] | [Status] |
| Accessibility | [Description] | [Status] |

---

## 9. Test Cases and Execution

### 9.1 Test Case References

List the test cases associated with this plan.

| Test Case ID | Title | Priority | Test Type | Status |
|---|---|---|---|---|
| TC-001 | [Title] | [Priority] | [Type] | [Status] |
| TC-002 | [Title] | [Priority] | [Type] | [Status] |

Test cases should follow the studio's Test Case Guidelines and use the dedicated test case template when applicable.

### 9.2 Execution Order

Describe important execution dependencies and recommended test ordering.

### 9.3 Execution Procedure

For each execution cycle:

1. Confirm the correct build and environment.
2. Verify test prerequisites.
3. Execute the assigned test cases.
4. Record actual results.
5. Compare actual behavior with expected results.
6. Report defects when necessary.
7. Re-run affected tests after fixes.
8. Update execution records.

### 9.4 Test Execution Records

| Test Case ID | Execution Date | Result | Executed By | Defect Reference |
|---|---|---|---|---|
| TC-001 | [Date] | [Result] | [Name] | [BUG-XXX / N/A] |
| TC-002 | [Date] | [Result] | [Name] | [Reference] |

### 9.5 Execution Status Definitions

| Status | Meaning |
|---|---|
| Not Run | Test has not been executed |
| Passed | Actual result matches expected result |
| Failed | Actual result does not match expected result |
| Blocked | Execution cannot proceed due to an unresolved dependency or issue |
| Skipped | Test was intentionally not executed |
| Not Applicable | Test does not apply to the current scope |

Do not mark blocked, skipped, or unexecuted tests as passed.

---

## 10. Defect Management

### 10.1 Defect Reporting

All confirmed defects must be recorded according to the studio's Bug Reporting Guidelines.

### 10.2 Defect Severity

Use the established severity definitions:

| Severity | Description |
|---|---|
| Critical | Causes a major failure, data loss, progression blocker, or prevents core functionality |
| High | Significantly affects functionality or player experience |
| Medium | Causes a limited functional or usability problem |
| Low | Minor issue with limited impact |

Severity and priority must remain distinct.

### 10.3 Defect Tracking

| Bug ID | Summary | Severity | Status | Related Test Case |
|---|---|---|---|---|
| BUG-XXX | [Description] | [Severity] | [Status] | [TC-XXX] |

### 10.4 Retesting

Describe how fixed defects will be verified.

Include:

- Original reproduction steps.
- Expected behavior after the fix.
- Relevant regression coverage.
- Additional affected scenarios.

### 10.5 Defect Acceptance and Deferral

Document unresolved defects that are accepted or deferred for the current testing scope.

Include:

- Reason for acceptance or deferral.
- Known impact.
- Workaround, if available.
- Responsible decision-maker.
- Follow-up action.

Critical defects should not be waived without explicit project owner review and documented justification.

---

## 11. Entry and Exit Criteria

### 11.1 Entry Criteria

Testing may begin when:

- [ ] The target build is available.
- [ ] The scope is defined.
- [ ] Relevant requirements and acceptance criteria are available.
- [ ] Required test cases are prepared.
- [ ] Test environment is configured.
- [ ] Required test data is available.
- [ ] Critical dependencies are functional.
- [ ] Known limitations are documented.

### 11.2 Exit Criteria

Testing may be considered complete when:

- [ ] Required test cases have been executed or explicitly accounted for.
- [ ] Critical test cases pass.
- [ ] Required acceptance criteria are satisfied.
- [ ] No unresolved critical defects remain, unless explicitly accepted by the project owner.
- [ ] High-severity defects have been reviewed and dispositioned.
- [ ] Relevant regression testing is complete.
- [ ] Required performance and compatibility checks are complete.
- [ ] Test results are documented.
- [ ] Outstanding risks and limitations are reported.
- [ ] The project owner has reviewed the results when approval is required.

### 11.3 Conditional Exit

If some criteria cannot be satisfied, document:

- Which criteria remain incomplete.
- Why they remain incomplete.
- Their impact.
- Any accepted risks.
- Required follow-up actions.
- Who authorized proceeding.

Testing completion does not automatically mean the feature or release is approved.

---

## 12. Schedule and Resources

### 12.1 Testing Schedule

| Activity | Planned Start | Planned End | Status |
|---|---|---|---|
| Test Preparation | [Date] | [Date] | [Status] |
| Environment Setup | [Date] | [Date] | [Status] |
| Test Execution | [Date] | [Date] | [Status] |
| Defect Verification | [Date] | [Date] | [Status] |
| Regression Testing | [Date] | [Date] | [Status] |
| Final Reporting | [Date] | [Date] | [Status] |

### 12.2 Required Resources

Identify the resources necessary for testing.

Examples:

- Development build.
- Test environment.
- Hardware.
- Automated test tools.
- Test data.
- Documentation.
- Human playtesters.
- External services.

### 12.3 Responsibilities

| Role | Responsibility |
|---|---|
| Project Owner | Approves scope, priorities, and accepted risks |
| Developer | Provides builds, resolves defects, and supports technical validation |
| Tester / QA | Designs and executes tests and reports results |
| AI Agent | Assists with test design, analysis, execution support, and reporting under human oversight |

For a solo project, one person may perform several roles. Responsibilities should remain clear even when roles overlap.

### 12.4 Resource Constraints

Document limitations that may affect the testing schedule or coverage.

---

## 13. Risks and Contingencies

### 13.1 Testing Risks

| Risk ID | Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|---|
| RISK-01 | [Risk] | [1–5] | [1–5] | [Mitigation] |

Consider:

- Unstable builds.
- Missing test data.
- Incomplete requirements.
- Unavailable dependencies.
- Limited hardware.
- Insufficient test coverage.
- Unreliable automated tests.
- Time constraints.
- Environment inconsistencies.

### 13.2 Contingency Plans

Describe how testing will proceed if important dependencies or resources become unavailable.

### 13.3 Known Limitations

Identify limitations in the testing approach that may affect confidence in the results.

---

## 14. Test Results and Reporting

### 14.1 Execution Summary

| Metric | Result |
|---|---:|
| Total Test Cases | [Number] |
| Passed | [Number] |
| Failed | [Number] |
| Blocked | [Number] |
| Skipped | [Number] |
| Not Run | [Number] |
| Not Applicable | [Number] |

Only include actual recorded execution results.

### 14.2 Defect Summary

| Severity | Open | Fixed | Deferred | Total |
|---|---:|---:|---:|---:|
| Critical | [Number] | [Number] | [Number] | [Number] |
| High | [Number] | [Number] | [Number] | [Number] |
| Medium | [Number] | [Number] | [Number] | [Number] |
| Low | [Number] | [Number] | [Number] | [Number] |

### 14.3 Coverage Summary

Summarize:

- Requirements covered.
- Test scenarios executed.
- Areas with incomplete coverage.
- Untested or partially tested functionality.
- Important limitations.

### 14.4 Test Findings

Describe significant observations, including:

- Confirmed defects.
- Unexpected behavior.
- Performance concerns.
- Usability problems.
- Environmental issues.
- Areas requiring additional validation.

### 14.5 Final Assessment

Select one:

- [ ] Testing Passed.
- [ ] Testing Passed with Known Issues.
- [ ] Testing Failed.
- [ ] Testing Incomplete.
- [ ] Testing Blocked.

Provide a concise explanation supporting the assessment.

### 14.6 Recommendations

List recommended follow-up actions.

---

## 15. AI-Assisted Test Planning Guidelines

AI agents may assist with test planning, test case generation, test execution support, and result analysis.

They MUST:

1. Read the relevant requirements, acceptance criteria, technical design, and testing standards.
2. Inspect existing test cases and regression coverage before creating duplicates.
3. Derive test scenarios from documented expected behavior.
4. Identify missing or ambiguous requirements instead of inventing expected results.
5. Include positive, negative, boundary, and failure scenarios where relevant.
6. Consider integration, persistence, and player progression dependencies.
7. Prioritize tests according to risk and player impact.
8. Avoid claiming tests were executed when they were only generated or reviewed.
9. Record actual results only when execution evidence exists.
10. Distinguish confirmed defects from suspected issues.
11. Preserve test execution history.
12. Avoid modifying production data or user save files during testing without authorization.
13. Report incomplete coverage and limitations honestly.
14. Request human approval for significant changes to test scope or acceptance conditions.

### 15.1 AI Test Plan Review Checklist

- [ ] Testing objectives are clear.
- [ ] Scope and exclusions are defined.
- [ ] Requirements have corresponding test coverage.
- [ ] Test strategy matches the risk and complexity of the feature.
- [ ] Environment and test data requirements are documented.
- [ ] Test scenarios include relevant edge cases.
- [ ] Regression coverage is considered.
- [ ] Entry and exit criteria are verifiable.
- [ ] Defect management is defined.
- [ ] Reporting requirements are clear.
- [ ] Assumptions and limitations are identified.
- [ ] No execution results have been fabricated.

---

## 16. Review and Approval

### 16.1 Review Checklist

- [ ] The test plan reflects the approved requirements.
- [ ] Scope and exclusions are appropriate.
- [ ] Test objectives are measurable.
- [ ] The testing approach is suitable.
- [ ] Test environment requirements are documented.
- [ ] Test data and prerequisites are defined.
- [ ] Important risks are addressed.
- [ ] Entry and exit criteria are clear.
- [ ] Test coverage is sufficient.
- [ ] Defect handling and reporting are defined.
- [ ] The project owner has reviewed the plan when approval is required.

### 16.2 Approval Record

| Reviewer | Role | Status | Date | Comments |
|---|---|---|---|---|
| [Name] | Tester / QA | [Pending / Reviewed] | [Date] | [Comments] |
| [Name] | Project Owner | [Pending / Approved] | [Date] | [Comments] |

### 16.3 Change History

| Version | Date | Author | Description |
|---|---|---|---|
| 1.0 | [YYYY-MM-DD] | [Author] | Initial test plan |

---

## 17. Related Documents

Use applicable documents from the shared studio knowledge base and project repository.

**Studio standards:**

- QA Strategy: `docs/05_qa_standards/QA_STRATEGY.md`
- Testing Strategy: `docs/02_technical_standards/TESTING_STRATEGY.md`
- Test Case Guidelines: `docs/05_qa_standards/TEST_CASE_GUIDELINES.md`
- Bug Reporting: `docs/05_qa_standards/BUG_REPORTING.md`
- Regression Testing: `docs/05_qa_standards/REGRESSION_TESTING.md`
- Acceptance Criteria Guidelines: `docs/05_qa_standards/ACCEPTANCE_CRITERIA_GUIDELINES.md`
- Playtesting Guidelines: `docs/05_qa_standards/PLAYTESTING_GUIDELINES.md`
- Definition of Done: `docs/00_studio_standards/DEFINITION_OF_DONE.md`

**Project documents:**

- Relevant Feature Specification: [Project path]
- Relevant Technical Design: [Project path]
- Relevant Gameplay System Specification: [Project path]
- Related Test Cases: [Project path]
- Related Bug Reports: [Project path]
- Related Test Execution Records: [Project path]

Only retain references to documents that exist in the applicable repository.

---

**End of Test Plan**
