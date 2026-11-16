# Qaki Agent Instructions

> Status: Active repository instruction
> Scope: OpenCode sessions in the Qaki repository
> Authority: This file routes and binds; it does not replace the studio standards or project documentation.

## 1. Purpose and precedence

OpenCode is the sole supported coding-agent configuration for this repository. Preserve the existing studio documentation and workflow ownership model.

Follow this authority order:

1. Explicit instructions from the project owner for the current task.
2. Approved project-specific requirements and specifications in `game_project/docs/`.
3. Approved Architecture Decision Records. Project ADRs belong in `game_project/docs/technical/adr/`.
4. Applicable studio standards under `docs/00_studio_standards/` and `docs/02_technical_standards/`.
5. Applicable studio guidelines, templates, and workflows.
6. General engineering practice.

Draft documents, inventory entries marked `Not Specified`, and recommendations are not approved policy. When authoritative documents conflict, report the conflict instead of silently choosing one. The studio standards remain the source of truth; `.opencode/rules/` is an operating layer, not a new standard.

## 2. Repository map

| Path | Responsibility |
|---|---|
| `docs/` | Reusable studio documentation: standards, guidelines, templates, and authoritative agent workflows. |
| `docs/07_agent_workflows/` | Authoritative task procedures. |
| `game_project/` | The only Godot project root; `res://` resolves here. |
| `game_project/docs/` | Game-specific documentation. Create it only when an actual document requires it. |
| `game_project/addons/` | Third-party plugins and addons. Do not edit their internals. |
| `.opencode/rules/` | OpenCode operating rules loaded automatically. |
| `.opencode/command/` | Thin OpenCode adapters to `docs/07_agent_workflows/`. |
| `.opencode/agent/` | Read-only specialist agents. |
| `.github/` | GitHub workflows, issue templates, and pull request template. |
| `references/` | Repository-level reference material. |

The repository root is not a Godot project root. Do not create `project.godot`, game scripts, scenes, resources, or assets at the repository root.

## 3. Read before acting

Before substantial work:

1. Read the applicable rule files in `.opencode/rules/`.
2. Read `docs/DOCUMENTATION_INVENTORY.md`.
3. Read the studio standards and guidelines relevant to the task.
4. Read the applicable `docs/07_agent_workflows/` procedure.
5. Inspect the actual implementation and project documents before relying on them.

Do not assume a referenced or planned path exists. Verify it. Do not load every document by default.

## 4. Owner authority and no invention

The project is in pre-production and has no approved game vision, pillars, design, or technical architecture unless a project document says so.

- Do not invent, infer, or silently extend game requirements, design decisions, or architectural constraints.
- Do not present a recommendation, draft, or assumption as an approved decision.
- Ask the project owner for missing information, or mark it explicitly as undecided.
- Record owner-approved project decisions under `game_project/docs/` at the location required by `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`.
- Request approval for significant architectural, scope, engine, tooling, or workflow changes.

## 5. Engineering constraints

- Use GDScript only. Do not introduce C#, GDExtension, native modules, or another language without explicit owner approval.
- The Godot project declares feature level `4.7` in `game_project/project.godot`. The verified executable and CI toolchain use Godot `4.7.2.stable`. Do not describe the project as pinning a 4.7.2 patch release.
- Verify engine APIs against the configured version before relying on them.
- Place game code by feature ownership under `game_project/features/`, genuinely shared code under `game_project/shared/`, and project-wide technical infrastructure under `game_project/infrastructure/`.
- Do not create type-oriented roots such as `game_project/scripts/`, `game_project/scenes/`, or `game_project/assets/` for game functionality.
- Do not create empty or speculative directories.
- Never commit or rely on `.godot/`. It is generated cache and is excluded by `.gitignore`.
- Do not edit `game_project/addons/` internals or change project-wide engine, rendering, physics, autoload, or import settings without approval.
- Follow `docs/02_technical_standards/` for GDScript, scenes, resources, signals, persistence, performance, and engine use.
- Follow `docs/03_art_audio_standards/` and `docs/02_technical_standards/ASSET_PIPELINE.md` for asset handling, naming, licensing, and validation.

## 6. Testing and verification

GdUnit4 v6.2.3 is the approved testing framework. It is not installed in `game_project/addons/`, no test suite exists, and `.github/workflows/ci.yml` has never been executed.

Use the minimum verification contract recorded in `.opencode/rules/project-context.md` and `docs/02_technical_standards/TESTING_STRATEGY.md`:

- Headless project import: `godot --headless --path game_project --import`.
- Parse check for changed GDScript: `godot --headless --path game_project --check-only --script <script>`.
- Headless smoke run only when a main scene exists: `godot --headless --path game_project --quit-after <frames>`.
- Manual smoke checks for behavior headless execution cannot observe.

