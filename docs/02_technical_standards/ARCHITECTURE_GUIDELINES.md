# Architecture Guidelines

## 1. Purpose

This document establishes reusable architectural principles and guidelines for designing, implementing, and maintaining software architecture across studio game projects.

Its purpose is to promote architectures that are:

- Maintainable and understandable.
- Modular and appropriately decoupled.
- Scalable according to actual project needs.
- Testable and reliable.
- Consistent with the capabilities and conventions of the Godot Engine.
- Practical for small teams and solo development.

These guidelines provide a common architectural foundation without requiring every game to use an identical architecture.

## 2. Scope

These guidelines apply to:

- Game systems and gameplay features.
- Feature boundaries and system responsibilities.
- Communication between systems.
- Scene and node architecture.
- Resource and data management.
- Shared functionality.
- Global services and autoloads.
- Persistence and save systems.
- External integrations.
- Architectural changes and technical decisions.

These guidelines are primarily intended for Godot projects implemented in GDScript.

Project-specific architecture decisions may introduce additional constraints when justified and documented.

## 3. Architectural Principles

### 3.1 Simplicity Over Unnecessary Complexity

Architecture MUST solve actual project requirements rather than hypothetical future problems.

Developers SHOULD:

- Prefer straightforward solutions over unnecessary abstractions.
- Introduce architectural patterns only when they provide a clear benefit.
- Avoid excessive inheritance, indirection, and configuration layers.
- Implement the simplest design that satisfies current requirements.
- Refactor when demonstrated needs justify additional structure.

Developers MUST NOT introduce architectural complexity solely to make the project appear more sophisticated or enterprise-oriented.

### 3.2 Separation of Responsibilities

Each system, feature, class, and component SHOULD have a clearly defined responsibility.

Developers SHOULD:

- Keep unrelated responsibilities separate.
- Avoid classes that accumulate unrelated functionality.
- Separate gameplay rules from presentation where practical.
- Keep data ownership explicit.
- Minimize dependencies between unrelated systems.

A component SHOULD have a clear purpose that can be explained without describing unrelated responsibilities.

### 3.3 Modularity

Systems SHOULD be designed as cohesive modules with well-defined responsibilities and boundaries.

Modular architecture SHOULD:

- Keep implementation details internal to their owning modules.
- Expose only necessary public functionality.
- Minimize dependencies between modules.
- Support independent development and testing where practical.
- Allow systems to evolve without requiring widespread changes.

Modularity MUST NOT become an excuse to create excessive numbers of small scripts or artificial abstractions.

### 3.4 High Cohesion and Low Coupling

Related functionality SHOULD remain together, while unrelated functionality SHOULD remain independent.

Developers SHOULD:

- Group functionality according to responsibility.
- Avoid unnecessary references between features.
- Minimize knowledge of other systems' internal implementations.
- Prefer explicit contracts over assumptions about internal behavior.
- Avoid circular dependencies.

### 3.5 Composition Over Inheritance

Composition SHOULD be preferred when combining independent behaviors or responsibilities.

Inheritance MAY be used when:

- A genuine and stable parent-child relationship exists.
- Derived classes share a meaningful common contract.
- The relationship improves clarity and reduces duplication.
- The inheritance hierarchy remains manageable.

Developers SHOULD avoid deep inheritance hierarchies and inheritance used primarily for code reuse.

Godot scenes, nodes, resources, and scripts SHOULD be composed according to their responsibilities.

### 3.6 Explicit Dependencies

Dependencies SHOULD be visible, understandable, and intentional.

Developers SHOULD:

- Pass dependencies explicitly when practical.
- Use signals or other communication mechanisms when direct references are unnecessary.
- Avoid hidden dependencies through global state.
- Document non-obvious architectural dependencies.
- Keep dependency ownership clear.

Implicit dependencies SHOULD be minimized because they make systems harder to understand, test, and maintain.

### 3.7 Incremental Evolution

Architecture SHOULD evolve alongside the project.

Developers SHOULD:

- Start with an appropriate level of structure.
- Validate architectural assumptions through implementation.
- Refactor when recurring problems become evident.
- Avoid premature generalization.
- Preserve working functionality during architectural improvements.

Architecture MUST support the project's current development stage without unnecessarily restricting future changes.

## 4. Architectural Boundaries

### 4.1 Feature-Oriented Architecture

Projects MUST follow the studio's feature-oriented project structure conventions.

Game functionality SHOULD be organized around identifiable features or systems rather than broad technical categories.

