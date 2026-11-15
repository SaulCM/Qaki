# Definition of Done

> Status: Draft (pending owner review)
> Scope: All studio work items, contributors, and AI agents

## 1. Purpose

This document establishes the studio-wide Definition of Done: the criteria that must be satisfied before a task, feature, fix, or other deliverable is reported as complete.

It exists to:

- Make completion mean the same thing across work categories.
- Prevent work from being reported as finished when it has only been written.
- Require evidence for completion claims rather than assertion.
- Distinguish implementation from validation, review, approval, and integration.
- Give human contributors and AI agents the same checklist and the same reporting obligations.

A deliverable is not done because code was produced, an asset was exported, or a document was drafted. It is done when its applicable criteria are satisfied and the evidence is reported honestly.

## 2. Scope

### 2.1 Coverage

This standard applies to:

- Gameplay programming and feature implementation.
- Architecture and infrastructure changes.
- Bug fixes.
- Automated tests and test infrastructure.
- Art, audio, and animation assets.
- UI/UX implementation and interface assets.
- Documentation.
- Configuration, tooling, and project setup.

### 2.2 Relationship with Other Standards

| Subject | Authoritative document |
|---|---|
| What the deliverable must achieve (per work item) | `docs/05_qa_standards/ACCEPTANCE_CRITERIA_GUIDELINES.md` |
| Quality principles and quality exceptions | `docs/00_studio_standards/QUALITY_STANDARDS.md` |
| Review process, severity, approval criteria | `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md` |
| Branch, pull request, and merge rules | `docs/00_studio_standards/BRANCHING_STRATEGY.md` |
| Commit format and commit rules | `docs/00_studio_standards/GIT_CONVENTIONS.md` |
| Testing approach | `docs/02_technical_standards/TESTING_STRATEGY.md` and `docs/05_qa_standards/` |
| Code standards | `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`, `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`, `docs/02_technical_standards/ENGINE_STANDARDS.md` |
| Asset standards | `docs/02_technical_standards/ASSET_PIPELINE.md` and `docs/03_art_audio_standards/` |
| Documentation conventions | `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md` |

Acceptance criteria and this Definition of Done are complementary. Acceptance criteria describe what a specific work item must achieve; this document describes how completion is demonstrated, reviewed, and reported. Acceptance criteria do not replace it (`ACCEPTANCE_CRITERIA_GUIDELINES.md`, section 2).

Where a project establishes stricter completion requirements, those requirements apply in addition to this standard. Where this standard and an approved project requirement conflict, the project requirement takes precedence for that project and the conflict is reported.

## 3. Requirement Keywords

- **MUST / MUST NOT** — mandatory for the work item it applies to.
- **SHOULD / SHOULD NOT** — expected practice; a deviation requires a stated reason in the completion report.
- **MAY** — permitted, not required.
- **When applicable / conditional** — the requirement applies only when the stated condition is met.

A requirement that does not apply to a work item is identified as not applicable. It is not silently skipped and it is not counted as satisfied.

## 4. Completion States

Completion is described with six distinct states. They are sequential in the order listed, are not interchangeable, and must not be claimed without evidence.

| State | Meaning | Evidence required |
|---|---|---|
| **Implemented** | The change exists in the working tree or branch as described | The change itself, plus a statement of what was changed and how it relates to the requirement |
| **Locally validated** | The change was exercised locally by the stated method | The exact commands or manual steps executed, and their actual results |
| **Automatically tested** | Automated tests covering the behavior were executed and passed | The test command used and its result summary; the tests executed and any that were skipped |
| **Reviewed** | The complete change was inspected against requirements, standards, and risk | Review findings by severity and their resolution, identifying the reviewing party |
| **Approved** | The project owner accepted the change | An explicit owner approval statement for that change |
| **Integrated** | The change is merged into the intended integration branch | The merge or pull request outcome, verified rather than assumed |

Rules:

- A work item MUST report the highest state it has actually reached.
- Implemented work MUST NOT be described as validated, tested, reviewed, approved, or integrated.
- Locally validated work MUST NOT be described as automatically tested when no automated test executed.
- Reviewed work MUST NOT be described as approved; review findings and approval are separate decisions.
- Approved work is not integrated until the merge has occurred and been verified.
- Approval and integration belong to the project owner. An AI agent MUST NOT claim either.
- A completion report that omits the unreached states implies they were reached; they MUST be stated explicitly instead.

## 5. Universal Requirements

The following requirements apply to every work item, regardless of category.

### 5.1 Requirements and Acceptance

- The requirement or task statement MUST be identified before implementation starts.
- Applicable acceptance criteria MUST be identified, or their absence reported.
- Ambiguous or contradictory requirements MUST be raised before decisions that materially affect the outcome.
- Unapproved design decisions MUST NOT be introduced to fill a requirement gap (`.cline/rules/project-context.md`; `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`).

### 5.2 Scope Discipline

- Only files required by the task MUST be modified.
- Unrelated refactoring, reformatting, renaming, and cleanup MUST NOT be included.
- Pre-existing issues found outside the task scope MUST be reported, not fixed.
- Unrelated or user-owned working-tree changes MUST be preserved (`.cline/rules/git-workflow.md`, section 6).

### 5.3 Standards Compliance

- The applicable studio and project standards MUST be identified and read before implementation.
- Applicable standards MUST be followed, or the deviation reported with justification.
- A conflict between authoritative documents MUST be reported rather than resolved silently.

### 5.4 Diagnostics

- The change MUST NOT introduce unexplained errors or warnings.
- Errors and warnings encountered during the work MUST be reported with enough context to locate them.
- Suppressing a warning or error to make a result appear clean is prohibited.

### 5.5 Evidence

- Completion claims MUST be supported by evidence, not assertion (`QUALITY_STANDARDS.md`, section 3.5).
- The validation actually executed MUST be reported, including negative or partial results.
- Validation that could not be performed MUST be reported as not performed, with the reason.

### 5.6 Final Inspection

- The complete diff MUST be reviewed before reporting completion.
- The diff MUST be confirmed to contain only the intended changes.
- Repository state (branch, staged files, untracked files) MUST be reported accurately.

### 5.7 Git Requirements

- The task MUST follow `BRANCHING_STRATEGY.md` and `GIT_CONVENTIONS.md`.
- No commit, merge, push, tag, or branch operation occurs without authorization for the task.
- Protected branches MUST NOT be modified.

## 6. Completion Criteria by Work Category

Different kinds of work are completed by different kinds of evidence. A documentation change does not require gameplay testing, and an art asset does not require unit tests. The category criteria below apply in addition to section 5.

### 6.1 Summary Matrix

| Work category | Local validation | Automated tests | Owner review | Subjective acceptance |
|---|---|---|---|---|
| Gameplay programming | Required | Expected when a test framework is configured | Required | When the requirement includes feel, clarity, or presentation |
| Architecture and infrastructure | Required | Expected when practical | Required | Not applicable |
| Bug fixes | Required; reproduction attempted or limitation documented | Regression coverage expected | Required | When the defect affects presentation or feel |
| Automated tests | Required (the suite is executed) | Not applicable (the tests are the deliverable) | Required | Not applicable |
| Art assets | Required (import and in-context inspection) | Not applicable unless asset tooling exists | Required | Required for art-direction conformity |
| Audio assets | Required (import and playback) | Not applicable unless asset tooling exists | Required | Required for audio-direction conformity |
| Animation | Required (playback, transitions, interruption) | Not applicable unless tooling exists | Required | Required |
| UI/UX | Required across supported resolutions and states | Expected for interface logic when a framework exists | Required | Required |
| Documentation | Required (accuracy, references, consistency) | Not applicable | Expected for shared standards; required when behavior or policy changes | Not applicable |
| Configuration and tooling | Required (project and tool behavior verified) | Not applicable unless the tooling has tests | Required | Not applicable |

