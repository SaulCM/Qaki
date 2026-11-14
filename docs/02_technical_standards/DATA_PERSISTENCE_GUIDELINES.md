# Data Persistence Guidelines

## 1. Purpose

This document establishes reusable technical guidelines for designing, implementing, validating, and maintaining data persistence systems across studio Godot projects.

Its purpose is to ensure that game data can be stored, retrieved, validated, and maintained reliably throughout the lifecycle of a game.

These guidelines establish expectations for:

- Persistent and transient data management.
- Save system architecture.
- Data serialization and deserialization.
- Save file organization.
- Data validation and integrity.
- Save compatibility and migration.
- Error handling and recovery.
- Data security and privacy.
- Testing and verification.

The objective is to provide reliable persistence mechanisms without introducing unnecessary architectural complexity.

## 2. Scope

These guidelines apply to:

- Player progress.
- Game settings and preferences.
- Inventory and equipment.
- Character progression.
- Quest and mission state.
- World and environment state.
- Unlockable content.
- Achievements and statistics.
- Checkpoints.
- Session recovery.
- Other data that must survive application or session termination.

These guidelines primarily target Godot projects implemented in GDScript.

Project-specific persistence requirements MAY introduce additional constraints based on gameplay, platform capabilities, and distribution requirements.

## 3. Data Persistence Principles

### 3.1 Explicit Persistence Requirements

Every system SHOULD define which data must persist and which data is temporary.

Developers SHOULD distinguish between:

- Persistent data: information that must survive application restarts or session changes.
- Session data: information that must survive scene transitions or remain available during the current session.
- Transient data: temporary information that can be discarded without affecting persistent progress.

Data MUST NOT be persisted simply because it exists in memory.

### 3.2 Clear Data Ownership

Every persistent data element MUST have a clearly identifiable owner.

The owning system SHOULD be responsible for:

- Defining the data structure.
- Validating modifications.
- Maintaining valid state.
- Exposing appropriate access.
- Defining persistence requirements.
- Handling data restoration.

Multiple systems SHOULD NOT independently modify the same persistent data without an explicit ownership and coordination model.

### 3.3 Reliability

Persistence operations SHOULD protect against incomplete, invalid, or corrupted data.

Developers SHOULD:

- Validate data before saving.
- Validate data after loading.
- Handle expected failures explicitly.
- Avoid assuming that files always exist or are valid.
- Preserve recoverable data when possible.
- Avoid reporting successful operations before confirming their completion.

### 3.4 Simplicity

Persistence architecture SHOULD remain proportional to project requirements.

Developers SHOULD:

- Prefer straightforward serialization mechanisms.
- Avoid unnecessary database systems.
- Avoid excessive abstraction layers.
- Introduce complex recovery mechanisms only when justified.
- Keep save formats understandable and maintainable.

### 3.5 Reproducibility and Compatibility

Persistent data structures SHOULD be documented and versioned when necessary.

Changes to save formats SHOULD be deliberate and validated to prevent older saves from becoming unusable without an appropriate migration or compatibility strategy.

## 4. Data Classification

### 4.1 Persistent Data

Persistent data represents information that must survive application restarts.

Examples include:

- Player progression.
- Inventory contents.
- Completed quests.
- Unlocked abilities.
- World changes.
- Settings and preferences.
- Achievements.
- Long-term statistics.

Persistent data MUST have an explicit storage and restoration strategy.

### 4.2 Session Data

Session data remains available during a gameplay session but does not necessarily need to survive application termination.

Examples include:

- Current combat state.
- Temporary encounter information.
- Scene transition parameters.
- Runtime references.
- Temporary interaction state.

Session data SHOULD be owned by the appropriate gameplay system or session coordinator.

### 4.3 Transient Data

Transient data is temporary information that can be reconstructed or discarded.

Examples include:

- UI animation progress.
- Temporary visual effects.
- Particle state.
- Hover state.
- Temporary input state.
- Nonessential runtime caches.

Transient data SHOULD NOT be included in save files unless a specific gameplay requirement justifies it.

### 4.4 Derived Data

