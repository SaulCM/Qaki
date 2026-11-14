# Bug Reporting Guidelines

## 1. Purpose

This document defines the standards and procedures for reporting, documenting, classifying, prioritizing, tracking, and verifying software defects during game development.

A bug report provides a clear and reproducible description of unexpected behavior so that developers, testers, and AI agents can understand the problem and determine how to resolve it.

The objectives are to:

- Communicate defects clearly and consistently.
- Make reported problems reproducible.
- Prioritize defects according to their impact.
- Reduce investigation and debugging time.
- Prevent duplicate or incomplete reports.
- Track defects through resolution and verification.
- Maintain a reliable record of known issues.

## 2. Scope

These guidelines apply to defects identified in:

- Gameplay mechanics and systems.
- User interface and user experience.
- Character behavior and animations.
- Physics and collision systems.
- Audio and visual effects.
- Level design and environments.
- Save and loading systems.
- Performance and resource management.
- Input and control systems.
- AI and NPC behavior.
- Platform-specific functionality.
- Build and deployment processes.
- Integrations and external dependencies.

They apply to defects discovered during development, internal testing, playtesting, automated testing, release validation, and post-release support.

This document defines how defects are reported and managed. Testing procedures and validation strategies are defined in the testing strategy and related QA documentation.

## 3. Bug Reporting Principles

### 3.1. Clarity

Reports MUST describe the observed problem using specific and understandable language.

Avoid vague descriptions such as:

- The game is broken.
- The enemy behaves incorrectly.
- The inventory does not work.
- The game has performance problems.

Describe the actual behavior and the conditions under which it occurs.

### 3.2. Reproducibility

Reports SHOULD include sufficient information to reproduce the defect.

When a defect cannot be reproduced consistently, document the observed frequency and any known conditions.

### 3.3. Evidence

Reports SHOULD include supporting evidence whenever it helps explain or verify the problem.

Evidence MAY include:

- Screenshots.
- Screen recordings.
- Logs.
- Error messages.
- Stack traces.
- Test results.
- Performance measurements.
- Save files or other relevant test data.

Evidence MUST NOT replace a written description of the problem.

### 3.4. Objective Reporting

Reports MUST distinguish observed facts from assumptions or suspected causes.

A reporter SHOULD describe what happened rather than prematurely prescribing a technical solution.

### 3.5. Actionability

A report SHOULD provide enough information for someone else to investigate the problem without repeatedly requesting basic details.

### 3.6. Traceability

Defects SHOULD have unique identifiers and remain traceable through investigation, implementation, testing, and closure.

### 3.7. No Blame

Bug reports exist to improve product quality, not to assign personal blame.

Reports SHOULD focus on the defect, its impact, and the conditions that produce it.

## 4. What Qualifies as a Bug

A bug is an unintended behavior or result that violates an approved requirement, expected behavior, technical constraint, or established product behavior.

Examples include:

- A player can pass through a solid wall.
- An enemy does not detect the player under the intended conditions.
- An inventory item disappears after loading a save.
- A button does not respond to the assigned input.
- A character animation becomes stuck.
- A sound effect plays repeatedly when it should play once.
- A scene crashes during loading.
- A gameplay system produces an incorrect result.
- A supported platform experiences a rendering failure.

### 4.1. Bugs Versus Other Work

Not every problem or improvement request is a bug.

| Type | Description |
|---|---|
| Bug | Existing behavior does not meet an approved requirement or expected behavior. |
| Feature Request | New functionality is requested. |
| Improvement | Existing functionality works but could be enhanced. |
| Technical Debt | An implementation or architectural issue that increases future maintenance cost. |
| Design Issue | A gameplay or product design decision requires reconsideration. |
| Content Issue | Art, audio, narrative, or other content is missing or incorrect. |
| Configuration Issue | A project or environment configuration is incorrect. |

When classification is uncertain, record the problem and mark its classification for review rather than silently discarding it.

## 5. Bug Report Requirements

A bug report MUST contain enough information to identify and understand the problem.

The following information is recommended.