"Not applicable" is a statement about the category, not permission to skip validation. Every category still requires the evidence required by its own criteria.

### 6.2 Gameplay Programming

A gameplay change is complete when:

- The approved behavior is implemented and matches its acceptance criteria.
- The change is integrated with the scenes, resources, and systems it depends on.
- Input, state transitions, and feedback behave as specified.
- Relevant edge cases and failure conditions are handled or reported.
- Applicable GDScript, architecture, scene, and engine standards are followed.
- Available validation was executed and its results reported.
- Behavior that depends on feel, readability, or presentation is flagged for owner evaluation rather than declared correct.
- Relevant gameplay documentation and specification are updated when the behavior changes.

### 6.3 Architecture and Infrastructure

An architectural or infrastructure change is complete when:

- The problem being solved and the affected systems are stated.
- The chosen approach is recorded or referenced, including alternatives considered when the decision is significant (`ARCHITECTURE_GUIDELINES.md`, section 14).
- Responsibilities, boundaries, and dependencies remain explicit and free of cycles.
- Feature ownership and project structure standards are respected.
- Significant architectural decisions received owner approval before implementation.
- An ADR is created or updated when the decision warrants one.
- Affected functionality was validated after the change, and regressions were considered.
- The architecture review checklist in `ARCHITECTURE_GUIDELINES.md` (section 17) was applied.

### 6.4 Bug Fixes

A bug fix is complete when:

- The reported behavior, the expected behavior, and the actual behavior are stated.
- Reproduction was attempted, or the limitation preventing reproduction is documented.
- The root cause is identified and the correction addresses it rather than the symptom.
- The change is the smallest reliable correction, without unrelated refactoring.
- Regression risk is assessed and relevant regression coverage is added where practical.
- The correction was validated, and the task is reported using an accurate status such as fixed and validated, fixed with validation incomplete, or unable to confirm the fix.
- The bug record is updated when the project tracks the defect in an issue or backlog item.
- Documentation is updated only when the fix changes documented behavior or reveals a missing requirement.

A bug fix MUST NOT be reported as fixed and validated when its correction has not been verified (`docs/07_agent_workflows/FIX_BUG.md`, section 19).

### 6.5 Automated Tests

A test contribution is complete when:

- The behavior under test and the reason for the test are clear.
- Tests verify observable behavior rather than incidental implementation detail.
- Positive, negative, and relevant boundary cases are covered.
- Tests are isolated, deterministic, and independent of execution order.
- Godot lifecycle and scene or resource dependencies are handled correctly.
- Test data and fixtures are controlled and not dependent on local-only state.
- The tests were executed and the results reported, including any failing or skipped tests.
- A failing test was investigated rather than removed, weakened, or skipped to obtain a passing run.
- Test placement and naming follow project structure and naming standards.

### 6.6 Art Assets

An art asset is complete when:

- Its purpose, owning feature, and intended in-game use are stated.
- It follows the approved art direction and the project's visual identity, or the deviation is explicitly reported for owner decision.
- It meets the applicable technical requirements: format, dimensions, orientation, and import settings.
- It is stored in the correct feature-oriented location with a compliant filename (`ART_ASSET_STANDARDS.md`, section 9).
- It imports without errors or missing dependencies (`ASSET_PIPELINE.md`, section 13.1).
- It was inspected in its intended context where the context exists (`ASSET_PIPELINE.md`, section 13.2).
- Licensing, attribution, and source-file requirements are satisfied when the asset is external or AI-generated.
- Performance impact has been considered for assets used at scale.
- The relevant documentation or asset list is updated.
- The art review checklist in `ART_ASSET_STANDARDS.md` (section 21) was applied.

An AI agent MUST NOT declare an asset approved. Visual conformity is an owner decision.

### 6.7 Audio Assets

