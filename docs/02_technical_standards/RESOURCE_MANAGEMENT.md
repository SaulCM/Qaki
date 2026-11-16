# Resource Management

## 1. Purpose

This document establishes studio-wide technical guidelines for managing resources in Godot projects.

Its purpose is to ensure that resources are organized, loaded, reused, modified, and released in a predictable and efficient manner.

These guidelines cover:

- Godot Resource fundamentals.
- Resource ownership and lifecycle.
- Resource organization.
- Resource creation and reuse.
- Resource loading and unloading.
- Shared and mutable resources.
- Runtime resource modification.
- Resource caching.
- Resource dependencies.
- Memory management.
- Resource validation and error handling.
- AI-assisted resource management.

The objective is to prevent resource duplication, unintended shared-state modifications, unnecessary memory consumption, and lifecycle-related errors.

## 2. Scope

These guidelines apply to Godot resources used across studio projects, including:

- `.tres` and `.res` files.
- Custom Resource classes.
- Textures and images.
- Audio resources.
- Materials and shaders.
- Meshes and models.
- Animation resources.
- TileSets and TileMaps-related resources.
- Gameplay configuration data.
- UI resources.
- Runtime-generated resources.
- Resources loaded dynamically.
- Resources shared between scenes and features.

These guidelines primarily target Godot 4.x projects implemented in GDScript.

Specific implementation details MUST remain compatible with the project's configured Godot version.

## 3. Fundamental Principles

### 3.1 Clear Resource Ownership

Every resource MUST have a clear logical owner.

Ownership determines:

- Which feature or system is responsible for the resource.
- Who may modify it.
- Where it is stored.
- How it is loaded.
- How its lifetime is managed.
- Which systems depend on it.

Resources SHOULD be stored and managed according to their actual responsibilities.

### 3.2 Reuse Where Appropriate

Resources SHOULD be reused when multiple systems require the same data or asset.

Developers SHOULD avoid unnecessary duplication of large resources.

However, resource sharing MUST NOT introduce unintended shared mutable state.

### 3.3 Explicit Lifecycle Management

Resources SHOULD have an understandable lifecycle.

Developers SHOULD know:

- When a resource becomes necessary.
- How it is loaded or created.
- Which objects retain references to it.
- When it is no longer needed.
- Whether it can be safely released.

### 3.4 Separation of Configuration and Runtime State

Reusable configuration data SHOULD remain separate from mutable runtime state.

Resources are particularly suitable for reusable configuration and data definitions.

Runtime state SHOULD be stored separately when independent instances or mutable gameplay state are required.

### 3.5 Controlled Complexity

Resource management SHOULD use Godot's native capabilities whenever they satisfy project requirements.

Custom resource managers, caching layers, registries, and loading frameworks MUST NOT be introduced without a clear justification.

## 4. Understanding Godot Resources

### 4.1 Resource Fundamentals

A Godot Resource is an object designed to hold data that can be serialized, reused, and referenced by other objects.

Resources are commonly used for:

- Configuration.
- Asset references.
- Gameplay definitions.
- Reusable data structures.
- Materials and rendering data.
- Audio and animation data.

Developers SHOULD understand the distinction between Resources and Nodes.

| Resource | Node |
|---|---|
| Primarily represents reusable data or configuration | Represents an object in the scene tree |
| Can be serialized and saved | Can participate in scene lifecycle |
| Can be shared between multiple consumers | Has scene-tree ownership and lifecycle |
| Does not belong to the scene tree | Belongs to the scene tree when instantiated |
| Commonly used for definitions and data | Commonly used for behavior and scene composition |

Resources MUST NOT be used as substitutes for Nodes when scene-tree behavior is required.

### 4.2 Built-in and Custom Resources

Developers SHOULD use Godot's built-in Resource types whenever they satisfy the requirements.

Custom Resource classes MAY be introduced when project-specific data structures are necessary.

Example:

```gdscript
extends Resource
class_name WeaponData

@export var weapon_id: String
@export var display_name: String
@export var base_damage: int = 10
@export var attack_speed: float = 1.0
```

Custom Resources SHOULD:

- Represent a coherent data concept.
- Have clear ownership.
- Use appropriate types.
- Provide meaningful defaults.
- Avoid unrelated responsibilities.
- Remain compatible with the project's serialization requirements.

