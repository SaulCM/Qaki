# Documentation Inventory

## 1. Purpose

This document is the central inventory of documentation maintained in the studio's shared documentation repository.

It also registers the repository's agent instructions (`.cline/rules/` and `.clinerules/workflows/`) and repository governance files (`.github/` and `references/`), because those files govern repository behavior and the documentation must remain consistent with them. Registered governance files are listed in section 16 and are not counted among the Markdown documents under `docs/`.

It provides a structured overview of available documentation, including studio standards, game design guidelines, technical standards, art and audio standards, production standards, QA standards, templates, and AI agent workflows.

The inventory helps developers and AI agents:

- Discover existing documentation.
- Identify the purpose and location of each document.
- Find authoritative references.
- Avoid creating duplicate documentation.
- Maintain consistency across documentation categories.
- Track documentation organization.
- Verify whether referenced documents actually exist.

This inventory represents the current documentation repository. It is not a roadmap of planned documentation.

## 2. Inventory Management Rules

The following rules apply when maintaining this inventory:

1. Only register documentation files that physically exist in the repository.
2. Use exact repository-relative paths, including capitalization and filename spelling.
3. Update the inventory whenever a document is created, renamed, moved, deprecated, or deleted.
4. Do not register planned or nonexistent documents.
5. Do not assume that a document is approved unless its approval status has been explicitly established.
6. Do not remove an inventory entry merely because its document is incomplete.
7. Preserve the distinction between studio standards, guidelines, templates, and agent workflows.
8. Verify the actual repository structure before making inventory changes.
9. Keep document descriptions concise and representative of their actual purpose.
10. Do not use this inventory as a substitute for reading the referenced documents.

### 2.1 Document status

The inventory does not automatically determine document approval status.

When document statuses are explicitly established, use the following values:

| Status | Description |
|---|---|
| Draft | Document is incomplete or under development. |
| In Review | Document is awaiting review or approval. |
| Approved | Document has been explicitly approved by the authorized owner. |
| Deprecated | Document is retained for reference but is no longer authoritative. |
| Not Specified | Document status has not been established in the inventory. |

An AI agent MUST NOT mark a document as Approved without explicit human authorization.

The `Status` column in sections 4 to 11 and in section 16 records the status of each registered file. `Not Specified` means that no status has been established for the file yet; it is neither an approval nor a draft classification.

## 3. Documentation Structure

The shared documentation repository follows this structure:

```text
docs/
├── DOCUMENTATION_INVENTORY.md
├── 00_studio_standards/
├── 01_game_design_guidelines/
├── 02_technical_standards/
│   └── adr/
├── 03_art_audio_standards/
├── 04_production_standards/
├── 05_qa_standards/
├── 06_templates/
└── 07_agent_workflows/
```

Each directory has a distinct responsibility.

| Directory | Responsibility |
|---|---|
| `00_studio_standards/` | Shared development principles, conventions, and mandatory studio practices. |
| `01_game_design_guidelines/` | Reusable game design principles and guidelines. |
| `02_technical_standards/` | Engineering, architecture, Godot, and technical implementation standards. |
| `03_art_audio_standards/` | Visual art, animation, audio, and presentation standards. |
| `04_production_standards/` | Production planning, execution, tracking, and release processes. |
| `05_qa_standards/` | Quality assurance, testing, acceptance, and defect management guidelines. |
| `06_templates/` | Reusable templates for creating project-specific documentation. |
| `07_agent_workflows/` | Standardized procedures for AI-assisted development tasks. |

## 4. Studio Standards

**Directory:** `docs/00_studio_standards/`

Studio standards define shared practices and expectations that apply across game projects.

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `00_studio_standards/BRANCHING_STRATEGY.md` | Defines Git branching conventions, branch purposes, integration practices, and branch protection expectations. | Not Specified | `GIT_CONVENTIONS.md`, `CODE_REVIEW_GUIDELINES.md`, `DEFINITION_OF_DONE.md`, `DEVELOPMENT_PHILOSOPHY.md`, `DOCUMENTATION_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `SPRINT_WORKFLOW.md`, `RELEASE_PROCESS.md`, `VERSIONING_STANDARDS.md`, `IMPLEMENT_FEATURE.md`, `FIX_BUG.md`, `REVIEW_CODE.md` |
| `00_studio_standards/CODE_REVIEW_GUIDELINES.md` | Defines code review principles, responsibilities, review criteria, finding severity, and approval expectations. | Not Specified | `GIT_CONVENTIONS.md`, `BRANCHING_STRATEGY.md`, `DEFINITION_OF_DONE.md` |
| `00_studio_standards/DEFINITION_OF_DONE.md` | Establishes the minimum completion criteria for tasks, features, fixes, and other deliverables. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `QUALITY_STANDARDS.md`, `CODE_REVIEW_GUIDELINES.md`, `GIT_CONVENTIONS.md`, `BRANCHING_STRATEGY.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `DOCUMENTATION_STANDARDS.md`, `GDSCRIPT_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md`, `ENGINE_STANDARDS.md`, `TESTING_STRATEGY.md`, `ASSET_PIPELINE.md`, `ART_ASSET_STANDARDS.md`, `AUDIO_ASSET_STANDARDS.md`, `ANIMATION_STANDARDS.md`, `UI_UX_STANDARDS.md`, `SPRINT_WORKFLOW.md`, `BACKLOG_MANAGEMENT.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md`, `REGRESSION_TESTING.md` |
| `00_studio_standards/DEVELOPMENT_PHILOSOPHY.md` | Describes the studio's development principles, engineering mindset, and approach to maintainable game development. | Not Specified | — |
| `00_studio_standards/DOCUMENTATION_STANDARDS.md` | Defines documentation structure, writing conventions, naming, status, maintenance, and governance. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `GIT_CONVENTIONS.md`, `BRANCHING_STRATEGY.md`, `CODE_REVIEW_GUIDELINES.md`, `DEFINITION_OF_DONE.md` |
| `00_studio_standards/GAME_DEVELOPMENT_LIFECYCLE.md` | Defines the general lifecycle stages and decision points used throughout game development. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `DEFINITION_OF_DONE.md`, `BRANCHING_STRATEGY.md`, `CODE_REVIEW_GUIDELINES.md` |
| `00_studio_standards/GIT_CONVENTIONS.md` | Defines Git usage conventions and repository collaboration practices. | Not Specified | — |
| `00_studio_standards/NAMING_CONVENTIONS.md` | Establishes naming conventions for GDScript, scenes, nodes, assets, resources, and project files. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `DOCUMENTATION_STANDARDS.md`, `GIT_CONVENTIONS.md`, `BRANCHING_STRATEGY.md`, `GDSCRIPT_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md`, `ART_ASSET_STANDARDS.md`, `AUDIO_ASSET_STANDARDS.md`, `CODE_REVIEW_GUIDELINES.md`, `DEFINITION_OF_DONE.md` |
| `00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md` | Defines the standard feature-oriented organization of Godot game projects. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `DOCUMENTATION_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `DEFINITION_OF_DONE.md`, `CODE_REVIEW_GUIDELINES.md`, `ARCHITECTURE_GUIDELINES.md`, `GDSCRIPT_STANDARDS.md`, `ASSET_PIPELINE.md` |
| `00_studio_standards/QUALITY_STANDARDS.md` | Establishes general quality expectations for game development deliverables. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `GAME_DEVELOPMENT_LIFECYCLE.md`, `DEFINITION_OF_DONE.md`, `CODE_REVIEW_GUIDELINES.md`, `DOCUMENTATION_STANDARDS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `ARCHITECTURE_GUIDELINES.md`, `GDSCRIPT_STANDARDS.md`, `ASSET_PIPELINE.md`, `ART_ASSET_STANDARDS.md` |

