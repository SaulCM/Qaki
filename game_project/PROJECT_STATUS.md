# Project Status

> Last updated: 2026-11-16
> Project owner: Saul
> Development phase: Pre-production
> Project status: Active

## 1. Project Overview


## 2. Current Milestone

Milestone 0 — Project Foundation and Pre-production.

Goal:
Establish the game's vision, core gameplay pillars,
technical architecture, and production standards.

## 3. Completed Work

- [x] GitHub repository created
- [x] Main branch established
- [x] Develop branch established
- [x] AI development Windows account configured
- [x] Documentation directory structure created
- [x] Configure OpenCode project rules
- [ ] Game vision approved
- [ ] Core gameplay pillars approved
- [ ] Technical architecture approved

## 4. In Progress

- [ ] Populate pre-production documentation
- [ ] Configure GitHub Actions
- [ ] Establish Godot project structure

## 5. Next Priorities

1. Finalize GAME_VISION.md.
2. Define CORE_PILLARS.md.
3. Define CORE_GAME_LOOP.md.
4. Establish the Technical Design Document.
5. Approve the initial architecture.

## 6. Blockers

- Blender and shared development tools setup pending.
- AI agent workflow validation pending.
- Release and playtest builds: no export presets, export automation, or documented build process is configured. A release build is blocked until the project owner defines supported platforms and export presets, and until the open release branching decisions in `docs/00_studio_standards/BRANCHING_STRATEGY.md` (section 19: R-1 release branches, R-2 source branch for `main`, R-7 tagging) are resolved.

## 7. Pending Decisions

- Final camera perspective.
- Initial vertical slice scope.

## 8. Development Rules

- Never commit directly to main.
- Use the approved branch prefixes from `docs/00_studio_standards/GIT_CONVENTIONS.md`: `feature/`, `fix/`, `refactor/`, `test/`, `docs/`, or `chore/`.
- Require human approval before merging PRs.
- Do not implement unapproved design decisions.
- Update this document when milestone status changes.

## 9. Recent Changes

### 2026-11-16
- Migrated agent configuration from Cline to OpenCode.

### 2026-11-12
- Created initial documentation structure.
- Established initial repository organization.