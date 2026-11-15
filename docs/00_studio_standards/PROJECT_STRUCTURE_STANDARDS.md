# Project Structure Standards

**Document Type:** Studio Standard  
**Status:** Draft  
**Applies To:** Repository-level structure and all studio game projects using Godot Engine and GDScript

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

- Repository-level structure and configuration.
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
- The boundary between reusable studio documentation and game-specific documentation.
- Development and build tooling.

This document defines where project elements belong and how they should be organized, and it establishes the boundary between the repository root and the Godot project root. Detailed naming rules, coding practices, and architectural principles are defined in their respective standards.

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

### 3.8 Two-Root Separation

The repository root and the Godot project root MUST remain distinct.

- The repository root MUST NOT be treated as the Godot project root.
- `game_project/` MUST be the Godot project root and MUST contain `project.godot`.
- Reusable studio documentation MUST remain in repository-root `docs/`.
- Game-specific documentation MUST remain in `game_project/docs/`.
- Game implementation MUST remain inside `game_project/`.

Studio infrastructure, studio documentation, and game implementation MUST NOT be mixed within the same organizational layer.

## 4. Standard Repository Structure

The repository uses a two-root architecture. The repository root holds studio infrastructure and reusable studio documentation. The Godot project root holds the game.

### 4.1 Repository Structure

Repository-level content MUST follow this organization.

```text
repository-root/
│
├── .cline/
│   └── rules/
│
├── .clinerules/
│   └── workflows/
│
├── .github/
│   ├── workflows/
│   ├── ISSUE_TEMPLATE/
│   └── PULL_REQUEST_TEMPLATE.md
│
├── docs/                              # Studio documentation only
│   ├── DOCUMENTATION_INVENTORY.md
│   ├── 00_studio_standards/
│   ├── 01_game_design_guidelines/
│   ├── 02_technical_standards/
│   ├── 03_art_audio_standards/
│   ├── 04_production_standards/
│   ├── 05_qa_standards/
│   ├── 06_templates/
│   └── 07_agent_workflows/
│
├── references/
│
├── game_project/                      # Godot project root
│
├── .clineignore
├── .gitattributes
├── .gitignore
└── README.md
```

The repository root MUST NOT contain `project.godot`.

Repository-level documentation in `docs/` MUST contain reusable studio material only. Game-specific specifications, production records, and implementation documents MUST NOT be placed there.

### 4.2 Godot Project Structure

`game_project/` is the Godot project root. It contains the game implementation and game-specific documentation.

Godot projects MUST follow the feature-oriented organizational model illustrated below.

```text
game_project/
│
├── project.godot
│
├── addons/
│
├── assets/
│
├── features/
│   ├── player/
│   │   ├── scenes/
│   │   ├── scripts/
│   │   ├── resources/
│   │   ├── assets/
│   │   └── tests/
│   │
│   └── inventory/
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
├── tests/
│
└── docs/                              # Game-specific documentation
    ├── game_design/
    ├── technical/
    ├── production/
    ├── qa/
    ├── art/
    └── audio/
```

### 4.3 Reference Structure Boundaries

Both illustrated structures are reference structures, not a requirement to create every directory.

Only create directories when they contain actual project content.

The repository MUST preserve the two-root separation and the feature-oriented organizational strategy even when the exact feature names and internal subdivisions differ.

## 5. Directory Responsibilities

Sections 5.1 to 5.7 describe directories inside the Godot project root (`game_project/`). Sections 5.8 to 5.14 identify the remaining project and repository-level directories.

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

### 5.5 `addons/`

Contains third-party Godot plugins and addons installed into the Godot project.

- Third-party plugins MUST remain inside `game_project/addons/`.
- Do not modify third-party addon code without a documented reason.
- Project code MUST NOT depend on studio documentation or repository tooling through an addon.

### 5.6 `assets/`

Contains game assets that are not owned by a single feature.

- Feature-specific assets SHOULD remain inside the owning feature.
- Assets used by multiple features MAY be stored in `game_project/assets/` or `game_project/shared/assets/` according to their use.
- Avoid maintaining duplicate copies of the same asset.

### 5.7 `tests/`

Contains project-level integration tests that validate interactions across multiple features.

Unit tests SHOULD remain inside the feature or shared module they validate.

Test organization is defined further in Section 8.

### 5.8 `docs/`

Contains game-specific documentation for the current game. The location is `game_project/docs/`.

Typical categories:

| Directory | Responsibility |
|---|---|
| `game_design/` | Game vision, mechanics, systems, narrative, and design specifications. |
| `technical/` | Architecture, technical specifications, and implementation decisions. |
| `production/` | Roadmaps, milestones, sprint plans, and production tracking. |
| `qa/` | Test plans, test reports, and quality-related project documentation. |
| `art/` | Project-specific art direction and visual specifications. |
| `audio/` | Project-specific audio direction and sound specifications. |

Requirements:

- Game-specific documentation MUST be created under `game_project/docs/`.
- Documents instantiated from templates in repository-root `docs/06_templates/` MUST be stored under `game_project/docs/`.
- Reusable studio standards MUST remain in repository-root `docs/` and MUST NOT be copied into `game_project/docs/`.
- Game-specific documentation SHOULD reference studio standards rather than copy their contents.
- Subdirectories SHOULD be created only when an actual document requires them.

### 5.9 `project.godot`

Contains the Godot project definition and project-wide configuration.

- `game_project/project.godot` MUST be the single Godot project definition in the repository.
- The repository root MUST NOT contain `project.godot`.
- All Godot `res://` paths resolve relative to `game_project/`.
- Project settings SHOULD be edited through the Godot editor where practical.
- AI agents MUST NOT change project configuration without explicit instruction.