Derived data can be reconstructed from other authoritative data.

Examples include:

- Calculated character statistics.
- Inventory weight totals.
- Cached navigation information.
- UI presentation values.
- Derived progression summaries.

Derived data SHOULD generally be recalculated after loading rather than persisted independently.

Persisting derived data MAY be appropriate when recalculation is expensive and consistency can be guaranteed.

## 5. Persistence Architecture

### 5.1 Separation of Responsibilities

Persistence responsibilities SHOULD be separated from gameplay logic when doing so improves maintainability.

A persistence architecture MAY include:

- Data models or data containers.
- Serialization and deserialization logic.
- Save and load coordination.
- Storage access.
- Validation.
- Migration handling.

These responsibilities MAY be implemented in separate components or combined when the project is sufficiently simple.

Developers MUST avoid coupling unrelated gameplay systems directly to low-level file operations.

### 5.2 Save System Ownership

Each project SHOULD have a clearly defined owner for save operations.

The save system SHOULD be responsible for coordinating:

- Save requests.
- Data collection.
- Serialization.
- Storage operations.
- Loading.
- Validation.
- Migration.
- Error reporting.

Individual features SHOULD expose the persistent information they own through defined interfaces or data structures.

The save system SHOULD NOT become the owner of every gameplay rule or feature's internal runtime state.

### 5.3 Feature-Owned Data

Persistent data SHOULD remain associated with the feature that owns it.

Examples:

- Inventory data belongs to the inventory feature.
- Quest progress belongs to the quest feature.
- Character progression belongs to the progression or character feature.
- Audio preferences belong to the relevant settings system.

A central save coordinator MAY aggregate feature-owned data into a save structure without taking ownership of each feature's internal behavior.

### 5.4 Autoload Considerations

A save coordinator MAY be implemented as an autoload when project-wide availability and lifecycle requirements justify it.

Before introducing a global save service, developers SHOULD evaluate whether a scene-owned or explicitly injected component is more appropriate.

A save autoload SHOULD:

- Have a focused responsibility.
- Expose a clear interface.
- Avoid containing unrelated gameplay logic.
- Avoid becoming an uncontrolled global state container.
- Handle save and load failures explicitly.

## 6. Save Data Design

### 6.1 Data Structures

Persistent data SHOULD use explicit and understandable data structures.

Developers SHOULD:

- Use consistent field names.
- Define expected data types.
- Establish sensible default values.
- Separate configuration from runtime state.
- Avoid unnecessary references to live scene nodes.
- Avoid storing engine objects when a stable data representation is sufficient.

Save structures SHOULD represent the information necessary to restore gameplay, not the entire runtime object hierarchy.

### 6.2 Stable Identifiers

Persistent references SHOULD use stable identifiers rather than relying exclusively on runtime object references or scene hierarchy paths.

Examples include:

- Item identifiers.
- Character identifiers.
- Quest identifiers.
- Level identifiers.
- World object identifiers.
- Unlockable content identifiers.

Identifiers SHOULD remain stable across ordinary content updates.

Renaming or replacing content SHOULD account for existing saved references.

### 6.3 Defaults

Every persistent data structure SHOULD define appropriate default values.

Loading logic SHOULD handle:

- Missing optional fields.
- Newly introduced fields.
- Missing settings.
- Invalid or unsupported values.

Defaults MUST NOT silently overwrite valid existing progress.

### 6.4 Data Validation

Persistent data MUST be validated before being applied to runtime systems.

Validation SHOULD check:

- Required fields.
- Data types.
- Value ranges.
- Identifier validity.
- Referential integrity.
- Expected collection sizes.
- Supported version.
- Consistency between related values.

Invalid data SHOULD be rejected, normalized, or recovered according to an explicit strategy.

Developers MUST NOT blindly trust serialized data.

## 7. Serialization and Deserialization

### 7.1 Serialization

Serialization converts runtime or model data into a format suitable for storage.

Serialization logic SHOULD:

- Produce predictable output.
- Preserve required information.
- Exclude unnecessary runtime references.
- Handle unsupported values explicitly.
- Use stable data representations.
- Include version information when appropriate.

