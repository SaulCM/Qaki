# Scene and Node Conventions

## 1. Purpose

This document establishes studio-wide conventions for designing, organizing, naming, and maintaining Godot scenes and nodes.

Its purpose is to ensure that scene structures remain understandable, modular, reusable, and maintainable as projects grow.

These conventions cover:

- Scene organization.
- Node hierarchy design.
- Node responsibilities.
- Scene composition.
- Scene instantiation.
- Node naming.
- Scene ownership.
- Node references.
- Scene lifecycle.
- Reusable scenes and components.
- Scene communication.
- Performance considerations.
- Scene validation and testing.

The objective is to establish consistent scene and node design practices while preserving Godot's native scene-based architecture.

## 2. Scope

These conventions apply to all Godot scenes and nodes developed for studio projects, including:

- Gameplay scenes.
- Character scenes.
- Enemy scenes.
- Environment scenes.
- UI scenes.
- Menu scenes.
- Level scenes.
- Component scenes.
- Effect scenes.
- Audio-related nodes.
- Infrastructure scenes.
- Test scenes.
- Editor tools and custom editor nodes.

These conventions primarily target Godot 4.x projects implemented in GDScript.

Specific implementations MUST remain compatible with the project's configured Godot version.

## 3. Fundamental Principles

### 3.1 Scenes as Composition Units

Scenes SHOULD represent meaningful, independently understandable units of functionality or content.

A scene MAY represent:

- A gameplay entity.
- A UI screen.
- A reusable component.
- A level or environment.
- A gameplay interaction.
- A visual or audio effect.
- A system coordinator.

Scenes SHOULD have clear purposes and avoid combining unrelated responsibilities.

### 3.2 Nodes as Focused Components

Each node SHOULD have a clear responsibility within its scene.

Developers SHOULD prefer smaller, focused node structures over monolithic nodes responsible for unrelated behavior.

### 3.3 Composition Over Inheritance

Scene composition SHOULD be preferred over deep inheritance hierarchies.

Reusable behavior SHOULD be composed through appropriate nodes, Resources, scripts, and signals.

Inheritance MAY be used when a genuine and stable type relationship exists.

### 3.4 Clear Ownership

Every scene and node SHOULD have an identifiable owner.

Ownership determines:

- Responsibility for behavior.
- Control over internal state.
- Lifecycle management.
- Modification permissions.
- Communication boundaries.

### 3.5 Simplicity

Scene hierarchies SHOULD remain as simple as reasonably possible.

Developers MUST avoid:

- Unnecessary wrapper nodes.
- Excessive nesting.
- Redundant scene boundaries.
- Overly generic components.
- Unnecessary inheritance.
- Unclear ownership.
- Excessive dependencies between unrelated nodes.

### 3.6 Explicit Interfaces

Reusable scenes SHOULD expose clear interfaces.

Other systems SHOULD interact with a scene through its intended public properties, methods, signals, or child components rather than depending on arbitrary internal implementation details.

## 4. Scene Organization

### 4.1 Feature-Oriented Structure

Scenes MUST follow the approved feature-oriented project structure.

Feature-specific scenes MUST be stored within their owning feature.

Example:

```text
features/
├── player/
│   ├── scenes/
│   │   ├── player.tscn
│   │   └── components/
│   │       ├── health_component.tscn
│   │       └── interaction_component.tscn
│   ├── scripts/
│   └── resources/
│
├── inventory/
│   ├── scenes/
│   │   ├── inventory_screen.tscn
│   │   └── inventory_slot.tscn
│   ├── scripts/
│   └── resources/
│
└── world/
    ├── scenes/
    │   ├── world.tscn
    │   └── environments/
    ├── scripts/
    └── resources/
```

The example illustrates possible organization. Projects SHOULD create only directories required by their actual features.

### 4.2 Shared Scenes

Scenes SHOULD be placed in `shared/` only when they are genuinely reused by multiple features and have no more appropriate feature owner.

Shared scenes MUST NOT depend on individual feature implementations.

Examples MAY include:

- Generic reusable UI elements.
- Shared visual effects.
- Generic interaction components.
- Common presentation elements.

### 4.3 Infrastructure Scenes

Infrastructure-owned scenes MAY be stored under `infrastructure/` when they support project-wide technical responsibilities.

Feature-specific gameplay scenes SHOULD NOT be moved into infrastructure merely because they are instantiated by multiple systems.

### 4.4 Scene and Script Separation

