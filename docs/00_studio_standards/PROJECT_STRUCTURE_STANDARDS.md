# Project Structure Standards

**Document Type:** Studio Standard  
**Status:** Draft  
**Applies To:** All studio game projects using Godot Engine and GDScript

---

## 1. Purpose

This document establishes mandatory standards for organizing Godot game projects using a feature-oriented directory structure.

A consistent feature-oriented structure improves:

- Code maintainability and discoverability.
- Separation of responsibilities.
- Feature independence and modularity.
- Reusability and dependency management.
- Collaboration between developers and AI agents.
- Testing and debugging.
- Long-term project scalability.

The objective is to organize project elements around meaningful game features and systems rather than separating all files exclusively by technical type.

## 2. Scope

This standard applies to:

- Godot project repositories.
- Game features and systems.
- GDScript source files.
- Scenes and scene-specific resources.
- Reusable components.
- Art, audio, animation, and other game assets.
- User interface resources.
- Configuration and project settings.
- Automated tests and testing resources.
- Project-specific technical documentation.
- Development and build tooling.

This document defines where project elements belong and how they should be organized. Detailed naming rules, coding practices, and architectural principles are defined in their respective standards.

## 3. Mandatory Organizational Principles

### 3.1 Feature-Oriented Organization

All project functionality MUST be organized primarily by feature or system responsibility.

Related scenes, scripts, resources, tests, and assets SHOULD be grouped together within their owning feature.

For example, inventory functionality belongs under the inventory feature rather than being distributed across unrelated global `scripts/`, `scenes/`, and `resources/` directories.

### 3.2 Single Organizational Strategy

Feature-oriented organization MUST be used consistently throughout the project.

Projects MUST NOT introduce a competing type-oriented organizational hierarchy for game functionality.

### 3.3 Separation of Concerns

Each feature MUST have a clearly defined responsibility.

A feature SHOULD contain the implementation elements necessary for its functionality without absorbing unrelated responsibilities.

### 3.4 Modularity

Features SHOULD minimize unnecessary dependencies on other features.

Shared functionality SHOULD be extracted into shared modules only when multiple features genuinely need it.

### 3.5 Discoverability

Developers and AI agents SHOULD be able to locate a feature's implementation, scenes, resources, and tests from its feature directory.

Avoid excessive directory nesting and unnecessary organizational abstractions.

### 3.6 Scalability

The project structure MUST support incremental growth.

New features and subdirectories SHOULD be introduced when actual requirements justify them.

### 3.7 Avoid Premature Organization

Do not create empty feature directories, unnecessary abstractions, or elaborate folder hierarchies for hypothetical future requirements.

Start with the simplest structure that adequately supports the current project.

## 4. Standard Repository Structure

Godot projects MUST follow the feature-oriented organizational model illustrated below.

```text
project-root/
│
├── .github/
│   ├── workflows/
│   ├── ISSUE_TEMPLATE/
│   └── PULL_REQUEST_TEMPLATE.md
│
├── .cline/
│   └── rules/
│
├── docs/
│   ├── game_design/
│   ├── technical/
│   ├── production/
│   └── qa/
│
├── features/
│   ├── player/
│   │   ├── scenes/
│   │   ├── scripts/
│   │   ├── resources/
│   │   ├── assets/
│   │   └── tests/
│   │
│   ├── inventory/
│   │   ├── scenes/
│   │   ├── scripts/
│   │   ├── resources/
│   │   ├── assets/
│   │   └── tests/
│   │
│   ├── combat/
│   │   ├── scenes/
│   │   ├── scripts/
│   │   ├── resources/
│   │   ├── assets/
│   │   └── tests/
│   │
│   └── dialogue/
│       ├── scenes/
│       ├── scripts/
│       ├── resources/
│       ├── assets/
│       └── tests/
│
├── shared/
│   ├── components/
│   ├── resources/
│   ├── scripts/
│   ├── assets/
│   └── tests/
│
├── infrastructure/
│   ├── autoload/
│   ├── configuration/
│   └── integrations/
│
├── tools/
│
├── .editorconfig
├── .gitattributes
├── .gitignore
├── project.godot
└── README.md
```

This is a reference structure, not a requirement to create every illustrated directory.