## 5. Game Design Guidelines

**Directory:** `docs/01_game_design_guidelines/`

Game design guidelines provide reusable principles and methods for designing coherent, engaging, and maintainable gameplay experiences.

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `01_game_design_guidelines/BALANCING_GUIDELINES.md` | Provides principles and methods for evaluating and balancing gameplay systems, player capabilities, resources, and difficulty. | Not Specified | — |
| `01_game_design_guidelines/CORE_LOOP_DESIGN_GUIDELINES.md` | Defines how to design and evaluate core gameplay loops and their supporting progression loops. | Not Specified | — |
| `01_game_design_guidelines/DESIGN_PRINCIPLES.md` | Establishes foundational principles for creating coherent, meaningful, and player-centered game experiences. | Not Specified | — |
| `01_game_design_guidelines/DIFFICULTY_DESIGN_GUIDELINES.md` | Provides guidelines for designing challenge, difficulty progression, fairness, and player failure. | Not Specified | — |
| `01_game_design_guidelines/ECONOMY_DESIGN_GUIDELINES.md` | Defines principles for designing game economies, resources, acquisition, consumption, scarcity, and value. | Not Specified | — |
| `01_game_design_guidelines/GAMEPLAY_DESIGN_GUIDELINES.md` | Provides general principles for designing gameplay experiences, interactions, and gameplay structures. | Not Specified | `DESIGN_PRINCIPLES.md`, `CORE_LOOP_DESIGN_GUIDELINES.md`, `BALANCING_GUIDELINES.md`, `DIFFICULTY_DESIGN_GUIDELINES.md`, `ECONOMY_DESIGN_GUIDELINES.md`, `DEVELOPMENT_PHILOSOPHY.md`, `QUALITY_STANDARDS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md` |
| `01_game_design_guidelines/LEVEL_DESIGN_GUIDELINES.md` | Defines principles for designing levels, spaces, navigation, encounters, pacing, and environmental experiences. | Not Specified | `DESIGN_PRINCIPLES.md`, `GAMEPLAY_DESIGN_GUIDELINES.md`, `CORE_LOOP_DESIGN_GUIDELINES.md`, `DIFFICULTY_DESIGN_GUIDELINES.md`, `BALANCING_GUIDELINES.md`, `DEVELOPMENT_PHILOSOPHY.md`, `QUALITY_STANDARDS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md` |
| `01_game_design_guidelines/MECHANIC_DESIGN_GUIDELINES.md` | Provides guidelines for creating clear, meaningful, and consistent gameplay mechanics. | Not Specified | `DESIGN_PRINCIPLES.md`, `GAMEPLAY_DESIGN_GUIDELINES.md`, `CORE_LOOP_DESIGN_GUIDELINES.md`, `LEVEL_DESIGN_GUIDELINES.md`, `BALANCING_GUIDELINES.md`, `DIFFICULTY_DESIGN_GUIDELINES.md`, `ECONOMY_DESIGN_GUIDELINES.md`, `DEVELOPMENT_PHILOSOPHY.md`, `QUALITY_STANDARDS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md` |
| `01_game_design_guidelines/NARRATIVE_DESIGN_GUIDELINES.md` | Establishes principles for story structure, characters, dialogue, worldbuilding, and narrative integration. | Not Specified | `DESIGN_PRINCIPLES.md`, `GAMEPLAY_DESIGN_GUIDELINES.md`, `CORE_LOOP_DESIGN_GUIDELINES.md`, `LEVEL_DESIGN_GUIDELINES.md`, `MECHANIC_DESIGN_GUIDELINES.md`, `DIFFICULTY_DESIGN_GUIDELINES.md`, `DEVELOPMENT_PHILOSOPHY.md`, `DOCUMENTATION_STANDARDS.md`, `QUALITY_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md` |
| `01_game_design_guidelines/PLAYER_EXPERIENCE_GUIDELINES.md` | Defines principles for understanding and improving player motivation, engagement, usability, and emotional experience. | Not Specified | — |
| `01_game_design_guidelines/PROGRESSION_DESIGN_GUIDELINES.md` | Provides guidelines for designing player progression, unlocks, advancement, mastery, and pacing. | Not Specified | `DESIGN_PRINCIPLES.md`, `CORE_LOOP_DESIGN_GUIDELINES.md`, `GAMEPLAY_DESIGN_GUIDELINES.md`, `MECHANIC_DESIGN_GUIDELINES.md`, `PLAYER_EXPERIENCE_GUIDELINES.md`, `BALANCING_GUIDELINES.md`, `DIFFICULTY_DESIGN_GUIDELINES.md`, `ECONOMY_DESIGN_GUIDELINES.md`, `NARRATIVE_DESIGN_GUIDELINES.md` |
| `01_game_design_guidelines/REWARD_DESIGN_GUIDELINES.md` | Defines principles for reward structures, incentives, reward pacing, and their relationship with gameplay and progression. | Not Specified | `DESIGN_PRINCIPLES.md`, `CORE_LOOP_DESIGN_GUIDELINES.md`, `GAMEPLAY_DESIGN_GUIDELINES.md`, `MECHANIC_DESIGN_GUIDELINES.md`, `PLAYER_EXPERIENCE_GUIDELINES.md`, `PROGRESSION_DESIGN_GUIDELINES.md`, `BALANCING_GUIDELINES.md`, `DIFFICULTY_DESIGN_GUIDELINES.md`, `ECONOMY_DESIGN_GUIDELINES.md`, `NARRATIVE_DESIGN_GUIDELINES.md` |
| `01_game_design_guidelines/UI_UX_DESIGN_GUIDELINES.md` | Establishes principles for designing understandable, accessible, and consistent user interfaces and interactions. | Not Specified | `DESIGN_PRINCIPLES.md`, `GAMEPLAY_DESIGN_GUIDELINES.md`, `PLAYER_EXPERIENCE_GUIDELINES.md`, `CORE_LOOP_DESIGN_GUIDELINES.md`, `MECHANIC_DESIGN_GUIDELINES.md`, `PROGRESSION_DESIGN_GUIDELINES.md`, `REWARD_DESIGN_GUIDELINES.md`, `NARRATIVE_DESIGN_GUIDELINES.md` |

