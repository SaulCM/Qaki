# Event and Signal Guidelines

## 1. Purpose

This document establishes reusable technical guidelines for designing, implementing, and maintaining event-driven communication across studio Godot projects.

Its purpose is to ensure that signals and events are used consistently, predictably, and appropriately to facilitate communication between systems without introducing unnecessary coupling or complexity.

These guidelines cover:

- Godot signals.
- Event-driven communication.
- Signal naming and declaration.
- Event ownership and responsibilities.
- Signal connections and disconnections.
- Event payloads.
- Communication between features.
- Event lifecycle management.
- Event ordering and execution.
- Error handling and debugging.
- Testing event-driven behavior.

The objective is to establish clear communication contracts while preserving maintainable feature boundaries.

## 2. Scope

These guidelines apply to:

- Gameplay systems.
- User interfaces.
- Scene and node communication.
- Feature-to-feature communication.
- Global services.
- Runtime state notifications.
- Gameplay events.
- UI events.
- System lifecycle events.
- Custom event coordination mechanisms.

These guidelines primarily target Godot 4.x projects implemented in GDScript.

Specific implementations MUST remain compatible with the project's configured Godot version.

## 3. Fundamental Principles

### 3.1 Explicit Communication

Communication between systems SHOULD be intentional and understandable.

Developers SHOULD:

- Define clear communication contracts.
- Use descriptive signal names.
- Keep event responsibilities focused.
- Make important dependencies identifiable.
- Avoid hidden communication behavior.

Events SHOULD communicate meaningful occurrences rather than serve as arbitrary substitutes for direct method calls.

### 3.2 Loose Coupling

Signals SHOULD be used when a system needs to notify other systems without knowing their implementation details.

The emitting system SHOULD NOT need to know which systems receive its events unless the relationship explicitly requires that knowledge.

### 3.3 Clear Ownership

Every signal MUST have an identifiable owner.

The owning component SHOULD define:

- When the signal is emitted.
- What the signal represents.
- What information it provides.
- What conditions trigger it.
- Which lifecycle rules apply.

Signals SHOULD be declared by the system responsible for the event they represent.

### 3.4 Appropriate Communication Mechanisms

Signals are not the only valid communication mechanism.

Developers SHOULD select communication methods according to the relationship between systems.

Use:

- Direct method calls when one system explicitly requests an operation from another.
- Signals when a system announces that something happened.
- Shared data structures or resources when systems need access to common data.
- Dedicated coordination components when orchestration is genuinely required.

Developers MUST NOT use signals merely to avoid every direct dependency.

### 3.5 Simplicity

Event-driven architecture SHOULD remain proportionate to project requirements.

Developers SHOULD avoid:

- Excessive event indirection.
- Unnecessary global event buses.
- Duplicate events.
- Unclear event ownership.
- Overly generic event payloads.
- Complex event frameworks for simple communication.

## 4. Godot Signals

### 4.1 Native Signal Usage

Godot's native signal system SHOULD be the default mechanism for event-driven communication.

Signals SHOULD be declared directly in the node or component responsible for the event.

Example:

```gdscript
signal health_changed(current_health: int, maximum_health: int)
signal died
```

Native signals SHOULD be preferred over custom observer implementations when Godot's built-in functionality satisfies the requirements.

### 4.2 Signal Declaration

Signals MUST have descriptive names that communicate the event they represent.

Developers SHOULD:

- Use `snake_case`.
- Prefer clear and concise names.
- Describe meaningful occurrences or state changes.
- Include relevant information in the signal name only when necessary.
- Avoid ambiguous or excessively generic names.

Examples:

```gdscript
signal health_changed(current_health: int)
signal item_collected(item_id: String)
signal quest_completed(quest_id: String)
signal interaction_started(target: Node)
signal interaction_finished
signal player_died
```

Avoid:

```gdscript
signal event
signal update
signal changed
signal notify
signal something_happened
```

### 4.3 Signal Declaration Location

Signals SHOULD be declared in the component that owns the corresponding event.

Examples:

| Event | Appropriate owner |
|---|---|
| Player health changed | Player health component or player system |
| Item collected | Inventory or collection system |
| Quest completed | Quest system |
| Button pressed | Button or UI component |
| Scene transition requested | Component responsible for requesting the transition |
| Audio playback completed | Audio playback component |

Signals SHOULD NOT be declared in unrelated components merely because those components need to access them.

### 4.4 Typed Signal Parameters

Signal parameters SHOULD use explicit types whenever practical.

Typed parameters improve readability and reduce communication errors.

Example:

```gdscript
signal item_collected(item_id: String, quantity: int)
signal experience_gained(amount: int)
signal target_selected(target: Node2D)
```

Developers SHOULD avoid loosely typed payloads when the expected information can be represented through a clear type.

### 4.5 Signal Documentation

Non-obvious signals SHOULD include documentation describing:

- Their meaning.
- Their emission conditions.
- Their parameters.
- Any important ordering or lifecycle expectations.

Example:

```gdscript
## Emitted after the player's health has been updated.
## Provides the current and maximum health values.
signal health_changed(current_health: int, maximum_health: int)
```

Documentation SHOULD focus on behavior that cannot be understood from the signal name and parameters alone.

## 5. Event Design

### 5.1 Event Meaning

An event MUST represent a meaningful occurrence or notification.

Events SHOULD describe what happened rather than expose unnecessary implementation details.

Examples:

- `enemy_defeated`
- `item_purchased`
- `quest_completed`
- `level_up`
- `door_unlocked`

Event names SHOULD communicate the meaning of the occurrence clearly.

### 5.2 Event Granularity

Events SHOULD represent meaningful changes at an appropriate level of detail.

Developers SHOULD avoid:

- Emitting multiple events for the same occurrence without justification.
- Creating events for trivial internal operations.
- Combining unrelated occurrences into one generic event.
- Emitting excessively frequent events when a simpler update mechanism is appropriate.

The appropriate event granularity SHOULD reflect the needs of its consumers.

### 5.3 State Change Events

Events SHOULD be emitted when the relevant state transition has actually occurred.

For example:

```gdscript
func take_damage(amount: int) -> void:
    health = max(health - amount, 0)
    health_changed.emit(health, maximum_health)

    if health == 0:
        died.emit()
```

Events SHOULD NOT announce successful state changes before the owning system has completed the relevant operation.

### 5.4 Commands and Events

Commands and events MUST be conceptually distinguished.

- A command requests that an operation be performed.
- An event announces that something has occurred.

Examples:

| Command | Event |
|---|---|
| `request_purchase(item_id)` | `item_purchased(item_id)` |
| `apply_damage(amount)` | `health_changed(value)` |
| `complete_quest(quest_id)` | `quest_completed(quest_id)` |
| `change_scene(scene_path)` | `scene_changed(scene_path)` |

Developers SHOULD use direct method calls or explicit request interfaces for commands.

Signals SHOULD generally communicate resulting events rather than act as unrestricted command dispatch mechanisms.

### 5.5 Event Payloads

Event payloads SHOULD contain only the information consumers need.

Developers SHOULD:

- Use explicit parameter types.
- Avoid unnecessarily large payloads.
- Prefer stable identifiers when passing references is unnecessary.
- Avoid exposing internal implementation details.
- Keep payload semantics consistent.

When passing node or object references, developers MUST consider their lifecycle and validity.

### 5.6 Event Immutability

Event payloads SHOULD be treated as notifications rather than shared mutable state.

Consumers SHOULD NOT modify shared event data in ways that affect other consumers.

When mutable data is necessary, ownership and modification responsibilities MUST be explicit.

## 6. Signal Connections

### 6.1 Connection Methods

Signals SHOULD be connected using Godot's supported connection mechanisms.

Example:

```gdscript
func _ready() -> void:
    health_changed.connect(_on_health_changed)
```

Developers MAY use editor-defined connections, code-defined connections, or other supported approaches.

The selected approach SHOULD remain consistent within a feature and understandable to maintainers.

### 6.2 Code-Based Connections

Code-based connections SHOULD be used when:

- Connections depend on runtime conditions.
- The relationship is established dynamically.
- The connection belongs to a specific lifecycle.
- The connection is easier to understand in code.

Example:

```gdscript
func _ready() -> void:
    player.health_changed.connect(_on_player_health_changed)


func _on_player_health_changed(current_health: int, maximum_health: int) -> void:
    update_health_display(current_health, maximum_health)
```

### 6.3 Editor-Based Connections

Editor-based connections MAY be used when they provide a clear and manageable relationship between scene-owned nodes.

Developers SHOULD avoid excessive dependence on editor-only connections when they make important communication relationships difficult to inspect or maintain.

### 6.4 Duplicate Connections

Developers MUST avoid unintended duplicate signal connections.

Before establishing a connection dynamically, developers SHOULD ensure that the connection does not already exist when repeated setup is possible.

Godot's `is_connected()` MAY be used when necessary.

Example:

```gdscript
if not health_changed.is_connected(_on_health_changed):
    health_changed.connect(_on_health_changed)
```

Duplicate connections MUST NOT be used as an implicit mechanism for repeated event execution.

### 6.5 Connection Ownership

The component responsible for establishing a connection SHOULD have a clear reason to own that connection.

Developers SHOULD avoid unrelated systems connecting themselves to arbitrary signals without a defined lifecycle or responsibility.

## 7. Disconnection and Lifecycle Management

### 7.1 Connection Lifecycle

Signal connections MUST respect the lifecycle of their participating objects.

Developers SHOULD understand when connections are established and when they should be removed.

Connections involving dynamically created or short-lived objects SHOULD receive particular attention.

### 7.2 Automatic Disconnection

Godot automatically manages certain signal connection lifecycles when objects are freed.

Developers SHOULD understand the engine's actual connection behavior rather than adding unnecessary manual cleanup.

### 7.3 Manual Disconnection

Manual disconnection SHOULD be used when a connection must stop before the connected object is destroyed.

Example:

```gdscript
func _exit_tree() -> void:
    if health_changed.is_connected(_on_health_changed):
        health_changed.disconnect(_on_health_changed)
```

The example is appropriate only when the connection's lifecycle requires explicit disconnection.

Developers MUST avoid unnecessary disconnection logic that duplicates behavior already handled by Godot.

### 7.4 Temporary Connections

Temporary connections SHOULD have clearly defined start and end conditions.

Examples include:

- Listening for an animation completion.
- Waiting for a one-time interaction.
- Receiving a temporary gameplay response.
- Tracking a short-lived node.

Godot's `CONNECT_ONE_SHOT` MAY be used when a connection should automatically disconnect after one emission.

### 7.5 Freed Objects

Developers MUST avoid accessing freed objects through retained references or event payloads.

Systems SHOULD validate references when their lifetime is not guaranteed.

## 8. Communication Between Features

### 8.1 Feature Boundaries

Signals SHOULD support communication between features without requiring direct access to their internal implementations.

Features SHOULD expose meaningful events through their public interfaces.

A feature MUST NOT require unrelated features to understand its internal node hierarchy or private implementation details.

### 8.2 Cross-Feature Communication

Cross-feature communication SHOULD use an explicit and understandable mechanism.

Appropriate mechanisms MAY include:

- Signals exposed by feature-owned components.
- Shared contracts or resources.
- Direct calls to public interfaces when the dependency is intentional.
- A dedicated coordinator when orchestration is justified.

Developers SHOULD minimize dependencies between features.

### 8.3 Shared Event Definitions

Shared event definitions MAY be introduced when multiple features genuinely require a common event contract.

Shared event definitions SHOULD:

- Represent project-wide concepts.
- Remain independent of individual feature implementations.
- Use stable and meaningful names.
- Avoid becoming a collection of unrelated notifications.

Feature-specific events SHOULD remain within their owning feature.

### 8.4 Global Event Buses

A global event bus MAY be introduced when many independent systems need to communicate through shared project-wide events and direct connections create unnecessary coupling.

A global event bus MUST NOT become the default communication mechanism for all systems.

Before introducing one, developers SHOULD evaluate:

- Whether native signals already solve the problem.
- Whether event ownership remains clear.
- Whether event flow can be traced.
- Whether debugging becomes more difficult.
- Whether event dependencies become hidden.
- Whether a smaller coordination mechanism would be sufficient.

If introduced, the event bus SHOULD:

- Have a clearly defined responsibility.
- Expose only necessary events.
- Avoid storing unrelated gameplay state.
- Use explicit typed event contracts where practical.
- Be documented and tested.

Significant global event bus architecture changes SHOULD be recorded through an ADR when appropriate.

## 9. Event Ordering and Execution

### 9.1 Emission Timing

Developers MUST understand when an event is emitted relative to the underlying state change.

Events SHOULD generally be emitted after the state they describe has been updated successfully.

The ordering of important operations SHOULD be explicit.

### 9.2 Synchronous Signals

Godot signals are normally emitted synchronously unless a deferred connection is used.

Developers SHOULD account for the fact that connected callbacks may execute during the emission call.

Signal callbacks SHOULD avoid unexpectedly changing the state of the emitting system in ways that violate its invariants.

### 9.3 Deferred Connections

Deferred signal connections MAY be used when immediate callback execution is inappropriate.

Example:

```gdscript
signal interaction_requested

func _ready() -> void:
    interaction_requested.connect(
        _on_interaction_requested,
        CONNECT_DEFERRED
    )
```

Deferred execution SHOULD be used deliberately.

Developers MUST NOT assume that deferred callbacks execute immediately or in the same call stack as the emission.

### 9.4 Reentrant Events

Developers SHOULD consider whether a signal callback can trigger another emission of the same signal or a related event.

Systems MUST protect important state transitions against unintended reentrant behavior.

### 9.5 Event Ordering Dependencies

Consumers SHOULD NOT rely on the execution order of independent signal connections unless that order is explicitly guaranteed and required.

When operation ordering matters, developers SHOULD use an explicit orchestration mechanism rather than depending on incidental connection order.

## 10. Event Reliability and Error Handling

### 10.1 Valid Event Conditions

Events MUST only be emitted when their defined conditions are satisfied.

The owning system SHOULD validate relevant state before emitting an event.

### 10.2 Missing Consumers

Events SHOULD remain valid even when no system is currently connected to them, unless the communication contract explicitly requires a consumer.

Developers SHOULD NOT assume that a signal has at least one listener.

### 10.3 Callback Responsibilities

Signal callbacks SHOULD remain focused on responding to the event.

Callbacks SHOULD:

- Validate relevant external data when necessary.
- Avoid unnecessary complex logic.
- Delegate unrelated responsibilities.
- Avoid expensive processing when it affects responsiveness.
- Handle expected failure conditions.

### 10.4 Error Visibility

Important failures inside event-driven workflows MUST be observable through appropriate diagnostics.

Developers SHOULD avoid silently ignoring errors that prevent an event consumer from performing its responsibility.

## 11. Event Performance

### 11.1 Appropriate Usage

Signals SHOULD be used for meaningful communication rather than replacing efficient direct data access or per-frame update mechanisms.

### 11.2 High-Frequency Events

Developers SHOULD evaluate the cost of frequently emitted events.

Examples include:

- Continuous movement updates.
- Frame-by-frame position changes.
- Frequent sensor or detection updates.
- Large-scale simulation notifications.

High-frequency communication SHOULD use an appropriate mechanism based on measured requirements.

### 11.3 Payload Efficiency

Event payloads SHOULD avoid unnecessary large data structures or expensive object references.

Developers SHOULD pass only the information required by consumers.

### 11.4 Optimization

Event-driven performance problems SHOULD be measured before introducing custom event infrastructure or optimization mechanisms.

Optimization MUST preserve event correctness and expected behavior.

## 12. Event Testing

### 12.1 Signal Declaration and Emission

Tests SHOULD verify that:

- Signals are declared correctly.
- Events are emitted under the intended conditions.
- Payload values are correct.
- Events are not emitted unexpectedly.
- State changes occur in the expected order.

### 12.2 Connection Testing

Tests SHOULD verify:

- Expected connections are established.
- Duplicate connections are avoided.
- Callbacks execute correctly.
- Disconnections occur when required.
- Freed objects do not cause invalid access.

### 12.3 Cross-Feature Testing

When events connect multiple features, tests SHOULD verify the complete communication flow.

Testing SHOULD confirm that changes in one feature produce the expected behavior in dependent features.

### 12.4 Edge Cases

Event-driven systems SHOULD be tested for:

- Missing listeners.
- Repeated emissions.
- Duplicate connections.
- Invalid payload values.
- Unexpected object destruction.
- Deferred callback execution.
- Reentrant event behavior.
- Scene transitions during active connections.

### 12.5 Integration Testing

Important event-driven workflows SHOULD receive integration testing when isolated unit tests cannot adequately verify the interaction between systems.

## 13. Documentation

Non-obvious event contracts SHOULD be documented.

Documentation MAY include:

- Event ownership.
- Emission conditions.
- Payload definitions.
- Connection responsibilities.
- Lifecycle expectations.
- Ordering requirements.
- Cross-feature dependencies.

Event documentation SHOULD remain close to the implementation or in the relevant feature documentation.

A separate event registry SHOULD only be introduced when the project has enough event complexity to justify maintaining one.

## 14. AI-Assisted Event and Signal Requirements

AI agents MUST follow these guidelines when implementing or modifying event-driven communication.

Agents MUST:

- Inspect existing signal declarations and connections.
- Identify event ownership.
- Follow established naming conventions.
- Use typed signal parameters where practical.
- Respect feature boundaries.
- Verify connection lifecycle behavior.
- Avoid unintended duplicate connections.
- Consider synchronous and deferred execution.
- Validate important event ordering requirements.
- Test affected communication workflows.
- Report changes to public event contracts.

Agents MUST NOT:

- Introduce unnecessary global event buses.
- Use signals as unrestricted substitutes for method calls.
- Emit events before the described state change has succeeded.
- Create unclear or overly generic event names.
- Expose private implementation details unnecessarily.
- Assume signal consumers always exist.
- Remove or rename public signals without evaluating dependent systems.

Agents SHOULD request approval before introducing significant project-wide event infrastructure or changing established cross-feature communication contracts.

## 15. Event and Signal Review Checklist

Before completing an event-driven implementation, verify:

- [ ] Each event has a clear meaning.
- [ ] Event ownership is identifiable.
- [ ] Signal names follow naming conventions.
- [ ] Parameters are typed where practical.
- [ ] Payloads contain only necessary information.
- [ ] Events are emitted after the relevant state changes.
- [ ] The communication mechanism is appropriate.
- [ ] Feature boundaries are respected.
- [ ] Connections are established at the correct lifecycle stage.
- [ ] Duplicate connections are avoided.
- [ ] Disconnection behavior is appropriate.
- [ ] Freed object references are handled safely.
- [ ] Synchronous and deferred execution are understood.
- [ ] Event ordering dependencies are explicit.
- [ ] Reentrant behavior has been considered.
- [ ] Important workflows are tested.
- [ ] Non-obvious event contracts are documented.

## 16. Exceptions

Exceptions MAY be introduced when project requirements justify alternative event-driven communication approaches.

Exceptions SHOULD:

- Have a clear technical justification.
- Identify affected systems and communication contracts.
- Explain relevant lifecycle and reliability implications.
- Be reviewed by the project owner when they affect shared architecture.
- Be documented when they introduce significant architectural decisions.

## 17. Related Documents

These guidelines SHOULD be used alongside:

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/ENGINE_STANDARDS.md`
- `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`
- `docs/02_technical_standards/adr/README.md`

Only documents that exist in the repository should be registered as active references in the documentation inventory.

## 18. Maintenance

These guidelines SHOULD be reviewed when:

- Godot changes its signal or event-related capabilities.
- The studio's architectural communication practices evolve.
- New project requirements introduce different event-handling needs.
- Repeated implementation experience reveals weaknesses in the guidelines.

Changes MUST preserve the document's purpose as a reusable studio-wide technical standard.