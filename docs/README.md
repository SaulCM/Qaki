# Studio Documentation

This directory contains the studio's reusable documentation for the Qaki project. Use this page to find the document that governs a task.

## How Authority Works

1. Explicit instructions from the project owner for the current task.
2. Approved project-specific requirements and specifications in `game_project/docs/`.
3. Approved Architecture Decision Records.
4. Studio standards in `docs/00_studio_standards/` and `docs/02_technical_standards/`.
5. Studio guidelines in `docs/01_game_design_guidelines/` and `docs/03_art_audio_standards/`.

Templates are structures, not requirements. Workflows are procedures, not standards. When two documents conflict, follow `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md` (section 4.7) and report the conflict rather than choosing silently.

## Directory Map

| Directory | Purpose |
|---|---|
| `docs/00_studio_standards/` | Mandatory studio practices: development philosophy, lifecycle, project structure, naming, documentation, Git, review, quality, and definition of done. |
| `docs/01_game_design_guidelines/` | Reusable game design principles and guidelines. |
| `docs/02_technical_standards/` | Engineering, architecture, Godot, GDScript, assets, persistence, performance, and testing standards. |
| `docs/02_technical_standards/adr/` | The studio ADR process (`ADR_PROCESS.md`) and the directory index (`README.md`). |
| `docs/03_art_audio_standards/` | Visual art, animation, audio, and UI standards. |
| `docs/04_production_standards/` | Production lifecycle, planning, milestones, release, risk, and postmortem guidance. |
| `docs/05_qa_standards/` | Quality assurance, testing, acceptance, defect reporting, regression, and playtesting. |
| `docs/06_templates/` | Templates for project-specific documents. |
| `docs/07_agent_workflows/` | Authoritative procedures for AI-assisted tasks. |

## Read This for That Task

| Task | Start with | Also relevant |
|---|---|---|
| Implement a feature | `docs/07_agent_workflows/IMPLEMENT_FEATURE.md` | `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`, `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`, `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md`, `docs/00_studio_standards/DEFINITION_OF_DONE.md` |
| Fix a defect | `docs/07_agent_workflows/FIX_BUG.md` | `docs/05_qa_standards/BUG_REPORTING.md`, `docs/05_qa_standards/REGRESSION_TESTING.md` |
| Refactor without changing behavior | `docs/07_agent_workflows/REFACTOR_CODE.md` | `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`, `docs/02_technical_standards/TESTING_STRATEGY.md` |
| Produce a technical design | `docs/07_agent_workflows/CREATE_TECHNICAL_DESIGN.md` | `docs/06_templates/TECHNICAL_DESIGN_TEMPLATE.md`, `docs/02_technical_standards/adr/ADR_PROCESS.md` |
| Review a change | `docs/07_agent_workflows/REVIEW_CODE.md` | `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md`, `docs/00_studio_standards/DEFINITION_OF_DONE.md` |
| Update documentation | `docs/07_agent_workflows/UPDATE_DOCUMENTATION.md` | `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`, `docs/DOCUMENTATION_INVENTORY.md` |
| Add or change an asset | `docs/03_art_audio_standards/` | `docs/02_technical_standards/ASSET_PIPELINE.md`, `.opencode/rules/asset-rules.md` |
| Build or change UI | `docs/03_art_audio_standards/UI_UX_STANDARDS.md` | `docs/01_game_design_guidelines/UI_UX_DESIGN_GUIDELINES.md`, `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md` |
| Test something | `docs/02_technical_standards/TESTING_STRATEGY.md` | `docs/05_qa_standards/` |
| Investigate performance | `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md` | `docs/02_technical_standards/ENGINE_STANDARDS.md` |
| Record an architecture decision | `docs/02_technical_standards/adr/ADR_PROCESS.md` | `docs/06_templates/ADR_TEMPLATE.md`, `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md` |
| Plan production or a release | `docs/04_production_standards/` | `docs/00_studio_standards/GAME_DEVELOPMENT_LIFECYCLE.md`, `docs/04_production_standards/PROJECT_LIFECYCLE.md`, `docs/00_studio_standards/BRANCHING_STRATEGY.md` |
| Report project status | `docs/07_agent_workflows/UPDATE_PROJECT_STATUS.md` | `game_project/PROJECT_STATUS.md` |

## Where Project-Specific Documentation Goes

Game-specific documentation belongs under `game_project/docs/`, for example:

- `game_project/docs/game_design/`
- `game_project/docs/technical/`
- `game_project/docs/production/`
- `game_project/docs/qa/`
- `game_project/docs/art/`
- `game_project/docs/audio/`

Create a subdirectory only when an actual document requires it. Do not add game-specific documentation to `docs/`, and do not copy studio standards into `game_project/docs/`.

`game_project/PROJECT_STATUS.md` is a documented exception: it is maintained at the Godot project root as the project's status front page (`docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`, section 5.8).

## Finding and Registering Documents

`docs/DOCUMENTATION_INVENTORY.md` registers every document under `docs/` and every governance file in `AGENTS.md`, `opencode.json`, `.opencode/`, `.github/`, and `references/`.

When a document is created, renamed, moved, or deleted, update the inventory in the same change. The inventory records only files that exist.

## Status and Approval

The inventory records a status for each registered file. `Not Specified` means that no status has been established; it is not an approval.

Approval is a project owner decision. A document's presence, age, or apparent completeness does not establish approval.

## Agent Configuration

OpenCode is the sole supported agent configuration. `AGENTS.md` routes tasks, `.opencode/rules/` contains operating rules, and `.opencode/agent/` contains read-only specialist agents. Execution adapters live in `.opencode/command/` and delegate to the authoritative workflows in `docs/07_agent_workflows/`; they do not define independent procedures. `opencode.json` declares instruction loading, command and agent discovery, and permissions, and must not contain provider or credential configuration.

## Related Documents

- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/DOCUMENTATION_INVENTORY.md`
- `README.md` (repository front door)