## 6. Technical Standards

**Directory:** `docs/02_technical_standards/`

Technical standards define engineering practices and technical expectations for Godot game projects.

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `02_technical_standards/ARCHITECTURE_GUIDELINES.md` | Defines architectural principles, feature boundaries, dependencies, modularity, and system organization. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `QUALITY_STANDARDS.md`, `DOCUMENTATION_STANDARDS.md`, `CODE_REVIEW_GUIDELINES.md`, `DEFINITION_OF_DONE.md`, `GDSCRIPT_STANDARDS.md`, `adr/README.md` |
| `02_technical_standards/ASSET_PIPELINE.md` | Describes the technical asset import, processing, integration, and optimization pipeline. | Not Specified | `PROJECT_STRUCTURE_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `QUALITY_STANDARDS.md`, `DEFINITION_OF_DONE.md`, `DOCUMENTATION_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md`, `adr/README.md` |
| `02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md` | Establishes principles for saving, loading, serialization, data integrity, and persistent game data. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `QUALITY_STANDARDS.md`, `DEFINITION_OF_DONE.md`, `DOCUMENTATION_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md`, `GDSCRIPT_STANDARDS.md`, `adr/README.md` |
| `02_technical_standards/ENGINE_STANDARDS.md` | Defines Godot engine usage, project configuration, engine compatibility, and general engine-related practices. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `QUALITY_STANDARDS.md`, `DOCUMENTATION_STANDARDS.md`, `DEFINITION_OF_DONE.md`, `ARCHITECTURE_GUIDELINES.md`, `ASSET_PIPELINE.md`, `DATA_PERSISTENCE_GUIDELINES.md`, `adr/README.md` |
| `02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md` | Defines appropriate event-driven communication, signal usage, event ownership, and communication between components. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `QUALITY_STANDARDS.md`, `CODE_REVIEW_GUIDELINES.md`, `ARCHITECTURE_GUIDELINES.md`, `ENGINE_STANDARDS.md`, `GDSCRIPT_STANDARDS.md`, `adr/README.md` |
| `02_technical_standards/GDSCRIPT_STANDARDS.md` | Establishes GDScript coding conventions, structure, typing, formatting, and implementation practices. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `QUALITY_STANDARDS.md`, `DEFINITION_OF_DONE.md`, `CODE_REVIEW_GUIDELINES.md`, `ARCHITECTURE_GUIDELINES.md`, `ENGINE_STANDARDS.md`, `EVENT_AND_SIGNAL_GUIDELINES.md`, `DATA_PERSISTENCE_GUIDELINES.md`, `adr/README.md` |
| `02_technical_standards/PERFORMANCE_GUIDELINES.md` | Provides guidelines for profiling, evaluating, and optimizing CPU, GPU, memory, loading, and runtime performance. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `QUALITY_STANDARDS.md`, `DEFINITION_OF_DONE.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `CODE_REVIEW_GUIDELINES.md`, `ARCHITECTURE_GUIDELINES.md`, `ENGINE_STANDARDS.md`, `GDSCRIPT_STANDARDS.md`, `ASSET_PIPELINE.md`, `EVENT_AND_SIGNAL_GUIDELINES.md`, `DATA_PERSISTENCE_GUIDELINES.md`, `adr/README.md` |
| `02_technical_standards/RESOURCE_MANAGEMENT.md` | Defines Godot resource ownership, loading, caching, sharing, duplication, and lifecycle management. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `QUALITY_STANDARDS.md`, `DEFINITION_OF_DONE.md`, `ARCHITECTURE_GUIDELINES.md`, `ENGINE_STANDARDS.md`, `GDSCRIPT_STANDARDS.md`, `DATA_PERSISTENCE_GUIDELINES.md`, `ASSET_PIPELINE.md`, `PERFORMANCE_GUIDELINES.md`, `EVENT_AND_SIGNAL_GUIDELINES.md`, `adr/README.md` |
| `02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md` | Establishes conventions for scene composition, node hierarchy, naming, ownership, and lifecycle management. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `QUALITY_STANDARDS.md`, `DEFINITION_OF_DONE.md`, `ARCHITECTURE_GUIDELINES.md`, `ENGINE_STANDARDS.md`, `GDSCRIPT_STANDARDS.md`, `EVENT_AND_SIGNAL_GUIDELINES.md`, `RESOURCE_MANAGEMENT.md`, `DATA_PERSISTENCE_GUIDELINES.md`, `PERFORMANCE_GUIDELINES.md`, `ASSET_PIPELINE.md`, `adr/README.md`, `UI_UX_DESIGN_GUIDELINES.md` |
| `02_technical_standards/TESTING_STRATEGY.md` | Defines testing levels, testing approaches, test organization, automation, and validation practices. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `QUALITY_STANDARDS.md`, `DEFINITION_OF_DONE.md`, `CODE_REVIEW_GUIDELINES.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md`, `GDSCRIPT_STANDARDS.md`, `SCENE_AND_NODE_CONVENTIONS.md`, `RESOURCE_MANAGEMENT.md`, `DATA_PERSISTENCE_GUIDELINES.md`, `PERFORMANCE_GUIDELINES.md`, `EVENT_AND_SIGNAL_GUIDELINES.md` |