An audio asset is complete when:

- Its purpose, owning feature, and playback context are stated.
- It follows the approved audio direction.
- Its format, duration, channel configuration, loudness, and dynamic range meet the applicable requirements.
- It contains no unintended clipping, noise, clicks, or artifacts that the validation was able to detect.
- It imports and plays correctly in the target environment.
- It was evaluated in context against other sounds that play simultaneously, where such a context exists.
- It is named and stored according to the audio naming and organization standards.
- Licensing, attribution, and source-file requirements are satisfied.
- The audio review checklist in `AUDIO_ASSET_STANDARDS.md` (section 20) was applied.

An AI agent MUST NOT claim audio was listened to, mixed, or validated by ear when it was not.

### 6.8 Animation

An animation deliverable is complete when:

- Its purpose, owning feature, and gameplay states are stated.
- Timing, spacing, and transitions support the intended motion and remain readable during gameplay.
- Playback ownership is explicit, and gameplay state remains authoritative.
- Looping, interruption, and transition behavior are intentional and verified.
- Animation resource references are valid and the animation plays without runtime errors.
- Integration with the character or object, its systems, audio, effects, and camera was verified where such integration exists.
- Naming, organization, and performance requirements are satisfied.
- The animation review checklist in `ANIMATION_STANDARDS.md` (section 18) was applied.

### 6.9 UI/UX

A UI/UX deliverable is complete when:

- The interface or flow satisfies its acceptance criteria.
- Visual, usability, and technical requirements in `UI_UX_STANDARDS.md` (section 22) were reviewed.
- Layouts behave correctly at supported resolutions and text is not clipped or overlapping.
- Interactive states, feedback, and error recovery are understandable.
- Supported input methods work, and focus or navigation behavior is correct.
- UI state reflects the underlying game state reliably.
- Accessibility considerations applicable to the interface were addressed or reported.
- The UI/UX review checklist in `UI_UX_STANDARDS.md` (section 24) was applied.

An AI agent MUST NOT independently approve significant changes to the established interface design system.

### 6.10 Documentation

A documentation change is complete when:

- Its purpose and intended audience are clear, and it does not duplicate an existing authoritative document.
- The information is accurate and reflects the actual repository state.
- Mandatory and recommended statements are distinguishable.
- Paths, filenames, and cross-references resolve to files that exist.
- Terminology and structure follow `DOCUMENTATION_STANDARDS.md`.
- The documentation inventory is updated when a document is created, renamed, moved, deprecated, or deleted.
- Approval status was not changed without owner authorization.
- Assumptions, unresolved questions, and incomplete sections are identified as such.

### 6.11 Configuration and Tooling

A configuration or tooling change is complete when:

- The problem and the intended effect of the change are stated.
- The change is the minimum required, without unrelated setting adjustments.
- Project-wide, engine, or shared configuration changes received owner approval.
- The project still opens and runs, and the affected tool or workflow still behaves as intended.
- Generated artifacts, caches, and local-only files were not committed.
- Sensitive values, credentials, and secrets were not introduced.
- The change and its effect on contributors are documented where the effect is not obvious.
- Rollback implications were considered for changes that are difficult to reverse.

## 7. Code Quality Requirements (When Code Changes)

When a work item changes code, the following apply:

- The applicable code standards MUST be followed: `GDSCRIPT_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md`, `SCENE_AND_NODE_CONVENTIONS.md`, `EVENT_AND_SIGNAL_GUIDELINES.md`, `RESOURCE_MANAGEMENT.md`, `ENGINE_STANDARDS.md`, and `PERFORMANCE_GUIDELINES.md` as relevant.
- Implementation language is GDScript unless the owner has approved otherwise.
- Naming MUST follow `NAMING_CONVENTIONS.md` and the conventions already used in the affected area.
- Script responsibilities MUST be focused, and the change MUST NOT introduce a monolithic script or a parallel implementation of an existing system.
- Public interfaces that other code depends on MUST NOT be rewritten without checking their consumers.
- New dependencies, frameworks, plugins, or abstractions MUST NOT be introduced without approval.
- Node references, resource lifetimes, signals, and connections MUST be handled according to their standards, including disconnection and cleanup where required.
- Error and edge-case handling MUST be explicit; important failures MUST NOT be swallowed.
- Debug output and temporary instrumentation MUST NOT remain in the change unless the project intentionally keeps it.
- The GDScript review checklist (`GDSCRIPT_STANDARDS.md`, section 18), the architecture review checklist (section 17), and the engine compliance checklist (`ENGINE_STANDARDS.md`, section 20) SHOULD be applied as applicable.

## 8. Testing and Validation (Conditional)

### 8.1 Current Project State

This section must be read against the actual state of the repository:

- The Godot project does not currently contain a `tests/` directory or any test suite, and GdUnit4 is not installed in `game_project/addons/`. The adopted framework, runner, and pinned version are recorded in `TESTING_STRATEGY.md` (section 11.5).
- `.github/workflows/ci.yml` is configured and runs project import validation, a GDScript parse check, and GdUnit4 test execution only when a test suite exists (`TESTING_STRATEGY.md`, section 11.6). `.github/workflows/validation.yml` remains an unconfigured placeholder. The workflow has not yet been executed, so no automated check has yet produced a result.

Therefore a work item MUST NOT be reported as automatically tested, or as passing continuous integration, unless such a test or check was actually executed and its result observed.

### 8.2 Requirements

- When a test framework or runner is configured and documented, relevant tests MUST be executed and the results reported (`TESTING_STRATEGY.md`, section 13.2).
- When no framework exists, the change MUST still be validated by the means actually available: static inspection, project or scene execution where possible, and documented manual steps.
- The validation method used MUST be named in the completion report, together with what it did and did not cover.
- Tests that already exist and cover the affected area MUST be run.
- Existing tests MUST NOT be deleted, weakened, or skipped to obtain a passing result.
- Failure of a validation step MUST be reported, not hidden or re-run until it appears to pass.
- A passing test suite does not by itself establish that behavior is correct, enjoyable, or balanced; those judgments belong to owner review and playtesting.

## 9. Regression Considerations

- The systems and files that could be affected by the change MUST be identified, not only the files that were edited.
- Shared resources, shared scenes, autoloads, signals, and configuration MUST be considered when their consumers exist.
- Save data, persistence formats, and compatibility behavior MUST be considered when the change touches them.
- Behavior intentionally preserved MUST be verified to remain unchanged where the change could reach it.
- Regression risk that was not tested MUST be disclosed rather than assumed to be absent.
- When a defect is fixed, regression coverage SHOULD be added where practical and where the test capability exists.

## 10. Performance Considerations (When Relevant)

Performance requirements apply when the change affects per-frame processing, physics, rendering, memory, loading time, asset size, or allocation behavior.

When applicable:

- The performance implication MUST be considered and stated.
- Expensive work MUST NOT be introduced into per-frame callbacks without justification.
- Optimization MUST be evidence-based; speculative optimization and premature caching are discouraged (`PERFORMANCE_GUIDELINES.md`).
- Measurements MUST be reported with the method used; an assumed improvement is not a measurement.
- When no measurement was performed, the completion report MUST state that performance was not measured.

When the change has no plausible performance impact, this section is recorded as not applicable rather than left unstated.

## 11. Documentation Requirements

- Documentation MUST be updated when the change alters behavior, architecture, workflows, conventions, or project configuration in a way that existing documentation would misrepresent.
- Studio documentation belongs under `docs/`; game-specific documentation belongs under `game_project/docs/`. They MUST NOT be mixed (`PROJECT_STRUCTURE_STANDARDS.md`).
- `docs/DOCUMENTATION_INVENTORY.md` MUST be updated when a document is created, renamed, moved, deprecated, or deleted.
- An authoritative document MUST be extended rather than duplicated by a new document covering the same subject.
- A document status MUST NOT be changed to approved without owner authorization.
- Documentation trivial changes SHOULD NOT be created purely to describe a code change that documentation does not need to reflect.
- A completion report MUST NOT claim documentation was updated when it was not.