### 5.1. Required Information

| Field | Description |
|---|---|
| Bug ID | Unique identifier for the defect. |
| Title | Short description of the problem. |
| Description | Explanation of the observed issue. |
| Environment | Relevant game version, build, and platform. |
| Preconditions | Required state or setup before reproduction. |
| Steps to Reproduce | Ordered steps that trigger the defect. |
| Expected Result | What should happen. |
| Actual Result | What actually happens. |
| Severity | Impact of the defect. |
| Status | Current investigation or resolution state. |

If a field is genuinely unknown or not applicable, indicate that explicitly rather than inventing information.

### 5.2. Recommended Information

When relevant, also include:

- Reproduction frequency.
- Priority.
- Affected feature or system.
- Relevant scene or location.
- Relevant character, item, or object.
- Input device and input method.
- Screenshot or video evidence.
- Error messages and logs.
- Suspected cause, clearly labeled as a hypothesis.
- Related work items or specifications.
- Workaround, if available.
- Reporter.
- Date discovered.
- Assigned developer.

## 6. Bug Report Title

Bug titles MUST summarize the problem clearly and concisely.

Recommended format:

`[Area] Short description of the incorrect behavior`

Examples:

- `[Inventory] Items disappear after loading a saved game`
- `[Combat] Player attacks do not register after dodging`
- `[Audio] Footstep sounds continue while the player is idle`
- `[UI] Settings menu does not retain master volume`
- `[Physics] Player passes through walls during a dash`
- `[Performance] Frame rate drops significantly in the forest area`

Titles SHOULD:

- Identify the affected system when known.
- Describe the incorrect behavior.
- Avoid unnecessary technical details.
- Avoid ambiguous phrases such as "does not work."
- Avoid including a proposed fix unless it is essential to identify the issue.

## 7. Steps to Reproduce

Reproduction steps MUST be written in chronological order.

Each step SHOULD describe one clear action or condition.

Example:

```markdown
### Steps to Reproduce

1. Launch the game.
2. Load an existing save.
3. Open the inventory.
4. Select a healing potion.
5. Use the potion.
6. Save the game.
7. Return to the main menu.
8. Load the same save.
9. Open the inventory.

### Expected Result

The remaining inventory items should match the state saved by the game.

### Actual Result

The healing potion is missing from the inventory after loading.
```

### 7.1. Preconditions

Document relevant conditions that must exist before following the steps.

Examples:

- The player must have at least one healing potion.
- The player must be in the forest level.
- A particular quest must be active.
- The game must be running with a specific graphics setting.
- The save file must have been created by a previous game version.

### 7.2. Reproduction Frequency

When possible, record how often the issue occurs.

Recommended descriptions:

- Always: Occurs on every attempt.
- Frequent: Occurs in most attempts.
- Intermittent: Occurs inconsistently.
- Rare: Occurs only under unusual conditions.
- Once: Observed once and not reproduced again.
- Unknown: Insufficient attempts to determine frequency.

A numerical estimate MAY be used.

Example: `Occurs in 3 out of 5 attempts (60%).`

### 7.3. Non-Reproducible Bugs

A defect that cannot currently be reproduced MUST NOT automatically be considered invalid.

Record:

- The original conditions.
- Available evidence.
- Approximate frequency.
- Relevant environment information.
- Attempts made to reproduce it.

The report MAY remain open or be assigned an appropriate status until sufficient information is available.

## 8. Severity Classification

Severity describes the technical or player-facing impact of a defect.

Severity SHOULD be based on the consequences of the problem, not the difficulty of fixing it.

Use the following classification.

### 8.1. Critical

<badge color="danger">Critical</badge>

A defect that makes the game or a critical part of it unusable, causes severe data loss, or creates a major security or integrity problem.

Examples:

- The game consistently crashes on startup.
- Player save data is irreversibly corrupted.
- A critical progression blocker prevents completion.
- A serious security vulnerability exposes sensitive information.
- A widespread failure prevents access to essential gameplay.

Critical defects require immediate attention.

