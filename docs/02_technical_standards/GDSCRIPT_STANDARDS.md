# GDScript Standards

## 1. Purpose

This document establishes the studio-wide coding standards for writing, reviewing, and maintaining GDScript code in Godot projects.

Its purpose is to ensure that scripts are:

- Readable and consistent.
- Maintainable and reusable.
- Properly structured.
- Type-safe where practical.
- Efficient and reliable.
- Compatible with the project's configured Godot version.
- Easy to test, debug, and extend.

These standards establish common implementation practices across studio projects while allowing individual projects to define additional requirements when justified.

## 2. Scope

These standards apply to all GDScript code developed for studio Godot projects, including:

- Gameplay systems.
- Feature-specific logic.
- UI controllers.
- Scene and node scripts.
- Resources and data models.
- Autoloads and global services.
- Tools and editor scripts.
- Automated tests.
- Runtime integrations.

These standards target Godot 4.x and MUST be adapted when a project uses a different engine version.

C# and other programming languages are outside the scope of this document.

## 3. General Coding Principles

### 3.1 Readability First

Code MUST be written primarily for human understanding and maintenance.

Developers SHOULD:

- Prefer clear expressions over clever implementations.
- Use descriptive names.
- Keep functions focused.
- Avoid unnecessary nesting.
- Make dependencies explicit.
- Follow consistent formatting.
- Document non-obvious behavior.

Code SHOULD communicate its intent without requiring excessive comments.

### 3.2 Simplicity

Implementations SHOULD be as simple as reasonably possible while satisfying the requirements.

Developers MUST avoid:

- Premature abstraction.
- Unnecessary inheritance.
- Overly generic systems.
- Unjustified design patterns.
- Duplicate functionality.
- Excessive configuration.
- Unnecessary indirection.

Complexity MUST be justified by actual requirements.

### 3.3 Consistency

Developers MUST follow established project conventions.

When modifying existing code, developers SHOULD preserve its established structure and style unless the task explicitly requires improvement.

New implementations MUST NOT introduce alternative conventions without justification.

### 3.4 Explicitness

Important behavior, dependencies, types, and responsibilities SHOULD be explicit.

Developers SHOULD avoid relying on implicit assumptions when those assumptions can cause errors or make code difficult to understand.

### 3.5 Maintainability

Scripts SHOULD be designed to accommodate expected changes without unnecessary modifications to unrelated systems.

Developers SHOULD prioritize:

- High cohesion.
- Low coupling.
- Clear responsibilities.
- Small and focused functions.
- Stable interfaces.
- Appropriate separation of concerns.

## 4. GDScript Language Conventions

### 4.1 Naming Conventions

All scripts MUST follow:

`docs/00_studio_standards/NAMING_CONVENTIONS.md`

The following conventions apply:

| Element | Convention | Example |
|---|---|---|
| Script files | `snake_case` | `player_controller.gd` |
| Classes | `PascalCase` | `PlayerController` |
| Variables | `snake_case` | `current_health` |
| Constants | `SCREAMING_SNAKE_CASE` | `MAX_HEALTH` |
| Functions | `snake_case` | `calculate_damage()` |
| Signals | `snake_case` | `health_changed` |
| Enum types | `PascalCase` | `MovementState` |
| Enum members | `SCREAMING_SNAKE_CASE` | `IDLE` |
| Private/internal members | Leading underscore | `_cached_value` |

Developers MUST use descriptive names and avoid unnecessary abbreviations.

### 4.2 Formatting

Scripts MUST use consistent formatting.

Developers SHOULD follow these rules:

- Use tabs for indentation, consistent with Godot's GDScript conventions.
- Use one statement per line.
- Separate logical sections with blank lines.
- Keep expressions readable.
- Use consistent spacing around operators.
- Avoid unnecessarily long lines.
- Use trailing commas in multiline collections and argument lists when appropriate and supported.
- Follow the project's configured formatter and editor settings.

Example:

```gdscript
extends CharacterBody2D
class_name PlayerController

const MAX_HEALTH: int = 100

var current_health: int = MAX_HEALTH


func take_damage(amount: int) -> void:
	if amount <= 0:
		return

	current_health = maxi(current_health - amount, 0)
```

