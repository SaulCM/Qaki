# Release Process

## 1. Purpose

This document defines the standard process for preparing, validating, approving, publishing, and maintaining game releases.

It establishes:

- Release planning and preparation requirements.
- Versioning and release identification.
- Build preparation and validation.
- Release approval responsibilities.
- Publishing and distribution procedures.
- Release documentation and artifact preservation.
- Post-release verification and maintenance.

The objective is to ensure that every release is deliberate, traceable, sufficiently tested, and reproducible.

## 2. Scope

These guidelines apply to all game releases produced by the studio, including:

- Initial public releases.
- Early Access releases.
- Public beta releases.
- Patches and bug-fix releases.
- Content updates.
- Major feature updates.
- Platform-specific releases.
- Hotfixes.

The process SHOULD be adapted to the distribution model, target platforms, project size, and release risk.

Internal development builds and experimental prototypes do not require the complete release process unless the project owner determines otherwise.

## 3. Release Principles

### 3.1. Release Readiness

A release MUST satisfy its defined acceptance criteria before publication.

A build being technically executable does not automatically mean it is ready for release.

### 3.2. Traceability

Every release MUST be identifiable through its version, source revision, and relevant build information.

The studio SHOULD preserve enough information to determine how a released build was produced.

### 3.3. Quality and Stability

Releases SHOULD be validated against the project's functional, technical, performance, and platform requirements.

Known issues MUST be evaluated before release.

### 3.4. Controlled Changes

Changes introduced during release preparation SHOULD be limited to necessary fixes and release-related adjustments.

Unrelated feature development SHOULD NOT be introduced into a release candidate.

### 3.5. Reproducibility

The release process SHOULD use documented and repeatable build procedures.

Builds SHOULD be generated from a known repository state and appropriate project configuration.

### 3.6. Explicit Approval

The project owner MUST approve the release before publication.

AI agents and automated pipelines MAY prepare and validate release artifacts but MUST NOT independently authorize publication.

### 3.7. Historical Integrity

Released artifacts, version information, and release records MUST be preserved.

Previously published releases MUST NOT be silently replaced or modified.

## 4. Release Types

The studio MAY use the following release categories.

### 4.1. Initial Release

The first officially distributed version of a game.

It SHOULD include:

- The intended initial game experience.
- Required gameplay systems and content.
- Validated platform builds.
- Release documentation.
- Credits and asset attributions.
- Known issue information, when applicable.

### 4.2. Major Release

A release introducing substantial changes to gameplay, content, systems, or overall product functionality.

Examples:

- Major gameplay expansions.
- Significant progression changes.
- Large content additions.
- Major technical updates.

Major releases MAY require additional compatibility, migration, and regression testing.

### 4.3. Minor Release

A release introducing smaller improvements or additional functionality without fundamentally changing the product.

Examples:

- New features.
- Additional levels or content.
- Usability improvements.
- Non-breaking gameplay enhancements.

### 4.4. Patch Release

A release primarily intended to correct defects or improve stability.

Examples:

- Gameplay bug fixes.
- UI corrections.
- Performance improvements.
- Compatibility fixes.
- Minor balancing adjustments.

### 4.5. Hotfix Release

An urgent release intended to resolve a critical issue affecting a published version.

Hotfixes MAY use an abbreviated release process when necessary, but MUST still receive appropriate validation and project owner approval.

The extent of validation SHOULD reflect the urgency and risk of the change.

### 4.6. Preview and Early Access Releases

Preview, public beta, and Early Access releases MAY contain incomplete features or known limitations.

Their intended status, limitations, and expectations MUST be communicated clearly to users.

They SHOULD still satisfy appropriate stability, compatibility, and data integrity requirements.

## 5. Release Planning

### 5.1. Release Scope

Each planned release SHOULD have a clearly defined scope.

The scope SHOULD identify:

- Release objectives.
- Included features and improvements.
- Included bug fixes.
- Target platforms.
- Target distribution channels.
- Known limitations.
- Excluded or deferred changes.

Changes MUST be evaluated against the release objectives before inclusion.

### 5.2. Release Readiness Criteria

The project SHOULD define measurable release acceptance criteria.

Depending on the release, these MAY include:

- Required features are complete.
- Required content is integrated.
- Critical defects are resolved.
- Required regression tests pass.
- Performance targets are satisfied.
- Platform requirements are met.
- Save compatibility is validated.
- Licensing and attribution requirements are satisfied.
- Release documentation is prepared.

### 5.3. Release Scheduling

Release dates SHOULD consider:

- Remaining development work.
- Testing capacity.
- Platform review requirements.
- Distribution requirements.
- Known technical risks.
- Available support capacity.