## 12. Asset and Resource Validation

When a work item adds, modifies, replaces, or removes an asset or resource:

- The asset MUST import successfully, with no import errors or missing resources (`ASSET_PIPELINE.md`, section 13.1).
- Resource references MUST resolve, and affected scenes MUST still load.
- Import settings MUST be appropriate for the asset type; shared or project-wide import changes require approval.
- The asset SHOULD be verified in its intended context, not only at import time.
- Generated caches and import artifacts MUST NOT be committed.
- An asset MUST NOT be deleted or replaced without checking its references, including dynamically loaded and configuration-referenced assets.
- Dangling references MUST NOT be left behind after a move, rename, or replacement.
- Licensing and attribution records MUST be preserved when an external or AI-generated asset is added or retired.
- Whether the asset was inspected in context MUST be reported honestly; import success is not visual or audible validation.

## 13. Git and Pull Request Requirements

- The work MUST follow `BRANCHING_STRATEGY.md` for branch use, pull request target, and integration.
- Commits, when authorized, MUST follow the format and rules in `GIT_CONVENTIONS.md` (sections 2 to 4).
- One commit SHOULD represent one logical change, and commits MUST NOT include unrelated files.
- Files MUST be staged explicitly and verified before committing.
- A pull request MUST target `develop` unless the owner directs otherwise.
- A pull request description MUST state the scope, the validation performed with results, the validation not performed with reasons, and any known limitations.
- A pull request MUST NOT be merged without explicit owner authorization.
- Protected branches, branch protection, and required checks MUST NOT be bypassed.
- Secrets, credentials, and personal data MUST NOT appear in any committed content.

## 14. Code Review Requirements

- A change MUST be reviewed before integration; review depth is proportional to risk, complexity, and impact (`CODE_REVIEW_GUIDELINES.md`, section 2).
- Reviewers MUST inspect the actual change, not only its description or commit messages.
- Findings MUST be classified by severity, and blocking findings MUST be resolved before approval (section 6).
- Approval requires the criteria in `CODE_REVIEW_GUIDELINES.md` (section 8.1).
- Material changes after approval require re-review (section 8.3).
- AI-assisted review is advisory. It MUST NOT be presented as approval, and an agent MUST NOT approve its own changes (sections 3.6 and 11).
- A review that could not be completed MUST be reported as incomplete, including which areas were not inspected.

## 15. AI-Assisted Development Requirements

These requirements apply in addition to every other section of this document.

### 15.1 Required Behavior

An AI agent MUST:

- Inspect the relevant repository structure and existing implementation before writing.
- Read the applicable studio and project documentation, including `docs/DOCUMENTATION_INVENTORY.md`, before implementation.
- Follow the applicable standards and the conventions already used in the affected area.
- Modify only files required by the task.
- Preserve unrelated user changes and existing behavior.
- Avoid introducing dependencies, plugins, autoloads, abstractions, or conventions that were not approved.
- Report assumptions, deviations, and open questions explicitly.
- Execute the validation steps that are available.
- Report the actual validation results, including failures and skipped steps.
- Identify behavior that was not verified.
- State the highest completion state actually reached, using the states in section 4.
- Report the repository state, the branch used, and any Git actions performed.

### 15.2 Prohibited Behavior

An AI agent MUST NOT:

- Claim that code, an asset, or a document was tested when it was not.
- Present implementation as validation.
- Report a task as complete when its applicable criteria were not satisfied.
- Suppress, ignore, or hide errors and warnings to produce a clean-looking result.
- Delete or weaken tests, checks, or validation steps to obtain a passing result.
- Approve its own work, merge it, or describe itself as the approver.
- Fabricate evidence, review results, or approval.
- Expand scope beyond the task without approval.
- Modify unrelated documentation, configuration, or files.

