# GDScript Standards

> Status: Draft (pending owner review)
> Last updated: 2026-11-15

## 1. Purpose

This rule defines how Cline must write, modify, and review GDScript in the Qaki Godot project.

It is an operating summary of the studio GDScript standards plus the constraints that govern game implementation. It does not replace the authoritative studio documents and must not contradict them.

The studio standards define the requirements. This rule defines how Cline applies them during a task.

## 2. Authority and Reading Order

Follow the authority order defined in `.cline/rules/project-context.md` (section 6):

1. Explicit instructions from the human maintainer for the current task.
2. Approved project-specific requirements and specifications in `game_project/docs/`.
3. Approved Architecture Decision Records (ADRs). `docs/02_technical_standards/adr/` holds the studio ADR process and template only; project-level ADRs for this game must be stored under `game_project/docs/technical/adr/` and must not be stored under repository-root `docs/`.
4. Applicable studio standards.
5. Applicable guidelines.
6. This rule and general engineering practice.

If this rule and an authoritative studio standard disagree, the studio standard wins. Report the conflict instead of silently choosing one.

Before writing or significantly changing GDScript, read the documents relevant to the task. Read only what the task needs; do not load the whole documentation set by default.

| Topic | Authoritative document |
|---|---|
| GDScript conventions, typing, formatting, script structure, error handling | `docs/02_technical_standards/GDSCRIPT_STANDARDS.md` |
| Names for files, classes, functions, variables, constants, signals, resources | `docs/00_studio_standards/NAMING_CONVENTIONS.md` |
| Where code, scenes, resources, and tests belong | `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md` |
| Architecture, dependencies, scene composition | `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md` |
| Scenes, nodes, node references, lifecycle usage | `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md` |
| Signals, events, connections, disconnection | `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md` |
| Resource ownership, sharing, mutation, lifecycle | `docs/02_technical_standards/RESOURCE_MANAGEMENT.md` |
| Configuration data and save data | `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md` |
| Performance-sensitive code | `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md` |
| Engine version, project settings, engine APIs | `docs/02_technical_standards/ENGINE_STANDARDS.md` |
| Tests, test organization, validation | `docs/02_technical_standards/TESTING_STRATEGY.md` and `docs/05_qa_standards/` |
| Completion and review expectations | `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md` |

## 3. Language and Project Boundaries

- Use GDScript for all game implementation.
- Do not introduce C#, GDExtension, native modules, or another language. `.cline/rules/project-context.md` permits C# only with explicit owner approval, and no such approval is recorded.
- All game scripts, scenes, resources, and assets live inside `game_project/`. `res://` resolves to `game_project/`.
- Never treat the repository root as the Godot project root.
- Target the Godot version configured in `game_project/project.godot`. Verify engine APIs against that version before relying on them; do not assume every Godot 4.x version exposes the same API.
- Third-party plugins and addons belong in `game_project/addons/` and are integrated only with owner approval. Do not edit addon internals to make a game task work.

## 4. Inspect Before Writing

Before writing or changing code:

1. Read the file(s) you intend to modify completely.
2. Search for existing implementations of the same behavior before adding new ones.
3. Determine which feature or shared area owns the responsibility, and who consumes it.
4. Identify the established patterns in that area: naming, typing, signal usage, script layout, error reporting.
5. Check whether tests already cover the behavior.

Follow the patterns that already exist in the project. Do not introduce a new style, pattern, or abstraction for a local task. If a new pattern is genuinely required, explain why and request approval before applying it more broadly.

Do not create a parallel implementation of an existing system without justification.

## 5. Naming

Studio naming conventions are authoritative. This is the GDScript-relevant subset:

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

- Use descriptive names and domain terminology. Avoid vague names such as `data`, `manager`, `handler`, or `helper` when a precise name exists.
- Boolean variables express the condition: `is_alive`, `can_interact`, `has_completed_quest`.
- Match the naming already used in the directory being edited.
- Do not rename existing files, classes, nodes, resources, or public identifiers to impose personal preference. Renaming that can break references requires justification and approval.

## 6. Static Typing

Static typing is expected throughout production GDScript wherever practical (`docs/02_technical_standards/GDSCRIPT_STANDARDS.md`, section 5).