Each feature SHOULD own its relevant:

- Scenes.
- GDScript files.
- Resources.
- Feature-specific assets.
- Tests.

Features SHOULD expose a limited and understandable interface to other parts of the project.

The internal implementation of a feature SHOULD remain private unless another feature has a legitimate reason to interact with it.

### 4.2 Feature Independence

Features SHOULD be developed with minimal unnecessary dependencies on other features.

A feature MUST NOT directly manipulate another feature's internal implementation when an explicit interface or communication mechanism is more appropriate.

When features need to interact, developers SHOULD prefer:

- Public methods with clearly defined responsibilities.
- Signals for event-driven communication.
- Shared data contracts or resources.
- Dedicated coordination systems when justified.

Direct references MAY be used when the dependency is simple, intentional, and appropriate.

### 4.3 Shared Functionality

The `shared/` directory MUST contain functionality genuinely reused by multiple features or functionality that has a clear project-wide responsibility.

Developers SHOULD:

- Avoid placing feature-specific functionality in `shared/`.
- Promote functionality into `shared/` only when reuse or ownership justifies it.
- Keep shared components independent of individual features.
- Avoid turning `shared/` into an unstructured collection of miscellaneous scripts.

Shared functionality MUST NOT depend on feature-specific implementations.

### 4.4 Infrastructure

The `infrastructure/` directory SHOULD contain project-wide technical services and supporting systems.

Examples include:

- Autoloads and global services.
- Configuration management.
- External integrations.
- Technical adapters.
- Project-wide infrastructure utilities.

Infrastructure SHOULD provide technical capabilities rather than accumulate unrelated gameplay responsibilities.

Infrastructure components MUST NOT become unnecessary central dependencies for every feature.

## 5. Godot Architecture Guidelines

### 5.1 Scenes and Nodes

Godot scenes SHOULD represent meaningful objects, interfaces, environments, or cohesive functional units.

Developers SHOULD:

- Keep scene responsibilities clear.
- Prefer reusable scenes when reuse provides practical value.
- Avoid excessively large scenes with unrelated responsibilities.
- Use node composition to organize behavior.
- Keep scene hierarchies understandable.
- Avoid unnecessary node depth and complexity.

Nodes SHOULD communicate through explicit references, signals, or other appropriate mechanisms.

Scene ownership and lifecycle responsibilities SHOULD be clear.

### 5.2 GDScript Responsibilities

GDScript files SHOULD contain cohesive and clearly defined functionality.

Developers SHOULD:

- Keep scripts focused on their intended responsibilities.
- Separate unrelated logic into appropriate components.
- Use typed variables, parameters, and return values where practical.
- Prefer clear public interfaces.
- Limit unnecessary dependencies.
- Avoid large scripts that manage unrelated systems.

Scripts attached to nodes SHOULD generally manage the behavior of those nodes or coordinate closely related components.

A script SHOULD NOT become a general-purpose manager simply because it is convenient to access.

### 5.3 Resources and Data

Godot Resources SHOULD be used for reusable data and configuration when appropriate.

Developers SHOULD consider Resources for:

- Feature configuration.
- Item definitions.
- Character definitions.
- Ability parameters.
- Enemy configuration.
- Progression data.
- Other reusable game data.

Data SHOULD be separated from behavior when doing so improves reuse, maintainability, or clarity.

Developers MUST understand resource sharing and mutation behavior before modifying shared Resource instances at runtime.

Runtime state SHOULD NOT unintentionally modify shared configuration resources.

### 5.4 Autoloads and Global Services

Autoloads SHOULD be introduced only when functionality genuinely requires project-wide availability or lifecycle management.

Appropriate examples may include:

- Save management.
- Audio coordination.
- Scene transitions.
- Global configuration.
- Application-level services.

Autoloads MUST NOT become default storage locations for arbitrary functionality.

Developers SHOULD:

- Keep each autoload focused.
- Avoid excessive numbers of autoloads.
- Minimize dependencies on global services.
- Avoid placing feature-specific gameplay logic in global services.
- Document important global responsibilities and dependencies.

Before introducing a new autoload, developers SHOULD evaluate whether a scene-owned component, feature service, or explicitly passed dependency is more appropriate.

### 5.5 Signals and Event-Driven Communication

Signals SHOULD be used when systems need to communicate that an event occurred without requiring unnecessary direct dependencies.

Appropriate examples include:

- Health changes.
- Item collection.
- Quest completion.
- Player interaction events.
- UI updates.
- Gameplay state changes.

