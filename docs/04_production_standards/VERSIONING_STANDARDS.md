# Versioning Standards

## 1. Purpose

This document defines the versioning conventions used to identify, track, and manage game projects and their releases.

It establishes standards for:

- Game version numbers.
- Semantic versioning.
- Pre-release versions.
- Development and build identifiers.
- Version control tags.
- Version changes and compatibility.
- Save data and serialization versions.
- Internal component versioning.
- Version documentation and traceability.
- AI-assisted version management.

The objective is to maintain consistent version identification, communicate changes clearly, preserve release history, and support reliable development and distribution.

## 2. Scope

These standards apply to all game projects developed within the studio.

They cover:

- Official game releases.
- Early Access and preview releases.
- Alpha, Beta, and Release Candidate builds.
- Development builds.
- Hotfixes and patches.
- Save data formats.
- Persistent data schemas.
- Custom content formats.
- Versioned project components and tools.

Projects MAY introduce additional version identifiers when required by their architecture, distribution platform, or technical dependencies.

These standards distinguish between the version of the game, the identity of a particular build, and the versions of data formats used by the game.

## 3. Versioning Principles

### 3.1. Consistency

Projects MUST use consistent version formats and naming conventions.

The same release MUST NOT be identified by conflicting version numbers across its release records and distribution information.

### 3.2. Traceability

Every official release MUST be traceable to its source revision and build information.

Development builds SHOULD also provide enough information to identify their origin when practical.

### 3.3. Historical Integrity

Published version identifiers MUST NOT be reused to identify different releases.

Existing release tags and historical records MUST be preserved.

### 3.4. Clear Compatibility

Version changes SHOULD communicate the significance of changes and potential compatibility implications.

Breaking changes to persistent data formats MUST be handled explicitly.

### 3.5. Appropriate Granularity

Versioning SHOULD be as simple as possible while providing sufficient information.

Do not introduce unnecessary version identifiers for components that do not require independent version tracking.

### 3.6. Automated Consistency

Where practical, version information SHOULD be maintained in one authoritative location and propagated to relevant build metadata, release notes, and in-game displays.

## 4. Game Versioning

### 4.1. Recommended Format

The studio uses Semantic Versioning as the default convention for stable game releases.

Format:

`MAJOR.MINOR.PATCH`

Example:

`1.4.2`

The components represent:

| Component | Meaning |
|---|---|
| MAJOR | Significant changes or compatibility implications |
| MINOR | New functionality or content that does not require a major version change |
| PATCH | Bug fixes and maintenance changes |

### 4.2. MAJOR Version

Increment the MAJOR version when a release introduces substantial changes to the product or compatibility expectations.

Examples:

- Major gameplay or progression redesigns.
- Significant changes to core systems.
- Breaking changes to supported persistent data formats.
- Major product revisions.
- Changes that require users to adapt to a substantially different version.

A MAJOR increment resets MINOR and PATCH to zero.

Example:

`1.8.4 → 2.0.0`

A major version change does not necessarily mean that every project system has been rewritten.

### 4.3. MINOR Version

Increment the MINOR version when adding meaningful functionality or content without requiring a major version change.

Examples:

- New gameplay features.
- Additional levels or areas.
- New character abilities.
- Additional game modes.
- Significant usability improvements.
- Non-breaking system enhancements.

A MINOR increment resets PATCH to zero.

Example:

`1.3.4 → 1.4.0`

### 4.4. PATCH Version

Increment the PATCH version for fixes and maintenance changes that do not introduce a significant new feature or require a major compatibility change.

Examples:

- Bug fixes.
- Stability improvements.
- Minor performance improvements.
- Small UI corrections.
- Compatibility fixes.
- Minor balancing adjustments.

Example:

`1.4.2 → 1.4.3`

### 4.5. Initial Version

The first stable public release SHOULD use:

`1.0.0`

Projects MAY use pre-release identifiers before the first stable release.

An initial public release MUST NOT be labeled `1.0.0` merely because development has reached a particular milestone. It should represent a deliberate stable release.

## 5. Pre-release Versioning

### 5.1. Purpose

Pre-release identifiers distinguish versions that are not yet considered stable releases.