Formatting SHOULD be automated through the project's chosen tooling when practical.

### 4.3 Script Organization

Scripts SHOULD follow a consistent logical declaration order.

Recommended order:

1. `@tool`, when required.
2. `extends`.
3. `class_name`, when required.
4. `@icon`, when required.
5. Documentation comments.
6. Signals.
7. Enums.
8. Constants.
9. Exported variables.
10. Public variables.
11. Private/internal variables.
12. `@onready` variables.
13. Built-in virtual methods.
14. Public methods.
15. Private/internal methods.
16. Signal callbacks.
17. Other specialized helpers.

This order MAY be adapted when a different arrangement improves clarity.

Scripts MUST NOT be organized into unnecessary sections merely to follow a rigid template.

### 4.4 Class Declaration

Use `class_name` when a script represents a reusable, independently identifiable type that benefits from global class registration.

Example:

```gdscript
extends Resource
class_name WeaponData
```

Developers SHOULD NOT register every script globally by default.

Scene-specific controllers and implementation details SHOULD generally remain scoped to their owning scenes or features unless broader access is justified.

### 4.5 Comments and Documentation

Comments SHOULD explain intent, constraints, non-obvious behavior, or important implementation decisions.

Comments MUST NOT simply repeat what the code already expresses.

Avoid:

```gdscript
# Subtract damage from health.
current_health -= damage
```

Prefer:

```gdscript
# Damage is clamped to prevent health from becoming negative.
current_health = maxi(current_health - damage, 0)
```

Public APIs and non-obvious functions SHOULD include documentation comments.

Example:

```gdscript
## Applies damage to the character.
## Emits health_changed after the health value has been updated.
func take_damage(amount: int) -> void:
	pass
```

Comments MUST remain accurate when implementation changes.

## 5. Static Typing

### 5.1 General Requirements

Static typing SHOULD be used throughout production GDScript code whenever practical.

Developers SHOULD explicitly declare:

- Variable types.
- Function parameter types.
- Function return types.
- Signal parameter types.
- Exported property types.
- Collection element types when supported and appropriate.

Example:

```gdscript
var current_health: int = 100
var movement_speed: float = 250.0
var is_alive: bool = true

func calculate_damage(base_damage: int, multiplier: float) -> int:
	return roundi(base_damage * multiplier)
```

### 5.2 Type Inference

Type inference MAY be used when the assigned value makes the type clear.

Example:

```gdscript
var player_name := "Player"
var movement_speed := 250.0
```

Explicit typing SHOULD be preferred when:

- The intended type is not immediately obvious.
- The variable represents an important interface.
- The type improves readability.
- The variable may be assigned values from different sources.
- The type prevents common errors.

### 5.3 Avoid Untyped Variables

Developers SHOULD avoid untyped variables in production code.

Avoid:

```gdscript
var data
var result
```

Prefer:

```gdscript
var data: Dictionary = {}
var result: int = 0
```

Use `Variant` or intentionally dynamic values only when dynamic typing is necessary.

Such usage SHOULD be limited and justified.

### 5.4 Function Return Types

Functions SHOULD explicitly declare return types.

Use `void` when a function does not return a value.

Example:

```gdscript
func update_health(value: int) -> void:
	current_health = value


func get_health_percentage() -> float:
	return float(current_health) / float(MAX_HEALTH)
```

### 5.5 Typed Collections

Typed collections SHOULD be used when their contents have a known type.

Example:

```gdscript
var inventory_items: Array[InventoryItem] = []
var active_enemies: Array[Node2D] = []
```

Dictionaries SHOULD use clear key and value conventions.

When dictionary contents have a predictable structure, developers SHOULD consider a typed Resource, RefCounted class, or other explicit data representation instead of relying on loosely structured dictionaries.

### 5.6 Type Safety

Developers MUST avoid unnecessary type casts and unsafe assumptions.

When accessing objects through generic references, validate their types when required.

Example:

```gdscript
var target := get_node_or_null("Target")

if target is CharacterBody2D:
	target.velocity = Vector2.ZERO
```