Report the exact command, exit status, and relevant output. State which checks were unavailable or not executed. Never claim code was tested, passing, CI-verified, reviewed, approved, or integrated without observed evidence. Do not install or upgrade GdUnit4 without owner approval.

## 7. Git safety

No commit, push, stage, merge, tag, branch change, rebase, reset, clean, or history rewrite is authorized merely by this file or by Bash permission.

- `main` and `develop` are protected. Never commit or push directly to either.
- Use an approved branch prefix: `feature/`, `fix/`, `refactor/`, `test/`, `docs/`, or `chore/`.
- Use `fix/` for bug fixes. Do not use `bugfix/`; the example in `docs/07_agent_workflows/FIX_BUG.md` conflicts with the approved `GIT_CONVENTIONS.md` prefixes and must not be followed.
- Pull requests target `develop`, not `main`.
- Treat uncommitted and untracked changes as user-owned. Never discard, reset, overwrite, or include them without explicit approval.
- Inspect `git status`, the current branch, and the diff before and after any authorized Git operation.
- Read `docs/00_studio_standards/GIT_CONVENTIONS.md` and `docs/00_studio_standards/BRANCHING_STRATEGY.md` before branch or integration work.

## 8. Defects

GitHub Issues is the authoritative defect tracker. Use `.github/ISSUE_TEMPLATE/bug_report.md` and the vocabulary in `docs/05_qa_standards/BUG_REPORTING.md`.

- Do not create a second authoritative defect record in a document, backlog, or another tracker.
- Do not close a defect without verification.
- Do not invent reproduction steps, environment details, evidence, or test results.
- Link fixes to the issue and update its lifecycle status when authorized.

## 9. Documentation

- Read `docs/DOCUMENTATION_INVENTORY.md` before creating, moving, renaming, or deleting documentation.
- Update the inventory in the same change whenever documentation structure changes.
- Studio documentation belongs under `docs/`; game-specific documentation belongs under `game_project/docs/`. Do not mix or duplicate them.
- Extend an authoritative document instead of creating a duplicate.
- Do not mark a document `Approved`. Only the project owner approves standards and significant specifications.
- Preserve unrelated user changes and existing approved requirements.

## 10. Workflow ownership

`docs/07_agent_workflows/` is the single source of procedural truth. `.opencode/command/` contains thin adapters that name the authoritative workflow, bind these rules, and pass the task through. They must not restate or replace the procedure.

| Command | Authoritative procedure |
|---|---|
| `/implement-feature` | `docs/07_agent_workflows/IMPLEMENT_FEATURE.md` |
| `/fix-bug` | `docs/07_agent_workflows/FIX_BUG.md` |
| `/refactor-code` | `docs/07_agent_workflows/REFACTOR_CODE.md` |
| `/review-code` | `docs/07_agent_workflows/REVIEW_CODE.md` |
| `/create-technical-design` | `docs/07_agent_workflows/CREATE_TECHNICAL_DESIGN.md` |
| `/generate-tests` | `docs/07_agent_workflows/GENERATE_TESTS.md` |
| `/update-documentation` | `docs/07_agent_workflows/UPDATE_DOCUMENTATION.md` |
| `/update-project-status` | `docs/07_agent_workflows/UPDATE_PROJECT_STATUS.md` |

Read the complete authoritative workflow before acting. Follow its approval gates. Do not create a new procedure in `.opencode/command/` or `.opencode/agent/`.

## 11. AI configuration protection

Do not modify OpenCode or provider configuration, API credentials, model selection, endpoints, or authentication. Do not add provider or credential configuration to `opencode.json`. Treat AI tool configuration as user-managed and outside repository task scope.

Do not edit addon internals, including comments that reference obsolete paths. Report stale references instead.

## 12. Completion reporting

A completion report must state:

- The task and the requirement or acceptance criteria used.
- The branch and repository state, including pre-existing user changes.
- Files created, modified, or deleted, and why each belongs to the task.
- The highest Definition of Done state actually reached: Implemented, Locally validated, Automatically tested, Reviewed, Approved, or Integrated.
- Validation commands, exit codes, and actual results.
- Validation not performed, why, and what remains unverified.
- Tests executed and their outcome, or an explicit statement that none could be executed.
- Documentation and inventory changes.
- Git actions performed and actions intentionally not performed.
- Known limitations, out-of-scope observations, and unresolved conflicts or owner decisions.

Implementation is not review, approval, or integration. The project owner retains final approval.

## 13. OpenCode permissions

`opencode.json` enables normal read, edit, and Bash work while denying secret-file reads and destructive Git commands. Permission to use Bash is not authorization for Git operations; section 7 governs. Read `.opencode/rules/` for the detailed operating rules.