### 4.3 Resource File Formats

Godot commonly uses:

- `.tres`: Text-based Resource files.
- `.res`: Binary Resource files.

The choice SHOULD reflect project requirements.

Text-based resources are generally easier to inspect and review in version control.

Binary resources MAY be appropriate when project requirements justify them.

Developers SHOULD follow established project conventions rather than mixing formats without reason.

## 5. Resource Organization

### 5.1 Feature-Oriented Ownership

Resources MUST follow the approved feature-oriented project structure.

Feature-specific resources MUST be stored within their owning feature.

Example:

```text
features/
├── inventory/
│   ├── resources/
│   │   ├── item_data.gd
│   │   └── definitions/
│   │       ├── health_potion.tres
│   │       └── iron_sword.tres
│   ├── scripts/
│   └── scenes/
│
├── combat/
│   ├── resources/
│   │   └── weapon_data.gd
│   ├── scripts/
│   └── scenes/
│
shared/
└── resources/
    └── common_configuration.tres
```

The example illustrates ownership, not a requirement to create every directory in every feature.

### 5.2 Shared Resources

Resources SHOULD be placed in `shared/` only when they are genuinely used by multiple features and have no more appropriate feature owner.

Shared resources MUST NOT depend on individual feature implementations.

### 5.3 Infrastructure Resources

Resources used by project-wide technical services MAY be stored under `infrastructure/` when they are genuinely infrastructure-owned.

Feature-specific gameplay definitions SHOULD NOT be placed in infrastructure merely because multiple systems access them.

### 5.4 Avoid Duplicate Definitions

Developers SHOULD avoid creating multiple independent definitions for the same logical resource when a shared definition is appropriate.

Before creating a new resource, inspect existing resources and determine whether they can be reused.

### 5.5 Resource Naming

Resource files MUST follow the studio naming conventions.

Examples:

```text
weapon_data.gd
iron_sword.tres
player_configuration.tres
main_theme.ogg
```

Resource identifiers SHOULD be stable and descriptive.

## 6. Resource Ownership and Sharing

### 6.1 Logical Ownership

A resource's logical owner is the feature or system responsible for defining and maintaining its data.

Logical ownership MUST remain clear even when multiple systems reference the resource.

### 6.2 Shared References

Godot Resources can be referenced by multiple consumers.

When a resource is shared, developers MUST understand that modifying it may affect every consumer referencing the same instance.

Example:

```gdscript
var weapon_a: WeaponData = load("res://features/combat/resources/definitions/sword.tres")
var weapon_b: WeaponData = load("res://features/combat/resources/definitions/sword.tres")
```

Both variables may reference the same cached Resource instance.

Developers MUST NOT assume that loading the same resource path produces independent mutable instances.

### 6.3 Immutable Configuration

Resources SHOULD be treated as immutable configuration after initialization whenever practical.

Examples include:

- Weapon definitions.
- Enemy configuration.
- Item definitions.
- Ability parameters.
- Character archetypes.
- Level configuration.

Runtime systems SHOULD read configuration data without modifying shared definitions.

### 6.4 Mutable Resources

Mutable shared resources MUST have an explicit modification policy.

Before modifying a shared Resource, developers MUST determine:

- Whether other consumers reference it.
- Whether modifications are intended to be shared.
- Whether the modification persists.
- Whether the resource must be duplicated.
- Whether concurrent operations can access it.

### 6.5 Independent Runtime Instances

When independent mutable state is required, developers SHOULD create separate instances or duplicate an existing Resource.

Example:

```gdscript
var runtime_weapon: WeaponData = weapon_definition.duplicate(true) as WeaponData
```

The duplication depth SHOULD be selected according to the resource's dependency structure.

Developers MUST understand that shallow and deep duplication have different behavior.

Duplicating a Resource does not automatically guarantee that every referenced object becomes independent in every possible configuration.

### 6.6 Resource Ownership and Node Lifecycles

A Resource can remain alive while references to it exist.

Developers SHOULD avoid assuming that freeing a Node automatically frees every Resource it references.

Resource lifetime SHOULD be understood independently from scene-tree lifetime.

