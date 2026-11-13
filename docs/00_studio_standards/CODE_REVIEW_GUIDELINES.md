
# Code Review Guidelines

## 1. Purpose

This document defines the standards and procedures for reviewing code and other repository changes before they are integrated into shared development branches.

The objectives are to:

- Maintain code quality and consistency.
- Prevent regressions and unintended behavior.
- Verify compliance with project architecture and technical standards.
- Identify security, reliability, and maintainability issues.
- Ensure changes are appropriately tested and documented.
- Establish a consistent review process for human and AI-generated contributions.

These guidelines apply to all pull requests, regardless of whether changes are produced by the project owner, an AI agent, or another contributor.

## 2. Scope

Code reviews apply to changes involving:

- GDScript source code.
- Scenes, nodes, and scene composition.
- Resources and configuration files.
- Gameplay systems and mechanics.
- UI and interaction logic.
- Asset imports and project configuration.
- Automated tests and test infrastructure.
- Build, automation, and CI/CD configuration.
- Documentation and technical specifications.

Review depth should be proportional to the change's complexity, risk, and potential impact.

## 3. Review Principles

All reviews should follow these principles:

### 3.1 Correctness First

Verify that the implementation satisfies the intended requirements and behaves correctly.

### 3.2 Maintainability

Prefer solutions that are understandable, focused, and consistent with the existing architecture.

Avoid unnecessary complexity, duplication, and premature abstraction.

### 3.3 Consistency

Changes must follow applicable project standards, conventions, and approved architectural decisions.

### 3.4 Minimal Scope

A pull request should address a clearly defined task.

Unrelated refactoring, formatting changes, and feature additions should be separated unless they are necessary for the requested implementation.

### 3.5 Evidence-Based Review

Review comments should identify concrete problems, explain their impact, and suggest actionable improvements.

Avoid subjective preferences that do not meaningfully improve the implementation.

### 3.6 Human Accountability

AI-generated reviews and automated checks can assist the process but do not replace the project owner's final review and approval.

## 4. Review Responsibilities

### 4.1 Author Responsibilities

The author of a pull request must:

- Ensure the implementation matches the task requirements.
- Follow applicable studio and project standards.
- Perform relevant local validation before requesting review.
- Include or update automated tests when appropriate.
- Update documentation when behavior, architecture, or workflows change.
- Provide a clear pull request description.
- Disclose known limitations, assumptions, and incomplete work.
- Respond to review feedback and resolve identified issues.

### 4.2 Reviewer Responsibilities

The reviewer must:

- Understand the task and expected behavior.
- Inspect the complete change, not only the summary.
- Verify correctness, architecture, maintainability, and test coverage.
- Identify regressions and unintended side effects.
- Check compliance with applicable standards.
- Distinguish blocking issues from optional improvements.
- Request clarification when requirements or implementation decisions are unclear.
- Approve only when the change satisfies the applicable acceptance criteria.

### 4.3 AI Agent Responsibilities

AI agents may:

- Inspect changes and identify potential defects.
- Check compliance with repository standards.
- Review test coverage and validation results.
- Suggest improvements and identify missing documentation.
- Prepare review summaries and address feedback when authorized.

AI agents must not:

- Approve or merge their own pull requests.
- Treat their own successful implementation or tests as proof of correctness.
- Hide failed checks, known defects, or incomplete work.
- Modify unrelated code merely to satisfy subjective review preferences.
- Bypass repository protection or review requirements.

The project owner retains final review and merge authority.

## 5. Review Checklist

Reviewers should evaluate the following areas as applicable.

### 5.1 Requirements and Behavior

- [ ] Does the implementation satisfy the task requirements?
- [ ] Are acceptance criteria addressed?
- [ ] Does the implementation handle expected use cases?
- [ ] Are edge cases and invalid inputs handled appropriately?
- [ ] Is existing behavior preserved where required?
- [ ] Are there unintended gameplay or user experience changes?

### 5.2 Architecture and Design