Developers SHOULD:

- Use descriptive signal names.
- Keep signal responsibilities clear.
- Avoid signals that obscure important execution flow.
- Ensure signal connections have appropriate lifecycle management.
- Avoid excessive event indirection.

Direct method calls MAY be preferable when the caller needs an immediate response or when the dependency is simple and explicit.

### 5.6 Scene Lifecycle and Node Ownership

Systems MUST respect Godot's scene and node lifecycle.

Developers SHOULD:

- Understand when nodes enter and exit the scene tree.
- Connect and disconnect signals appropriately.
- Avoid accessing nodes before they are ready.
- Avoid retaining references to freed nodes.
- Use appropriate lifecycle methods.
- Manage asynchronous operations and deferred calls carefully.

Lifecycle-dependent behavior SHOULD be implemented consistently and documented when non-obvious.

## 6. Communication Between Systems

### 6.1 Communication Contracts

Systems SHOULD communicate through clear and stable contracts.

A communication contract defines:

- What functionality is exposed.
- What information is required.
- What results or events can be expected.
- What assumptions and limitations apply.
- Which system owns the relevant data.

Contracts SHOULD minimize knowledge of implementation details.

### 6.2 Direct References

Direct references MAY be used when:

- The relationship is clear.
- The dependency is intentional.
- The caller legitimately requires access to the target.
- The resulting coupling remains manageable.

Developers SHOULD avoid creating extensive chains of references between unrelated systems.

### 6.3 Signals

Signals SHOULD be preferred for event notification when the sender does not need to control the receiver's implementation.

Signals MUST NOT be used merely to avoid every direct dependency.

Communication mechanisms SHOULD be selected according to the actual relationship between systems.

### 6.4 Shared State

Shared mutable state SHOULD be minimized.

When shared state is necessary:

- Its owner MUST be identifiable.
- Its modification rules MUST be clear.
- Its lifecycle MUST be understood.
- Access SHOULD be controlled.
- Changes SHOULD be observable when other systems depend on them.

Multiple systems SHOULD NOT independently modify the same state without a clearly defined ownership model.

## 7. Data Ownership and State Management

### 7.1 Single Ownership

Every important piece of mutable game state SHOULD have a clearly identifiable owner.

The owning system SHOULD be responsible for:

- Initializing the state.
- Validating modifications.
- Maintaining its invariants.
- Exposing appropriate access.
- Managing its lifecycle.

Other systems SHOULD request changes through the owner's public interface rather than directly modifying internal state.

### 7.2 Separation of Configuration and Runtime State

Configuration data and runtime state SHOULD be separated when their lifecycles or responsibilities differ.

Examples:

- An item definition describes an item's properties.
- An inventory entry represents an owned item and its current quantity.
- An enemy definition describes an enemy archetype.
- An enemy instance contains runtime health and behavior state.

This separation SHOULD prevent runtime changes from unintentionally affecting shared definitions.

### 7.3 Persistence

Persistent state SHOULD be managed through an explicit persistence mechanism.

Developers SHOULD:

- Define which state must survive a session.
- Separate persistent data from transient runtime state.
- Avoid coupling gameplay systems directly to file operations.
- Validate loaded data.
- Handle missing, invalid, or outdated save data appropriately.
- Consider compatibility when save formats evolve.

Persistence architecture MUST be appropriate to the project's actual requirements.

## 8. Dependencies and Dependency Management

### 8.1 Dependency Direction

Dependencies SHOULD follow a deliberate and understandable direction.

Developers MUST avoid circular dependencies between features and shared components.

The general dependency expectations are:

- Features MAY depend on shared functionality.
- Shared functionality MUST NOT depend on individual features.
- Infrastructure SHOULD provide technical capabilities without depending on individual gameplay features.
- Feature-to-feature dependencies SHOULD be minimized and explicitly justified.

### 8.2 Dependency Minimization

Developers SHOULD avoid:

- Unnecessary global references.
- Hidden dependencies.
- Circular references.
- Excessive cross-feature communication.
- Dependencies on internal implementation details.
- Large coordination systems introduced without demonstrated need.

### 8.3 Dependency Changes

Significant dependency changes SHOULD be reviewed for their effect on:

- Existing feature boundaries.
- Maintainability.
- Testability.
- Runtime behavior.
- Future development.
- Architectural consistency.

Changes that materially alter the project's architecture MUST be evaluated for an Architecture Decision Record.

## 9. Error Handling and Reliability