## 7. Resource Creation and Initialization

### 7.1 Creating Resources

Resources SHOULD be created using the appropriate Godot APIs.

Example:

```gdscript
var weapon_data := WeaponData.new()

weapon_data.weapon_id = "iron_sword"
weapon_data.base_damage = 15
```

Developers SHOULD prefer reusable `.tres` definitions when data needs to be configured, reviewed, or shared independently of runtime code.

Runtime creation MAY be used when the resource is generated from gameplay state or procedural requirements.

### 7.2 Initialization

Resources SHOULD have valid default values.

Custom Resource classes SHOULD remain usable without requiring unnecessary initialization steps.

When initialization depends on external data, the responsible system MUST ensure that the required data is available before the resource is used.

### 7.3 Validation

Resources SHOULD be validated before use when their data can be incomplete, externally modified, or generated dynamically.

Validation MAY include:

- Required identifiers.
- Valid numerical ranges.
- Required references.
- Valid configuration combinations.
- Expected collection contents.
- Resource compatibility.

### 7.4 Avoid Hidden Initialization Dependencies

Developers SHOULD avoid resources that require undocumented initialization order or implicit access to unrelated global systems.

Initialization requirements MUST be explicit when they cannot be avoided.

## 8. Resource Loading

### 8.1 Loading Strategy

Resources SHOULD be loaded according to their usage and expected lifetime.

Developers SHOULD distinguish between:

- Resources required at startup.
- Resources required by a specific feature.
- Resources loaded on demand.
- Resources loaded asynchronously.
- Resources generated during runtime.

### 8.2 Static Resource References

Static resource references SHOULD be used when dependencies are known at development time and should be included in the scene or script dependency graph.

Example:

```gdscript
const WEAPON_DATA: Resource = preload(
    "res://features/combat/resources/definitions/iron_sword.tres"
)
```

`preload()` SHOULD be used for resources that must be available when the script is loaded.

Developers MUST avoid preloading large collections of resources without considering startup time and memory usage.

### 8.3 Dynamic Resource Loading

`load()` SHOULD be used when resources are selected dynamically or loaded at runtime.

Example:

```gdscript
func load_weapon_data(resource_path: String) -> WeaponData:
    var resource := load(resource_path) as WeaponData

    if resource == null:
        push_error("Failed to load weapon resource: %s" % resource_path)
        return null

    return resource
```

Dynamic loading SHOULD validate the resulting resource before use.

### 8.4 Resource Paths

Resource paths SHOULD be managed consistently.

Developers SHOULD:

- Use valid project resource paths.
- Avoid unnecessary hardcoded path duplication.
- Keep feature resource locations stable.
- Use explicit configuration when paths vary by project or runtime context.

Resource paths MUST NOT be constructed from untrusted input without appropriate validation.

### 8.5 ResourceLoader

`ResourceLoader` SHOULD be used when resource loading requires more explicit control or when its additional capabilities are appropriate.

Developers SHOULD NOT introduce custom loading abstractions when standard loading functions are sufficient.

### 8.6 Threaded Loading

Threaded resource loading MAY be used when loading large resources would otherwise cause noticeable interruptions.

Threaded loading MUST follow Godot's documented resource-loading and thread-safety requirements.

Developers SHOULD:

- Check loading status.
- Handle loading failures.
- Avoid accessing incomplete resources.
- Respect object and scene lifecycles.
- Avoid unnecessary concurrent loading operations.

### 8.7 Loading Failures

Required resources MUST be validated before dependent systems begin operating.

Optional resources SHOULD have an appropriate fallback or graceful failure behavior.

Loading failures MUST provide useful diagnostics.

## 9. Resource Caching and Reuse

### 9.1 Native Resource Cache

Godot provides resource caching behavior for loaded resources.

Developers SHOULD understand the engine's caching behavior before implementing additional caching systems.

### 9.2 Custom Caches

Custom resource caches MAY be introduced when they solve a demonstrated problem that native resource caching does not adequately address.

A custom cache MUST define:

- Resource ownership.
- Cache keys.
- Loading behavior.
- Invalidation rules.
- Memory limits when appropriate.
- Cleanup behavior.
- Failure handling.

### 9.3 Cache Invalidation