Type checks SHOULD be used where object identity or runtime type is not guaranteed.

### 5.7 Warnings

Production scripts SHOULD NOT introduce unexplained compiler warnings.

Warnings SHOULD be resolved rather than suppressed.

Warning suppression MAY be used when:

- The warning is intentional.
- The reason is documented.
- The suppression is limited to the necessary scope.

Developers MUST NOT disable warnings globally to conceal implementation problems.

## 6. Variables, Constants, and State

### 6.1 Variable Declaration

Variables SHOULD be declared as close as practical to the scope where they are needed.

Developers SHOULD avoid unnecessary class-level state.

Local variables SHOULD be preferred when state does not need to persist between function calls.

### 6.2 Constants

Use constants for values that are fixed and meaningful within the script or class.

Example:

```gdscript
const MAX_HEALTH: int = 100
const DEFAULT_MOVEMENT_SPEED: float = 250.0
```

Avoid unexplained magic numbers.

Prefer named constants when a value has domain meaning or is reused.

Not every literal value requires a constant. Simple values used once in obvious contexts MAY remain inline.

### 6.3 State Management

State SHOULD be explicit and have a clear owner.

Developers SHOULD:

- Keep state local to the responsible component.
- Avoid unnecessary shared mutable state.
- Define valid state transitions.
- Prevent contradictory state combinations.
- Validate state before performing important operations.

When multiple related values represent one logical state, consider an enum or dedicated data structure.

### 6.4 Boolean Variables

Boolean variables SHOULD express clear conditions.

Avoid ambiguous names such as:

```gdscript
var active: bool
var status: bool
var flag: bool
```

Prefer:

```gdscript
var is_alive: bool
var can_interact: bool
var has_completed_quest: bool
```

### 6.5 Avoid Unnecessary Global State

Global state SHOULD be limited to genuinely project-wide responsibilities.

Developers MUST NOT use autoloads as convenient storage for unrelated feature state.

Feature-owned state SHOULD remain within the owning feature unless a clear shared ownership model exists.

## 7. Functions and Methods

### 7.1 Single Responsibility

Functions SHOULD perform one coherent responsibility.

Developers SHOULD keep functions focused and avoid combining unrelated operations.

A function MAY coordinate several smaller operations when orchestration is its intended responsibility.

### 7.2 Function Length

Functions SHOULD remain short enough to understand without excessive scrolling or mental context switching.

There is no universal line limit.

Developers SHOULD extract meaningful operations when doing so improves readability, reuse, or testability.

Unnecessary extraction into tiny functions SHOULD be avoided.

### 7.3 Parameters

Functions SHOULD accept only the information required to perform their responsibility.

Developers SHOULD:

- Use descriptive parameter names.
- Declare parameter types.
- Avoid excessive parameter lists.
- Group related information into a dedicated data structure when appropriate.
- Avoid passing unnecessary node references or global objects.

Large parameter lists MAY indicate that a function has too many responsibilities or that a dedicated data structure is needed.

### 7.4 Return Values

Functions SHOULD return meaningful results when callers need them.

Avoid modifying external state unnecessarily when returning a result would make behavior clearer.

Functions SHOULD NOT use return values and side effects in confusing or contradictory ways.

### 7.5 Early Returns

Early returns SHOULD be used to simplify conditional logic and reduce nesting.

Example:

```gdscript
func interact(target: Node) -> void:
	if target == null:
		return

	if not target.has_method("interact"):
		return

	target.interact()
```

### 7.6 Avoid Excessive Nesting

Deeply nested conditionals SHOULD be simplified where practical.

Developers MAY use:

- Early returns.
- Guard clauses.
- Extracted helper functions.
- State-based logic.
- Clearly defined conditions.

The resulting implementation MUST remain easy to understand.

### 7.7 Avoid Boolean Parameter Ambiguity

Functions with multiple boolean parameters SHOULD be avoided when their meaning is unclear.

Avoid:

```gdscript
configure_enemy(true, false, true)
```

GDScript has no named-argument call syntax. Prefer a typed configuration object or a configuration Resource when several settings form a meaningful set:

```gdscript
class_name EnemySettings
extends Resource

@export var is_aggressive: bool = false
@export var can_patrol: bool = true
@export var can_flee: bool = true
```