The serialized representation SHOULD remain independent of incidental scene hierarchy or node lifecycle details.

### 7.2 Deserialization

Deserialization reconstructs application data from stored information.

Deserialization logic MUST:

- Validate the stored representation.
- Verify required fields and types.
- Handle missing or invalid values.
- Check compatibility.
- Avoid partially applying invalid data.
- Report relevant failures.

Data SHOULD be validated before being applied to gameplay systems.

### 7.3 Godot Serialization Options

Godot provides several mechanisms for storing and serializing data.

The appropriate mechanism SHOULD be selected according to data requirements.

Common options include:

| Mechanism | Appropriate use |
|---|---|
| JSON | Human-readable structured data, settings, and simple save formats |
| ConfigFile | Configuration and user preferences |
| ResourceSaver / ResourceLoader | Godot Resource serialization and loading |
| FileAccess | Direct file operations and custom formats |
| Binary serialization | Compact or specialized data formats when justified |

Developers SHOULD prefer the simplest suitable mechanism.

The selected mechanism MUST be compatible with the project's Godot version and target platforms.

### 7.4 JSON

JSON MAY be used for structured save data when readability, debugging, and portability are important.

Developers SHOULD:

- Use consistent field names.
- Validate parsed values.
- Handle missing fields.
- Avoid assuming that parsed JSON has the expected structure.
- Avoid storing unsupported runtime objects directly.
- Consider file size and parsing costs for large datasets.

JSON MUST NOT be treated as inherently secure or tamper-proof.

### 7.5 ConfigFile

Godot's `ConfigFile` SHOULD be considered for settings and simple configuration data.

Examples include:

- Audio preferences.
- Display settings.
- Input preferences.
- Accessibility options.
- Other user-configurable preferences.

Developers SHOULD avoid using configuration files as a substitute for a structured gameplay save system when the data model becomes complex.

### 7.6 Godot Resources

Godot Resources MAY be used to represent persistent data when their serialization behavior and lifecycle are appropriate.

Developers MUST understand Resource sharing and mutation behavior.

Runtime state SHOULD NOT unintentionally modify shared configuration resources.

When a resource represents persistent runtime state, its ownership, serialization requirements, and compatibility expectations MUST be explicit.

## 8. Save File Management

### 8.1 Storage Location

Save data MUST be stored in an appropriate writable location provided by the target platform.

For Godot projects, `user://` SHOULD be used for user-generated persistent data unless platform-specific requirements justify another supported location.

Developers MUST NOT assume that the project's installation directory is writable.

### 8.2 Save Organization

Save files SHOULD follow a consistent and documented structure.

Depending on project requirements, storage MAY include:

- Main save files.
- Backup files.
- User settings.
- Profile metadata.
- Checkpoint data.
- Temporary save files.

The structure SHOULD remain simple and understandable.

### 8.3 Multiple Save Slots

Multiple save slots MAY be supported when required by the game design.

Each slot SHOULD have a stable identifier and clearly defined metadata.

Slot metadata MAY include:

- Save identifier.
- Save format version.
- Creation timestamp.
- Last modified timestamp.
- Player or profile identifier.
- Playtime.
- Current level or location.
- Preview information.

Metadata SHOULD NOT be treated as authoritative gameplay data unless explicitly designed for that purpose.

### 8.4 File Naming

Save files SHOULD use predictable and consistent names.

File names SHOULD:

- Avoid ambiguous naming.
- Use stable identifiers.
- Avoid exposing sensitive information.
- Follow project naming conventions.
- Support multiple slots when necessary.

### 8.5 File Access

File operations MUST handle expected errors.

Developers SHOULD verify:

- Whether a file exists.
- Whether the file can be opened.
- Whether writing succeeded.
- Whether reading succeeded.
- Whether parsed content is valid.
- Whether the destination has sufficient storage where the platform exposes this information.

File operations SHOULD NOT silently fail.

## 9. Save Operations and Data Integrity

### 9.1 Save Triggers

Save operations MAY be triggered by:

- Explicit player actions.
- Checkpoints.
- Scene transitions.
- Important progression events.
- Autosave intervals.
- Application lifecycle events.

Save triggers SHOULD be defined according to the intended gameplay experience.

Developers SHOULD avoid unnecessary repeated writes.

### 9.2 Autosave

Autosave SHOULD provide a reliable way to preserve progress without disrupting gameplay.

Developers SHOULD define:

- When autosaving occurs.
- Which data is included.
- Whether player interaction is interrupted.
- How save failures are communicated.
- Whether previous valid saves are preserved.

Autosave frequency SHOULD balance player convenience, storage operations, and performance.

### 9.3 Atomic Save Strategy

Important save operations SHOULD minimize the risk of destroying the previous valid save when a write fails.

A safer strategy MAY include:

1. Serialize the data.
2. Write it to a temporary file.
3. Verify that the write succeeded.
4. Preserve the existing valid save.
5. Replace the destination with the new save.
6. Verify the resulting file when appropriate.

The exact implementation SHOULD account for the guarantees and limitations of the target platform and filesystem.

A temporary file strategy MUST NOT be described as fully atomic unless the underlying replacement operation actually provides that guarantee.

### 9.4 Backup Strategy

Backup mechanisms SHOULD be introduced according to the value and recoverability of player progress.

Possible strategies include:

- Previous-save backup.
- Rotating backups.
- Checkpoint backups.
- Profile-level backups.

Backup policies SHOULD define:

- When backups are created.
- How many are retained.
- How backups are validated.
- When backups can be restored.
- How storage usage is controlled.

### 9.5 Data Integrity

Save systems SHOULD detect invalid or incomplete data when practical.

Possible mechanisms include:

- Structural validation.
- Version validation.
- Checksums.
- File size checks.
- Consistency checks.

Checksums MAY detect accidental corruption but MUST NOT be considered a complete protection against intentional modification.

### 9.6 Save Failure Handling

Save failures MUST be handled explicitly.

Possible causes include:

- Insufficient storage.
- Permission errors.
- Invalid paths.
- Serialization errors.
- Interrupted writes.
- Corrupted data.
- Unsupported save versions.

The system SHOULD:

- Preserve existing valid data when possible.
- Report the failure appropriately.
- Provide useful diagnostic information.
- Avoid falsely reporting success.
- Allow recovery when a safe recovery path exists.

## 10. Loading and Restoration

### 10.1 Loading Sequence

Loading SHOULD follow a controlled sequence:

1. Identify the requested save.
2. Check whether the save exists.
3. Read the stored data.
4. Parse or deserialize the content.
5. Validate the structure.
6. Verify compatibility.
7. Apply required migrations.
8. Construct or restore runtime state.
9. Validate restored gameplay state.
10. Continue the game.

The sequence MAY be adapted to project requirements but MUST prevent invalid data from being applied blindly.

### 10.2 Restoration Order

Dependencies between restored systems SHOULD be considered.

Systems SHOULD be restored in an order that respects their dependencies.

For example:

- Global configuration may need to be loaded before gameplay initialization.
- Player identity may need to be restored before inventory.
- World state may need to be initialized before restoring modified objects.
- UI state may need to be reconstructed after gameplay data is restored.

Restoration order SHOULD be explicit when initialization dependencies exist.

### 10.3 Missing or Invalid Saves

The game MUST define appropriate behavior when:

- No save exists.
- A save cannot be opened.
- A save is corrupted.
- A save contains unsupported data.
- Required content is missing.
- Restoration fails.

A new game SHOULD NOT accidentally overwrite an existing valid save because loading failed.

### 10.4 Partial Restoration

Partial restoration SHOULD be avoided when it could leave the game in an inconsistent state.

When partial recovery is supported, the system MUST define:

- Which data can be restored independently.
- Which data is discarded.
- Which defaults are applied.
- How consistency is re-established.
- How the player is informed when appropriate.

## 11. Save Compatibility and Migration

### 11.1 Save Versioning

Persistent save formats SHOULD include an explicit format version.