Only create directories when they contain actual project content.

The project MUST preserve the feature-oriented organizational strategy even when its exact feature names and internal subdivisions differ.

## 5. Directory Responsibilities

### 5.1 `features/`

Contains the implementation of individual game features and gameplay systems.

Each feature MUST have a clearly defined responsibility and SHOULD be independently understandable.

Examples:

```text
features/
├── player/
├── inventory/
├── combat/
├── dialogue/
├── crafting/
├── quest/
├── interaction/
└── save_load/
```

Feature names SHOULD represent meaningful game capabilities or cohesive systems.

A feature MAY contain:

| Directory | Responsibility |
|---|---|
| `scenes/` | Scenes owned by the feature. |
| `scripts/` | GDScript implementation. |
| `resources/` | Feature-specific Godot resources and data. |
| `assets/` | Assets exclusively owned by the feature. |
| `tests/` | Tests validating the feature. |

These subdivisions SHOULD be created only when necessary.

A small feature MAY keep its files directly inside its root directory until additional organization becomes useful.

### 5.2 Feature Ownership

Each file MUST have one identifiable primary owner.

The owning feature is responsible for maintaining its implementation and associated resources.

For example:

```text
features/
└── inventory/
    ├── scenes/
    │   └── inventory_panel.tscn
    ├── scripts/
    │   ├── inventory_system.gd
    │   └── inventory_slot.gd
    ├── resources/
    │   └── inventory_configuration.tres
    └── tests/
        └── test_inventory_system.gd
```

Avoid placing inventory-specific functionality inside the player feature merely because the player uses the inventory.

### 5.3 `shared/`

Contains reusable functionality and resources genuinely used by multiple features.

Typical categories:

| Directory | Responsibility |
|---|---|
| `components/` | Reusable components shared across features. |
| `resources/` | Shared resource definitions and configurations. |
| `scripts/` | Reusable scripts and utilities. |
| `assets/` | Assets used by multiple features. |
| `tests/` | Tests for shared functionality. |

Requirements:

- Shared functionality MUST have a clear reusable responsibility.
- A feature MUST NOT depend on unrelated feature internals through the shared directory.
- Do not move code into `shared/` merely to avoid choosing an owning feature.
- Shared modules SHOULD have minimal dependencies on individual features.

### 5.4 `infrastructure/`

Contains project-level technical infrastructure that supports the application as a whole.

Typical categories:

| Directory | Responsibility |
|---|---|
| `autoload/` | Scripts registered as Godot autoloads. |
| `configuration/` | Project-wide runtime and system configuration. |
| `integrations/` | External service and platform integrations. |

Infrastructure MUST NOT become a general-purpose location for unrelated gameplay functionality.

Gameplay systems SHOULD remain inside their respective feature directories unless they genuinely provide project-wide infrastructure.

### 5.5 `docs/`

Contains project-specific documentation.

Typical categories:

| Directory | Responsibility |
|---|---|
| `game_design/` | Game vision, mechanics, systems, narrative, and design specifications. |
| `technical/` | Architecture, technical specifications, and implementation decisions. |
| `production/` | Roadmaps, milestones, sprint plans, and production tracking. |
| `qa/` | Test plans, test reports, and quality-related project documentation. |

Reusable studio standards MUST remain in the designated shared studio documentation location.

Project documentation SHOULD reference shared standards rather than copy their contents.

### 5.6 `.github/`

Contains GitHub-specific repository configuration.

Typical contents:

- CI/CD workflows.
- Issue templates.
- Pull request templates.
- Repository automation configuration.

It MUST NOT contain game source code or runtime assets.

### 5.7 `.cline/`

Contains Cline-specific configuration and agent instructions.

Typical contents:

- Agent rules.
- Tool-specific workflow instructions.
- Project context instructions.

Agent instructions SHOULD reference authoritative documentation instead of duplicating studio standards.

### 5.8 `tools/`

Contains development utilities that support the project but are not part of the game's runtime.

Examples:

- Asset-processing scripts.
- Data-generation utilities.
- Development-only automation.
- Validation scripts.
- Editor support tools.

Runtime game functionality MUST NOT depend on development-only tools unless explicitly intended.

## 6. Feature Boundaries and Dependencies