```gdscript
var settings := EnemySettings.new()
settings.is_aggressive = true
settings.can_patrol = false
settings.can_flee = true
configure_enemy(settings)
```

A single boolean parameter is acceptable when the function name and the call site make its meaning clear.

## 8. Classes and Responsibilities

### 8.1 Class Cohesion

Each script SHOULD have a clear and focused responsibility.

A script SHOULD NOT become a central location for unrelated gameplay, UI, persistence, and coordination logic.

### 8.2 Inheritance

Inheritance SHOULD be used when there is a genuine and stable relationship between types.

Developers SHOULD prefer composition when behavior needs to be combined or reused independently.

Deep inheritance hierarchies SHOULD be avoided.

### 8.3 Composition

Composition SHOULD be preferred for combining independent responsibilities.

Godot nodes, Resources, and smaller GDScript classes MAY be used to compose functionality.

Components SHOULD expose clear interfaces and avoid unnecessary knowledge of their consumers.

### 8.4 Reusable Classes

Reusable classes SHOULD be introduced when multiple systems genuinely need the same behavior or when a responsibility benefits from independent ownership.

Developers MUST avoid creating abstractions solely for hypothetical future reuse.

### 8.5 Static Functions and Variables

Static members MAY be used for stateless operations or class-level responsibilities.

Developers SHOULD NOT use static members as a substitute for proper dependency management or uncontrolled global state.

## 9. Godot-Specific Coding Practices

### 9.1 Scene and Node Responsibilities

Scripts attached to nodes SHOULD have responsibilities appropriate to their position in the scene hierarchy.

Developers SHOULD:

- Keep scene controllers focused.
- Avoid placing all feature logic in a single root node.
- Use components for independently meaningful responsibilities.
- Avoid unnecessary node dependencies.
- Keep node ownership and lifecycle behavior understandable.

### 9.2 Node References

Node references SHOULD be explicit and reliable.

Developers SHOULD use:

- `@onready` for references that require the node to be inside the scene tree.
- `get_node()` when the node is required and its existence is guaranteed.
- `get_node_or_null()` when the node is optional or may not exist.

Example:

```gdscript
@onready var health_bar: ProgressBar = $HealthBar
```

Use of `$` SHOULD remain limited to clear and stable scene relationships.

### 9.3 Avoid Fragile Node Paths

Developers SHOULD avoid unnecessary dependence on long or fragile node paths.

When scene structure changes frequently, consider:

- Dedicated child components.
- Explicit references.
- Signals.
- Exported node references where appropriate.
- Stable scene interfaces.

Node paths MUST NOT be treated as globally stable identifiers without justification.

### 9.4 Lifecycle Methods

Godot lifecycle methods SHOULD be used according to their intended responsibilities.

Common methods include:

- `_init()`
- `_enter_tree()`
- `_ready()`
- `_process(delta)`
- `_physics_process(delta)`
- `_input(event)`
- `_unhandled_input(event)`
- `_exit_tree()`
- `_notification(what)`

Developers MUST understand the execution order and lifecycle implications of the methods they override.

Initialization logic SHOULD be placed in the appropriate lifecycle method rather than being distributed arbitrarily.

### 9.5 Processing Methods

`_process(delta)` SHOULD be used for frame-dependent updates that do not require physics synchronization.

`_physics_process(delta)` SHOULD be used for physics-related updates that require fixed-step processing.

Developers SHOULD disable processing when it is no longer needed.

Avoid placing expensive or unrelated operations inside per-frame callbacks.

### 9.6 Signals

Signals SHOULD be used for event-driven communication when appropriate.

All signal declarations, connections, payloads, and lifecycle behavior MUST follow:

`docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md`

### 9.7 Resources

Godot Resources SHOULD be used for reusable data definitions and configuration when appropriate.

Developers MUST understand that Resources can be shared between nodes and scenes.

Mutable Resource state SHOULD be managed carefully to avoid unintended changes affecting multiple consumers.

Use resource duplication or separate runtime state when independent mutable instances are required.

### 9.8 Autoloads