Scene files SHOULD primarily define node composition, configuration, and resource references.

Scripts SHOULD implement behavior appropriate to their responsibilities.

Developers SHOULD avoid embedding excessive gameplay logic in scene-specific scripts when it belongs in dedicated components or systems.

### 4.5 Scene Dependencies

Scene dependencies SHOULD remain understandable and intentional.

Developers SHOULD avoid scenes that indirectly instantiate large and unnecessary dependency hierarchies.

## 5. Scene Design

### 5.1 Scene Responsibility

Every scene MUST have a clear purpose.

Before creating a scene, developers SHOULD identify:

- What the scene represents.
- What behavior it owns.
- Which systems use it.
- Whether it needs to be reusable.
- Which dependencies it requires.
- How it is instantiated and removed.

### 5.2 Scene Boundaries

A separate scene SHOULD be created when a group of nodes represents a meaningful reusable unit or has an independently understandable lifecycle.

Good candidates include:

- Characters.
- Enemies.
- Inventory slots.
- Interactive objects.
- Weapons.
- UI panels.
- Reusable effects.
- Environmental objects.

Developers SHOULD NOT create a separate scene for every small node grouping when doing so adds unnecessary complexity.

### 5.3 Reusability

Reusable scenes SHOULD expose configuration through:

- Exported properties.
- Resource definitions.
- Public methods.
- Signals.
- Clearly defined child nodes.

Reusable scenes SHOULD NOT depend on specific parent scene hierarchies unless that dependency is explicitly part of their contract.

### 5.4 Scene Independence

A reusable scene SHOULD be instantiable without requiring unrelated scenes to exist.

Dependencies SHOULD be provided explicitly through appropriate references, configuration, or initialization methods.

### 5.5 Scene Variants

When multiple scenes share the same fundamental structure, developers MAY use:

- Inherited scenes.
- Shared child scenes.
- Reusable components.
- Resource-based configuration.

The chosen approach SHOULD minimize duplication without introducing unnecessary inheritance or configuration complexity.

### 5.6 Scene Size

Large scenes SHOULD be evaluated for opportunities to separate meaningful responsibilities.

However, scene size alone MUST NOT determine whether a scene should be split.

The decision SHOULD consider:

- Responsibility boundaries.
- Reusability.
- Ownership.
- Complexity.
- Testing requirements.
- Runtime behavior.

## 6. Node Hierarchy Design

### 6.1 Hierarchy Clarity

Node hierarchies MUST communicate their structural and functional relationships clearly.

Developers SHOULD organize nodes according to:

- Ownership.
- Composition.
- Transform relationships.
- Processing responsibilities.
- Functional grouping.

### 6.2 Parent Responsibilities

Parent nodes SHOULD coordinate their relevant children without becoming responsible for every internal operation.

Parents SHOULD:

- Own appropriate shared state.
- Coordinate child components.
- Expose meaningful public behavior.
- Manage relevant child lifecycles.

Parents SHOULD NOT access arbitrary child internals unnecessarily.

### 6.3 Child Responsibilities

Child nodes SHOULD own their specific behavior and internal state.

Children SHOULD communicate important changes through appropriate signals or public interfaces.

Children SHOULD NOT depend on unrelated sibling implementation details.

### 6.4 Avoid Deep Hierarchies

Node hierarchies SHOULD remain reasonably shallow.

Excessive nesting increases navigation and maintenance complexity.

Developers SHOULD extract meaningful reusable scenes when nesting becomes difficult to understand.

There is no universal maximum hierarchy depth. The decision SHOULD reflect actual complexity.

### 6.5 Avoid Unnecessary Wrapper Nodes

Wrapper nodes SHOULD only be introduced when they provide a meaningful purpose.

Valid reasons MAY include:

- Transform grouping.
- Visual organization.
- Physics organization.
- Lifecycle coordination.
- Reusable scene composition.
- Container behavior.

Nodes MUST NOT be added merely to create additional hierarchy levels.

### 6.6 Organizational Nodes

Organizational nodes MAY be used to group related children.

Their purpose SHOULD be clear from their name and position in the hierarchy.

Example:

```text
Player
├── Visuals
│   ├── Sprite
│   └── AnimationPlayer
├── CollisionShape
├── HealthComponent
└── InteractionComponent
```

This structure is illustrative and SHOULD be adapted to actual gameplay requirements.

## 7. Node Naming

### 7.1 General Rules

Node names MUST follow:

`docs/00_studio_standards/naming_conventions.md`