A target release date MUST NOT override critical quality or stability requirements.

### 5.4. Release Plan

For significant releases, maintain a release plan containing:

- Release identifier or version.
- Release objectives.
- Scope.
- Target platforms.
- Target date, when applicable.
- Responsible owner.
- Required validation.
- Known risks.
- Dependencies.
- Approval requirements.

Small patches MAY use a simplified release record.

## 6. Versioning

### 6.1. Version Identification

Every published release MUST have a unique and identifiable version.

The recommended versioning format is:

`MAJOR.MINOR.PATCH`

Examples:

- `1.0.0` — Initial stable release.
- `1.1.0` — Minor feature or content update.
- `1.1.1` — Patch release.
- `2.0.0` — Major release.

The project MAY adopt additional version identifiers when required by its distribution platform or release model.

### 6.2. Version Changes

Under the recommended format:

- **MAJOR:** Significant changes that may introduce compatibility or migration requirements.
- **MINOR:** Backward-compatible functionality or content additions.
- **PATCH:** Backward-compatible fixes and maintenance changes.

Pre-release identifiers MAY be used for preview builds.

Examples:

- `1.0.0-alpha.1`
- `1.0.0-beta.2`
- `1.0.0-rc.1`

### 6.3. Version Consistency

The version SHOULD be consistent across:

- Project configuration.
- Build metadata.
- Release notes.
- Distribution information.
- Relevant in-game version displays.

The project MUST define its authoritative version source to avoid conflicting version information.

### 6.4. Versioning Standard

Projects SHOULD follow the studio versioning standard when available.

Platform-specific version requirements MAY require additional identifiers.

## 7. Release Branch and Source Control Management

### 7.1. Release Source

A release MUST be generated from an identifiable and stable source revision.

The project SHOULD record:

- Git commit hash.
- Source branch.
- Release tag.
- Relevant repository state.
- Build configuration.

### 7.2. Release Branches

When the branching strategy uses release branches, they SHOULD follow the established studio naming conventions.

For example:

`release/1.0.0`

Release branches SHOULD contain only changes required to stabilize and prepare the release.

### 7.3. Protected Branches

The studio branching strategy MUST be respected during release preparation.

- Protected branches MUST NOT be modified through unauthorized direct pushes.
- Pull requests and required validation MUST be followed.
- Force-pushing or rewriting shared history MUST NOT be used to prepare releases.
- Release integration MUST follow the approved branching strategy.

### 7.4. Release Tags

Published releases SHOULD have an annotated Git tag identifying the exact source revision.

Recommended format:

`vMAJOR.MINOR.PATCH`

Example:

`v1.0.0`

Release tags MUST NOT be moved or reused to identify a different release.

### 7.5. Source Integrity

The source revision used to generate the release MUST be known.

Uncommitted changes MUST NOT be silently included in an official release build.

## 8. Release Build Preparation

### 8.1. Build Configuration

Before generating a release build:

- Verify the selected Godot version.
- Verify the intended export preset.
- Verify the target platform.
- Verify release configuration.
- Verify required project settings.
- Verify required resources and plugins.
- Verify that development-only configuration is not unintentionally included.

### 8.2. Asset and Resource Validation

Validate that:

- Required assets are present.
- Resources load correctly.
- Import settings are appropriate.
- No required asset is missing.
- Fonts and localization resources are included when applicable.
- Audio and visual assets behave correctly.
- External dependencies are available and permitted.

### 8.3. Export Preparation

Release builds MUST use the appropriate export configuration.

Projects SHOULD maintain documented export presets for supported platforms.

Export settings SHOULD be reviewed when platform requirements or engine versions change.

### 8.4. Build Identification

Each release build SHOULD include enough information to identify:

- Game version.
- Build identifier.
- Target platform.
- Source revision.
- Build date, when useful.
- Build configuration.

Build identifiers MAY distinguish multiple builds generated from the same game version.

### 8.5. Build Artifacts

Release artifacts SHOULD be stored in an organized location outside temporary development output.

The project SHOULD preserve:

- Final exported packages.
- Relevant build metadata.
- Release configuration information.
- Checksums when useful.
- Supporting files required for distribution.

Generated development caches and temporary files MUST NOT be treated as release artifacts.

## 9. Release Candidate Preparation

### 9.1. Purpose

A Release Candidate (RC) is a build intended to become the final release if it passes the required validation.

### 9.2. Candidate Creation

A release candidate SHOULD:

- Be generated from a known source revision.
- Use release configuration.
- Include the intended release scope.
- Have a unique build identifier.
- Be stored as a preserved artifact.
- Be subjected to release validation.