### 6.1 Feature Independence

Features SHOULD encapsulate their own implementation details.

A feature MUST NOT directly manipulate another feature's internal state when an established public interface, signal, or shared component provides an appropriate interaction mechanism.

### 6.2 Cross-Feature Communication

Features SHOULD communicate through clearly defined interfaces.

Appropriate mechanisms MAY include:

- Signals.
- Public methods.
- Shared data resources.
- Explicitly defined interfaces or contracts.
- Dedicated coordination systems when justified.

Avoid unnecessary direct references between unrelated features.

### 6.3 Dependency Direction

Dependencies SHOULD follow the architecture established for the project.

- Shared modules SHOULD NOT depend on individual gameplay features.
- Features SHOULD NOT depend on unrelated feature internals.
- Infrastructure SHOULD provide technical support without becoming a container for gameplay logic.
- Circular dependencies between features MUST be avoided.

### 6.4 Feature Extraction

Functionality MAY be moved into a separate feature or shared module when its responsibility and reuse justify the separation.

Do not split cohesive functionality into multiple features simply to create smaller directories.

## 7. Godot-Specific Organization

### 7.1 Project Root

The `project.godot` file MUST remain at the Godot project root.

The root SHOULD contain only essential project-level files and organizational directories.

### 7.2 Scenes

Scene files (`.tscn`) SHOULD reside within the `scenes/` directory of their owning feature.

Example:

```text
features/
└── player/
    └── scenes/
        ├── player.tscn
        └── player_camera.tscn
```

Reusable scenes shared across multiple features MAY reside in an appropriate shared module.

### 7.3 Scripts

GDScript files (`.gd`) SHOULD reside within the `scripts/` directory of their owning feature.

Example:

```text
features/
└── combat/
    └── scripts/
        ├── combat_controller.gd
        └── damage_calculator.gd
```

A script MUST have a clear primary responsibility.

Avoid creating duplicate implementations of the same functionality across features.

### 7.4 Resources

Godot resources SHOULD be stored according to their ownership.

- Feature-specific resources belong in the feature's `resources/` directory.
- Shared resources belong in `shared/resources/`.
- Project-wide configuration belongs in `infrastructure/configuration/`.

Use Godot resource formats such as `.tres` and `.res` where appropriate.

### 7.5 Autoloads

Scripts registered as Godot autoloads MUST be stored in:

```text
infrastructure/
└── autoload/
```

Autoloads MUST have clearly defined project-wide responsibilities.

Do not register ordinary gameplay objects or unnecessary helper scripts as autoloads.

### 7.6 Assets

Assets SHOULD be stored close to their owning feature when they are feature-specific.

Example:

```text
features/
└── player/
    └── assets/
        ├── textures/
        ├── audio/
        └── animations/
```

Assets genuinely shared by multiple features SHOULD be stored in `shared/assets/`.

Avoid maintaining duplicate copies of the same asset without a clear reason.

### 7.7 Node Organization

Node names and scene hierarchy MUST reflect the responsibilities of the scene and its components.

A scene SHOULD keep its internal node structure cohesive and avoid unnecessarily large or deeply nested hierarchies.

Node organization MUST NOT be used as a substitute for proper feature boundaries.

### 7.8 Generated Files

The `.godot/` directory contains generated editor and import data.

It MUST NOT be treated as source-controlled project content.

The repository's `.gitignore` MUST exclude generated Godot cache data unless a specific project requirement justifies an exception.

Generated data MUST NOT be manually edited as part of normal development.

### 7.9 Resource References

Godot resource references SHOULD use stable project-relative resource paths.

Developers and AI agents MUST check references before moving or renaming scenes, scripts, resources, or assets.

After structural changes, verify that:

- Resource references remain valid.
- Scenes load correctly.
- Required imports complete successfully.
- No missing-resource errors are introduced.

## 8. Testing Organization

Tests SHOULD be located within the feature or shared module they validate.

Examples:

```text
features/
└── inventory/
    └── tests/
        ├── test_inventory_system.gd
        └── test_inventory_slot.gd

shared/
└── tests/
    └── test_damage_calculator.gd
```

Integration tests MAY be organized in a dedicated project-level test directory when they validate interactions across multiple features.

Example:

