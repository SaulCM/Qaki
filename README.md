# Qaki

Prototype isometric game, developed in Godot 4.7.

This repository has two roots: the studio documentation that governs how the game is built, and the Godot project itself.

## Repository Layout

| Path | Responsibility |
|---|---|
| `docs/` | Reusable studio documentation: standards, guidelines, technical standards, art and audio standards, production and QA standards, templates, and agent workflows. |
| `game_project/` | The Godot project. `game_project/project.godot` is the single Godot project definition; `res://` resolves here. |
| `AGENTS.md` | Repository-level OpenCode instructions and task routing. |
| `opencode.json` | OpenCode V1 configuration: instruction loading, command and agent discovery, and permissions. |
| `.opencode/rules/` | Always-loaded OpenCode operating rules. |
| `.opencode/command/` | Thin execution adapters that delegate to the authoritative studio workflows in `docs/07_agent_workflows/`. |
| `.opencode/agent/` | Read-only specialist agents for review, verification, and documentation audit. |
| `.github/` | CI workflows, issue templates, and the pull request template. |
| `references/` | Repository-level reference material. |

## Start Here

- **Find the right document** → `docs/README.md`.
- **Current project status** → `game_project/PROJECT_STATUS.md`.
- **Studio-wide rules** → `docs/00_studio_standards/`.
- **Technical standards** → `docs/02_technical_standards/`.
- **OpenCode instructions** → `AGENTS.md` and `.opencode/rules/`.
- **AI-assisted procedures** → `docs/07_agent_workflows/` and `.opencode/command/`.
- **Documentation inventory** → `docs/DOCUMENTATION_INVENTORY.md`.

## Documentation Map

| Directory | Contents |
|---|---|
| `docs/00_studio_standards/` | Mandatory studio practices: lifecycle, philosophy, structure, naming, documentation, Git, review, quality, and completion. |
| `docs/01_game_design_guidelines/` | Reusable game design principles and guidelines. |
| `docs/02_technical_standards/` | Engineering, architecture, Godot, GDScript, assets, persistence, performance, and testing standards. |
| `docs/02_technical_standards/adr/` | The studio ADR process (`ADR_PROCESS.md`) and its index. |
| `docs/03_art_audio_standards/` | Visual, audio, animation, and UI standards. |
| `docs/04_production_standards/` | Production lifecycle, planning, release, risk, and postmortem guidance. |
| `docs/05_qa_standards/` | Quality assurance, testing, defect reporting, and playtesting. |
| `docs/06_templates/` | Templates for project-specific documents. |
| `docs/07_agent_workflows/` | Authoritative procedures for AI-assisted tasks. |

## Current State

- Development phase: pre-production (`game_project/PROJECT_STATUS.md`).
- Agent configuration: OpenCode only (`AGENTS.md`, `opencode.json`, and `.opencode/`).
- Engine: Godot 4.7 feature level; verified executable and CI toolchain use Godot 4.7.2. Forward Plus rendering; Jolt Physics.
- No game scripts, scenes, or resources exist outside `game_project/addons/` yet.
- `game_project/docs/` has not been created yet; project-specific documentation will be added there as decisions are approved.

## Contributing

- `main` and `develop` are protected. Do not commit directly to either.
- Use an approved branch prefix: `feature/`, `fix/`, `refactor/`, `test/`, `docs/`, or `chore/`.
- Game requirements and design decisions are supplied and approved by the project owner. Agents record them and do not invent them.
- `.github/workflows/validation.yml` is configured to check documentation references and inventory parity, but it has not yet been executed. Do not claim a validation check passed until it has actually run.

## Scope of This File

This page is a front door, not a standard. `docs/README.md` routes tasks to the authoritative documents.