- Type variables, function parameters, function return values, signal parameters, exported properties, and known collection contents.
- Declare `-> void` for functions that return nothing.
- Use `:=` inference when the assigned value makes the type obvious. Require explicit types for interfaces, ambiguous values, and variables assigned from several sources.
- Avoid untyped variables in production code. Limit `Variant` and intentionally dynamic values to justified cases.
- Avoid unnecessary casts. Validate objects reached through generic references with `is` checks, and validate the result of dynamic `load()` calls before use.
- Do not introduce unexplained compiler warnings. Resolve warnings rather than suppressing them; when suppression is justified, document the reason and keep it narrowly scoped. Never disable warnings globally.

## 7. Formatting and Script Structure

- Use tabs for indentation, consistent with Godot's GDScript conventions.
- One statement per line; blank lines between logical sections; consistent spacing around operators; avoid unnecessarily long lines.
- Follow the project's formatter and editor settings when one is configured.
- Follow the recommended declaration order: `@tool`, `extends`, `class_name`, `@icon`, documentation comments, signals, enums, constants, exported variables, public variables, private variables, `@onready` variables, built-in virtual methods, public methods, private methods, signal callbacks, helpers.
- Use `class_name` only for reusable, independently identifiable types. Do not register every script globally.
- Comments explain intent, constraints, and non-obvious behavior; they must not restate the code. Use `##` documentation comments for public or non-obvious APIs, and keep them accurate when implementation changes.

## 8. Responsibilities and Feature-Oriented Structure

- Place code by ownership under `game_project/`: `features/<feature>/` for feature-specific implementation, `shared/` for genuinely cross-feature code, `infrastructure/` for project-wide technical services.
- Keep related scripts, scenes, and resources together inside their owning feature. Do not introduce a type-oriented root hierarchy (`scripts/`, `scenes/`, `resources/` at repository or project root) for game functionality.
- Do not create empty directories or speculative structure. Create directories only when an actual file requires them.
- Each script has one clear responsibility. Avoid monolithic scripts that combine unrelated gameplay, UI, persistence, and coordination logic.
- Separate gameplay rules, input handling, presentation, persistence, and UI responsibilities where practical.
- Prefer composition over inheritance. Use inheritance only for a genuine, stable type relationship, and avoid deep hierarchies.
- Apply SOLID principles where they provide practical value. Do not add abstractions, interfaces, frameworks, or design patterns that the requirements do not justify.
- Do not duplicate gameplay or business logic across scripts. Extract shared code only when it is genuinely reused and has a clear owner.
- Avoid circular dependencies between features. Prefer explicit dependencies, public interfaces, and signals over hidden coupling.
- Keep gameplay logic independent from presentation wherever practical.

## 9. Godot Lifecycle and Engine Conventions

- Use lifecycle methods according to their intent: `_init()` for data construction, `_enter_tree()` and `_ready()` for scene wiring, `_process(delta)` for frame-dependent updates, `_physics_process(delta)` for physics-synchronized updates, `_input(event)` and `_unhandled_input(event)` for input, `_exit_tree()` for cleanup.
- Do not distribute initialization arbitrarily across lifecycle methods. Understand execution order before overriding a method.
- Disable processing when it is no longer needed. Avoid expensive or unrelated work, repeated scene-tree searches, and repeated resource loading inside per-frame callbacks.
- Node references: use `@onready` for references that require tree entry, `get_node()` only when the node is guaranteed to exist, `get_node_or_null()` when it is optional. Keep `$Path` usage limited to clear, stable scene relationships, and avoid long fragile node paths.
- Use `InputMap` actions rather than hardcoded physical keys when configurable actions exist. Keep input handling separate from unrelated gameplay logic.
- Respect the physics lifecycle and physics API requirements. Do not mutate physics state at unsafe execution points.
- After `await`, assume the object or scene may have changed or been freed; re-validate before continuing.
- Free nodes with `queue_free()`, release references that are no longer needed, and avoid leaking connections or retained Resources.

## 10. Signals, Resources, and Autoloads

- Signals: follow `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md` for declarations, payload types, connection, disconnection, ordering, and lifecycle. Use signals for decoupled event notification, not as a replacement for every direct method call.
- Resources: follow `docs/02_technical_standards/RESOURCE_MANAGEMENT.md`. Treat shared definitions as immutable configuration after initialization, understand that repeated `load()` calls may return the same cached instance, duplicate when independent mutable state is required, and validate dynamically loaded resource types.
- Autoloads: reserve them for genuinely project-wide services. Do not use autoloads as storage for unrelated feature state. Adding, removing, or changing an autoload changes global architecture and `game_project/project.godot`; request approval first.
- Groups: use only for intentional category-based discovery, not as a generic lookup mechanism.

## 11. Error Handling and Diagnostics