### 5.10 `.github/`

Contains GitHub-specific repository configuration.

Typical contents:

- CI/CD workflows.
- Issue templates.
- Pull request templates.
- Repository automation configuration.

It MUST NOT contain game source code or runtime assets.

### 5.11 `.cline/`

Contains Cline-specific configuration and agent instructions.

Typical contents:

- Agent rules.
- Tool-specific workflow instructions.
- Project context instructions.

Agent instructions SHOULD reference authoritative documentation instead of duplicating studio standards.

### 5.12 `.clinerules/`

Contains Cline execution workflows in `.clinerules/workflows/`.

These workflows define how agents perform repository tasks. They MUST reference authoritative studio and project documentation instead of duplicating its requirements.

Studio agent procedures remain in repository-root `docs/07_agent_workflows/`. Cline execution workflows MUST NOT contain studio standards.

### 5.13 `references/`

Contains repository-level reference material used for research and production support.

Typical categories include:

- `architectural/`
- `audio/`
- `historical/`
- `visual/`

Requirements:

- Reference material is not authoritative documentation. Studio standards and approved project documentation take precedence.
- Game implementation MUST NOT depend on `references/` at runtime.
- Material that the game imports or ships MUST be stored inside `game_project/`.

### 5.14 `tools/`

Contains development utilities that support the project but are not part of the game's runtime.

Examples:

- Asset-processing scripts.
- Data-generation utilities.
- Development-only automation.
- Validation scripts.
- Editor support tools.

Runtime game functionality MUST NOT depend on development-only tools unless explicitly intended.

## 6. Feature Boundaries and Dependencies

### 6.1 Repository and Project Ownership Boundaries

| Element | Location |
|---|---|
| Studio standards, guidelines, templates, and agent workflows | Repository-root `docs/` |
| Game-specific documentation | `game_project/docs/` |
| Shared game code | `game_project/shared/` |
| Feature-specific implementation | `game_project/features/` |
| Project-wide technical infrastructure | `game_project/infrastructure/` |
| Third-party plugins and addons | `game_project/addons/` |
| Repository-level reference material | `references/` |
| Cline configuration and execution workflows | `.cline/` and `.clinerules/` |
| GitHub configuration | `.github/` |

Requirements:

- Studio documentation MUST describe reusable standards and processes. It MUST NOT contain game-specific specifications, production records, or implementation details.
- Game-specific documentation belongs to the game project and MUST be maintained under `game_project/docs/`.
- Game implementation MUST NOT depend on repository documentation directories at runtime.
- Feature code MUST NOT depend on studio documentation or repository-level reference material.
- Shared code belongs in `game_project/shared/` and MUST NOT depend on individual gameplay features.
- Project-wide infrastructure belongs in `game_project/infrastructure/` and MUST NOT become a container for gameplay logic.
- Third-party plugins belong in `game_project/addons/` and MUST remain isolated from studio documentation.

### 6.2 Feature Independence

Features SHOULD encapsulate their own implementation details.

A feature MUST NOT directly manipulate another feature's internal state when an established public interface, signal, or shared component provides an appropriate interaction mechanism.

### 6.3 Cross-Feature Communication

Features SHOULD communicate through clearly defined interfaces.

Appropriate mechanisms MAY include:

- Signals.
- Public methods.
- Shared data resources.
- Explicitly defined interfaces or contracts.
- Dedicated coordination systems when justified.

Avoid unnecessary direct references between unrelated features.

### 6.4 Dependency Direction

Dependencies SHOULD follow the architecture established for the project.

- Shared modules SHOULD NOT depend on individual gameplay features.
- Features SHOULD NOT depend on unrelated feature internals.
- Infrastructure SHOULD provide technical support without becoming a container for gameplay logic.
- Circular dependencies between features MUST be avoided.

### 6.5 Feature Extraction

Functionality MAY be moved into a separate feature or shared module when its responsibility and reuse justify the separation.

Do not split cohesive functionality into multiple features simply to create smaller directories.

## 7. Godot-Specific Organization

### 7.1 Project Root

The Godot project root is `game_project/`.

The `project.godot` file MUST remain at the Godot project root.

The repository root MUST NOT contain `project.godot`.

All Godot `res://` paths resolve relative to `game_project/`.

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

The `.godot/` directory inside the Godot project root contains generated editor and import data.

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
2. Treat `game_project/` as the Godot project root.
3. Read relevant project and studio documentation.
4. Identify the owning feature of each new file.
5. Check whether an appropriate feature or shared module already exists.
6. Follow the established feature-oriented organization.
7. Preserve clear feature boundaries.
8. Avoid introducing unnecessary directories or duplicate structures.
9. Preserve Godot resource paths and dependencies.
10. Update documentation when structural changes affect documented organization.

AI agents MUST NOT:

- Treat the repository root as the Godot project root.
- Create game-specific documentation under repository-root `docs/`.
- Create studio-wide documentation under `game_project/docs/`.
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

- [ ] The repository root was not treated as the Godot project root.
- [ ] Game-specific files and documentation are located inside `game_project/`.
- [ ] Game-specific documentation is located under `game_project/docs/`.
- [ ] Studio documentation was not duplicated inside `game_project/docs/`.
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

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`
- `docs/02_technical_standards/ASSET_PIPELINE.md`

Only maintain references to documents that actually exist in the repository.

## 15. Maintenance

This document MUST be reviewed when:

- Studio-wide project organization practices change.
- Godot introduces significant changes to project organization or resource management.
- Repeated structural problems indicate that the standard needs clarification.
- New project requirements justify changes to the reference structure.

Changes to this standard require project owner approval before being marked `Approved`.