```text
tests/
└── integration/
    ├── test_player_combat.gd
    └── test_inventory_save_load.gd
```

Test organization MUST make the tested feature or system identifiable.

## 9. Project Growth and Refactoring

The project structure MUST evolve according to actual requirements.

New features or directories MAY be introduced when:

- A new gameplay capability is implemented.
- Existing feature responsibilities become too broad.
- A system requires a clear independent boundary.
- Shared functionality is genuinely reused.
- Testing requires better isolation.
- A significant architectural change justifies reorganization.

Structural changes SHOULD:

1. Have a clear justification.
2. Preserve existing functionality.
3. Maintain feature ownership.
4. Update affected references and documentation.
5. Be reviewed for broken dependencies.
6. Include appropriate validation.

Avoid large-scale directory reorganizations without a demonstrated benefit.

## 10. Files and Content That Should Not Be Committed

The repository MUST exclude generated, temporary, or local-only files unless explicitly required.

Typical examples include:

- Godot generated cache directories.
- Temporary editor files.
- Local debugging output.
- Unnecessary build artifacts.
- Personal IDE configuration.
- Operating-system metadata.
- Temporary exported builds.
- Local secrets and credentials.

The `.gitignore` file MUST reflect the project's actual tooling and workflow.

Do not exclude original source assets, project resources, or required configuration files merely because they are generated or imported by a tool.

## 11. AI-Assisted Development Requirements

AI agents MUST follow this standard when creating or modifying project structure.

Before making structural changes, agents MUST:

1. Inspect the existing repository structure.
2. Read relevant project and studio documentation.
3. Identify the owning feature of each new file.
4. Check whether an appropriate feature or shared module already exists.
5. Follow the established feature-oriented organization.
6. Preserve clear feature boundaries.
7. Avoid introducing unnecessary directories or duplicate structures.
8. Preserve Godot resource paths and dependencies.
9. Update documentation when structural changes affect documented organization.

AI agents MUST NOT:

- Introduce a type-oriented root hierarchy for game functionality.
- Move feature-specific files into unrelated features.
- Place shared functionality inside a feature without considering its ownership.
- Use `shared/` as a general dumping ground.
- Place gameplay functionality inside `infrastructure/` without justification.
- Reorganize the repository solely according to personal preferences.
- Move files without checking references and dependencies.
- Delete directories or files without verifying their purpose.

Significant structural changes MUST be proposed for human approval before implementation.

## 12. Compliance Checklist

Before completing a task, verify that:

- [ ] New functionality belongs to an appropriate feature.
- [ ] Related scenes, scripts, resources, assets, and tests are grouped by ownership.
- [ ] The feature-oriented organizational strategy is consistently followed.
- [ ] Feature boundaries and dependencies are respected.
- [ ] Shared functionality is genuinely reusable.
- [ ] Infrastructure contains only project-level technical responsibilities.
- [ ] Godot project configuration and resource references remain valid.
- [ ] Generated and temporary files are appropriately excluded.
- [ ] No unnecessary directories or duplicate structures were introduced.
- [ ] Structural changes are reflected in relevant documentation.
- [ ] Appropriate validation has been performed.

## 13. Exceptions

Projects MAY introduce additional organizational subdivisions when their requirements justify them.

However, the feature-oriented organizational model MUST remain the primary and exclusive structure for game functionality.

Exceptions MUST:

1. Have a clear justification.
2. Be documented in the relevant project documentation.
3. Preserve feature ownership and responsibility.
4. Avoid introducing competing organizational strategies.
5. Be approved by the project owner when they materially affect architecture.

## 14. Related Documents

- `development_philosophy.md`
- `documentation_standards.md`
- `naming_conventions.md`
- `architecture_guidelines.md`
- `gdscript_standards.md`
- `asset_management_standards.md`
- `definition_of_done.md`
- `code_review_guidelines.md`

Only maintain references to documents that actually exist in the repository.

## 15. Maintenance

This document MUST be reviewed when:

- Studio-wide project organization practices change.
- Godot introduces significant changes to project organization or resource management.
- Repeated structural problems indicate that the standard needs clarification.
- New project requirements justify changes to the reference structure.

Changes to this standard require project owner approval before being marked `Approved`.