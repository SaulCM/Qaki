# Project Context

## 1. Repository Identity

This repository is the solo-developed **Qaki** studio workspace and Godot game repository.

It has two distinct roots:

| Root | Purpose |
|---|---|
| Repository root | Studio infrastructure, reusable studio documentation, references, and repository-level configuration. |
| `game_project/` | The Godot game project, including all game implementation and game-specific documentation. |

Repository root responsibilities:

- Cline configuration and execution workflows.
- GitHub configuration.
- Reusable studio documentation.
- Repository-level reference material.
- Version-control and repository configuration.

The Godot project root is `game_project/`. It contains `project.godot` and is the only directory treated as a Godot project.

The repository root MUST NOT be treated as the Godot project root.

## 2. Directory Responsibilities

| Path | Responsibility |
|---|---|
| `.cline/` | Cline configuration. `.cline/rules/` contains always-loaded agent rules. |
| `.clinerules/` | Cline execution workflows in `.clinerules/workflows/`. |
| `.github/` | GitHub configuration: CI workflows, issue templates, and pull request template. |
| `docs/` | Reusable studio documentation only: standards, guidelines, templates, and agent workflows. |
| `references/` | Repository-level reference material used for research and production support. |
| `game_project/` | Godot project root: `project.godot`, `addons/`, `assets/`, `features/`, `shared/`, `infrastructure/`, `tests/`. |
| `game_project/docs/` | Game-specific documentation created from studio templates. |

Repository-level configuration files (`.clineignore`, `.gitattributes`, `.gitignore`, `README.md`) remain at the repository root.

`game_project/docs/` is part of the approved architecture. Create its subdirectories only when an actual game-specific document requires them.

## 3. Documentation Boundaries

- Never create game-specific documentation under repository-root `docs/`.
- Never create studio-wide documentation under `game_project/docs/`.
- Resolve project-specific documentation paths from the Godot project root (`game_project/`).
- Resolve studio documentation paths from the repository root.
- Read `docs/DOCUMENTATION_INVENTORY.md` before selecting studio documentation.
- Follow `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md` for documentation structure, authority, and maintenance.
- Follow `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md` for repository and Godot project organization.
- Studio templates live in `docs/06_templates/`. Instantiating a template produces a game-specific document under `game_project/docs/`.
- Studio agent workflows live in `docs/07_agent_workflows/`. Cline execution workflows live in `.clinerules/workflows/`.
- Do not duplicate studio documentation inside `game_project/docs/`. Reference studio documents instead.

## 4. Godot Development Boundaries

- Treat `game_project/` as the Godot project root.
- Game scripts, scenes, resources, and assets belong inside `game_project/`.
- Use GDScript as the implementation language.
- Do not introduce C# without explicit owner approval.
- Third-party plugins and addons belong in `game_project/addons/`.
- Feature-specific implementation belongs in `game_project/features/`.
- Shared game code belongs in `game_project/shared/`.
- Project-wide infrastructure belongs in `game_project/infrastructure/`.
- Game implementation must not depend on repository documentation directories at runtime.
- Do not create unnecessary empty directories.

## 5. Agent Behavior

- Inspect existing files before creating new ones.
- Preserve established architecture and conventions.
- Do not invent game design decisions.
- Request approval for significant architectural changes.
- Never modify files outside the task scope.
- Report conflicts between authoritative documents instead of silently choosing one.

## 6. Authority Order

1. Explicit instructions from the human maintainer for the current task.
2. Approved project-specific requirements and specifications.
3. Approved Architecture Decision Records.
4. Applicable studio standards, including mandatory documentation standards.
5. Applicable domain guidelines.
6. General engineering and game-development practices.

## 7. AI Tool Configuration Protection

- Never modify Cline settings, API provider selection, API keys, model selection, API endpoints, authentication credentials, or other AI tool configuration.
- Never change the configured AI provider from its current selection.
- Never attempt to optimize, repair, replace, or reconfigure the AI provider.
- Treat all AI tool configuration as user-managed and outside repository task scope.
- If a task appears to require changing AI tool configuration, stop and request explicit owner approval.
- These restrictions apply even when a configuration change appears necessary to complete a task.