Architecture SHOULD make failures understandable and manageable.

Developers SHOULD:

- Validate inputs at appropriate boundaries.
- Handle expected failure conditions explicitly.
- Avoid silently ignoring important errors.
- Provide useful diagnostic information.
- Prevent invalid state transitions.
- Keep failure handling close to the responsible system when practical.

Error handling MUST be proportional to the risk and importance of the operation.

Critical operations such as save management, resource loading, and external integrations SHOULD have explicit failure-handling strategies.

## 10. Testability

Architecture SHOULD support practical testing.

Developers SHOULD:

- Keep important game rules independently testable where practical.
- Avoid unnecessary reliance on global state.
- Expose clear interfaces for important systems.
- Separate deterministic logic from engine-dependent behavior when beneficial.
- Keep dependencies replaceable when testing requires it.
- Avoid tightly coupling gameplay rules to presentation.

Testing requirements SHOULD influence architecture when they materially improve reliability and maintainability.

However, architecture MUST NOT become unnecessarily complex solely to accommodate theoretical testing scenarios.

## 11. Performance Considerations

Architecture SHOULD consider performance without introducing premature optimization.

Developers SHOULD:

- Understand the expected runtime responsibilities of each system.
- Avoid unnecessary per-frame processing.
- Avoid excessive object and node creation.
- Manage resource loading and unloading appropriately.
- Consider memory usage and scene complexity.
- Profile performance before implementing significant optimizations.

Performance-sensitive systems SHOULD have clearly defined responsibilities and measurable performance expectations where appropriate.

Optimization MUST preserve correctness and maintainability.

## 12. Extensibility and Reuse

Architecture SHOULD support reasonable future changes without attempting to anticipate every possible requirement.

Developers SHOULD:

- Identify genuine variation points.
- Use configuration and composition where appropriate.
- Reuse existing systems when their responsibilities genuinely match.
- Avoid duplicating established shared functionality.
- Avoid creating generic frameworks for isolated use cases.

A system SHOULD be generalized only when there is a demonstrated need or a well-supported design requirement.

Reuse MUST NOT introduce unnecessary coupling or make feature-specific behavior harder to understand.

## 13. Architectural Patterns

Architectural patterns MAY be used when they solve an identifiable problem.

Examples include:

- Component-based architecture.
- State machines.
- Event-driven communication.
- Object pooling.
- Dependency injection.
- Model-View-Controller or Model-View-Presenter.
- Data-driven design.
- Service-oriented organization.

Pattern selection SHOULD consider:

- The problem being solved.
- The complexity introduced.
- Compatibility with Godot.
- Ease of implementation.
- Testability.
- Maintainability.
- Actual project requirements.

Developers MUST NOT apply patterns solely because they are commonly used in other projects.

Patterns SHOULD remain understandable to the people maintaining the game.

## 14. Architectural Documentation and Decisions

### 14.1 Documentation Expectations

Architecture documentation SHOULD explain important structural decisions and relationships.

Documentation MAY include:

- System responsibilities.
- Feature boundaries.
- Dependency relationships.
- Data ownership.
- Communication contracts.
- Lifecycle responsibilities.
- Important constraints.
- Integration requirements.

Documentation SHOULD focus on information that is difficult to understand from the implementation alone.

### 14.2 Architecture Decision Records

An Architecture Decision Record (ADR) MUST be created for significant technical or architectural decisions.

Examples include:

- Selecting a major architectural approach.
- Introducing a substantial project-wide dependency.
- Changing feature boundaries or dependency direction.
- Introducing a major global service.
- Changing persistence architecture.
- Replacing an established technical approach.
- Making a decision with substantial long-term maintenance implications.

Minor implementation choices do not normally require ADRs.

ADRs MUST follow the studio's ADR process and template defined in:

`docs/02_technical_standards/adr/`

Project-specific ADRs MUST be stored in the relevant game's repository.

### 14.3 Architectural Changes

Before making a significant architectural change, developers SHOULD:

1. Identify the problem or requirement.
2. Inspect the existing architecture.
3. Evaluate the impact on existing features.
4. Consider simpler alternatives.
5. Identify affected dependencies and interfaces.
6. Document the decision when an ADR is required.
7. Obtain the required project owner approval.

AI agents MUST NOT independently introduce significant architectural changes without the required approval.

## 15. Anti-Patterns

Developers SHOULD avoid the following architectural anti-patterns:

### 15.1 God Objects

Classes or autoloads that accumulate unrelated responsibilities and become central dependencies for many systems.

