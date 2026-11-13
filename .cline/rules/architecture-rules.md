
# Architecture Rules

## Purpose

Define the architectural principles that all game implementation work must follow.

These rules prioritize maintainability, modularity, testability, and controlled complexity in a solo-developed Godot project.

## 1. General Principles

- Follow separation of concerns.
- Prefer composition over inheritance when appropriate.
- Keep systems loosely coupled and highly cohesive.
- Apply SOLID principles where they provide practical value.
- Avoid unnecessary abstractions, frameworks, and design patterns.
- Prefer explicit dependencies over hidden global dependencies.
- Keep gameplay logic independent from presentation wherever practical.
- Avoid introducing architecture that is more complex than the problem requires.
- Preserve existing architectural decisions unless a change is justified and approved.

## 2. Inspect Before Implementing

Before modifying architecture or implementing a significant feature:

1. Inspect the existing project structure.
2. Identify relevant scenes, scripts, resources, and autoloads.
3. Identify dependencies and communication paths.
4. Search for existing functionality that can be reused.
5. Check relevant architecture documentation and ADRs.
6. Identify potential side effects before proposing changes.

Do not create a parallel implementation of an existing system without justification.

## 3. Scene and Node Architecture

- Scenes should represent cohesive, reusable game entities or interface components.
- Keep scene responsibilities focused.
- Avoid excessively large scenes with unrelated responsibilities.
- Prefer reusable scenes for repeated gameplay objects.
- Use scene inheritance only when there is a meaningful shared structure.
- Avoid deep and fragile scene inheritance hierarchies.
- Keep node hierarchies understandable and intentional.
- Use composition and child scenes to build complex entities.
- Avoid tightly coupling unrelated scenes through direct node paths.

## 4. Script Responsibilities

- Each script should have a clear responsibility.
- Avoid monolithic scripts that control unrelated systems.
- Separate gameplay rules, input handling, presentation, persistence, and UI responsibilities when appropriate.
- Avoid duplicating business or gameplay logic across scripts.
- Keep functions focused and reasonably small.
- Avoid excessive dependencies between scripts.
- Use signals for appropriate event-driven communication.
- Do not use signals as a substitute for every direct method call.

## 5. Global State and Autoloads

- Use autoloads only for genuinely global services or state.
- Avoid turning autoloads into containers for unrelated functionality.
- Do not introduce global mutable state without justification.
- Prefer passing references or dependencies explicitly when practical.
- Document the responsibility of each autoload.
- Avoid circular dependencies between global services and gameplay systems.

## 6. Communication and Dependencies

Choose communication mechanisms based on responsibility:

- Direct references for explicit, local relationships.
- Signals for decoupled event notification.
- Resources for reusable data definitions and configuration.
- Autoloads for carefully scoped global services.
- Groups for intentional category-based node discovery.

Avoid:
- Excessive use of get_node() across unrelated scene boundaries.
- Fragile hardcoded node paths.
- Circular dependencies.
- Hidden communication channels that make execution difficult to trace.

## 7. Data and Resources

- Separate configuration data from runtime behavior where appropriate.
- Use custom Resources for reusable, structured game data when beneficial.
- Avoid hardcoding large amounts of balancing or configuration data into scripts.
- Keep resource ownership and mutation behavior clear.
- Avoid unintentionally sharing mutable Resource instances between independent entities.
- Use appropriate serialization and persistence mechanisms.

## 8. Architectural Changes

For significant architectural changes:

1. Explain the problem being solved.
2. Identify affected systems.
3. Consider alternatives.
4. Evaluate complexity, maintainability, and performance.
5. Identify migration and compatibility implications.
6. Check whether an Architecture Decision Record (ADR) is needed.

Do not silently introduce major architectural changes.

## 9. Performance

- Prefer simple, readable implementations first.
- Avoid unnecessary per-frame processing.
- Avoid expensive operations inside _process() and _physics_process().
- Use signals, timers, caching, and event-driven updates when appropriate.
- Profile before applying complex optimizations.
- Do not sacrifice maintainability for speculative performance improvements.

## 10. Validation

After architectural modifications:

- Verify scene references and resource paths.
- Check for dependency and initialization issues.
- Run relevant automated tests.
- Run the project or relevant scenes when possible.
- Check for errors and warnings.
- Update affected documentation when architecture changes.

## 11. Documentation Authority

Consult applicable documents under:

- docs/02_technical_standards/
- docs/02_technical_standards/adr/
- Project-specific technical design documents.

If these paths change, follow the actual repository structure.

When a rule conflicts with an approved ADR or project-specific architectural decision, report the conflict rather than silently overriding the decision.