Node names SHOULD:

- Use `PascalCase`.
- Describe their purpose.
- Remain concise.
- Avoid unnecessary abbreviations.
- Be understandable in the scene tree.

Examples:

```text
Player
HealthComponent
InteractionArea
InventoryPanel
AnimationPlayer
CollisionShape
```

### 7.2 Descriptive Names

Developers SHOULD prefer names that communicate the node's responsibility.

Avoid generic names such as:

```text
Node
Node2
Container
Object
Manager
Helper
```

Generic engine node names MAY remain when their purpose is obvious and changing them provides no meaningful benefit.

### 7.3 Internal Node Names

Internal nodes SHOULD use consistent names across instances of the same reusable scene.

This improves readability and allows stable references when the scene contract requires them.

### 7.4 Unique Node Names

Godot's unique node naming feature MAY be used when it improves access to an important node within an appropriate scene context.

Developers SHOULD NOT mark every node as unique.

Unique node names MUST NOT be used as a substitute for clear ownership or explicit dependencies.

## 8. Node Types and Responsibilities

### 8.1 Appropriate Node Selection

Developers SHOULD select node types according to their intended behavior.

Examples include:

| Requirement | Appropriate node types |
|---|---|
| General scene organization | Node, Node2D, Node3D |
| 2D physics character | CharacterBody2D |
| 3D physics character | CharacterBody3D |
| 2D collision detection | Area2D |
| 3D collision detection | Area3D |
| 2D visual representation | Sprite2D |
| 3D visual representation | MeshInstance3D |
| Animation control | AnimationPlayer |
| UI layout | Control and derived nodes |
| Audio playback | AudioStreamPlayer variants |

These are examples, not mandatory node selections for every situation.

### 8.2 Avoid Misusing Node Types

Developers MUST NOT select node types solely because they provide convenient functionality unrelated to their intended purpose.

The selected node SHOULD represent the actual responsibility required.

### 8.3 Specialized Nodes

Specialized nodes SHOULD be used when their built-in behavior reduces unnecessary custom implementation.

Custom implementations SHOULD only be introduced when engine-provided nodes do not satisfy the requirements.

## 9. Scripts Attached to Nodes

### 9.1 Script Responsibilities

Scripts SHOULD implement behavior appropriate to the node or scene they control.

A script SHOULD NOT become a central location for unrelated systems.

### 9.2 Thin Scene Controllers

Scene root scripts SHOULD primarily coordinate their scene's behavior.

Complex responsibilities SHOULD be delegated to appropriate components or feature-owned systems.

### 9.3 Script Attachment

Scripts SHOULD be attached to the node whose responsibility they implement.

Developers SHOULD avoid attaching unrelated behavior to convenient but semantically incorrect nodes.

### 9.4 Script Reuse

Reusable behavior SHOULD be implemented through appropriate components, shared scripts, or other composition mechanisms.

Developers SHOULD NOT duplicate substantial behavior across multiple scenes when a clear reusable abstraction is justified.

### 9.5 Coding Standards

All attached scripts MUST follow:

`docs/02_technical_standards/gdscript_standards.md`

## 10. Scene Communication

### 10.1 Communication Principles

Nodes SHOULD communicate through explicit and understandable interfaces.

Developers SHOULD select communication mechanisms according to the relationship between the participants.

### 10.2 Direct References

Direct references MAY be used when the dependency is intentional and the referenced node has a stable ownership relationship.

Developers SHOULD avoid unnecessary dependencies on distant or unrelated nodes.

### 10.3 Signals

Signals SHOULD be used when a node announces an event without requiring knowledge of its consumers.

Examples include:

- Health changed.
- Interaction completed.
- Item collected.
- Animation finished.
- Component state changed.

All signal declarations and connections MUST follow:

`docs/02_technical_standards/event_and_signal_guidelines.md`

### 10.4 Parent-Child Communication

Parent-child communication SHOULD follow clear ownership rules.

Parents MAY call public methods on children when the dependency is intentional.

Children SHOULD use signals to notify parents of meaningful events when direct references are unnecessary.

### 10.5 Sibling Communication

Sibling nodes SHOULD NOT depend heavily on one another's internal implementations.

When coordination is necessary, communication SHOULD occur through their owner, an explicit shared interface, or an appropriate signal contract.

### 10.6 Cross-Feature Communication

Cross-feature scene communication MUST respect approved feature boundaries.

Features SHOULD communicate through public interfaces, signals, or shared contracts rather than accessing another feature's internal scene hierarchy.

