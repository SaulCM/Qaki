# Project Context

## 1. Repository identity and roots

This repository is the solo-developed **Qaki** studio workspace and Godot game repository.

| Root | Purpose |
|---|---|
| Repository root | Studio infrastructure, reusable studio documentation, references, and repository-level configuration. |
| `game_project/` | The Godot game project, including game implementation and game-specific documentation. |

The Godot project root is `game_project/`. It contains `project.godot` and is the only directory treated as a Godot project. The repository root MUST NOT be treated as the Godot project root.

## 2. Directory responsibilities

| Path | Responsibility |
|---|---|
| `.opencode/rules/` | Always-loaded OpenCode operating rules. |
| `.opencode/command/` | Thin OpenCode execution adapters that delegate to `docs/07_agent_workflows/`. |
| `.opencode/agent/` | Read-only specialist OpenCode agents. |
| `.github/` | GitHub configuration: CI workflows, issue templates, and pull request template. |
| `docs/` | Reusable studio documentation only: standards, guidelines, templates, and agent workflows. |
| `references/` | Repository-level reference material used for research and production support. |
| `game_project/` | Godot project root. It currently contains `project.godot`, `icon.svg`, `icon.svg.import`, `PROJECT_STATUS.md`, and `addons/`. |
| `game_project/docs/` | Game-specific documentation created from studio templates. It does not exist yet. |

Repository-level configuration files (`AGENTS.md`, `opencode.json`, `.gitattributes`, `.gitignore`, `README.md`) remain at the repository root.

**Planned, not yet created.** `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md` defines the intended layout of the Godot project — `assets/`, `features/`, `shared/`, `infrastructure/`, `tests/`, and `docs/` under `game_project/`. Those are reference structures, not a requirement to create every directory, and none of them exists at present. Create directories only when an actual file requires them.

Do not state, assume, or rely on a planned directory as if it already exists. Verify the current structure before depending on a path.

## 3. Documentation boundaries

- Never create game-specific documentation under repository-root `docs/`.
- Never create studio-wide documentation under `game_project/docs/`.
- Resolve project-specific documentation paths from the Godot project root (`game_project/`).
- Resolve studio documentation paths from the repository root.
- Read `docs/DOCUMENTATION_INVENTORY.md` before selecting studio documentation.
- Follow `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md` for documentation structure, authority, and maintenance.
- Follow `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md` for repository and Godot project organization.
- Studio templates live in `docs/06_templates/`. Instantiating a template produces a game-specific document under `game_project/docs/`.
- Studio agent workflows live in `docs/07_agent_workflows/`. OpenCode commands live in `.opencode/command/` and must delegate to the authoritative workflow.
- Do not duplicate studio documentation inside `game_project/docs/`. Reference studio documents instead.

## 4. Godot development boundaries

- Treat `game_project/` as the Godot project root.
- Game scripts, scenes, resources, and assets belong inside `game_project/`.
- Use GDScript as the implementation language.
- Do not introduce C# without explicit owner approval.
- Third-party plugins and addons belong in `game_project/addons/`; do not edit their internals.
- Feature-specific implementation belongs in `game_project/features/`.
- Shared game code belongs in `game_project/shared/`.
- Project-wide infrastructure belongs in `game_project/infrastructure/`.
- Game implementation must not depend on repository documentation directories at runtime.
- Do not create unnecessary empty directories.
- Do not commit generated `.godot/` cache or import artifacts.

## 5. Agent behavior

- Inspect existing files before creating new ones.
- Preserve established architecture and conventions.
- Do not invent game design decisions.
- Request approval for significant architectural changes.
- Never modify files outside the task scope.
- Report conflicts between authoritative documents instead of silently choosing one.
- Treat uncommitted and untracked changes as user-owned.

### 5.1 Greenfield project authorship

Where the game project has not yet defined and approved its game vision, game pillars, game design, technical design, or other project-specific requirements, the gap MUST NOT be closed by inventing content.

- The project owner is responsible for providing and approving the game vision, game pillars, game design decisions, technical architecture decisions, and project-specific requirements.
- The agent MAY ask questions, analyse alternatives, present recommendations with trade-offs, record owner-approved decisions, and identify missing requirements and contradictions.
- The agent MUST NOT invent, infer, or silently extend game requirements, design decisions, or architectural constraints, and MUST NOT present a recommendation, draft, or assumption as an approved decision.
- When required information is missing, ask the project owner or mark it explicitly as undecided. Do not proceed as though the gap had been settled.
- Record owner-approved decisions under `game_project/docs/` at the location required by `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`. A decision counts as approved only when the project owner explicitly approved it.