### 6.1 Architecture Decision Records

**Directory:** `docs/02_technical_standards/adr/`

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `02_technical_standards/adr/README.md` | Defines the Architecture Decision Record process, including when ADRs are required, their structure, lifecycle, and approval responsibilities. | Not Specified | — |

## 7. Art and Audio Standards

**Directory:** `docs/03_art_audio_standards/`

Art and audio standards establish reusable expectations for visual and audio production, integration, and consistency.

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `03_art_audio_standards/ANIMATION_STANDARDS.md` | Defines animation principles, production expectations, timing, motion, integration, and optimization. | Not Specified | `DEVELOPMENT_PHILOSOPHY.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `QUALITY_STANDARDS.md`, `ENGINE_STANDARDS.md`, `ASSET_PIPELINE.md`, `RESOURCE_MANAGEMENT.md`, `GDSCRIPT_STANDARDS.md`, `PERFORMANCE_GUIDELINES.md`, `SCENE_AND_NODE_CONVENTIONS.md`, `EVENT_AND_SIGNAL_GUIDELINES.md`, `GAMEPLAY_DESIGN_GUIDELINES.md`, `MECHANIC_DESIGN_GUIDELINES.md`, `PLAYER_EXPERIENCE_GUIDELINES.md`, `UI_UX_DESIGN_GUIDELINES.md` |
| `03_art_audio_standards/ART_ASSET_STANDARDS.md` | Establishes requirements for visual assets, asset quality, naming, organization, reuse, and integration. | Not Specified | `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `QUALITY_STANDARDS.md`, `ASSET_PIPELINE.md`, `PERFORMANCE_GUIDELINES.md`, `RESOURCE_MANAGEMENT.md`, `ANIMATION_STANDARDS.md` |
| `03_art_audio_standards/ART_PIPELINE.md` | Describes the visual art production lifecycle from planning and concept development through review and engine integration. | Not Specified | `DEFINITION_OF_DONE.md`, `DOCUMENTATION_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `ASSET_PIPELINE.md`, `PERFORMANCE_GUIDELINES.md`, `ART_ASSET_STANDARDS.md`, `ANIMATION_STANDARDS.md` |
| `03_art_audio_standards/AUDIO_ASSET_STANDARDS.md` | Establishes requirements for audio assets, technical properties, naming, quality, and integration. | Not Specified | `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `QUALITY_STANDARDS.md`, `ENGINE_STANDARDS.md`, `PERFORMANCE_GUIDELINES.md`, `RESOURCE_MANAGEMENT.md`, `ART_PIPELINE.md`, `ART_ASSET_STANDARDS.md` |
| `03_art_audio_standards/AUDIO_PIPELINE.md` | Describes the audio production lifecycle from planning and source acquisition through mixing, mastering, and engine integration. | Not Specified | `DEFINITION_OF_DONE.md`, `DOCUMENTATION_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `ENGINE_STANDARDS.md`, `PERFORMANCE_GUIDELINES.md`, `RESOURCE_MANAGEMENT.md`, `AUDIO_ASSET_STANDARDS.md`, `ART_PIPELINE.md` |
| `03_art_audio_standards/UI_UX_STANDARDS.md` | Defines visual and interaction standards for user interfaces and user experience presentation. | Not Specified | `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `QUALITY_STANDARDS.md`, `PLAYER_EXPERIENCE_GUIDELINES.md`, `UI_UX_DESIGN_GUIDELINES.md`, `ARCHITECTURE_GUIDELINES.md`, `EVENT_AND_SIGNAL_GUIDELINES.md`, `GDSCRIPT_STANDARDS.md`, `ART_ASSET_STANDARDS.md`, `ART_PIPELINE.md`, `ANIMATION_STANDARDS.md` |
| `03_art_audio_standards/VISUAL_CONSISTENCY_GUIDELINES.md` | Establishes principles for maintaining visual coherence across characters, environments, objects, interfaces, and other game assets. | Not Specified | `QUALITY_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `PLAYER_EXPERIENCE_GUIDELINES.md`, `UI_UX_DESIGN_GUIDELINES.md`, `ASSET_PIPELINE.md`, `ENGINE_STANDARDS.md`, `ART_ASSET_STANDARDS.md`, `ART_PIPELINE.md`, `ANIMATION_STANDARDS.md`, `UI_UX_STANDARDS.md` |

## 8. Production Standards

**Directory:** `docs/04_production_standards/`

Production standards define how work is planned, organized, tracked, evaluated, and delivered.

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `04_production_standards/BACKLOG_MANAGEMENT.md` | Defines how work items are created, organized, prioritized, refined, tracked, and maintained. | Not Specified | `BRANCHING_STRATEGY.md`, `CODE_REVIEW_GUIDELINES.md`, `DEFINITION_OF_DONE.md`, `DOCUMENTATION_STANDARDS.md`, `GAME_DEVELOPMENT_LIFECYCLE.md` |
| `04_production_standards/MILESTONE_GUIDELINES.md` | Establishes principles for defining, planning, tracking, reviewing, and completing project milestones. | Not Specified | `DEFINITION_OF_DONE.md`, `GAME_DEVELOPMENT_LIFECYCLE.md`, `QUALITY_STANDARDS.md`, `BACKLOG_MANAGEMENT.md` |
| `04_production_standards/POSTMORTEM_GUIDELINES.md` | Defines how to evaluate completed work, identify lessons, and document actionable improvements. | Not Specified | `DEFINITION_OF_DONE.md`, `DEVELOPMENT_PHILOSOPHY.md`, `DOCUMENTATION_STANDARDS.md`, `GAME_DEVELOPMENT_LIFECYCLE.md`, `BACKLOG_MANAGEMENT.md`, `MILESTONE_GUIDELINES.md` |
| `04_production_standards/PROJECT_LIFECYCLE.md` | Describes project-specific production stages, objectives, deliverables, and stage transition criteria. | Not Specified | `GAME_DEVELOPMENT_LIFECYCLE.md`, `DEFINITION_OF_DONE.md`, `DOCUMENTATION_STANDARDS.md`, `BACKLOG_MANAGEMENT.md`, `MILESTONE_GUIDELINES.md`, `POSTMORTEM_GUIDELINES.md` |
| `04_production_standards/RELEASE_PROCESS.md` | Defines the operational process for preparing, validating, approving, publishing, and maintaining releases. | Not Specified | `BRANCHING_STRATEGY.md`, `DEFINITION_OF_DONE.md`, `DOCUMENTATION_STANDARDS.md`, `GAME_DEVELOPMENT_LIFECYCLE.md`, `ENGINE_STANDARDS.md`, `ASSET_PIPELINE.md`, `TESTING_STRATEGY.md`, `PROJECT_LIFECYCLE.md`, `MILESTONE_GUIDELINES.md`, `POSTMORTEM_GUIDELINES.md` |
| `04_production_standards/RISK_MANAGEMENT.md` | Establishes principles for identifying, evaluating, mitigating, tracking, and escalating project risks. | Not Specified | `DEFINITION_OF_DONE.md`, `DEVELOPMENT_PHILOSOPHY.md`, `GAME_DEVELOPMENT_LIFECYCLE.md`, `ARCHITECTURE_GUIDELINES.md`, `PERFORMANCE_GUIDELINES.md`, `TESTING_STRATEGY.md`, `BACKLOG_MANAGEMENT.md`, `MILESTONE_GUIDELINES.md`, `PROJECT_LIFECYCLE.md`, `RELEASE_PROCESS.md`, `POSTMORTEM_GUIDELINES.md` |
| `04_production_standards/SPRINT_WORKFLOW.md` | Defines the sprint planning, execution, review, and retrospective workflow. | Not Specified | `DEFINITION_OF_DONE.md`, `BRANCHING_STRATEGY.md`, `DEVELOPMENT_PHILOSOPHY.md`, `GAME_DEVELOPMENT_LIFECYCLE.md`, `BACKLOG_MANAGEMENT.md`, `MILESTONE_GUIDELINES.md`, `PROJECT_LIFECYCLE.md`, `RISK_MANAGEMENT.md`, `POSTMORTEM_GUIDELINES.md` |
| `04_production_standards/VERSIONING_STANDARDS.md` | Establishes version numbering, release identification, compatibility, and version management conventions. | Not Specified | `BRANCHING_STRATEGY.md`, `DOCUMENTATION_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `DATA_PERSISTENCE_GUIDELINES.md`, `ENGINE_STANDARDS.md`, `RESOURCE_MANAGEMENT.md`, `PROJECT_LIFECYCLE.md`, `RELEASE_PROCESS.md`, `RISK_MANAGEMENT.md` |