### 8.2. High

<badge color="warning">High</badge>

A defect that seriously affects gameplay, progression, or an important system but does not completely prevent the product from functioning.

Examples:

- A major quest cannot be completed.
- A core gameplay mechanic fails under common conditions.
- Important player progress is lost intermittently.
- A significant system becomes unusable.
- Severe performance problems occur in an important gameplay area.

High-severity defects SHOULD be resolved before release unless explicitly accepted by the project owner.

### 8.3. Medium

<badge color="info">Medium</badge>

A defect that affects functionality or player experience but has a limited impact or a reasonable workaround.

Examples:

- An inventory interaction behaves incorrectly in a specific situation.
- A non-critical UI element displays incorrect information.
- An enemy occasionally becomes stuck.
- An animation does not transition correctly under an uncommon condition.
- A sound effect fails to play in a particular scenario.

Medium-severity defects SHOULD be prioritized according to release impact and available capacity.

### 8.4. Low

<badge color="success">Low</badge>

A minor defect with limited functional or player-facing impact.

Examples:

- Minor visual alignment issues.
- Small text formatting errors.
- A non-essential sound effect plays at an incorrect volume.
- A minor animation inconsistency.
- A low-impact visual artifact.

Low-severity defects MAY be scheduled for later maintenance when appropriate.

### 8.5. Severity Guidelines

| Severity | General Impact | Typical Response |
|---|---|---|
| Critical | Product unusable, severe data loss, or major integrity failure | Immediate investigation |
| High | Major gameplay or system disruption | Resolve before release when possible |
| Medium | Noticeable functional or experience problem | Prioritize through backlog |
| Low | Minor inconvenience or cosmetic issue | Schedule according to available capacity |

Severity MUST reflect actual impact and should not be inflated simply to make a defect receive attention.

## 9. Priority Classification

Priority determines how urgently a defect should be addressed.

Severity and priority are related but different:

- Severity measures the impact of the defect.
- Priority measures the urgency of resolving it.

The project owner or authorized contributor SHOULD determine final priority based on severity, release timing, dependencies, frequency, and available resources.

Recommended priority levels:

| Priority | Meaning |
|---|---|
| P0 - Immediate | Requires immediate action or blocks critical work. |
| P1 - High | Should be addressed as soon as practical. |
| P2 - Normal | Should be scheduled in the regular backlog. |
| P3 - Low | Can be addressed when capacity allows. |

Examples:

- A Critical defect affecting the current release is normally P0.
- A High defect blocking a milestone is normally P1.
- A Medium defect with a workaround is normally P2.
- A Low cosmetic defect is normally P3.

These are guidelines, not automatic mappings. A low-severity issue may receive high priority when it affects a release requirement, while a serious issue in an unused prototype may have lower immediate priority.

AI agents MUST NOT independently override project priority decisions.

## 10. Bug Lifecycle and Statuses

Every tracked defect SHOULD have a status representing its current state.

Recommended lifecycle:

| Status | Description |
|---|---|
| Reported | A defect has been submitted but not yet reviewed. |
| Triaged | The report has been reviewed and classified. |
| Confirmed | The defect has been reproduced or sufficiently validated. |
| In Progress | Investigation or implementation of a fix is underway. |
| Fixed | A correction has been implemented and is ready for verification. |
| In Verification | The fix is being tested. |
| Reopened | The defect persists or has returned after being marked fixed. |
| Closed | The fix has been verified or the report has been formally resolved. |
| Deferred | Resolution has been postponed by an explicit decision. |
| Rejected | The report is invalid, expected behavior, or not accepted as a defect. |
| Duplicate | The same defect is already tracked in another report. |

### 10.1. Status Rules

- A new report begins as `Reported`.
- Classification and priority are evaluated during triage.
- A defect SHOULD become `Confirmed` when sufficient evidence supports it.
- `Fixed` MUST NOT be treated as equivalent to `Closed`.
- A defect MUST be verified before being closed as successfully resolved.
- A defect that still occurs after verification MUST be reopened.
- Deferred defects MUST retain their relevant information and rationale.
- Duplicate reports SHOULD reference the original defect.

