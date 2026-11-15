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
| `game_project/` | Godot project root. It currently contains `project.godot`, `icon.svg`, `icon.svg.import`, `PROJECT_STATUS.md`, and `addons/`. |
| `game_project/docs/` | Game-specific documentation created from studio templates. Planned; it does not exist yet. |

Repository-level configuration files (`.clineignore`, `.gitattributes`, `.gitignore`, `README.md`) remain at the repository root.

**Planned, not yet created.** `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md` (sections 4.2, 4.3, and 5) defines the intended layout of the Godot project — `assets/`, `features/`, `shared/`, `infrastructure/`, `tests/`, and `docs/` under `game_project/`. Those structures are reference structures, not a requirement to create every directory, and none of them exists at present. `game_project/docs/` is part of the approved architecture: create it and its subdirectories only when an actual game-specific document requires them, and create any other directory only when an actual file requires it.

Do not state, assume, or rely on a planned directory as if it already exists. Verify the current structure before depending on a path.

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

### 5.1 Greenfield Project Authorship

Where the game project has not yet defined and approved its game vision, game pillars, game design, technical design, or other project-specific requirements — the current state of this repository — the gap MUST NOT be closed by inventing content.

- The project owner is responsible for providing and approving the following, consistent with `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md` (section 12.1) and `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md` (section 8.2):
  - the game vision;
  - the game pillars;
  - game design decisions;
  - technical architecture decisions;
  - project-specific requirements.
- The agent MAY ask the project owner questions, analyse alternatives, present recommendations with their trade-offs, record decisions the project owner has approved, and identify missing requirements and contradictions between documents.
- The agent MUST NOT invent, infer, or silently extend game requirements, design decisions, or architectural constraints, and MUST NOT present a recommendation, draft, or assumption as an approved decision.
- When required information is missing, the agent MUST ask the project owner for it, or explicitly mark it as undecided in the task report or the project document concerned. It MUST NOT proceed as though the gap had been settled.
- A decision supplied by the project owner is recorded as a project document under `game_project/docs/` at the location required by `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md` (section 3.3), and counts as approved only when the project owner explicitly approved it. Creating or updating that document follows `.cline/rules/documentation-management.md`.

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

## 8. Minimum Verification Contract

`docs/02_technical_standards/TESTING_STRATEGY.md` (section 13.6) requires a minimum verification contract. No testing framework, test runner, or CI job exists in this repository, and no game script, scene, or main scene exists yet, so this section records the checks that can actually be executed today. `TESTING_STRATEGY.md` (section 11.3) requires project-specific execution commands to be documented in the game repository; the long-term record belongs in `game_project/docs/technical/overview.md`, which does not exist yet, so these values are recorded here until it is created.

- **Engine executable (verified 2026-11-15):** `C:\Program Files\Godot\Godot_v4.7.2-stable_win64.exe\Godot_v4.7.2-stable_win64_console.exe`, reporting `4.7.2.stable.official.ed1daf0bf` for `--version`. If that path does not exist, report it; do not substitute a different engine version without owner approval.
- **Automated project validation:** `& '<engine executable>' --headless --path game_project --import` — verified with exit status `0`. It opens the project headlessly, imports resources, loads the enabled `godot_mcp` editor plugin, and quits. The plugin reports `ObjectDB instances were leaked at exit` and `resources still in use at exit` on stderr; these originate from the plugin's shutdown, and the exit status remains `0`.
- **Script parse check** (not yet applicable; no game scripts exist): `& '<engine executable>' --headless --path game_project --check-only --script <script path>`.
- **Headless smoke run** (not yet applicable; no main scene is defined, and the command currently exits with status `1` and `Can't run project: no main scene defined`): `& '<engine executable>' --headless --path game_project --quit-after <frames>`.
- **Manual smoke checklist:** the five checks in `docs/02_technical_standards/TESTING_STRATEGY.md` (section 13.6) apply to every change, together with the scenes and behavior that the change affects.

Completion reports MUST state which automated commands were executed, their exit status and relevant output, which manual checks were performed, and that no test framework, runner, or CI job exists. A change MUST NOT be described as tested, passing, or CI-verified on the strength of these checks alone.

These commands write only to `game_project/.godot/`, which `.gitignore` excludes (`.gitignore`, line 7). That directory MUST NOT be committed.