## 9. QA Standards

**Directory:** `docs/05_qa_standards/`

QA standards define quality assurance practices and testing-related processes throughout development.

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `05_qa_standards/ACCEPTANCE_CRITERIA_GUIDELINES.md` | Defines how to write clear, measurable, and verifiable acceptance criteria for project deliverables. | Not Specified | `DEFINITION_OF_DONE.md`, `QUALITY_STANDARDS.md`, `CODE_REVIEW_GUIDELINES.md`, `GAMEPLAY_DESIGN_GUIDELINES.md`, `MECHANIC_DESIGN_GUIDELINES.md`, `BACKLOG_MANAGEMENT.md`, `SPRINT_WORKFLOW.md`, `TESTING_STRATEGY.md` |
| `05_qa_standards/BUG_REPORTING.md` | Establishes the process and required information for reporting, classifying, tracking, and verifying defects. | Not Specified | `DEFINITION_OF_DONE.md`, `QUALITY_STANDARDS.md`, `CODE_REVIEW_GUIDELINES.md`, `TESTING_STRATEGY.md`, `BACKLOG_MANAGEMENT.md`, `RISK_MANAGEMENT.md`, `RELEASE_PROCESS.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md` |
| `05_qa_standards/PLAYTESTING_GUIDELINES.md` | Defines methods for conducting player testing, observing behavior, collecting feedback, and evaluating player experience. | Not Specified | `DEFINITION_OF_DONE.md`, `QUALITY_STANDARDS.md`, `PLAYER_EXPERIENCE_GUIDELINES.md`, `DIFFICULTY_DESIGN_GUIDELINES.md`, `BALANCING_GUIDELINES.md`, `CORE_LOOP_DESIGN_GUIDELINES.md`, `UI_UX_DESIGN_GUIDELINES.md`, `BACKLOG_MANAGEMENT.md`, `MILESTONE_GUIDELINES.md`, `POSTMORTEM_GUIDELINES.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md`, `BUG_REPORTING.md`, `TESTING_STRATEGY.md` |
| `05_qa_standards/QA_STRATEGY.md` | Establishes the overall quality assurance approach, responsibilities, activities, and quality objectives. | Not Specified | `DEFINITION_OF_DONE.md`, `QUALITY_STANDARDS.md`, `CODE_REVIEW_GUIDELINES.md`, `DEVELOPMENT_PHILOSOPHY.md`, `TESTING_STRATEGY.md`, `BACKLOG_MANAGEMENT.md`, `MILESTONE_GUIDELINES.md`, `PROJECT_LIFECYCLE.md`, `RISK_MANAGEMENT.md`, `RELEASE_PROCESS.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md`, `BUG_REPORTING.md`, `PLAYTESTING_GUIDELINES.md` |
| `05_qa_standards/REGRESSION_TESTING.md` | Defines how to select, execute, maintain, and evaluate regression tests after changes. | Not Specified | `DEFINITION_OF_DONE.md`, `QUALITY_STANDARDS.md`, `CODE_REVIEW_GUIDELINES.md`, `TESTING_STRATEGY.md`, `RISK_MANAGEMENT.md`, `RELEASE_PROCESS.md`, `QA_STRATEGY.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md`, `BUG_REPORTING.md`, `PLAYTESTING_GUIDELINES.md` |
| `05_qa_standards/TEST_CASE_GUIDELINES.md` | Establishes conventions for designing, documenting, organizing, and executing individual test cases. | Not Specified | `DEFINITION_OF_DONE.md`, `QUALITY_STANDARDS.md`, `TESTING_STRATEGY.md`, `BACKLOG_MANAGEMENT.md`, `QA_STRATEGY.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md`, `BUG_REPORTING.md`, `PLAYTESTING_GUIDELINES.md`, `REGRESSION_TESTING.md` |