### 10.2. Closure Requirements

A defect MAY be closed when:

- The reported behavior has been corrected and verified.
- The report is confirmed as expected behavior.
- The report is a duplicate and references the original.
- The report is rejected with a documented explanation.
- The project owner explicitly accepts a documented resolution or exception.

Closure reasons SHOULD be recorded.

## 11. Bug Triage

Triage is the process of reviewing new reports and deciding how they should be handled.

Triage SHOULD evaluate:

1. Whether the report describes a genuine defect.
2. Whether sufficient information is available.
3. Whether the defect can be reproduced.
4. Which system or feature is affected.
5. The severity of the problem.
6. The appropriate priority.
7. Whether an existing report already describes the same issue.
8. Whether the defect blocks development, testing, a milestone, or release.
9. Whether immediate action is necessary.

### 11.1. Triage Outcomes

A report MAY be:

- Confirmed and scheduled.
- Returned for additional information.
- Classified as a duplicate.
- Rejected as expected behavior.
- Reclassified as a feature request or improvement.
- Deferred with a documented reason.
- Escalated for immediate investigation.

### 11.2. Triage Responsibility

The project owner is responsible for final decisions about:

- Priority.
- Scope implications.
- Deferred defects.
- Release-blocking status.
- Accepted exceptions.
- Disputed expected behavior.

AI agents MAY assist with classification and recommendations but MUST NOT independently make decisions that change approved project scope or release acceptance.

## 12. Evidence and Attachments

Supporting evidence SHOULD be attached when it helps reproduce, understand, or verify a defect.

### 12.1. Screenshots

Screenshots are useful for:

- UI defects.
- Visual artifacts.
- Incorrect animations.
- Rendering issues.
- Incorrect object placement.
- Unexpected game states.

Screenshots SHOULD show enough context to understand the problem.

### 12.2. Screen Recordings

Recordings are recommended for:

- Intermittent defects.
- Animation problems.
- Timing-related issues.
- Complex reproduction sequences.
- Gameplay interactions.
- State transition problems.

### 12.3. Logs and Error Messages

When available, include:

- Godot debugger output.
- Runtime errors.
- Stack traces.
- Relevant application logs.
- Import or resource loading errors.
- Build and export errors.

Logs SHOULD include relevant context without unnecessary unrelated output.

### 12.4. Save Files and Test Data

When a defect depends on a particular save file or data state, include a suitable reproduction file when practical.

Before sharing test data, verify that it does not contain sensitive personal information or unrelated private information.

### 12.5. Evidence Quality

Evidence SHOULD:

- Correspond to the reported game version and environment.
- Be readable.
- Include relevant context.
- Avoid unnecessary information.
- Be stored in an appropriate repository or issue-tracking location.

Do not modify evidence in a way that changes the meaning of the observed defect.

## 13. Bug Verification and Regression

After a defect is marked `Fixed`, it MUST be verified before successful closure.

Verification SHOULD include:

1. Repeating the original reproduction steps.
2. Confirming that the expected behavior now occurs.
3. Checking relevant boundary conditions.
4. Testing related functionality.
5. Performing regression testing when appropriate.
6. Recording the verification result.

### 13.1. Verification Outcomes

| Outcome | Meaning |
|---|---|
| Passed | The defect no longer occurs under the tested conditions. |
| Failed | The defect still occurs or the correction introduces another problem. |
| Blocked | Verification cannot proceed because of an external dependency or environment issue. |
| Not Run | Verification has not been performed. |

A failed verification SHOULD return the defect to `Reopened` or `In Progress`, depending on the workflow.

### 13.2. Regression Considerations

Fixes SHOULD be evaluated for unintended effects on related systems.

Examples:

- A movement fix should not break jumping or collision behavior.
- An inventory fix should not corrupt equipment state.
- A save system fix should not break loading older supported saves.
- An audio fix should not interrupt unrelated audio playback.

### 13.3. Verification Evidence