### 15.3 Honest Reporting of Limitations

When a validation step cannot be performed, the agent MUST:

1. State which step could not be performed.
2. State why it could not be performed.
3. State what was done instead, if anything.
4. State what remains unverified as a result.

Generating an implementation is not evidence of its correctness. A task completed by an AI agent does not constitute review, approval, or integration.

## 16. Final Reporting Requirements

A completion report MUST state the following. Items that do not apply are marked as not applicable rather than omitted silently.

### 16.1 Report Contents

- **Task:** what was requested, and the acceptance criteria or requirement used.
- **Branch and repository state:** branch name, whether the working tree was clean before the work, and whether any user-owned changes existed.
- **Changes:** the files created, modified, or deleted, and why each belongs to the task.
- **Completion state:** the highest state reached, using the definitions in section 4.
- **Validation performed:** each check, the method or command used, and its actual result.
- **Validation not performed:** each check that was skipped or unavailable, with the reason.
- **Tests:** tests executed and their outcome, or an explicit statement that no test framework or runner is configured.
- **Regression assessment:** what could be affected, what was checked, and what remains unverified.
- **Performance:** measured, considered without measurement, or not applicable.
- **Documentation:** documents updated, or a statement that none required updating.
- **Assets:** imports and in-context checks performed, or not performed.
- **Review and approval:** whether a review occurred, by whom, and whether approval was given. Neither is claimed without evidence.
- **Git actions:** commits, pushes, merges, or branch operations performed, and any that were intentionally not performed.
- **Known limitations:** unfinished work, assumptions, and unverified behavior.
- **Out-of-scope observations:** issues noticed but not addressed because they belong to separate work.

### 16.2 Reporting Rules

- The report MUST describe what actually happened, not what was intended.
- Uncertainty MUST be stated as uncertainty.
- A limitation MUST NOT be softened into a success statement.
- The report MUST NOT imply review, approval, or integration that did not occur.

### 16.3 Reduced Report for Low-Risk Work

A documentation-only correction or another demonstrably low-risk change MAY use the compact report form below. The compact form does not waive any item in section 16.1: every item is either stated or explicitly marked not applicable. Code, asset, configuration, and behavior changes MUST NOT use it unless the project owner authorizes a reduced report.

Illustrative example for a documentation-only correction:

| Report item | Content |
|---|---|
| Task | Correct a template reference in a workflow. Acceptance: the reference resolves and no procedure changes. |
| Branch and repository state | `feature/studio-documentation`; clean tree before the work; no user-owned changes. |
| Changes | The workflow file, one reference corrected. No other file belongs to the task. |
| Completion state | Implemented and locally validated. |
| Validation performed | Changed section read; all old references searched (none remain); `git diff --check` passed. |
| Validation not performed | No Markdown renderer or link checker was available. |
| Tests | No test framework or runner is configured; no automated test applies. |
| Regression assessment | Documentation only; no runtime behavior. Rendered appearance remains unverified. |
| Performance | Not applicable. |
| Documentation | The changed workflow; inventory unchanged because its entry is unchanged. |
| Assets | Not applicable. |
| Review and approval | Not reviewed; no approval is claimed. |
| Git actions | None; changes left unstaged for review. |
| Known limitations | None beyond the unperformed checks above. |
| Out-of-scope observations | None. |

The example is illustrative. It does not authorize omitting an item that applies, and it does not change the completion states defined in section 4.

## 17. Exceptions and Incomplete Work

### 17.1 Incomplete Work

Work that is not fully done MUST be reported as incomplete, with the partial outcome named, for example:

- Implemented, validation incomplete.
- Implemented and locally validated, automated tests unavailable.
- Fix applied, correction not confirmed.
- Documentation drafted, references not yet verified.
- Blocked pending owner decision or missing information.