They MAY be used for:

- Alpha releases.
- Beta releases.
- Release Candidates.
- Preview builds.
- Experimental public releases.

### 5.2. Format

Use Semantic Versioning pre-release identifiers:

`MAJOR.MINOR.PATCH-IDENTIFIER`

Examples:

- `0.1.0-alpha.1`
- `0.1.0-alpha.2`
- `0.8.0-beta.1`
- `1.0.0-rc.1`
- `1.0.0-rc.2`

### 5.3. Alpha Versions

Alpha versions represent early or incomplete development builds.

Examples:

- `0.1.0-alpha.1`
- `0.5.0-alpha.3`

Alpha releases MAY contain:

- Incomplete gameplay systems.
- Placeholder assets.
- Missing content.
- Known defects.
- Unbalanced mechanics.
- Experimental functionality.

Their limitations SHOULD be communicated clearly.

### 5.4. Beta Versions

Beta versions represent more complete builds intended for broader testing and stabilization.

Examples:

- `0.8.0-beta.1`
- `0.9.0-beta.2`

Beta versions SHOULD contain substantially complete gameplay functionality and content appropriate to the testing objectives.

### 5.5. Release Candidates

A Release Candidate is a build intended to become the final release if no release-blocking problems are discovered.

Examples:

- `1.0.0-rc.1`
- `1.0.0-rc.2`

If a candidate requires a significant correction, generate a new candidate identifier.

When the candidate is approved without requiring further changes, the final release MAY use the corresponding stable version:

`1.0.0-rc.2 → 1.0.0`

### 5.6. Pre-release Ordering

Pre-release versions MUST follow Semantic Versioning ordering rules.

For example:

`1.0.0-alpha.1 < 1.0.0-beta.1 < 1.0.0-rc.1 < 1.0.0`

Once a stable release is published, its version MUST NOT be reused for another build containing different changes.

## 6. Development Versioning

### 6.1. Purpose

Development versions identify builds produced during active development that are not official releases.

They MAY be used for:

- Internal testing.
- Automated builds.
- Continuous integration.
- Feature validation.
- Prototype distribution.
- Team testing.

### 6.2. Recommended Format

Development builds SHOULD use the next intended release version with a development pre-release identifier.

Examples:

- `0.2.0-dev.15`
- `0.8.0-dev.42`
- `1.1.0-dev.7`

The numeric suffix MAY represent a development build sequence.

### 6.3. Build Metadata

Semantic Versioning supports build metadata using a plus sign.

Example:

`1.1.0-dev.7+build.142`

Build metadata MAY identify:

- CI build number.
- Pipeline execution.
- Source revision.
- Internal build information.

Build metadata does not affect Semantic Versioning precedence.

### 6.4. Development Build Requirements

Development builds SHOULD expose enough information to identify:

- Game version.
- Build identifier.
- Source revision.
- Build configuration.
- Target platform.

Development identifiers MUST NOT be confused with official release versions.

## 7. Build Identification

### 7.1. Game Version Versus Build Number

The game version identifies the release or development version.

The build number identifies a particular generated build.

Multiple builds MAY share the same game version when they represent different build attempts or platform exports.

Example:

| Game Version | Build Number | Description |
|---|---|---|
| 1.0.0-rc.1 | 101 | First Release Candidate build |
| 1.0.0-rc.1 | 102 | Rebuilt candidate |
| 1.0.0 | 103 | Approved stable release |

### 7.2. Build Number Format

Projects MAY use an incrementing integer for build identification.

Example:

`BUILD-00142`

Automated pipelines SHOULD generate build numbers when supported.

Build numbers MUST NOT be treated as replacements for game version numbers.

### 7.3. Source Revision

Every official release MUST record the Git commit hash from which it was built.

Development builds SHOULD record the source revision when practical.

The source revision provides stronger traceability than a build number alone.

### 7.4. Platform Builds

Different platform exports MAY share the same game version when they represent the same release.

Example:

- `1.0.0` Windows build.
- `1.0.0` Linux build.
- `1.0.0` macOS build.

Platform-specific build identifiers MAY distinguish individual artifacts.