- [ ] Does the implementation follow the established architecture?
- [ ] Are responsibilities clearly separated?
- [ ] Are dependencies explicit and appropriately scoped?
- [ ] Is coupling between systems reasonable?
- [ ] Are existing components reused where appropriate?
- [ ] Does the change introduce unnecessary abstractions or complexity?
- [ ] Are shared resources and global state handled safely?
- [ ] Are relevant architectural decisions documented?

### 5.3 Code Quality

- [ ] Are names clear and consistent with project conventions?
- [ ] Are functions and scripts focused on specific responsibilities?
- [ ] Is the code readable and reasonably simple?
- [ ] Is duplicated logic avoided?
- [ ] Are types used appropriately?
- [ ] Are magic numbers and unexplained constants avoided?
- [ ] Are comments useful and accurate?
- [ ] Are errors and exceptional conditions handled appropriately?
- [ ] Is dead code avoided?

### 5.4 Godot and GDScript

- [ ] Does the implementation follow the project's configured Godot version?
- [ ] Are node references and scene dependencies valid?
- [ ] Are lifecycle callbacks used appropriately?
- [ ] Is `_process()` or `_physics_process()` used only when necessary?
- [ ] Are signals used appropriately for event communication?
- [ ] Are exported properties and Resources used consistently?
- [ ] Are scene and resource paths valid?
- [ ] Are autoloads and global state justified?
- [ ] Are shared mutable Resources handled correctly?
- [ ] Are there avoidable runtime errors, warnings, or parser errors?

### 5.5 Testing and Reliability

- [ ] Are relevant automated tests included or updated?
- [ ] Do existing tests still pass?
- [ ] Have affected scenes or systems been executed and validated?
- [ ] Are important edge cases covered?
- [ ] Are regression risks considered?
- [ ] Are test results accurately reported?
- [ ] Are manual testing requirements documented when automation is insufficient?

### 5.6 Performance

- [ ] Does the implementation introduce unnecessary per-frame work?
- [ ] Are expensive operations performed at appropriate times?
- [ ] Are unnecessary allocations, repeated calculations, or resource loads avoided?
- [ ] Are performance-sensitive changes justified and validated where appropriate?

Do not require premature optimization. Performance concerns should be based on reasonable technical evidence or identifiable risks.

### 5.7 Security and Data Integrity

- [ ] Are external inputs validated where necessary?
- [ ] Are sensitive values and credentials excluded from source control?
- [ ] Are file and resource operations safe?
- [ ] Are save data and persistent state handled consistently?
- [ ] Are dependencies and third-party assets from acceptable sources?
- [ ] Are potentially destructive operations appropriately controlled?

### 5.8 Documentation and Repository Hygiene

- [ ] Are relevant technical documents updated?
- [ ] Are architectural changes accompanied by an ADR when required?
- [ ] Are asset licenses and attribution recorded where applicable?
- [ ] Are temporary files, debug artifacts, and unnecessary generated files excluded?
- [ ] Are project configuration changes intentional?
- [ ] Are commit messages and pull request descriptions meaningful?

## 6. Review Severity

Review findings must communicate their impact and urgency.

| Severity | Classification | Meaning |
|---|---|---|
| Critical | Blocking | Security, data integrity, project stability, or fundamental functionality is seriously compromised. |
| High | Blocking | Significant functional defect, regression, or architectural violation that must be resolved before merging. |
| Medium | Usually blocking | Meaningful maintainability, reliability, or correctness issue. Resolve before merging unless explicitly accepted by the project owner. |
| Low | Non-blocking | Minor improvement that does not prevent the change from being safely integrated. |
| Suggestion | Informational | Optional alternative or improvement without a demonstrated defect. |

Severity should reflect actual impact, not personal preference.

A reviewer should clearly identify which findings must be resolved before approval.

## 7. Review Comments

Review comments should be:

- Specific and actionable.
- Respectful and professional.
- Focused on the changed code or its direct consequences.
- Supported by an explanation of the problem and its impact.
- Proportionate to the severity of the issue.

A useful review comment should generally include:

1. **Problem:** What is wrong?
2. **Impact:** Why does it matter?
3. **Recommendation:** What should change?

Avoid vague comments such as "This is bad" or "Refactor this."

When proposing an alternative implementation, explain why it is preferable.