Autoloads SHOULD be reserved for genuinely project-wide services or state.

Appropriate examples MAY include:

- Global audio coordination.
- Scene transition coordination.
- Persistent session management.
- Centralized configuration access.

Developers MUST NOT use autoloads as a default location for all reusable functionality.

### 9.9 Input Handling

Input handling SHOULD use Godot's InputMap and configured actions.

Developers SHOULD avoid hardcoding physical keys when configurable input actions are appropriate.

Example:

```gdscript
if Input.is_action_just_pressed("interact"):
	interact()
```

Input responsibilities SHOULD remain separate from unrelated gameplay logic when practical.

### 9.10 Physics

Physics operations MUST respect Godot's physics lifecycle and API requirements.

Developers SHOULD:

- Perform physics-related updates in the appropriate callbacks.
- Use physics queries appropriately.
- Avoid modifying physics state at unsafe execution points.
- Understand collision layers and masks.
- Avoid unnecessary physics queries.

### 9.11 Asynchronous Operations

When using `await`, developers MUST consider the possibility that the object or scene may change or be destroyed before execution resumes.

Example:

```gdscript
func play_animation() -> void:
	await animation_player.animation_finished

	if not is_inside_tree():
		return

	_on_animation_completed()
```

The exact validation required depends on the operation and lifecycle.

Asynchronous logic SHOULD remain understandable and avoid unnecessary state dependencies.

## 10. Error Handling and Validation

### 10.1 Input Validation

Functions SHOULD validate external or untrusted input when necessary.

Validation SHOULD be proportional to the risk and responsibility of the function.

Developers SHOULD NOT repeatedly validate values that are guaranteed by a well-defined internal contract unless doing so provides meaningful protection.

### 10.2 Preconditions

Important preconditions SHOULD be explicit.

Example:

```gdscript
func purchase_item(item_id: String) -> bool:
	if item_id.is_empty():
		return false

	if not inventory.has_item(item_id):
		return false

	return inventory.purchase(item_id)
```

### 10.3 Error Reporting

Errors SHOULD provide enough context to identify the failure.

Developers SHOULD use appropriate Godot diagnostics, including:

- `push_warning()`
- `push_error()`
- `assert()`
- Return values indicating failure.
- Explicit error handling.

Example:

```gdscript
if resource == null:
	push_error("Failed to load required weapon resource.")
	return
```

### 10.4 Assertions

Assertions SHOULD be used to detect violated development assumptions and invariants.

Assertions MUST NOT replace necessary runtime validation of external input or recoverable failures.

### 10.5 Silent Failures

Important failures MUST NOT be silently ignored.

When an operation cannot complete, its caller SHOULD receive an appropriate result or diagnostic.

## 11. Performance and Memory

### 11.1 Performance Awareness

Developers SHOULD consider performance when designing frequently executed or resource-intensive code.

Optimization SHOULD be based on profiling or clear evidence.

### 11.2 Avoid Unnecessary Work

Developers SHOULD avoid:

- Repeated expensive calculations.
- Unnecessary object creation.
- Excessive scene-tree searches.
- Unnecessary per-frame operations.
- Repeated resource loading.
- Redundant data transformations.

### 11.3 Caching

Caching MAY be used when repeated calculations or lookups are demonstrably expensive.

Cached values MUST have a clear invalidation strategy.

Developers SHOULD avoid caches that introduce more complexity than the performance benefit justifies.

### 11.4 Memory Management

Developers MUST understand Godot's object lifetime and reference-counting behavior.

Developers SHOULD:

- Release references when no longer needed.
- Avoid retaining unnecessary nodes or Resources.
- Use `queue_free()` appropriately for nodes.
- Consider object ownership.
- Avoid memory leaks caused by long-lived references or event connections.

### 11.5 Object Creation

Repeated object creation in performance-sensitive code SHOULD be evaluated.

Object pooling MAY be introduced when profiling demonstrates a meaningful benefit.

Pooling MUST NOT be introduced prematurely.

## 12. Data and Configuration

### 12.1 Separation of Logic and Data

Reusable configuration SHOULD be separated from implementation logic when doing so improves maintainability.

Godot Resources SHOULD be considered for:

- Character statistics.
- Item definitions.
- Enemy configuration.
- Ability parameters.
- Gameplay tuning values.

### 12.2 Exported Variables

Exported variables SHOULD be used when values need to be configured through the Godot Inspector.

Example:

```gdscript
@export var movement_speed: float = 250.0
@export var maximum_health: int = 100
```

Exported properties SHOULD have meaningful defaults and appropriate type constraints.

### 12.3 Runtime State

Developers SHOULD distinguish between:

- Configuration data.
- Runtime state.
- Persistent data.
- Derived or cached values.

These categories SHOULD NOT be mixed unnecessarily.

Persistent data and save/load behavior MUST follow:

`docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md`

### 12.4 Magic Values

Important gameplay and technical values SHOULD be named or stored in appropriate configuration data.

Developers SHOULD avoid scattering duplicated tuning values across unrelated scripts.

Project-specific balancing decisions SHOULD remain in the relevant game design documentation or configuration assets.

### 12.5 Player-Facing Text

Player-facing text SHOULD be stored in configurable data or localisation Resources rather than embedded in gameplay logic, so that wording can be reviewed, corrected, and translated without modifying scripts.

Hardcoded player-facing strings MAY be used for temporary development, debugging, or placeholder output, but MUST be externalised before the interface is accepted.

## 13. Dependencies and Architecture

### 13.1 Dependency Direction

Scripts MUST respect the project's approved architecture and feature boundaries.

The project structure MUST follow:

`docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`

### 13.2 Feature-Oriented Organization

GDScript files MUST be organized according to their owning feature or system.

Developers MUST NOT introduce a type-oriented root hierarchy as an alternative to the approved feature-oriented structure.

### 13.3 Shared Functionality

Reusable scripts SHOULD be placed in `shared/` only when they are genuinely used by multiple features and do not belong to a single feature.

Shared code MUST NOT depend on individual feature implementations.

### 13.4 Infrastructure

Project-wide technical services SHOULD be placed in `infrastructure/` according to their responsibilities.

Developers SHOULD avoid placing feature-specific gameplay behavior in infrastructure.

### 13.5 Circular Dependencies

Circular dependencies between features or components MUST be avoided.

Signals, shared contracts, and explicit public interfaces SHOULD be considered when they provide a simpler dependency structure.

### 13.6 Dependency Injection

Dependencies SHOULD be explicit and manageable.

Developers MAY use constructor parameters, exported references, initialization methods, or other appropriate Godot mechanisms.

A dependency injection framework SHOULD NOT be introduced unless project complexity justifies it.

## 14. Testing and Testability

### 14.1 Testable Code

Scripts SHOULD be designed so that important behavior can be tested independently where practical.

Developers SHOULD avoid unnecessary dependence on:

- Global mutable state.
- Hardcoded scene paths.
- Hidden runtime assumptions.
- Uncontrolled external services.
- Unpredictable timing.

### 14.2 Unit Testing

Independent logic SHOULD be tested separately when doing so provides meaningful confidence.

Examples include:

- Damage calculations.
- Inventory rules.
- Resource consumption.
- Progression calculations.
- State transitions.
- Validation functions.

### 14.3 Integration Testing

Interactions between nodes, scenes, and features SHOULD receive integration testing when isolated tests are insufficient.

### 14.4 Deterministic Behavior

Logic SHOULD be deterministic when practical.

Randomness, time dependencies, and external inputs SHOULD be controllable or replaceable during testing when they affect test reliability.

### 14.5 Test Standards

Testing implementation and execution MUST follow the applicable documents in:

`docs/05_qa_standards/`

## 15. Security and Reliability

### 15.1 Input Trust

Developers MUST NOT assume that external input is valid.

Relevant inputs SHOULD be validated before they affect important game state.

### 15.2 Persistence Integrity

Save data and loaded resources SHOULD be validated before being used.

Developers SHOULD avoid trusting serialized values without considering corruption, incompatible versions, or unexpected content.

### 15.3 Sensitive Information

Secrets, credentials, private tokens, and other sensitive information MUST NOT be embedded in scripts or committed to source control.

### 15.4 Runtime Reliability