Platform-specific changes that materially affect functionality SHOULD be documented and evaluated separately.

## 8. Git Tags and Release Identification

### 8.1. Release Tags

Every official release SHOULD have a Git tag.

Recommended format:

`vMAJOR.MINOR.PATCH`

Examples:

- `v1.0.0`
- `v1.1.0`
- `v1.1.1`
- `v2.0.0`

### 8.2. Pre-release Tags

Pre-release versions SHOULD use matching tags.

Examples:

- `v1.0.0-alpha.1`
- `v1.0.0-beta.1`
- `v1.0.0-rc.1`

### 8.3. Annotated Tags

Release tags SHOULD be annotated to preserve useful metadata.

A release tag SHOULD include:

- Version.
- Release description.
- Release date.
- Relevant release information.

### 8.4. Tag Immutability

Published release tags MUST NOT be moved, deleted, or reused to identify a different release.

Corrections MUST receive a new version and tag.

### 8.5. Tag Creation

Release tags MUST be created according to the approved branching strategy and release process.

Only authorized contributors or automation MAY create official release tags.

AI agents MUST NOT independently tag or publish official releases without explicit authorization.

## 9. Version Source of Truth

### 9.1. Authoritative Version

Each project MUST define a single authoritative source for its game version.

The selected source SHOULD be easy to maintain and accessible to the build process.

Possible approaches include:

- A version constant in project configuration.
- A dedicated version configuration file.
- A build-time version variable.
- A version field maintained by the release pipeline.

The project SHOULD avoid maintaining independent manually updated version values in multiple locations.

### 9.2. Godot Integration

Godot projects MAY use the `config/version` property in `project.godot` as the authoritative game version.

Example:

```ini
[application]

config/name="Game Name"
config/version="1.0.0"
```

Projects MAY expose the version through a dedicated configuration or autoload when required.

Example:

```gdscript
extends Node

const GAME_VERSION: String = "1.0.0"
```

When using a dedicated version source, the project SHOULD automate synchronization with build metadata and other required locations.

### 9.3. Version Display

The game SHOULD display its version in an appropriate location when useful.

Possible locations include:

- Main menu.
- Settings screen.
- Debug information.
- Development overlay.
- Error reports.

Development builds SHOULD make their non-release status clear when distributed internally or to testers.

### 9.4. Version Consistency

Before release, verify that:

- Project configuration contains the correct version.
- Build metadata identifies the correct version.
- Release notes use the correct version.
- Git tags match the release version.
- Distribution metadata is consistent.

Conflicting version information MUST be resolved before publication.

## 10. Save Data and Schema Versioning

Game versioning and persistent data versioning serve different purposes.

A game release version identifies the product release.

A save data version identifies the structure and format of persisted data.

These versions MUST NOT be treated as interchangeable.

### 10.1. Save Data Version

Projects using persistent save data SHOULD maintain an explicit save format version.

Example:

```json
{
  "save_version": 2,
  "player": {},
  "inventory": {},
  "world": {}
}
```

The save version SHOULD change when the serialized data structure or interpretation changes in a way that requires migration or compatibility handling.

### 10.2. Save Version Changes

Increment the save version when changes affect compatibility.

Examples:

- Renaming serialized fields.
- Changing data types.
- Restructuring nested objects.
- Introducing required fields.
- Changing identifier formats.
- Removing fields needed by previous versions.

A save version does not need to change for every game release.

### 10.3. Migration

When a game supports loading older save formats, it MUST define how those formats are handled.

Migration logic SHOULD:

- Identify the source save version.
- Apply the required transformations.
- Validate the resulting data.
- Preserve player data whenever practical.
- Handle unsupported versions safely.
- Avoid silently overwriting the original save during an unsuccessful migration.

### 10.4. Unsupported Save Versions

The game MUST handle unsupported save versions deliberately.

Possible responses include:

- Rejecting the save with a clear error.
- Offering a recovery or backup option.
- Providing a supported migration path.
- Informing the player that the save was created by an incompatible version.

The game MUST NOT silently interpret incompatible data as valid.

### 10.5. Schema Versioning

Other persistent data structures MAY have independent schema versions when necessary.

Examples:

- Player profile format.
- World state format.
- Configuration format.
- Custom content format.
- Mod data format.

Independent schema versions SHOULD only be introduced when they provide meaningful compatibility or migration benefits.

## 11. Component and Dependency Versioning

### 11.1. Internal Components

Internal game systems SHOULD NOT receive independent version numbers by default.

A component version MAY be useful when it:

- Is independently distributed.
- Has a stable external interface.
- Is reused across multiple projects.
- Has independent compatibility requirements.
- Requires independent release management.

Avoid unnecessary versioning of ordinary scripts, scenes, and resources.

### 11.2. Plugins and External Dependencies

Projects MUST track relevant external dependencies.

Depending on the dependency, record:

- Name.
- Version.
- Source.
- License.
- Compatibility requirements.
- Upgrade considerations.

Dependency versions SHOULD be pinned or constrained when necessary to preserve reproducible builds.

### 11.3. Godot Engine Version

Each project MUST define its intended Godot engine version.

Engine upgrades SHOULD be treated as controlled technical changes.

Before upgrading, evaluate:

- API compatibility.
- Project configuration changes.
- Plugin compatibility.
- Resource and scene compatibility.
- Rendering differences.
- Physics behavior.
- Export behavior.
- Performance impact.

Engine version changes SHOULD be documented when they materially affect the project.

### 11.4. Plugin and Tool Upgrades

External plugin and tool upgrades SHOULD be evaluated before integration.

Significant upgrades SHOULD include appropriate testing and rollback considerations.

Projects SHOULD avoid upgrading dependencies without a clear reason.

## 12. Version Compatibility

### 12.1. Compatibility Policy

Each project SHOULD define its compatibility expectations for:

- Save files.
- Configuration data.
- User-generated content.
- Mods, when supported.
- Network protocols, when applicable.
- External integrations.

### 12.2. Breaking Changes

Breaking changes MUST be identified before release.

When a breaking change affects player data or external integrations, the project SHOULD define:

- Affected versions.
- Expected consequences.
- Migration requirements.
- Recovery options.
- User communication requirements.

### 12.3. Backward Compatibility

Backward compatibility SHOULD be preserved when it provides meaningful value to players or other consumers of the project's data.

It is not necessary to preserve every historical format indefinitely.

Compatibility decisions SHOULD consider project scope, technical complexity, and player impact.

### 12.4. Forward Compatibility

Projects SHOULD NOT assume that older game versions can safely interpret data produced by newer versions.

When forward compatibility is not supported, the game SHOULD communicate this clearly.

## 13. Version Changes and Release Management

### 13.1. Version Assignment

The version for a planned release SHOULD be determined during release planning.

The selected version MUST reflect the actual scope and compatibility implications of the changes.

### 13.2. Version Increment Decisions

Before assigning a new version, evaluate:

- Changes since the previous release.
- New functionality.
- Bug fixes.
- Compatibility implications.
- Persistent data changes.
- Distribution requirements.

### 13.3. Rejected Release Candidates

If a Release Candidate is rejected:

- The candidate version MAY remain unchanged while the same candidate is rebuilt only when the project explicitly tracks candidates by separate build identifiers.
- If a new candidate iteration is issued, increment its pre-release identifier.

Example:

`1.0.0-rc.1 → 1.0.0-rc.2`

### 13.4. Hotfixes

Hotfixes SHOULD increment the PATCH component when they correct an already released version without introducing a major or minor release.

Example:

`1.2.0 → 1.2.1`

Urgent hotfixes MUST still receive unique version identification.

### 13.5. Release Corrections

A published release MUST NOT be silently replaced under the same version identifier.

If a published package must be corrected, issue a new version or follow the distribution platform's explicitly documented replacement mechanism while preserving release traceability.

## 14. Version Documentation

Each project SHOULD maintain release history and version information.

Recommended locations include:

- `CHANGELOG.md` at the project root, once the project maintains one.
- `game_project/docs/production/releases/` for detailed release records.
- Project configuration for the authoritative game version.
- Version control tags for source revision identification.

### 14.1. Changelog

A changelog SHOULD summarize meaningful changes between releases.

Recommended categories include:

- Added.
- Changed.
- Fixed.
- Removed.
- Deprecated.
- Security.

Example:

```markdown
# Changelog

## [1.1.0] - YYYY-MM-DD

### Added
- New inventory sorting functionality.

### Changed
- Improved player movement responsiveness.

### Fixed
- Fixed an issue preventing item pickup in certain situations.

## [1.0.0] - YYYY-MM-DD

### Added
- Initial stable release.
```

The changelog SHOULD focus on meaningful changes rather than reproducing every commit message.

### 14.2. Release Records

Each significant release SHOULD have a release record containing:

- Version.
- Release date.
- Release type.
- Source revision.
- Git tag.
- Build identifiers.
- Target platforms.
- Summary of changes.
- Compatibility notes.
- Known issues.

Detailed publication and approval procedures are defined in the release process.

## 15. Versioning Checklist

Use this checklist when preparing a release or changing version information.

### Game Version

- [ ] Version follows the approved format.
- [ ] Version increment reflects the scope of changes.
- [ ] Pre-release identifiers are used when appropriate.
- [ ] Version is unique.

### Build Identification

- [ ] Build identifier is available.
- [ ] Source revision is recorded.
- [ ] Target platform is identified.
- [ ] Build metadata is consistent.

### Git

- [ ] Release tag follows the naming convention.
- [ ] Tag references the correct source revision.
- [ ] Existing release tags remain unchanged.
- [ ] Branching rules are respected.

### Compatibility

- [ ] Save data changes have been evaluated.
- [ ] Required schema versions are updated.
- [ ] Migration requirements are understood.
- [ ] Breaking changes are documented.
- [ ] Compatibility has been tested where applicable.

### Documentation

- [ ] Changelog is updated.
- [ ] Release record is prepared.
- [ ] Version information is consistent across project artifacts.
- [ ] Known compatibility limitations are documented.

## 16. AI-Assisted Version Management

AI agents MAY assist with:

- Proposing version increments.
- Reviewing changes between releases.
- Drafting changelog entries.
- Checking version consistency.
- Identifying compatibility implications.
- Reviewing save data migrations.
- Verifying release metadata.
- Preparing version documentation.

AI agents MUST:

1. Inspect actual project and repository state.
2. Follow the established versioning convention.
3. Distinguish game versions from build identifiers and data schema versions.
4. Identify potential breaking changes.
5. Preserve release history.
6. Report uncertainty.
7. Request approval for official version changes when required.
8. Verify version consistency before reporting completion.

AI agents MUST NOT:

- Invent release history.
- Reuse published version identifiers.
- Move or overwrite existing release tags.
- Change persistent data versions without reviewing migration implications.
- Publish official releases without authorization.
- Claim compatibility without validation.
- Independently redefine the project's versioning strategy.

The project owner retains responsibility for approving official release versions and compatibility decisions.

## 17. Exceptions

Projects MAY introduce alternative versioning schemes when required by:

- Distribution platforms.
- Early Access programs.
- Platform-specific requirements.
- External integration contracts.
- Existing project compatibility requirements.
- Specialized product release models.

Exceptions SHOULD be documented in the project repository.

Projects MUST preserve sufficient version information to identify releases and maintain traceability.

Changes to studio-wide versioning conventions require project owner approval.

## 18. Related Documents

- `docs/00_studio_standards/BRANCHING_STRATEGY.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md`
- `docs/02_technical_standards/ENGINE_STANDARDS.md`
- `docs/02_technical_standards/RESOURCE_MANAGEMENT.md`
- `docs/04_production_standards/PROJECT_LIFECYCLE.md`
- `docs/04_production_standards/RELEASE_PROCESS.md`
- `docs/04_production_standards/RISK_MANAGEMENT.md`

## 19. Maintenance

These standards SHOULD be reviewed periodically and updated when:

- Versioning requirements change.
- New distribution platforms are adopted.
- Save data compatibility requirements evolve.
- Build and release automation changes.
- New project dependencies introduce versioning requirements.
- Recurring versioning problems reveal process improvements.

Changes MUST preserve the distinction between reusable studio versioning conventions and project-specific versioning decisions.

The project owner is responsible for approving changes to these standards.