Cached data MUST have a clear invalidation strategy.

Developers SHOULD consider whether changes to source data or runtime configuration make cached values invalid.

### 9.4 Cache Lifetime

Caches SHOULD have a bounded or otherwise justified lifetime.

Long-lived caches MUST be evaluated for memory consumption.

### 9.5 Avoid Redundant Caching

Developers MUST NOT create additional caches merely to duplicate functionality already provided by Godot.

Caching SHOULD be introduced only when it provides a measurable or clearly justified benefit.

## 10. Resource Modification

### 10.1 Modification Responsibility

Only the responsible system SHOULD modify a resource when that resource represents mutable shared state.

Consumers SHOULD NOT modify configuration resources owned by another feature without an explicit contract.

### 10.2 Runtime Configuration Changes

When runtime changes are necessary, developers SHOULD determine whether those changes belong in:

- A duplicated runtime Resource.
- A dedicated runtime state object.
- A feature-owned component.
- A persistent data model.

The original reusable definition SHOULD remain unchanged unless shared modification is explicitly intended.

### 10.3 Resource Duplication

`Resource.duplicate()` MAY be used when an independent copy is necessary.

Developers MUST select duplication behavior carefully.

Deep duplication SHOULD NOT be used indiscriminately because it may duplicate more data and dependencies than required.

### 10.4 Resource Local To Scene

Godot provides resource-locality behavior for scene instances.

Developers SHOULD understand the `resource_local_to_scene` property when a Resource needs independent instances across scene instances.

This behavior MUST be validated for the actual resource and scene structure.

It SHOULD NOT replace an explicit ownership strategy.

### 10.5 Editor and Runtime Separation

Editor-authored configuration SHOULD remain separate from runtime modifications.

Runtime systems SHOULD NOT accidentally modify shared editor-authored data in ways that affect other consumers or future scene instances.

## 11. Runtime-Generated Resources

### 11.1 Appropriate Usage

Runtime-generated Resources MAY be used for:

- Procedural content.
- Dynamic configuration.
- Runtime material instances.
- Generated data structures.
- Temporary gameplay definitions.
- Runtime customization.

### 11.2 Ownership

Generated resources MUST have a clear owner and lifetime.

Developers SHOULD identify which component is responsible for retaining and releasing references.

### 11.3 Temporary Resources

Temporary resources SHOULD be released when they are no longer required and no references remain.

Developers MUST avoid accumulating generated resources indefinitely.

### 11.4 Persistence

Runtime-generated resources MUST NOT be assumed to persist automatically.

When generated data must survive application restarts, it MUST use an appropriate serialization and persistence mechanism.

Persistence requirements MUST follow:

`docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md`

### 11.5 ResourceSaver

`ResourceSaver` MAY be used when runtime-generated Resources need to be serialized.

Saving generated resources SHOULD follow explicit ownership, validation, and persistence rules.

Developers SHOULD avoid writing arbitrary runtime-generated resources into project source directories.

## 12. Memory Management and Cleanup

### 12.1 Resource Lifetime

Developers SHOULD understand Godot's reference-counting behavior for Resources and other reference-counted objects.

A Resource generally remains available while references to it remain.

### 12.2 Releasing References

References SHOULD be released when they are no longer required.

Example:

```gdscript
func clear_current_weapon() -> void:
    current_weapon = null
```

Setting a reference to `null` does not guarantee immediate memory reclamation if other references remain.

### 12.3 Node-Owned Resources

When Resources are referenced by Nodes, developers SHOULD understand how the Node's destruction and remaining references affect Resource lifetime.

### 12.4 Resource Leaks

Developers SHOULD investigate:

- Long-lived references to unused Resources.
- Unbounded resource caches.
- Repeated runtime resource creation.
- Unnecessary retained scene instances.
- Persistent collections holding obsolete resources.
- Event connections retaining unexpected references.

### 12.5 Explicit Cache Clearing

Godot provides mechanisms such as `ResourceLoader` cache management.

Cache clearing SHOULD only be used when its behavior and impact are understood.

Developers MUST avoid clearing shared resources while active systems still depend on them.

### 12.6 Memory Monitoring

Projects SHOULD monitor memory usage during representative gameplay scenarios.