### 10.7 Avoid Fragile Scene-Tree Traversal

Developers SHOULD avoid frequent or deeply nested scene-tree searches to locate unrelated systems.

Use explicit references or appropriate coordination mechanisms when dependencies are stable and important.

## 11. Scene Instantiation and Lifecycle

### 11.1 Scene Instantiation

Scenes SHOULD be instantiated through clear ownership responsibilities.

Example:

```gdscript
const ENEMY_SCENE: PackedScene = preload(
    "res://features/enemies/scenes/enemy.tscn"
)


func spawn_enemy() -> void:
    var enemy := ENEMY_SCENE.instantiate()
    get_tree().current_scene.add_child(enemy)
```

The component responsible for instantiation SHOULD understand:

- Where the instance belongs.
- Which configuration it requires.
- Who owns its lifecycle.
- How it is removed.

### 11.2 PackedScene Usage

`PackedScene` SHOULD be used for reusable scene definitions.

Developers SHOULD distinguish between a scene resource and an instantiated scene node hierarchy.

### 11.3 Initialization

Scene instances SHOULD receive required configuration before dependent behavior begins.

Initialization requirements MUST be explicit.

Developers SHOULD avoid relying on fragile timing assumptions between parent and child `_ready()` execution.

### 11.4 Node Lifecycle

Developers MUST understand relevant Godot lifecycle methods, including:

- `_enter_tree()`
- `_ready()`
- `_process(delta)`
- `_physics_process(delta)`
- `_exit_tree()`

Lifecycle-dependent behavior SHOULD be implemented in the appropriate method.

### 11.5 Adding and Removing Nodes

Nodes SHOULD be added and removed through their owning systems.

Use `queue_free()` when deferred node destruction is appropriate.

Developers MUST avoid accessing nodes after they have been freed.

### 11.6 Reparenting

Reparenting MAY be used when gameplay requires changing node ownership or hierarchy.

Developers SHOULD consider:

- Transform preservation.
- Lifecycle callbacks.
- Processing behavior.
- Signal connections.
- Ownership implications.
- Dependencies on parent structure.

Reparenting SHOULD NOT be used as a substitute for clear scene architecture.

## 12. Node References and Dependencies

### 12.1 Explicit References

Important node dependencies SHOULD be explicit.

Developers MAY use:

- `@onready` references.
- Exported node references.
- Initialization parameters.
- Public interfaces.
- Signals.

### 12.2 Node Paths

Node paths SHOULD be used when the relationship is stable and meaningful.

Developers SHOULD avoid long paths that depend on unrelated hierarchy details.

### 12.3 Optional References

Optional node references SHOULD be handled explicitly.

Use `get_node_or_null()` when the referenced node may legitimately be absent.

Required nodes SHOULD fail visibly when their absence represents an invalid scene configuration.

### 12.4 Parent Dependencies

Reusable scenes SHOULD NOT assume a specific parent type or hierarchy unless it is part of their documented contract.

### 12.5 Dependency Direction

Dependencies MUST follow the approved architecture.

In particular:

- Shared scenes MUST NOT depend on individual feature implementations.
- Features MUST NOT create circular dependencies.
- Infrastructure MUST NOT contain feature-specific gameplay responsibilities.
- Scene composition MUST respect feature ownership.

## 13. Components and Reusable Behavior

### 13.1 Component Design

Components SHOULD represent focused responsibilities that can be composed into larger scenes.

Examples include:

- Health.
- Interaction.
- Inventory.
- Movement.
- Detection.
- Targeting.
- Audio presentation.

Components SHOULD have clear responsibilities and interfaces.

### 13.2 Component Independence

Components SHOULD avoid unnecessary dependencies on their owning scene.

A component SHOULD remain reusable when its responsibility is genuinely reusable.

### 13.3 Component Scenes

Component scenes MAY be used when a component requires multiple nodes, visual representation, physics behavior, or an independent lifecycle.

Simple components MAY be implemented as scripts attached to appropriate nodes when a separate scene would add unnecessary complexity.

### 13.4 Component Communication

Components SHOULD communicate through their public methods, signals, or explicitly defined shared interfaces.

They SHOULD NOT depend on arbitrary sibling node names or internal structures.

### 13.5 Avoid Over-Componentization

Not every small behavior requires a separate component.

Developers SHOULD introduce components when they improve cohesion, reuse, testability, or independent lifecycle management.

## 14. Scene Inheritance and Overrides