### 15.2 Excessive Global State

Using global variables or autoloads as the default communication and data-sharing mechanism.

### 15.3 Circular Dependencies

Features or components that depend on each other in ways that make ownership and execution difficult to understand.

### 15.4 Overengineering

Introducing unnecessary frameworks, abstractions, interfaces, or layers without a demonstrated benefit.

### 15.5 Premature Generalization

Designing highly generic systems before understanding the actual requirements and variation points.

### 15.6 Excessive Inheritance

Creating deep or rigid inheritance hierarchies where composition would provide clearer behavior and ownership.

### 15.7 Feature Boundary Violations

Allowing features to manipulate the internal implementation of unrelated features.

### 15.8 Uncontrolled Shared Functionality

Placing unrelated or feature-specific functionality into shared directories without clear ownership.

### 15.9 Hidden Dependencies

Relying on undocumented global references, implicit scene paths, or initialization assumptions.

### 15.10 Excessive Indirection

Making simple functionality difficult to follow through unnecessary layers of managers, wrappers, or event forwarding.

## 16. AI-Assisted Architecture Requirements

AI agents MUST follow these guidelines when creating or modifying architecture.

Agents MUST:

- Inspect the existing project structure before proposing architectural changes.
- Read applicable architecture and technical standards.
- Respect the established feature-oriented organization.
- Preserve existing architectural decisions unless explicitly authorized to change them.
- Avoid introducing unnecessary patterns, abstractions, or dependencies.
- Keep feature responsibilities and dependency boundaries clear.
- Avoid placing feature-specific functionality in shared or infrastructure directories without justification.
- Identify significant architectural consequences before implementation.
- Create or update ADRs when required.
- Request human approval for significant architectural changes.
- Report architectural changes and their impact.
- Validate affected functionality after implementation.

Agents MUST NOT:

- Introduce a new architectural style without approval.
- Restructure the project merely to match personal preferences.
- Create global services without justification.
- Introduce circular dependencies.
- Bypass established interfaces without explaining why.
- Claim architectural compliance without inspecting the relevant implementation.

When existing architecture conflicts with these guidelines, agents SHOULD report the conflict and propose a proportionate solution rather than silently restructuring the project.

## 17. Architecture Review Checklist

Before completing a significant architectural change, verify:

- [ ] Responsibilities are clearly defined.
- [ ] Feature boundaries are respected.
- [ ] Dependencies are intentional and understandable.
- [ ] Circular dependencies have been avoided.
- [ ] Shared functionality is genuinely shared.
- [ ] Infrastructure responsibilities remain appropriate.
- [ ] Global services are justified and focused.
- [ ] Data ownership is clear.
- [ ] Runtime state is separated from configuration where appropriate.
- [ ] Communication contracts are understandable.
- [ ] The design is compatible with Godot and GDScript conventions.
- [ ] Important behavior remains testable.
- [ ] Performance implications have been considered.
- [ ] The solution avoids unnecessary complexity.
- [ ] Required architecture documentation and ADRs are updated.
- [ ] Existing functionality has been validated.

## 18. Exceptions

Exceptions to these guidelines MAY be introduced when project requirements justify them.

Exceptions SHOULD:

- Have a clear technical or design justification.
- Be proportional to the problem being solved.
- Identify affected systems and potential consequences.
- Be reviewed by the project owner.
- Be documented when they introduce significant architectural implications.

An exception MUST NOT silently invalidate an established architectural decision.

## 19. Related Documents

These guidelines SHOULD be used alongside:

- `docs/00_studio_standards/development_philosophy.md`
- `docs/00_studio_standards/project_structure_standards.md`
- `docs/00_studio_standards/naming_conventions.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/00_studio_standards/documentation_standards.md`
- `docs/00_studio_standards/code_review_guidelines.md`
- `docs/00_studio_standards/definition_of_done.md`
- `docs/02_technical_standards/gdscript_standards.md`
- `docs/02_technical_standards/adr/README.md`

Only documents that exist in the repository should be registered as active references in the documentation inventory.

## 20. Maintenance

These guidelines SHOULD be reviewed when:

- The studio's architectural practices evolve.
- Godot introduces relevant architectural capabilities or changes.
- Repeated project experience reveals weaknesses in the guidelines.
- New technical requirements justify additional standards.
- Existing guidance becomes unnecessarily restrictive or outdated.

Changes MUST preserve the document's purpose as a reusable studio-wide architecture standard.

The project owner is responsible for approving changes to these guidelines.