Resource-intensive features SHOULD be tested for unexpected memory growth.

## 13. Resource Dependencies

### 13.1 Dependency Awareness

Resources may reference other Resources.

Developers SHOULD understand the dependency graph of important resource definitions.

### 13.2 Dependency Direction

Resource dependencies SHOULD remain consistent with the approved project architecture.

Shared resources MUST NOT introduce dependencies on individual features.

### 13.3 Circular Dependencies

Circular resource dependencies SHOULD be avoided.

Developers SHOULD prefer clear dependency direction and explicit references.

### 13.4 Large Dependency Graphs

Resource definitions SHOULD NOT load large and unnecessary dependency graphs.

Developers SHOULD evaluate whether a resource needs to reference another resource directly or whether a stable identifier or smaller data contract is more appropriate.

### 13.5 Resource Ownership Boundaries

A feature SHOULD NOT depend on the internal resource organization of another feature.

Cross-feature dependencies SHOULD use intentional public contracts.

## 14. Resources and Data Persistence

### 14.1 Configuration Versus Persistent State

Configuration Resources and persistent gameplay state MUST remain conceptually distinct.

For example:

- `WeaponData` may define the default properties of a weapon.
- A runtime weapon state may contain durability, upgrades, and current ammunition.

Persistent gameplay changes SHOULD NOT unintentionally modify reusable configuration definitions.

### 14.2 Serialization

Resources MAY be serialized when their data structure and project requirements justify it.

Developers SHOULD consider:

- Stable identifiers.
- Resource compatibility.
- Versioning.
- Data validation.
- Migration requirements.
- Dependencies.

### 14.3 Save Data

Save systems MUST NOT rely on incidental in-memory Resource state as the only representation of persistent gameplay progress.

Persistent state MUST be saved and restored according to the project's persistence design.

### 14.4 Resource References in Save Data

When persistent data references resources, developers SHOULD prefer stable identifiers or controlled resource paths rather than fragile runtime object references.

The save system MUST validate referenced resources when loading saved data.

## 15. Asset Resources and Import Management

### 15.1 Asset Resource Responsibilities

Imported assets and their runtime resource usage SHOULD follow the project's asset pipeline.

### 15.2 Import Configuration

Developers SHOULD avoid modifying imported resource settings without understanding their impact on memory, rendering, audio, and platform compatibility.

### 15.3 Imported Resources

Imported resources SHOULD be referenced through valid Godot resource paths.

Developers MUST NOT modify generated import artifacts directly.

### 15.4 Asset Pipeline Standards

Asset sourcing, import, processing, optimization, and validation MUST follow:

`docs/02_technical_standards/ASSET_PIPELINE.md`

## 16. Error Handling and Reliability

### 16.1 Resource Validation

Resources SHOULD be validated at appropriate boundaries.

Validation MUST be proportional to the resource's source and intended use.

### 16.2 Missing Resources

Required resource failures MUST be reported clearly.

Optional resource failures SHOULD be handled gracefully when possible.

### 16.3 Invalid Resource Types

Dynamically loaded resources SHOULD be checked against their expected type before use.

Example:

```gdscript
var resource := load(resource_path)

if not resource is WeaponData:
    push_error("Loaded resource is not a valid WeaponData resource.")
    return
```

### 16.4 Corrupted or Incompatible Data

Resources loaded from user-generated, external, or persistent data SHOULD be treated as potentially invalid.

Systems SHOULD validate data before allowing it to affect important runtime state.

### 16.5 Failure Recovery

Systems SHOULD define an appropriate response to resource-loading or initialization failures.

Depending on the resource, this MAY include:

- Using a fallback resource.
- Disabling the affected feature.
- Displaying an error.
- Retrying a recoverable operation.
- Returning a failure result.

## 17. Resource Testing and Validation

### 17.1 Resource Definition Testing

Important Resource classes SHOULD be tested for:

- Correct defaults.
- Valid property types.
- Expected initialization behavior.
- Serialization compatibility.
- Validation behavior.
- Duplication behavior when relevant.

### 17.2 Loading Tests

Resource-loading workflows SHOULD be tested for:

- Valid paths.
- Missing files.
- Invalid resource types.
- Failed loading.
- Dynamic selection.
- Asynchronous completion.
- Scene transitions during loading.