## 10. Templates

**Directory:** `docs/06_templates/`

Templates provide reusable document structures that AI agents and developers can instantiate for individual game projects.

Templates are not project specifications themselves. Their purpose is to guide the creation of project-specific documents.

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `06_templates/ADR_TEMPLATE.md` | Template for documenting architectural decisions, alternatives, consequences, and approval. | Not Specified | — |
| `06_templates/ART_DIRECTION_TEMPLATE.md` | Template for defining a project's visual identity, artistic principles, references, and production constraints. | Not Specified | — |
| `06_templates/AUDIO_DIRECTION_TEMPLATE.md` | Template for defining audio identity, music, sound effects, ambience, dialogue, and technical direction. | Not Specified | — |
| `06_templates/CHARACTER_TEMPLATE.md` | Template for documenting individual characters, including narrative identity, personality, appearance, behavior, and gameplay role. | Not Specified | — |
| `06_templates/CORE_GAME_LOOP_TEMPLATE.md` | Template for documenting the core gameplay loop, its stages, player actions, feedback, and supporting loops. | Not Specified | — |
| `06_templates/CORE_PILLARS_TEMPLATE.md` | Template for defining a game's core design pillars, player promises, priorities, and validation criteria. | Not Specified | — |
| `06_templates/GAMEPLAY_SYSTEM_TEMPLATE.md` | Template for specifying gameplay systems, their components, rules, interactions, and player-facing behavior. | Not Specified | — |
| `06_templates/GAME_DESIGN_DOCUMENT_TEMPLATE.md` | Template for creating a comprehensive game design document covering the major aspects of a game. | Not Specified | — |
| `06_templates/GAME_VISION_TEMPLATE.md` | Template for defining a game's identity, vision, audience, intended experience, and creative direction. | Not Specified | — |
| `06_templates/LEVEL_DESIGN_TEMPLATE.md` | Template for documenting level objectives, layout, navigation, encounters, pacing, and player experience. | Not Specified | `LEVEL_DESIGN_GUIDELINES.md`, `TESTING_STRATEGY.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md` |
| `06_templates/MECHANIC_TEMPLATE.md` | Template for specifying an individual gameplay mechanic, including rules, states, interactions, and consequences. | Not Specified | `MECHANIC_DESIGN_GUIDELINES.md`, `BALANCING_GUIDELINES.md`, `PROGRESSION_DESIGN_GUIDELINES.md`, `GDSCRIPT_STANDARDS.md`, `TESTING_STRATEGY.md`, `TEST_CASE_GUIDELINES.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md` |
| `06_templates/MILESTONE_TEMPLATE.md` | Template for defining milestone objectives, deliverables, acceptance criteria, dependencies, and completion status. | Not Specified | `MILESTONE_GUIDELINES.md`, `BACKLOG_MANAGEMENT.md`, `SPRINT_WORKFLOW.md`, `RISK_MANAGEMENT.md`, `DEFINITION_OF_DONE.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md`, `QA_STRATEGY.md`, `POSTMORTEM_GUIDELINES.md` |
| `06_templates/NARRATIVE_OVERVIEW_TEMPLATE.md` | Template for documenting a game's narrative direction, premise, world, themes, characters, and story structure. | Not Specified | — |
| `06_templates/POSTMORTEM_TEMPLATE.md` | Template for documenting completed work, outcomes, lessons learned, and improvement actions. | Not Specified | `POSTMORTEM_GUIDELINES.md`, `MILESTONE_GUIDELINES.md`, `BACKLOG_MANAGEMENT.md`, `SPRINT_WORKFLOW.md`, `RISK_MANAGEMENT.md`, `DEFINITION_OF_DONE.md`, `QA_STRATEGY.md`, `BUG_REPORTING.md` |
| `06_templates/QUEST_TEMPLATE.md` | Template for documenting quest objectives, stages, characters, choices, outcomes, rewards, and completion conditions. | Not Specified | `NARRATIVE_DESIGN_GUIDELINES.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md` |
| `06_templates/ROADMAP_TEMPLATE.md` | Template for defining project direction, strategic priorities, milestones, and planned development outcomes. | Not Specified | `PROJECT_LIFECYCLE.md`, `MILESTONE_GUIDELINES.md`, `MILESTONE_TEMPLATE.md`, `BACKLOG_MANAGEMENT.md`, `SPRINT_WORKFLOW.md`, `RISK_MANAGEMENT.md`, `DEFINITION_OF_DONE.md`, `QA_STRATEGY.md`, `POSTMORTEM_GUIDELINES.md` |
| `06_templates/TECHNICAL_DESIGN_TEMPLATE.md` | Template for documenting technical solutions, architecture, components, dependencies, implementation considerations, and validation. | Not Specified | — |
| `06_templates/TECHNICAL_OVERVIEW_TEMPLATE.md` | Template for describing a project's technical foundation, technology choices, architecture, tools, and major technical constraints. | Not Specified | `ARCHITECTURE_GUIDELINES.md`, `GDSCRIPT_STANDARDS.md`, `SCENE_AND_NODE_CONVENTIONS.md`, `RESOURCE_MANAGEMENT.md`, `EVENT_AND_SIGNAL_GUIDELINES.md`, `PERFORMANCE_GUIDELINES.md`, `DATA_PERSISTENCE_GUIDELINES.md`, `TESTING_STRATEGY.md`, `adr/README.md` |
| `06_templates/TEST_PLAN_TEMPLATE.md` | Template for planning testing activities, scope, environments, scenarios, resources, execution, and exit criteria. | Not Specified | `QA_STRATEGY.md`, `TESTING_STRATEGY.md`, `TEST_CASE_GUIDELINES.md`, `BUG_REPORTING.md`, `REGRESSION_TESTING.md`, `ACCEPTANCE_CRITERIA_GUIDELINES.md`, `PLAYTESTING_GUIDELINES.md`, `DEFINITION_OF_DONE.md` |
| `06_templates/WORLD_OVERVIEW_TEMPLATE.md` | Template for documenting a game's world, setting, geography, history, cultures, factions, locations, and world rules. | Not Specified | `DESIGN_PRINCIPLES.md`, `NARRATIVE_DESIGN_GUIDELINES.md`, `LEVEL_DESIGN_GUIDELINES.md`, `GAMEPLAY_DESIGN_GUIDELINES.md`, `ART_ASSET_STANDARDS.md`, `ART_PIPELINE.md`, `AUDIO_ASSET_STANDARDS.md` |