Record relevant verification details:

- Game version or build.
- Environment.
- Test scenario.
- Result.
- Relevant evidence.
- Known limitations.

## 14. Duplicate and Related Defects

Before creating a new report, search existing defect records for similar problems.

When a duplicate is identified:

- Keep the most complete report as the primary record.
- Mark the additional report as `Duplicate`.
- Reference the original bug ID.
- Preserve any new evidence or reproduction information.

Related defects SHOULD be linked when they share a system, dependency, or suspected cause.

Do not combine unrelated defects simply because they affect the same feature.

## 15. Known Issues and Deferred Bugs

Not every defect must be fixed immediately.

A defect MAY be deferred when:

- Its impact is acceptable for the current development stage.
- A reasonable workaround exists.
- Resolution requires disproportionate effort.
- It depends on an external change.
- The issue is outside the current milestone scope.

Deferred defects MUST retain:

- Bug ID.
- Description.
- Severity.
- Priority.
- Deferral rationale.
- Known workaround, if available.
- Relevant milestone or release consideration.

Critical defects involving security, data integrity, or severe player progress loss SHOULD NOT be deferred without explicit project owner review and documented risk acceptance.

Known release issues MUST be documented in the relevant release information when they affect users.

## 16. Bug Report Template

Use the following template when creating a new defect report.

```markdown
# [Area] Short description of the defect

## Identification

- **Bug ID:** BUG-XXX
- **Status:** Reported
- **Severity:** Medium
- **Priority:** P2 - Normal
- **Affected Feature:** Feature or system name
- **Reporter:** Name or agent identifier
- **Date Reported:** YYYY-MM-DD

## Environment

- **Game Version:** X.Y.Z
- **Build:** BUILD-XXXXX
- **Platform:** Windows / Linux / macOS / Other
- **Godot Version:** X.Y
- **Configuration:** Debug / Release
- **Additional Context:** Relevant environment details

## Description

Describe the problem and its impact.

## Preconditions

- Condition 1.
- Condition 2.

## Steps to Reproduce

1. Step one.
2. Step two.
3. Step three.

## Expected Result

Describe what should happen.

## Actual Result

Describe what actually happens.

## Reproduction Frequency

- **Frequency:** Always / Frequent / Intermittent / Rare / Once / Unknown
- **Attempts:** X out of Y, if known

## Evidence

- Screenshot:
- Video:
- Logs:
- Save File:
- Additional Evidence:

## Additional Information

- **Workaround:** None / Description
- **Suspected Cause:** Hypothesis only, if applicable
- **Related Issues:** BUG-XXX
- **Related Requirements:** Work item or acceptance criterion IDs

## Resolution

- **Assigned To:**
- **Fix Description:**
- **Affected Commit or PR:**
- **Fixed Version:**
- **Verification Result:** Not Run / Passed / Failed / Blocked
- **Verification Evidence:**
- **Closure Reason:**
```

The template MAY be simplified for minor defects. Unknown fields SHOULD be marked as `Unknown`, `Not Available`, or `Not Applicable` as appropriate.

## 17. Defect Tracking and Repository Management

Projects SHOULD use a single authoritative location for tracking active defects.

This MAY be:

- GitHub Issues.
- A project management tool.
- A dedicated issue tracker.
- A structured project defect register.

The project MUST avoid maintaining multiple conflicting sources of truth.

### 17.1. Identifier Convention

When the tracking system does not provide automatic identifiers, use:

`BUG-XXX`

Examples:

- `BUG-001`
- `BUG-002`
- `BUG-003`

Identifiers MUST be unique and MUST NOT be reused.

### 17.2. Labels

Projects MAY use labels to classify defects.

Suggested labels:

- `bug`
- `severity:critical`
- `severity:high`
- `severity:medium`
- `severity:low`
- `area:gameplay`
- `area:ui`
- `area:audio`
- `area:performance`
- `area:persistence`
- `regression`
- `release-blocker`
- `needs-reproduction`
- `needs-information`

Labels SHOULD remain consistent throughout the project.