Partial delivery is acceptable when it is stated. It is not acceptable when it is presented as complete.

### 17.2 Scope Reduction

Reducing the requested scope requires owner approval. The completion report MUST identify what was not delivered and why.

### 17.3 Exceptions to This Standard

An exception to a requirement in this definition is permitted only when:

1. The reason is stated.
2. The affected requirement is identified.
3. The associated risk or limitation is described.
4. The responsible decision-maker is identified.
5. A resolution plan exists when the gap is temporary.
6. The exception is documented when it materially affects quality or traceability.
7. The project owner approves it.

AI agents MUST NOT independently approve an exception or declare a requirement inapplicable in order to complete a task (`QUALITY_STANDARDS.md`, sections 17 and 18).

### 17.4 Relationship to Task Status

A work item MUST NOT be moved to Done in a backlog or tracking system until its acceptance criteria and the applicable requirements of this document are satisfied (`SPRINT_WORKFLOW.md`, section 8.4; `BACKLOG_MANAGEMENT.md`, section 12.1).

## 18. Related Documentation

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md` — Studio development principles.
- `docs/00_studio_standards/QUALITY_STANDARDS.md` — Quality expectations, evidence, AI requirements, quality exceptions.
- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md` — Review process, severity, approval criteria.
- `docs/00_studio_standards/GIT_CONVENTIONS.md` — Commit and branch conventions.
- `docs/00_studio_standards/BRANCHING_STRATEGY.md` — Branch lifecycle, pull request targets, merge rules.
- `docs/00_studio_standards/NAMING_CONVENTIONS.md` — Naming conventions.
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md` — Project and documentation organization.
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md` — Documentation conventions and maintenance.
- `docs/02_technical_standards/GDSCRIPT_STANDARDS.md` — GDScript implementation standards.
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md` — Architecture requirements and review checklist.
- `docs/02_technical_standards/ENGINE_STANDARDS.md` — Godot version, configuration, and engine compliance.
- `docs/02_technical_standards/TESTING_STRATEGY.md` — Testing levels, execution, and AI testing requirements.
- `docs/02_technical_standards/ASSET_PIPELINE.md` — Asset import, validation, and version control.
- `docs/03_art_audio_standards/ART_ASSET_STANDARDS.md` — Art asset requirements and review.
- `docs/03_art_audio_standards/AUDIO_ASSET_STANDARDS.md` — Audio asset requirements and review.
- `docs/03_art_audio_standards/ANIMATION_STANDARDS.md` — Animation requirements and review.
- `docs/03_art_audio_standards/UI_UX_STANDARDS.md` — Interface requirements and review.
- `docs/04_production_standards/SPRINT_WORKFLOW.md` and `docs/04_production_standards/BACKLOG_MANAGEMENT.md` — Task status and completion handling.
- `docs/05_qa_standards/ACCEPTANCE_CRITERIA_GUIDELINES.md` — Acceptance criteria definition.
- `docs/05_qa_standards/REGRESSION_TESTING.md` — Regression testing expectations.
- `docs/07_agent_workflows/` — Agent execution procedures that reference this definition.
- `.cline/rules/gdscript-standards.md`, `.cline/rules/asset-rules.md`, `.cline/rules/git-workflow.md` — Mandatory agent behavior.

## 19. Maintenance

This definition SHOULD be reviewed when:

- A test framework, test runner, or continuous integration is configured, since section 8 then changes from a limitation to a requirement.
- New work categories are introduced, or an existing category's completion criteria change.
- The studio adopts new tooling that makes additional validation possible.
- Repeated completion-report problems show that a criterion is unclear or impractical.
- Related standards change their requirements in a way that affects completion criteria.

Changes MUST preserve the distinction between the completion states in section 4 and MUST NOT weaken the evidence requirements. The project owner is responsible for approving changes to this document.