The version SHOULD represent the structure and interpretation of the stored data.

Developers SHOULD NOT rely exclusively on the game version to determine save compatibility.

### 11.2 Schema Changes

Changes to persistent data structures SHOULD be evaluated for compatibility with existing saves.

Potential changes include:

- Adding fields.
- Removing fields.
- Renaming fields.
- Changing data types.
- Changing identifiers.
- Modifying value ranges.
- Changing data relationships.

Changes that affect existing saves MUST have a defined compatibility strategy.

### 11.3 Migration

Migration logic SHOULD transform older save data into the current supported format.

Migration steps SHOULD:

- Identify the source version.
- Apply transformations in a controlled order.
- Preserve valid player progress.
- Introduce appropriate defaults.
- Validate the resulting structure.
- Avoid repeatedly applying the same migration.

Migration SHOULD be deterministic whenever practical.

### 11.4 Backward Compatibility

Projects SHOULD define which historical save versions are supported.

Compatibility requirements MAY depend on:

- Release strategy.
- Expected update frequency.
- Platform constraints.
- Player progression value.
- Distribution model.

When backward compatibility is not supported, the project SHOULD define how incompatible saves are handled and communicated.

### 11.5 Migration Safety

Migration SHOULD NOT overwrite the only valid copy of an older save before the migrated data has been validated.

Developers SHOULD preserve a recoverable copy when migration risks data loss.

Migration behavior MUST be tested using representative saves from supported older versions.

## 12. Data Security and Privacy

### 12.1 Data Minimization

Save files SHOULD contain only information required by the game.

Developers SHOULD avoid storing:

- Unnecessary personal information.
- Credentials or authentication secrets.
- Sensitive information unrelated to gameplay.
- Redundant information that can be reconstructed.

### 12.2 Local Save Security

Developers MUST NOT assume that locally stored save data is trusted.

Data loaded from files SHOULD be validated before it affects gameplay.

Important gameplay rules MUST NOT rely exclusively on the assumption that save files cannot be modified.

### 12.3 Sensitive Data

Sensitive data MUST NOT be stored in plaintext unless explicitly justified and approved.

Authentication credentials, API keys, and private tokens MUST NOT be embedded in save files.

When a project handles personal information, storage and processing MUST follow applicable platform and legal requirements.

### 12.4 Cloud Saves

Cloud persistence MAY be introduced when required by the game or platform.

Cloud save systems SHOULD define:

- Authentication requirements.
- Data ownership.
- Upload and download behavior.
- Conflict resolution.
- Offline behavior.
- Synchronization retries.
- Failure handling.
- Data version compatibility.

Cloud synchronization MUST NOT silently overwrite newer or otherwise valid player progress.

Cloud persistence SHOULD be designed separately from local serialization when their responsibilities differ.

## 13. Concurrency and Asynchronous Operations

Save and load operations MAY use asynchronous processing when supported and justified.

Developers SHOULD consider:

- Whether the data may change during serialization.
- Whether simultaneous save operations are possible.
- Whether a load can occur while a save is running.
- Whether scene transitions can interrupt operations.
- Whether multiple systems can request persistence simultaneously.

The persistence system SHOULD prevent conflicting operations.

When an operation captures runtime state, the system SHOULD define whether it uses a snapshot or reads live state throughout the operation.

Asynchronous persistence MUST handle completion and failure explicitly.

## 14. Performance and Storage

Persistence operations SHOULD avoid unnecessary impact on gameplay performance.

Developers SHOULD consider:

- Save file size.
- Serialization and parsing cost.
- Write frequency.
- Storage operations.
- Memory consumption.
- Loading time.
- Data duplication.

Large or expensive operations MAY be moved away from performance-sensitive gameplay moments when appropriate.

Incremental saving, compression, or specialized storage mechanisms SHOULD be introduced only when requirements justify their complexity.

## 15. Testing and Validation

Persistence systems MUST be tested beyond successful save and load scenarios.

### 15.1 Functional Testing

Tests SHOULD verify:

- New save creation.
- Existing save loading.
- Data modification and saving.
- Correct restoration.
- Multiple save slots when supported.
- Settings persistence.
- Checkpoint restoration.
- Autosave behavior.

### 15.2 Failure Testing

Tests SHOULD include:

- Missing save files.
- Invalid file contents.
- Malformed serialized data.
- Missing required fields.
- Unsupported versions.
- Invalid identifiers.
- Failed write operations.
- Interrupted save operations where testable.
- Insufficient storage where testable.

### 15.3 Compatibility Testing

When save compatibility is supported, tests MUST include representative saves from older supported versions.

Tests SHOULD verify:

- Correct migration.
- Preserved progression.
- Appropriate defaults.
- Valid restored state.
- Rejection of unsupported versions.

### 15.4 Regression Testing

Changes to persistent data structures MUST be evaluated for their effect on existing save behavior.

Regression tests SHOULD cover affected systems and critical player progression paths.

### 15.5 Test Data

Representative save files SHOULD be maintained as test fixtures when they provide meaningful compatibility or regression coverage.

Test fixtures MUST NOT contain real user credentials or sensitive personal information.

## 16. AI-Assisted Persistence Requirements

AI agents MUST follow these guidelines when implementing or modifying persistence systems.

Agents MUST:

- Inspect existing save architecture before making changes.
- Identify the ownership of affected persistent data.
- Preserve existing save compatibility requirements.
- Validate serialized and deserialized data.
- Handle missing and invalid data explicitly.
- Avoid storing unnecessary runtime references.
- Consider the effects of schema changes.
- Implement migrations when required.
- Test save and load behavior.
- Report compatibility risks and limitations.

Agents MUST NOT:

- Change persistent data structures without evaluating existing saves.
- Remove or overwrite valid player data without authorization.
- Assume local save data is valid or trusted.
- Introduce hidden persistence dependencies.
- Report a successful save without verifying the operation.
- Claim migration compatibility without testing representative older saves.

Agents MUST request human approval before introducing breaking save-format changes, removing supported save versions, or implementing destructive migration strategies.

## 17. Persistence Review Checklist

Before completing a persistence-related task, verify:

- [ ] Persistent, session, and transient data are distinguished.
- [ ] Data ownership is explicit.
- [ ] The save structure is understandable.
- [ ] Stable identifiers are used where necessary.
- [ ] Configuration and runtime state are appropriately separated.
- [ ] Serialization and deserialization are validated.
- [ ] Storage uses an appropriate writable location.
- [ ] File operations handle errors.
- [ ] Existing valid saves are protected against failed writes.
- [ ] Loading and restoration follow the required dependency order.
- [ ] Save format versioning is implemented where necessary.
- [ ] Compatibility and migration requirements are addressed.
- [ ] Sensitive information is not unnecessarily stored.
- [ ] Save and load behavior has been tested.
- [ ] Relevant failure scenarios have been tested.
- [ ] Documentation has been updated.

## 18. Exceptions

Exceptions MAY be introduced when project requirements justify an alternative persistence strategy.

Exceptions SHOULD:

- Have a clear technical justification.
- Identify affected data and systems.
- Explain compatibility implications.
- Document relevant risks.
- Be reviewed by the project owner when they affect established persistence conventions.

Breaking changes to existing player data MUST NOT be introduced silently.

## 19. Related Documents

These guidelines SHOULD be used alongside:

- `docs/00_studio_standards/development_philosophy.md`
- `docs/00_studio_standards/project_structure_standards.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/documentation_standards.md`
- `docs/02_technical_standards/architecture_guidelines.md`
- `docs/02_technical_standards/gdscript_standards.md`
- `docs/02_technical_standards/adr/README.md`

Only documents that exist in the repository should be registered as active references in the documentation inventory.

## 20. Maintenance

These guidelines SHOULD be reviewed when:

- Godot changes relevant serialization or file-access capabilities.
- The studio adopts new persistence technologies.
- New target platforms introduce different storage requirements.
- Save compatibility requirements evolve.
- Repeated project experience reveals weaknesses in existing practices.

Changes MUST preserve the document's purpose as a reusable studio-wide technical standard.