### 17.3. Repository Organization

When defects are tracked as GitHub Issues, the issue tracker SHOULD be the authoritative record.

Screenshots, recordings, logs, and other large evidence files SHOULD be stored using an appropriate attachment or artifact mechanism rather than committed unnecessarily to the source repository.

Project-specific defect records MAY be stored under:

`docs/qa/bug_reports/`

However, individual Markdown reports SHOULD only be used when they provide meaningful value beyond the issue tracker.

## 18. AI-Assisted Bug Reporting

AI agents MAY assist with:

- Drafting bug reports from test failures.
- Summarizing error logs.
- Identifying missing report information.
- Suggesting reproduction steps.
- Grouping related defects.
- Detecting likely duplicates.
- Recommending severity and priority.
- Preparing regression test suggestions.
- Summarizing defect status.
- Reviewing verification evidence.

AI agents MUST:

1. Separate observed facts from hypotheses.
2. Preserve original reproduction information.
3. Avoid inventing environment details.
4. Use actual logs and test evidence when available.
5. Identify missing information.
6. Reference existing issue IDs when available.
7. Follow the established severity and priority definitions.
8. Preserve defect history.
9. Report verification results accurately.
10. Request human review for uncertain or high-impact decisions.

AI agents MUST NOT:

- Claim a defect is reproduced without actually reproducing it or having sufficient evidence.
- Invent screenshots, logs, or test results.
- Mark a defect as fixed without implementation evidence.
- Close defects without required verification or authorization.
- Delete or rewrite historical reports without approval.
- Change approved priorities or release-blocking decisions independently.
- Modify user data or save files without authorization.

The project owner retains final authority over defect acceptance, prioritization, deferral, and closure decisions.

## 19. Bug Reporting Checklist

Before submitting a bug report, verify the following:

### Report Quality

- [ ] The title clearly identifies the problem.
- [ ] The description explains the observed behavior.
- [ ] Expected and actual results are documented.
- [ ] Steps to reproduce are included.
- [ ] Relevant preconditions are specified.
- [ ] Environment information is included.
- [ ] Reproduction frequency is recorded when known.

### Classification

- [ ] The issue is correctly classified as a defect.
- [ ] Severity reflects its actual impact.
- [ ] Priority is assigned or left for triage.
- [ ] Existing reports have been checked for duplicates.

### Evidence

- [ ] Relevant screenshots or recordings are attached when useful.
- [ ] Relevant logs or error messages are included.
- [ ] Evidence corresponds to the reported environment.
- [ ] Sensitive or unrelated information is excluded.

### Resolution

- [ ] The defect has an appropriate tracking status.
- [ ] The fix is linked to the relevant commit or pull request when applicable.
- [ ] Original reproduction steps have been verified.
- [ ] Regression risks have been considered.
- [ ] Closure reason and verification results are recorded.

## 20. Exceptions

Projects MAY adapt bug reporting requirements according to their development stage and complexity.

For early prototypes, experimental features, and temporary builds, a simplified report MAY be sufficient.

However, defects involving data loss, security, crashes, release-blocking behavior, or serious player impact MUST receive appropriate documentation and attention regardless of project stage.

Exceptions SHOULD be documented when they materially affect defect tracking, verification, or release quality.

## 21. Related Documents

- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/00_studio_standards/code_review_guidelines.md`
- `docs/02_technical_standards/testing_strategy.md`
- `docs/04_production_standards/backlog_management.md`
- `docs/04_production_standards/risk_management.md`
- `docs/04_production_standards/release_process.md`
- `docs/05_qa_standards/acceptance_criteria_guidelines.md`

## 22. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- Defect tracking practices change.
- New testing tools are introduced.
- Recurring reporting problems are identified.
- Release requirements evolve.
- AI-assisted QA workflows introduce new requirements.
- Defect analysis reveals opportunities to improve quality processes.

Changes MUST preserve the distinction between defect reporting, test execution, acceptance, and general work completion.

The project owner is responsible for approving changes to these guidelines.