Important systems SHOULD handle expected failure conditions without leaving the game in an inconsistent state.

Security and reliability practices SHOULD follow applicable studio and project standards.

## 16. Refactoring and Technical Debt

### 16.1 Refactoring

Refactoring SHOULD improve code structure without unintentionally changing externally observable behavior.

Developers SHOULD:

- Preserve existing functionality.
- Maintain or improve test coverage.
- Make focused changes.
- Verify affected integrations.
- Avoid combining unrelated refactoring with feature implementation.

### 16.2 Technical Debt

Known technical debt SHOULD be documented when it has meaningful impact on maintainability, reliability, or future development.

Developers SHOULD NOT introduce avoidable shortcuts that create disproportionate long-term costs.

### 16.3 Legacy Code

When working with existing code that does not follow these standards, developers SHOULD improve it incrementally.

Large-scale rewrites MUST have a clear justification and appropriate approval.

## 17. AI-Assisted GDScript Development

AI agents MUST follow these standards when creating, modifying, or reviewing GDScript code.

Agents MUST:

- Inspect the relevant scripts and scene structure before modifying code.
- Read applicable architecture and project structure documentation.
- Follow established naming and formatting conventions.
- Use static typing wherever practical.
- Declare function return types.
- Respect feature ownership and dependency boundaries.
- Use Godot APIs compatible with the configured engine version.
- Preserve existing behavior unless changes are requested.
- Handle node and Resource lifecycles correctly.
- Consider signal connections and asynchronous execution.
- Validate errors and warnings.
- Run appropriate tests and project validation.
- Report validation results accurately.

Agents MUST NOT:

- Introduce C# or another programming language under this standard.
- Introduce unnecessary frameworks or abstractions.
- Create global state without justification.
- Bypass established architecture.
- Ignore existing conventions.
- Suppress warnings without justification.
- Claim code has been tested when it has not.
- Modify unrelated scripts without a clear reason.

Agents SHOULD request owner approval before introducing significant architectural changes, new shared abstractions, or project-wide coding conventions.

## 18. Code Review Checklist

Before submitting GDScript changes for review, verify:

- [ ] The implementation satisfies the requested behavior.
- [ ] Script responsibilities are clear.
- [ ] Naming conventions are followed.
- [ ] Formatting is consistent.
- [ ] Static typing is used appropriately.
- [ ] Function signatures include appropriate return types.
- [ ] Functions have focused responsibilities.
- [ ] Class cohesion is maintained.
- [ ] Dependencies are explicit and appropriate.
- [ ] Feature-oriented organization is respected.
- [ ] Godot lifecycle methods are used correctly.
- [ ] Node and Resource references are managed safely.
- [ ] Signals follow event and signal guidelines.
- [ ] Errors and edge cases are handled appropriately.
- [ ] Performance-sensitive code has been considered.
- [ ] No unnecessary global state or abstractions were introduced.
- [ ] Tests have been added or updated where appropriate.
- [ ] No unexplained warnings or errors remain.
- [ ] Documentation is updated where necessary.

## 19. Exceptions

Exceptions MAY be made when project-specific requirements justify an alternative implementation.

Exceptions SHOULD:

- Have a clear technical justification.
- Be limited to the necessary scope.
- Preserve readability and maintainability.
- Be documented when they affect shared conventions.
- Receive project owner approval when they introduce significant architectural or technical changes.

Repeated exceptions SHOULD trigger a review of this standard.

## 20. Related Documents

These standards SHOULD be used alongside:

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/ENGINE_STANDARDS.md`
- `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md`
- `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md`
- `docs/02_technical_standards/adr/ADR_PROCESS.md`

Only documents that physically exist in the repository SHOULD be registered as active references in the documentation inventory.

## 21. Maintenance

These standards SHOULD be reviewed when:

- Godot introduces relevant GDScript language changes.
- The studio adopts new coding tools or validation practices.
- Repeated code review findings reveal weaknesses in the standards.
- Project experience identifies better implementation practices.
- Existing conventions become unnecessarily restrictive or outdated.

Changes MUST preserve the document's purpose as a reusable studio-wide GDScript coding standard.