## 11. AI Agent Workflows

**Directory:** `docs/07_agent_workflows/`

Agent workflows define repeatable procedures for AI agents performing common game development tasks.

These workflows complement the studio standards and templates. They do not replace human approval or authorize agents to make significant decisions independently.

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `07_agent_workflows/CREATE_CORE_PILLARS.md` | Defines the process for identifying, evaluating, documenting, and proposing a game's core design pillars. | Not Specified | — |
| `07_agent_workflows/CREATE_GAME_CONCEPT.md` | Defines the process for developing and documenting a game concept from an initial idea. | Not Specified | — |
| `07_agent_workflows/CREATE_GAME_VISION.md` | Defines the process for establishing a game's identity, intended experience, audience, and creative direction. | Not Specified | — |
| `07_agent_workflows/CREATE_TECHNICAL_DESIGN.md` | Defines the process for analyzing technical requirements, evaluating solutions, and producing technical design documentation. | Not Specified | — |
| `07_agent_workflows/DESIGN_GAMEPLAY_SYSTEM.md` | Defines the process for designing and documenting interconnected gameplay systems. | Not Specified | — |
| `07_agent_workflows/DESIGN_GAME_MECHANIC.md` | Defines the process for designing, specifying, and evaluating individual gameplay mechanics. | Not Specified | — |
| `07_agent_workflows/FIX_BUG.md` | Defines the process for reproducing, investigating, correcting, and validating software defects. | Not Specified | — |
| `07_agent_workflows/GENERATE_TESTS.md` | Defines the process for analyzing requirements and generating appropriate automated or manual test cases. | Not Specified | — |
| `07_agent_workflows/IMPLEMENT_FEATURE.md` | Defines the process for analyzing requirements, implementing features, validating changes, and preparing them for review. | Not Specified | — |
| `07_agent_workflows/REVIEW_CODE.md` | Defines the process for reviewing code changes for correctness, architecture, maintainability, testing, and quality. | Not Specified | — |
| `07_agent_workflows/REVIEW_DESIGN.md` | Defines the process for evaluating game design documents, gameplay systems, mechanics, and player experience. | Not Specified | — |
| `07_agent_workflows/UPDATE_DOCUMENTATION.md` | Defines the process for creating, updating, synchronizing, validating, and maintaining project documentation. | Not Specified | — |
| `07_agent_workflows/UPDATE_PROJECT_STATUS.md` | Defines the process for evaluating and reporting project progress, milestones, risks, blockers, and upcoming priorities. | Not Specified | — |

## 12. Documentation Responsibilities

The following distinctions define how the documentation categories should be used.

| Category | Primary responsibility |
|---|---|
| Studio Standards | Establish reusable rules and expectations across projects. |
| Game Design Guidelines | Provide reusable principles for making game design decisions. |
| Technical Standards | Establish reusable engineering and implementation practices. |
| Art and Audio Standards | Establish reusable visual and audio production expectations. |
| Production Standards | Define how development work is planned and managed. |
| QA Standards | Define quality assurance and testing practices. |
| Templates | Provide structures for creating project-specific documents. |
| Agent Workflows | Define procedures AI agents follow when executing development tasks. |

### 12.1 Project-specific documentation

The shared documentation repository is not the location for individual game specifications, implementation records, or production history.

Each game project should maintain its own documentation, including when applicable:

- Game concept and vision.
- Core pillars.
- Game design document.
- Gameplay and mechanic specifications.
- Character, quest, and level specifications.
- Narrative and world documentation.
- Technical design documents.
- Architecture decision records.
- Test plans and test cases.
- Backlog and roadmap.
- Milestone and sprint records.
- Risk register.
- Release records.
- Postmortems.

Project-specific documentation should follow the reusable studio standards and use the templates provided in `docs/06_templates/`. Documents created from those templates belong under `game_project/docs/`.

## 13. Maintenance Responsibilities

Documentation maintenance is a shared responsibility.

### 13.1 AI agents

AI agents MUST:

- Read this inventory before creating or modifying documentation.
- Inspect the actual repository structure.
- Use existing documents when they already serve the required purpose.
- Preserve exact paths and filenames.
- Update this inventory when documentation structure changes.
- Register only files that physically exist.
- Verify inventory entries after changes.
- Report missing references and inconsistencies.
- Avoid creating duplicate authoritative documents.
- Never mark documents Approved without human authorization.

### 13.2 Human owner

The authorized documentation owner is responsible for:

- Approving studio-wide standards.
- Approving significant documentation structure changes.
- Reviewing proposed changes to shared standards.
- Establishing document approval status.
- Resolving conflicting documentation decisions.
- Maintaining the overall quality and consistency of the documentation repository.

## 14. Inventory Verification

The inventory should be verified whenever documentation changes occur.

Verification should confirm:

- Every registered path exists.
- Every listed filename matches the actual filename.
- No existing documentation file is unintentionally omitted.
- No document appears more than once.
- Descriptions accurately represent document purposes.
- Directory classifications remain correct.
- Deprecated documents are identified appropriately.
- Cross-references point to valid locations where applicable.

