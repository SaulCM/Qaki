# Architecture Rules

## 1. Purpose

Define the architectural principles that all game implementation work must follow. These rules prioritize maintainability, modularity, testability, and controlled complexity in a solo-developed Godot project.

This is an operating rule. The authoritative architecture requirements remain in `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`, the project structure standards, and approved ADRs.

## 2. General principles

- Follow separation of concerns.
- Prefer composition over inheritance when appropriate.
- Keep systems loosely coupled and highly cohesive.
- Keep each script and scene responsible for one cohesive concern. Depend on declared public methods and signals rather than another component's internals.
- Avoid unnecessary abstractions, frameworks, and design patterns.
- Prefer explicit dependencies over hidden global dependencies.
- Keep gameplay logic independent from presentation wherever practical.
- Avoid architecture more complex than the problem requires.
- Preserve existing architectural decisions unless a change is justified and approved.

## 3. Inspect before implementing

Before modifying architecture or implementing a significant feature:

1. Inspect the existing project structure.
2. Identify relevant scenes, scripts, resources, and autoloads.
3. Identify dependencies and communication paths.
4. Search for existing functionality that can be reused.
5. Check relevant architecture documentation and ADRs.
6. Identify potential side effects before proposing changes.

Do not create a parallel implementation of an existing system without justification.

## 4. Scene and node architecture

- Scenes represent cohesive, reusable game entities or interface components.
- Keep scene responsibilities focused; avoid excessively large scenes with unrelated responsibilities.
- Prefer reusable scenes for repeated gameplay objects.
- Use scene inheritance only for meaningful shared structure and avoid deep, fragile hierarchies.
- Use composition and child scenes to build complex entities.
- Avoid tightly coupling unrelated scenes through direct node paths.

## 5. Script responsibilities

- Each script has a clear responsibility.
- Avoid monolithic scripts that control unrelated systems.
- Separate gameplay rules, input handling, presentation, persistence, and UI responsibilities when appropriate.
- Avoid duplicating business or gameplay logic across scripts.
- Keep functions focused and reasonably small.
- Avoid excessive dependencies between scripts.
- Use signals for appropriate event-driven communication; do not use signals as a substitute for every direct method call.

## 6. Global state and autoloads

- Use autoloads only for genuinely global services or state.
- Do not turn autoloads into containers for unrelated functionality.
- Do not introduce global mutable state without justification.
- Prefer passing references or dependencies explicitly when practical.
- Document the responsibility of each autoload.
- Avoid circular dependencies between global services and gameplay systems.

## 7. Communication and dependencies

Choose communication mechanisms based on responsibility:

- Direct references for explicit, local relationships.
- Signals for decoupled event notification.
- Resources for reusable data definitions and configuration.
- Autoloads for carefully scoped global services.
- Groups for intentional category-based node discovery.

Avoid:

- Excessive `get_node()` use across unrelated scene boundaries.
- Fragile hardcoded node paths.
- Circular dependencies.
- Hidden communication channels that make execution difficult to trace.

## 8. Data and resources

- Separate configuration data from runtime behavior where appropriate.
- Use custom Resources for reusable, structured game data when beneficial.
- Avoid hardcoding large amounts of balancing or configuration data into scripts.
- Keep resource ownership and mutation behavior clear.
- Avoid unintentionally sharing mutable Resource instances between independent entities.
- Use appropriate serialization and persistence mechanisms.

## 9. Architectural changes

For significant architectural changes:

1. Explain the problem being solved.
2. Identify affected systems.
3. Consider alternatives.
4. Evaluate complexity, maintainability, and performance.
5. Identify migration and compatibility implications.
6. Check whether an Architecture Decision Record is needed.

Do not silently introduce major architectural changes. Significant decisions require project owner approval.

## 10. Performance

- Prefer simple, readable implementations first.
- Avoid unnecessary per-frame processing.
- Avoid expensive operations inside `_process()` and `_physics_process()`.
- Use signals, timers, caching, and event-driven updates when appropriate.
- Profile before applying complex optimizations.
- Do not sacrifice maintainability for speculative performance improvements.

## 11. Validation

After architectural modifications:

- Verify scene references and resource paths.
- Check for dependency and initialization issues.
- Run relevant automated tests when available.
- Run the project or relevant scenes when possible.
- Check for errors and warnings.
- Update affected documentation when architecture changes.

## 12. Documentation authority

Consult applicable documents under:

- `docs/02_technical_standards/`
- `docs/02_technical_standards/adr/`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- Approved project-specific technical designs and ADRs under `game_project/docs/`

If these paths change, follow the actual repository structure. When a rule conflicts with an approved ADR or project-specific architectural decision, report the conflict rather than silently overriding the decision.