### 9.3. Candidate Stabilization

During candidate stabilization:

- New feature development SHOULD stop.
- Changes SHOULD be limited to necessary fixes.
- Fixes MUST be reviewed and tested.
- Significant changes SHOULD trigger additional regression testing.
- The candidate MUST be regenerated when its source changes.

### 9.4. Candidate Rejection

A candidate MUST be rejected when an unresolved issue makes release unacceptable.

A new candidate SHOULD be generated after relevant fixes are integrated.

### 9.5. Candidate Approval

A candidate MAY be approved when it satisfies the release acceptance criteria and the project owner authorizes publication.

## 10. Release Validation

### 10.1. General Requirements

Every release MUST receive validation appropriate to its scope and risk.

Validation SHOULD be performed on the actual exported build whenever practical.

Testing only the editor or development environment is insufficient to establish release readiness.

### 10.2. Functional Validation

Validate:

- Application startup.
- Main menu and navigation.
- Core gameplay.
- Critical game systems.
- Player input.
- Progression.
- Inventory and resource systems, when applicable.
- Save and loading.
- Game completion and failure states.
- Important UI interactions.

### 10.3. Regression Testing

Validate that changes have not broken existing functionality.

Regression testing SHOULD prioritize:

- Modified features.
- Dependent systems.
- Critical gameplay paths.
- Previously defective functionality.
- Save compatibility.
- Shared systems.

### 10.4. Platform Validation

For each supported platform, validate relevant requirements.

Examples:

- Export and installation.
- Startup and shutdown.
- Input and controls.
- Resolution and display behavior.
- Audio output.
- File access.
- Save locations.
- Performance.
- Platform-specific integrations.

### 10.5. Performance Validation

Validate relevant performance characteristics, including:

- Frame rate.
- Frame-time consistency.
- Memory usage.
- Loading times.
- CPU and GPU utilization.
- Physics performance.
- Resource loading.
- Long-session stability.

Performance acceptance criteria SHOULD be defined by the project.

### 10.6. Data and Save Validation

When the game uses persistent data, validate:

- New save creation.
- Save loading.
- Save updates.
- Save integrity.
- Version compatibility.
- Migration behavior.
- Recovery from invalid or incomplete data, where supported.

### 10.7. Security and Privacy

Where applicable, validate:

- Sensitive data handling.
- Network communication.
- Authentication and authorization.
- External service dependencies.
- User data storage.
- Distribution of credentials or private configuration.

Secrets MUST NOT be included in public release artifacts.

### 10.8. Validation Results

Validation results MUST be recorded accurately.

Use the following statuses where applicable:

- **Passed:** Validation completed successfully.
- **Failed:** Validation identified an unacceptable result.
- **Not Run:** Validation has not been performed.
- **Not Applicable:** The validation does not apply to this release.
- **Blocked:** Validation could not be completed due to an unresolved dependency or issue.

A validation activity MUST NOT be marked as passed without evidence.

## 11. Defect Management and Release Blocking

### 11.1. Defect Evaluation

Known defects MUST be reviewed before release.

Evaluate:

- Severity.
- Frequency.
- Reproducibility.
- Affected platforms.
- Player impact.
- Workarounds.
- Risk of data loss.
- Potential consequences of leaving the defect unresolved.

### 11.2. Release-Blocking Defects

The following issues SHOULD normally block a release:

- Crashes during critical gameplay paths.
- Corrupted or lost player data.
- Unusable core gameplay.
- Broken progression that prevents meaningful completion.
- Critical security or privacy vulnerabilities.
- Severe performance problems.
- Missing required content.
- Distribution or installation failures.
- Violations of applicable legal or licensing requirements.

### 11.3. Accepted Known Issues

A release MAY proceed with known non-blocking issues when:

- Their impact is understood.
- Their severity has been evaluated.
- Appropriate workarounds exist when necessary.
- The project owner explicitly accepts the risk.
- The issues are documented.

Critical issues MUST NOT be reclassified merely to meet a release date.

## 12. Release Approval

### 12.1. Approval Authority

The project owner is responsible for approving official releases.

Other contributors MAY provide recommendations and validation results.

AI agents MAY prepare release documentation and report readiness but MUST NOT approve or publish releases independently.

### 12.2. Approval Requirements

Before approval, review:

- Release scope.
- Version information.
- Source revision.
- Build artifacts.
- Validation results.
- Open defects.
- Known limitations.
- Platform readiness.
- Required documentation.
- Licensing and attribution.
- Distribution readiness.

### 12.3. Approval Decision

The project owner SHOULD record one of the following decisions:

- **Approved:** Release is authorized.
- **Approved with Conditions:** Release is authorized subject to explicitly documented conditions.
- **Rejected:** Release is not authorized.
- **Deferred:** Additional work or validation is required before a decision.

Approval MUST be recorded before publication.

## 13. Release Publication

### 13.1. Publication Preparation

Before publishing:

- Confirm the approved build is selected.
- Confirm version and build identifiers.
- Verify package integrity.
- Prepare release notes.
- Prepare store or distribution information.
- Verify required metadata.
- Verify screenshots, trailers, and promotional assets when applicable.
- Verify credits and attributions.
- Confirm the intended distribution channel.

### 13.2. Publication

Publish the approved artifact through the intended distribution platform.

The published artifact MUST correspond to the approved release build.

Publication SHOULD follow the distribution platform's requirements and review procedures.

### 13.3. Publication Verification

After publication:

- Verify that the release is available through the intended channel.
- Verify package download or installation when practical.
- Verify startup and basic functionality.
- Verify version information.
- Confirm that the correct release notes and metadata are visible.
- Record publication problems.

### 13.4. Release Record

Record:

- Released version.
- Publication date.
- Source revision.
- Release tag.
- Build identifier.
- Target platforms.
- Distribution channels.
- Release approval.
- Relevant validation results.
- Known issues.

## 14. Release Notes

### 14.1. Purpose

Release notes communicate relevant changes and known limitations to users and stakeholders.

They SHOULD be clear, accurate, and appropriate for the intended audience.

### 14.2. Recommended Structure

Release notes SHOULD include:

- Game name.
- Version.
- Release date.
- Release type.
- Summary.
- New features.
- Improvements.
- Bug fixes.
- Known issues.
- Compatibility or save migration information, when applicable.
- Credits or acknowledgments when relevant.

### 14.3. Writing Requirements

Release notes MUST NOT:

- Claim features that are not included.
- Claim defects have been fixed without verification.
- Hide important known limitations.
- Expose confidential technical information.
- Include credentials, secrets, or sensitive user data.

Technical details SHOULD be translated into understandable language when communicating with players.

## 15. Post-release Monitoring

### 15.1. Initial Monitoring

After release, monitor for:

- Crashes.
- Installation problems.
- Critical gameplay defects.
- Save corruption.
- Performance regressions.
- Platform-specific failures.
- Distribution problems.
- Significant player feedback.

### 15.2. Issue Prioritization

Post-release issues SHOULD be evaluated based on their severity and impact.

Critical issues SHOULD receive immediate attention.

Noncritical improvements MAY be scheduled for future releases.

### 15.3. Post-release Decisions

Depending on the findings, the project owner MAY decide to:

- Continue monitoring.
- Prepare a patch.
- Prepare an urgent hotfix.
- Roll back a distribution where supported.
- Temporarily suspend distribution.
- Schedule a larger update.

The decision and its reasoning SHOULD be recorded when the impact is significant.

## 16. Hotfix Process

Hotfixes address urgent problems affecting a published release.

### 16.1. Hotfix Initiation

A hotfix SHOULD be initiated when an issue:

- Causes widespread crashes.
- Prevents critical gameplay.
- Causes player data loss or corruption.
- Introduces a serious security or privacy risk.
- Makes a platform release unusable.
- Creates another unacceptable player-impacting problem.

### 16.2. Hotfix Implementation

The hotfix SHOULD:

- Address the identified problem.
- Minimize unrelated changes.
- Follow the approved Git workflow.
- Include appropriate regression testing.
- Preserve the original release history.

### 16.3. Hotfix Validation

Validation MAY be reduced according to urgency, but MUST cover the affected functionality and relevant critical paths.

The risks associated with reduced validation MUST be understood and accepted by the project owner.

### 16.4. Hotfix Publication

The project owner MUST approve the hotfix before publication.

The hotfix MUST receive its own version or build identification.

Release records and notes MUST identify the correction.

## 17. Release Artifact Preservation

### 17.1. Artifact Retention

The project SHOULD preserve important release artifacts, including:

- Published game packages.
- Release candidate builds.
- Release metadata.
- Release notes.
- Source revision identifiers.
- Relevant build configurations.
- Validation records.
- Checksums, when used.

### 17.2. Reproducibility

The project SHOULD preserve sufficient information to reproduce a release build where practical.

This MAY include:

- Godot version.
- Export presets.
- Plugin versions.
- Build scripts.
- Required dependencies.
- Relevant environment configuration.

Sensitive credentials MUST NOT be stored in release records or public repositories.

### 17.3. Release Integrity

Published release artifacts SHOULD NOT be silently overwritten.