## 8. Pull Request Review Process

The standard review process is:

1. The author creates a pull request targeting the appropriate integration branch.
2. The author provides a description, scope, and validation results.
3. Automated CI checks execute.
4. The reviewer inspects the implementation and its associated changes.
5. Review findings are documented and classified by severity.
6. The author addresses blocking findings.
7. Updated changes and relevant checks are reviewed again.
8. The project owner approves and merges the pull request.

The applicable branch targets and merge policies are defined in `BRANCHING_STRATEGY.md`.

### 8.1 Approval Criteria

A pull request may be approved when:

- The implementation satisfies its requirements.
- No unresolved critical or high-severity findings remain.
- Medium-severity findings have been resolved or explicitly accepted by the project owner.
- Relevant automated checks pass.
- Required manual validation has been completed.
- Documentation is updated where necessary.
- The change does not violate approved architectural decisions or mandatory standards.

### 8.2 Request Changes

A reviewer should request changes when blocking issues remain.

The review must explain what needs to be corrected and why.

### 8.3 Re-Review

When an author updates a pull request:

- Review the new changes.
- Verify that previous findings were addressed.
- Check for regressions introduced by the corrections.
- Re-run relevant validation when necessary.

Previously approved changes should be reviewed again if subsequent commits materially alter their behavior or scope.

## 9. Testing Expectations

Testing requirements depend on the change's risk and scope.

At minimum:

- Small documentation-only changes should be checked for accuracy, consistency, and valid references.
- Small code changes should receive relevant targeted validation.
- Gameplay or system changes should receive targeted tests and regression checks.
- Changes affecting shared systems should receive broader integration testing.
- Architectural changes should include appropriate validation of affected systems.
- Performance-sensitive changes should be validated with profiling or other relevant measurements when justified.

A passing test suite does not guarantee correctness. Reviewers should also consider missing tests and untested scenarios.

## 10. Architectural and Standards Exceptions

If a change cannot comply with an existing standard or approved architectural decision:

1. Explain the reason.
2. Identify the affected standard or decision.
3. Describe the alternatives considered.
4. Explain the consequences and risks.
5. Obtain project owner approval before introducing the exception.
6. Update the relevant documentation or ADR when necessary.

Exceptions must be explicit rather than silently introduced through implementation.

## 11. AI-Assisted Code Review

AI-assisted reviews should use the following principles:

- Provide the agent with the task requirements and relevant project documentation.
- Ask it to inspect the complete diff and relevant surrounding code.
- Require findings to include file paths, locations, severity, and explanations.
- Ask it to distinguish confirmed defects from potential risks.
- Require it to report validation performed and validation not performed.
- Verify important findings against the actual implementation.
- Do not treat generated review summaries as approval.

AI review prompts should prioritize correctness, regressions, architecture, security, and missing tests over cosmetic suggestions.

The project owner must independently evaluate significant findings and make the final approval decision.

## 12. Review Completion Report

For substantial reviews, provide a concise summary containing:

- Pull request or change identifier.
- Scope reviewed.
- Overall review outcome.
- Blocking findings.
- Non-blocking findings and suggestions.
- Tests and validation inspected.
- Known limitations or unresolved risks.

The report must distinguish between checks that were actually executed and checks that were only inspected or recommended.

## 13. Related Documentation

This document should be used together with:

- `GIT_CONVENTIONS.md` — General Git practices and repository conventions.
- `BRANCHING_STRATEGY.md` — Branch lifecycle, pull request targets, and integration rules.
- `COMMIT_CONVENTIONS.md` — Commit message format and commit practices, if maintained separately.
- `DEFINITION_OF_DONE.md` — Completion and acceptance requirements.
- `docs/02_technical_standards/` — Technical implementation standards.
- `docs/06_templates/` — Reusable pull request and review templates, where available.

## 14. Maintenance

These guidelines should be reviewed when:

- The repository workflow changes.
- The technical architecture evolves significantly.
- New tools or automated review processes are introduced.
- Recurring review problems reveal gaps in the guidelines.

Changes to this document should preserve consistency with the other studio standards.

The project owner is responsible for maintaining and approving updates.