- Validate external or untrusted input at the boundaries where it enters the system. Do not repeat validation for values guaranteed by a well-defined internal contract.
- Make important preconditions explicit and use early returns to keep control flow readable.
- Report failures with enough context to identify them, using `push_error()`, `push_warning()`, `assert()`, explicit failure return values, or explicit error handling.
- Assertions detect violated development assumptions; they do not replace runtime validation of external input or recoverable failures.
- Never silently ignore an important failure. The caller receives a result or a diagnostic.
- Do not leave debug `print()` calls in committed code, and do not use `print()` as the error-reporting mechanism.

## 12. Performance

- Write the simple, readable implementation first.
- Optimize only with evidence: profiling results or a clear, specific performance requirement.
- Do not add caching, pooling, or per-frame tricks speculatively. Any cache needs a clear invalidation strategy.
- Follow `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md` and the performance rules in `.cline/rules/architecture-rules.md`.

## 13. Tests and Validation

- Add or update tests when the change affects testable behavior, when a test already covers the area, or when the task requires them. Follow `docs/02_technical_standards/TESTING_STRATEGY.md` and the applicable documents in `docs/05_qa_standards/`.
- Use the testing framework and execution method the project has adopted. The project has not yet established a test suite or runner under `game_project/tests/`; when no automated tests exist for the affected area, state that explicitly instead of implying coverage.
- Validate by parsing the script and, where possible, running the project or the affected scene. Report the errors and warnings actually observed.
- Distinguish clearly between static inspection and runtime validation. Never claim code was run, tested, or verified when it was not.
- The GitHub Actions workflows under `.github/workflows/` are currently unconfigured placeholders. Do not assume automated checks will catch a mistake.

## 14. Scope Discipline

- Modify only files required by the task.
- Preserve the surrounding code's existing style and structure; do not reformat or refactor untouched code.
- Do not perform drive-by cleanups, renames, or unrelated improvements.
- Do not modify `game_project/project.godot`, engine settings, autoloads, or addon internals unless the task requires it and approval has been given.
- If you find a problem outside the task scope, report it instead of fixing it.

## 15. Request Owner Approval Before

- Introducing C#, GDExtension, native code, or another language.
- Adding, removing, or replacing third-party plugins or addons in `game_project/addons/`.
- Adding, removing, or changing an autoload.
- Introducing a project-wide convention, shared abstraction, or new architectural pattern.
- Changing feature boundaries, shared interfaces, or resource ownership.
- Changing engine version, project-wide settings, or rendering and physics configuration.
- Modifying or migrating save-data formats or persistent data contracts.
- Making destructive changes to existing scenes, resources, or scripts.

## 16. Prohibited Actions

Cline must not:

- Introduce a language other than GDScript.
- Bypass or ignore established architecture and feature boundaries.
- Ignore existing project conventions or invent competing ones.
- Create a parallel implementation of an existing system.
- Introduce global mutable state or unnecessary abstractions without justification.
- Suppress warnings to hide defects.
- Claim that code was tested or validated when it was not.
- Modify unrelated scripts, scenes, or resources.
- Rewrite existing public interfaces without checking their consumers.

## 17. Review Checklist

Before reporting GDScript work as complete:

- [ ] The implementation satisfies the requested behavior and stays within scope.
- [ ] The relevant studio documents were actually read.
- [ ] Existing implementations and patterns were inspected first.
- [ ] Naming follows `docs/00_studio_standards/NAMING_CONVENTIONS.md` and the conventions already used locally.
- [ ] Static typing is used where practical, and return types are declared.
- [ ] Functions and scripts have clear, focused responsibilities.
- [ ] Files are placed by feature ownership under `game_project/`.
- [ ] Godot lifecycle methods are used correctly, and processing is disabled when unnecessary.
- [ ] Signals, resources, autoloads, and node references follow their respective studio documents.
- [ ] Errors and edge cases are handled and reported, not swallowed.
- [ ] Tests were added or updated where the change requires them, or the absence of tests is stated.
- [ ] No unexplained warnings or errors remain.
- [ ] No unrelated files were modified.

## 18. Related Workspace Rules

- `.cline/rules/project-context.md` — repository roots, directory responsibilities, authority order.
- `.cline/rules/architecture-rules.md` — architectural constraints for implementation.
- `.cline/rules/asset-rules.md` — handling of scenes, resources, and assets as files.
- `.cline/rules/git-workflow.md` — branch, commit, and safety requirements for the resulting change.
- `.cline/rules/documentation-management.md` — documentation duties when behavior or design documentation changes.