### 17.3 Sharing and Mutation Tests

Tests SHOULD verify that shared and duplicated resources behave as intended.

When independent runtime state is required, tests SHOULD confirm that modifying one instance does not unintentionally modify another.

### 17.4 Lifecycle Tests

Important resource lifecycle workflows SHOULD be tested for:

- Creation.
- Reference retention.
- Cleanup.
- Cache invalidation.
- Scene destruction.
- Long-running usage.

### 17.5 Memory Validation

Resource-intensive systems SHOULD be tested for unexpected memory growth and resource retention.

### 17.6 Integration Testing

When resources are shared between features, integration tests SHOULD verify that dependencies and ownership contracts remain correct.

## 18. AI-Assisted Resource Management

AI agents MUST follow these guidelines when creating, modifying, loading, or reviewing Godot Resources.

Agents MUST:

- Inspect existing resource definitions before creating new ones.
- Identify the logical owner of each resource.
- Follow feature-oriented organization.
- Respect shared resource boundaries.
- Understand resource caching behavior.
- Distinguish configuration from runtime state.
- Consider whether a resource is shared or independently mutable.
- Use duplication when independent mutable instances are required.
- Validate dynamically loaded resources.
- Consider resource lifetime and memory usage.
- Respect persistence and asset pipeline standards.
- Test important resource lifecycle behavior.
- Report changes to shared resource contracts.

Agents MUST NOT:

- Modify shared configuration resources unintentionally.
- Assume repeated loads always create independent instances.
- Introduce custom resource managers without justification.
- Create duplicate resource definitions unnecessarily.
- Store feature-specific resources in unrelated directories.
- Clear resource caches without evaluating dependencies.
- Assume freeing a Node releases every referenced Resource.
- Treat in-memory Resource changes as automatically persistent.

Agents SHOULD request owner approval before introducing significant project-wide resource infrastructure or changing established resource ownership boundaries.

## 19. Resource Management Review Checklist

Before completing resource-related work, verify:

- [ ] Resource ownership is clear.
- [ ] Resource location follows feature-oriented organization.
- [ ] Existing definitions were checked before creating new ones.
- [ ] Resource types and properties are appropriate.
- [ ] Default values are valid.
- [ ] Configuration and runtime state are separated.
- [ ] Shared mutable state is managed intentionally.
- [ ] Resource duplication behavior is understood.
- [ ] Resource loading strategy is appropriate.
- [ ] Dynamic resource loading is validated.
- [ ] Cache behavior is understood.
- [ ] Resource dependencies respect architecture.
- [ ] Resource lifetime is understood.
- [ ] Unnecessary references are released.
- [ ] Memory implications have been considered.
- [ ] Persistence requirements are handled correctly.
- [ ] Asset pipeline rules are followed.
- [ ] Error handling is appropriate.
- [ ] Relevant tests have been added or updated.
- [ ] Documentation is updated when necessary.

## 20. Exceptions

Exceptions MAY be introduced when project-specific requirements justify alternative resource management approaches.

Exceptions SHOULD:

- Have a clear technical justification.
- Identify affected resources and systems.
- Explain ownership and lifecycle implications.
- Document relevant performance and memory trade-offs.
- Receive project owner approval when they introduce significant architectural changes.

Repeated exceptions SHOULD trigger a review of these guidelines.

## 21. Related Documents

These guidelines SHOULD be used alongside:

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/ENGINE_STANDARDS.md`
- `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`
- `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md`
- `docs/02_technical_standards/ASSET_PIPELINE.md`
- `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md`
- `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md`
- `docs/02_technical_standards/adr/ADR_PROCESS.md`
- Applicable documents in `docs/05_qa_standards/`

Only documents that physically exist in the repository SHOULD be registered as active references in the documentation inventory.

## 22. Maintenance

These guidelines SHOULD be reviewed when:

- Godot changes Resource behavior or loading capabilities.
- The studio adopts new resource management practices.
- Repeated resource lifecycle or memory issues reveal weaknesses in the guidelines.
- New project requirements introduce different resource ownership models.
- Development experience identifies more effective resource management approaches.

Changes MUST preserve the document's purpose as a reusable studio-wide technical standard.