### 14.1 Inherited Scenes

Scene inheritance MAY be used when multiple scenes share a stable base structure and behavior.

Examples MAY include:

- Character variants.
- Enemy variants.
- UI variants.
- Reusable environment configurations.

### 14.2 Inheritance Boundaries

Inherited scenes SHOULD preserve the purpose and contract of their base scene.

Developers SHOULD avoid deeply nested scene inheritance.

### 14.3 Overrides

Overrides SHOULD be limited to meaningful variations.

Excessive overrides MAY indicate that the base scene has too many responsibilities or that composition would be more appropriate.

### 14.4 Composition Alternative

Before introducing scene inheritance, developers SHOULD consider whether shared child scenes, components, or Resource-based configuration provide a simpler solution.

## 15. UI Scene Conventions

### 15.1 UI Ownership

UI scenes SHOULD own their presentation and interaction responsibilities.

Gameplay systems SHOULD NOT directly manipulate unrelated UI internals.

### 15.2 UI Composition

Complex interfaces SHOULD be divided into meaningful reusable scenes.

Examples include:

- Inventory screens.
- Inventory slots.
- Dialog panels.
- HUD components.
- Settings sections.
- Confirmation dialogs.

### 15.3 UI Communication

UI scenes SHOULD expose clear methods and signals.

They SHOULD communicate user intent and presentation events without taking ownership of unrelated gameplay state.

### 15.4 UI State

UI state SHOULD have a clear owner.

Developers SHOULD avoid duplicated state between UI components and gameplay systems.

### 15.5 UI Standards

UI design and interaction behavior MUST follow the applicable guidelines in:

`docs/01_game_design_guidelines/ui_ux_design_guidelines.md`

## 16. Scene Performance

### 16.1 Node Count

Node count SHOULD be considered when designing large or frequently instantiated scenes.

However, node count alone MUST NOT be treated as a reliable indicator of performance problems.

Optimization SHOULD be based on profiling.

### 16.2 Processing

Nodes SHOULD only enable processing when necessary.

Developers SHOULD avoid unnecessary per-frame and physics-frame callbacks.

### 16.3 Visibility and Processing

Hidden or inactive scenes SHOULD avoid unnecessary processing when their behavior does not require it.

Visibility and processing MUST be managed separately when necessary.

### 16.4 Instantiation Costs

Frequently instantiated scenes SHOULD be evaluated for initialization and allocation costs.

Object pooling MAY be considered when profiling demonstrates a meaningful benefit.

### 16.5 Scene Complexity

Large scenes SHOULD be evaluated for unnecessary dependencies, excessive active nodes, expensive initialization, and resource usage.

### 16.6 Performance Standards

Performance measurement and optimization MUST follow:

`docs/02_technical_standards/performance_guidelines.md`

## 17. Resource Management

### 17.1 Scene Resources

Scenes SHOULD reference Resources according to their ownership and sharing requirements.

### 17.2 Shared Resources

Developers MUST understand that multiple scene instances may reference the same Resource.

Mutable Resources SHOULD be duplicated or otherwise isolated when independent runtime state is required.

### 17.3 Resource Loading

Scene dependencies SHOULD avoid unnecessarily loading large collections of resources.

Dynamic loading SHOULD be considered when resource availability can be deferred without compromising gameplay.

### 17.4 Resource Lifecycle

Resource creation, loading, sharing, caching, and cleanup MUST follow:

`docs/02_technical_standards/resource_management.md`

## 18. Testing and Validation

### 18.1 Scene Validation

Important scenes SHOULD be validated for:

- Correct root node.
- Expected child hierarchy.
- Required scripts.
- Required Resources.
- Valid node references.
- Valid signal connections.
- Correct initialization.
- Expected runtime behavior.

### 18.2 Reusable Scene Testing

Reusable scenes SHOULD be tested independently where practical.

Tests SHOULD verify that they function within their documented dependencies and configuration.

### 18.3 Integration Testing

Scene interactions SHOULD be tested when they involve multiple features or complex lifecycle behavior.

### 18.4 Lifecycle Testing

Important scene workflows SHOULD be tested for:

- Instantiation.
- Initialization.
- Activation and deactivation.
- Reparenting when applicable.
- Scene transitions.
- Removal and destruction.
- Resource cleanup.

### 18.5 Runtime Validation

Scenes SHOULD be tested in the running game rather than relying exclusively on editor inspection.

### 18.6 Test Standards

Testing MUST follow applicable standards in:

`docs/05_qa_standards/`

## 19. Documentation

Non-obvious scene contracts SHOULD be documented.

Documentation MAY include:

- Scene purpose.
- Root node responsibility.
- Required child nodes.
- Public methods.
- Signals.
- Exported configuration.
- Dependencies.
- Lifecycle expectations.
- Reuse constraints.

Documentation SHOULD remain close to the relevant feature or scene.

A separate scene registry SHOULD only be introduced when project complexity justifies maintaining one.

## 20. AI-Assisted Scene and Node Development

AI agents MUST follow these conventions when creating, modifying, or reviewing scenes and nodes.

Agents MUST:

- Inspect existing scene hierarchies before making changes.
- Respect feature-oriented organization.
- Identify scene and node responsibilities.
- Follow node naming conventions.
- Preserve established scene contracts.
- Use appropriate Godot node types.
- Keep hierarchies understandable.
- Respect scene ownership and lifecycle.
- Use explicit dependencies.
- Follow signal and Resource management standards.
- Validate scene instantiation and runtime behavior.
- Update relevant documentation when public scene contracts change.

Agents MUST NOT:

- Introduce type-oriented root organization.
- Create unnecessary wrapper nodes.
- Build excessively deep scene hierarchies.
- Introduce unrelated responsibilities into existing scenes.
- Depend on fragile node paths without justification.
- Access another feature's internal scene hierarchy unnecessarily.
- Modify shared scene contracts without evaluating their consumers.
- Introduce unnecessary scene inheritance or component abstractions.

Agents SHOULD request owner approval before introducing significant changes to scene architecture, shared scene interfaces, or established feature boundaries.

## 21. Scene and Node Review Checklist

Before completing scene-related work, verify:

- [ ] The scene has a clear purpose.
- [ ] The scene belongs to the correct feature or shared area.
- [ ] The root node is appropriate.
- [ ] Node responsibilities are clear.
- [ ] The hierarchy is understandable.
- [ ] Node names follow naming conventions.
- [ ] Unnecessary wrapper nodes are avoided.
- [ ] Scripts are attached to appropriate nodes.
- [ ] Dependencies are explicit and justified.
- [ ] Reusable scenes have clear interfaces.
- [ ] Scene ownership and lifecycle are understood.
- [ ] Signal connections follow established guidelines.
- [ ] Resource references follow resource management guidelines.
- [ ] Feature boundaries are respected.
- [ ] Processing is enabled only when necessary.
- [ ] Scene instantiation and cleanup work correctly.
- [ ] Required tests have been added or updated.
- [ ] Runtime behavior has been validated.
- [ ] Documentation reflects significant interface changes.

## 22. Exceptions

Exceptions MAY be introduced when project-specific requirements justify alternative scene or node structures.

Exceptions SHOULD:

- Have a clear technical justification.
- Identify affected scenes and features.
- Explain relevant ownership and lifecycle implications.
- Preserve maintainability.
- Receive project owner approval when they introduce significant architectural changes.
- Be documented when they establish a reusable exception.

## 23. Related Documents

These conventions SHOULD be used alongside:

- `docs/00_studio_standards/development_philosophy.md`
- `docs/00_studio_standards/naming_conventions.md`
- `docs/00_studio_standards/project_structure_standards.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/00_studio_standards/definition_of_done.md`
- `docs/02_technical_standards/architecture_guidelines.md`
- `docs/02_technical_standards/engine_standards.md`
- `docs/02_technical_standards/gdscript_standards.md`
- `docs/02_technical_standards/event_and_signal_guidelines.md`
- `docs/02_technical_standards/resource_management.md`
- `docs/02_technical_standards/data_persistence_guidelines.md`
- `docs/02_technical_standards/performance_guidelines.md`
- `docs/02_technical_standards/asset_pipeline.md`
- `docs/02_technical_standards/adr/README.md`
- `docs/01_game_design_guidelines/ui_ux_design_guidelines.md`
- Applicable documents in `docs/05_qa_standards/`

Only documents that physically exist in the repository SHOULD be registered as active references in the documentation inventory.

## 24. Maintenance

These conventions SHOULD be reviewed when:

- Godot changes scene or node behavior.
- The studio adopts new scene composition practices.
- Repeated architectural issues reveal weaknesses in current conventions.
- Project experience identifies more maintainable scene structures.
- New project requirements introduce different scene lifecycle needs.

Changes MUST preserve the document's purpose as a reusable studio-wide technical standard.