Corrections MUST be distributed as a new release or an explicitly documented replacement according to the distribution platform's capabilities.

## 18. Release Documentation and Records

Each significant release SHOULD have a record stored in the project repository.

Recommended location:

`game_project/docs/production/releases/`

A release record MAY include:

- Version and release type.
- Release scope.
- Release date.
- Source revision and Git tag.
- Build information.
- Target platforms.
- Validation summary.
- Known issues.
- Approval record.
- Publication information.
- Links to relevant artifacts.

Release records SHOULD be concise and should not duplicate the complete contents of existing test reports or project documentation.

## 19. AI-Assisted Release Management

AI agents MAY assist with:

- Preparing release checklists.
- Summarizing changes between versions.
- Drafting release notes.
- Reviewing version consistency.
- Identifying missing validation.
- Summarizing test results.
- Analyzing known defects.
- Preparing release records.
- Checking repository state.
- Reviewing build metadata.

AI agents MUST:

1. Use actual repository and build information.
2. Verify source revisions and version identifiers.
3. Distinguish completed validation from planned validation.
4. Report failed and blocked checks.
5. Identify unresolved release risks.
6. Follow the approved branching strategy.
7. Preserve existing release history.
8. Request approval before publication.

AI agents MUST NOT:

- Invent test results.
- Claim an artifact was published without verification.
- Change release versions without authorization.
- Modify or reuse published release tags.
- Bypass branch protection.
- Approve a release.
- Publish an official release without explicit authorization.

The project owner retains responsibility for release decisions.

## 20. Release Checklist

Use the applicable checklist before publishing a release.

### Planning

- [ ] Release objectives are defined.
- [ ] Release scope is documented.
- [ ] Target platforms are identified.
- [ ] Acceptance criteria are defined.
- [ ] Release risks are reviewed.

### Source and Version Control

- [ ] Source revision is identified.
- [ ] Repository state is appropriate.
- [ ] Required changes are integrated.
- [ ] Version number is correct.
- [ ] Release tag is prepared.
- [ ] Protected branch rules are respected.

### Build Preparation

- [ ] Correct Godot version is used.
- [ ] Export configuration is verified.
- [ ] Required assets and resources are included.
- [ ] Build configuration is correct.
- [ ] Build identifier is recorded.
- [ ] Release artifact is preserved.

### Validation

- [ ] Startup and installation are validated.
- [ ] Critical gameplay paths are tested.
- [ ] Regression testing is completed.
- [ ] Save and loading behavior is validated.
- [ ] Platform requirements are checked.
- [ ] Performance is evaluated.
- [ ] Known defects are reviewed.
- [ ] Validation results are recorded.

### Approval

- [ ] Release documentation is prepared.
- [ ] Release notes are reviewed.
- [ ] Credits and attributions are verified.
- [ ] Known limitations are documented.
- [ ] Release readiness is evaluated.
- [ ] Project owner approval is recorded.

### Publication

- [ ] Approved artifact is published.
- [ ] Published version is verified.
- [ ] Installation or download is checked where practical.
- [ ] Release notes and metadata are available.
- [ ] Publication information is recorded.

### Post-release

- [ ] Initial release monitoring is performed.
- [ ] Reported critical issues are evaluated.
- [ ] Release artifacts are preserved.
- [ ] Release records are updated.

## 21. Exceptions

Projects MAY simplify or adapt the release process according to:

- Project size.
- Release type.
- Distribution platform.
- Development model.
- Technical constraints.
- Release urgency.

Exceptions MUST NOT eliminate necessary safeguards for data integrity, legal compliance, release authorization, or critical quality risks.

Significant exceptions SHOULD be documented with their justification and accepted risks.

## 22. Related Documents

- `docs/00_studio_standards/BRANCHING_STRATEGY.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/00_studio_standards/GAME_DEVELOPMENT_LIFECYCLE.md`
- `docs/02_technical_standards/ENGINE_STANDARDS.md`
- `docs/02_technical_standards/ASSET_PIPELINE.md`
- `docs/02_technical_standards/TESTING_STRATEGY.md`
- `docs/04_production_standards/PROJECT_LIFECYCLE.md`
- `docs/04_production_standards/MILESTONE_GUIDELINES.md`
- `docs/04_production_standards/POSTMORTEM_GUIDELINES.md`

## 23. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- Release workflows change.
- New distribution platforms are adopted.
- Build and validation processes evolve.
- Recurring release problems reveal process improvements.
- New tools or automation materially affect release management.

Changes MUST preserve the distinction between reusable studio release practices and project-specific release configurations.

The project owner is responsible for approving changes to these guidelines.