A complete inventory verification should compare this document against the actual contents of the `docs/` directory.

## 15. Inventory Summary

The current documentation repository contains the following registered files:

| Category | Document count |
|---|---:|
| Documentation inventory | 1 |
| Studio standards | 10 |
| Game design guidelines | 13 |
| Technical standards | 11 |
| Art and audio standards | 7 |
| Production standards | 8 |
| QA standards | 6 |
| Templates | 20 |
| AI agent workflows | 13 |
| **Total** | **89** |

The governance files registered in section 16 are not counted in the total above, which covers the Markdown documents under `docs/`.

| Location | File count |
|---|---:|
| Agent rules (`.cline/rules/`) | 6 |
| Execution workflows (`.clinerules/workflows/`) | 4 |
| GitHub configuration (`.github/`) | 5 |
| Reference collections (`references/`) | 4 |
| **Total** | **19** |

**Inventory status:** Reflects the actual contents of the repository. Status and dependencies are recorded for each registered file; `Not Specified` means that no status has been established.

**Approval status:** Not specified by this inventory.

**Maintenance:** Update this document whenever the actual documentation repository structure changes.

## 16. Governance Files Outside `docs/`

The following files govern repository behavior, agent behavior, or the documentation process itself. They are registered here so that the inventory covers every file that can contradict or amend the documentation under `docs/`.

Paths in this section are relative to the repository root.

| Document | Description | Status | Dependencies |
|---|---|---|---|
| `.cline/rules/architecture-rules.md` | Always-loaded rule defining architectural principles and implementation constraints. | Not Specified | — |
| `.cline/rules/asset-rules.md` | Always-loaded rule defining how scenes, resources, and assets are handled as files. | Not Specified | `ASSET_PIPELINE.md`, `ART_ASSET_STANDARDS.md`, `ART_PIPELINE.md`, `AUDIO_ASSET_STANDARDS.md`, `AUDIO_PIPELINE.md`, `ANIMATION_STANDARDS.md`, `UI_UX_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `RESOURCE_MANAGEMENT.md`, `SCENE_AND_NODE_CONVENTIONS.md`, `ENGINE_STANDARDS.md` |
| `.cline/rules/documentation-management.md` | Always-loaded rule defining how AI agents discover, maintain, and verify documentation. | Not Specified | `DOCUMENTATION_STANDARDS.md` |
| `.cline/rules/gdscript-standards.md` | Always-loaded rule defining how GDScript is written, reviewed, and validated. | Not Specified | `GDSCRIPT_STANDARDS.md`, `NAMING_CONVENTIONS.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `ARCHITECTURE_GUIDELINES.md`, `SCENE_AND_NODE_CONVENTIONS.md`, `EVENT_AND_SIGNAL_GUIDELINES.md`, `RESOURCE_MANAGEMENT.md`, `DATA_PERSISTENCE_GUIDELINES.md`, `PERFORMANCE_GUIDELINES.md`, `ENGINE_STANDARDS.md`, `TESTING_STRATEGY.md`, `CODE_REVIEW_GUIDELINES.md` |
| `.cline/rules/git-workflow.md` | Always-loaded rule defining mandatory agent Git behavior and repository protections. | Not Specified | `GIT_CONVENTIONS.md`, `BRANCHING_STRATEGY.md` |
| `.cline/rules/project-context.md` | Always-loaded rule defining repository roots, directory responsibilities, and authority order. | Not Specified | `adr/README.md`, `PROJECT_STRUCTURE_STANDARDS.md`, `DOCUMENTATION_STANDARDS.md`, `DEVELOPMENT_PHILOSOPHY.md`, `ENGINE_STANDARDS.md`, `TESTING_STRATEGY.md` |
| `.clinerules/workflows/code-review.md` | Cline execution workflow for reviewing a change. | Not Specified | `REVIEW_CODE.md` |
| `.clinerules/workflows/create-technical-design.md` | Cline execution workflow for producing a technical design. | Not Specified | `CREATE_TECHNICAL_DESIGN.md`, `adr/README.md` |
| `.clinerules/workflows/fix-bug.md` | Cline execution workflow for investigating and correcting a defect. | Not Specified | `FIX_BUG.md`, `BRANCHING_STRATEGY.md`, `GIT_CONVENTIONS.md`, `DEFINITION_OF_DONE.md` |
| `.clinerules/workflows/implement-feature.md` | Cline execution workflow for implementing a feature. | Not Specified | `IMPLEMENT_FEATURE.md`, `BRANCHING_STRATEGY.md`, `GIT_CONVENTIONS.md` |
| `.github/ISSUE_TEMPLATE/bug_report.md` | Defect report form aligned with the defect reporting standard. | Not Specified | `BUG_REPORTING.md` |
| `.github/ISSUE_TEMPLATE/feature_request.md` | Feature request form for proposing new functionality. | Not Specified | — |
| `.github/PULL_REQUEST_TEMPLATE.md` | Pull request description template aligned with the review and completion standards. | Not Specified | `BRANCHING_STRATEGY.md`, `DEFINITION_OF_DONE.md`, `GIT_CONVENTIONS.md`, `CODE_REVIEW_GUIDELINES.md`, `TESTING_STRATEGY.md` |
| `.github/workflows/ci.yml` | Continuous integration workflow: project import, script parse check, and automated tests. | Not Specified | `TESTING_STRATEGY.md`, `BRANCHING_STRATEGY.md` |
| `.github/workflows/validation.yml` | Documentation validation workflow: reference resolution and inventory parity. | Not Specified | `DOCUMENTATION_STANDARDS.md` |
| `references/architectural/README.md` | Reference collection for architectural material. | Not Specified | — |
| `references/audio/README.md` | Reference collection for audio material. | Not Specified | — |
| `references/historical/README.md` | Reference collection for historical material. | Not Specified | — |
| `references/visual/README.md` | Reference collection for visual material. | Not Specified | — |

**Approval status:** Not specified by this inventory.

**Maintenance:** Update this document whenever the actual documentation repository structure changes.