## 6. Authority order

1. Explicit instructions from the project owner for the current task.
2. Approved project-specific requirements and specifications in `game_project/docs/`.
3. Approved Architecture Decision Records. Project ADRs belong under `game_project/docs/technical/adr/`.
4. Applicable studio standards, including mandatory documentation standards.
5. Applicable domain guidelines.
6. General engineering and game-development practice.

## 7. AI tool configuration protection

- Never modify OpenCode settings, provider selection, API keys, model selection, API endpoints, authentication credentials, or other AI tool configuration.
- Never add provider or credential configuration to `opencode.json`.
- Never attempt to optimize, repair, replace, or reconfigure the AI provider.
- Treat all AI tool configuration as user-managed and outside repository task scope.
- If a task appears to require changing AI tool configuration, stop and request explicit owner approval.

## 8. Engine and project configuration

`game_project/project.godot` is authoritative for project settings. The values below must be re-verified against that file before being relied on.

### 8.1 Engine version

- **Declared project feature level:** Godot `4.7` — `application/config/features=PackedStringArray("4.7", "Forward Plus")`.
- **Verified engine executable:** `4.7.2.stable.official.ed1daf0bf` for `--version`, consistent with the declared `4.7` feature level.
- The project does not pin a patch release. No exact patch version is declared in `game_project/project.godot`.
- Changing the engine version is a controlled technical change requiring project owner approval (`docs/02_technical_standards/ENGINE_STANDARDS.md`). This record does not authorize an upgrade, downgrade, or substitution.

### 8.2 Current project configuration

Verified from `game_project/project.godot`:

| Setting | Value | Source key |
|---|---|---|
| Rendering method | `Forward Plus` | `application/config/features` |
| Rendering device driver (Windows) | `d3d12` | `rendering/rendering_device/driver.windows` |
| 3D physics engine | `Jolt Physics` | `physics/3d/physics_engine` |
| Stretch mode | `canvas_items` | `display/window/stretch/mode` |
| Stretch aspect | `expand` | `display/window/stretch/aspect` |
| Configuration format version | `5` | `config_version` |
| Application name | `Qaki` | `application/config/name` |
| Project icon | `res://icon.svg` | `application/config/icon` |
| Enabled editor plugin | `res://addons/godot_mcp/plugin.cfg` | `editor_plugins/enabled` |
| Implementation language | GDScript | No C# or .NET feature is declared, and no C# approval is recorded. |

The rendering method, driver, physics engine, and display behavior describe the current configuration; they are not approval to change any of them. Any change requires project owner approval and, when substantial, an ADR.

## 9. Minimum verification contract

GdUnit4 v6.2.3 is the adopted testing framework and command-line runner, but it is not installed in `game_project/addons/`, no test suite exists, and `.github/workflows/ci.yml` has never been executed. No game script, scene, or main scene exists yet.

- **Engine executable:** `C:\Program Files\Godot\Godot_v4.7.2-stable_win64.exe\Godot_v4.7.2-stable_win64_console.exe`, reporting `4.7.2.stable.official.ed1daf0bf` for `--version`. If that path does not exist, report it; do not substitute a different engine version without owner approval.
- **Automated project validation:** `& '<engine executable>' --headless --path game_project --import`. The enabled `godot_mcp` editor plugin may report `ObjectDB instances were leaked at exit` and `resources still in use at exit` on stderr; these originate from the plugin's shutdown.
- **Script parse check** (not yet applicable; no game scripts exist): `& '<engine executable>' --headless --path game_project --check-only --script <script path>`.
- **Headless smoke run** (not yet applicable; no main scene is defined): `& '<engine executable>' --headless --path game_project --quit-after <frames>`.
- **Manual smoke checklist:** the five checks in `docs/02_technical_standards/TESTING_STRATEGY.md` section 13.6 apply to every change, together with the scenes and behavior affected by the change.

Completion reports MUST state which automated commands were executed, their exit status and relevant output, which manual checks were performed, and which automated tests and CI checks were unavailable or not executed. A change MUST NOT be described as tested, passing, or CI-verified on the strength of these checks alone.

These commands write only to `game_project/.godot/`, which `.gitignore` excludes. That directory MUST NOT be committed.
