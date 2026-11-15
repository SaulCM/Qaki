# Technical Overview Template

> **Purpose:** This template defines the structure for a project's technical overview.
>
> A technical overview records the technical facts that are specific to one game project: the engine and project configuration, target platforms and performance targets, testing toolchain, persistence decisions, asset import defaults, dependencies and licensing, and the location of architecture records.
>
> It is a project document. Instantiate it at `game_project/docs/technical/overview.md` and keep the studio standards as the authority for how those facts are used. Do not copy studio standards into it.
>
> Record only decisions the project owner has approved. Where a value has not been decided, write `Not established` and keep the item visible; do not invent a value.

---

## 1. Document Information

| Field | Value |
|---|---|
| Project | [Project name] |
| Status | Draft |
| Owner | [Project owner] |
| Created Date | [YYYY-MM-DD] |
| Last Updated | [YYYY-MM-DD] |
| Related ADRs | [ADR IDs or `None`] |
| Related Documents | [Links] |

---

## 2. Engine and Project Configuration

Reference: `docs/02_technical_standards/ENGINE_STANDARDS.md` (sections 4 and 5).

| Setting | Value | Source |
|---|---|---|
| Godot feature level | [Value or `Not established`] | `game_project/project.godot` |
| Verified engine version | [Value or `Not established`] | [Verification record] |
| Rendering method | [Value or `Not established`] | `game_project/project.godot` |
| Rendering device driver | [Value or `Not established`] | `game_project/project.godot` |
| Physics engine | [Value or `Not established`] | `game_project/project.godot` |
| Display stretch mode and aspect | [Value or `Not established`] | `game_project/project.godot` |

Record how the engine version was verified, not only what it is.

---

## 3. Target Platforms and Performance Targets

Reference: `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md` (section 4).

| Item | Value |
|---|---|
| Supported platforms | [Values or `Not established`] |
| Minimum hardware per platform | [Values or `Not established`] |
| Intended frame rate per platform | [Values or `Not established`] |
| Display resolution | [Values or `Not established`] |
| Performance baseline location | [Scene, build, or test scenario used for comparison, or `Not established`] |

Do not record a performance target that the project owner has not approved. An unmeasured build is not evidence that a target is met.

---

## 4. Testing and Validation Toolchain

Reference: `docs/02_technical_standards/TESTING_STRATEGY.md` (sections 11.3 to 11.6).

| Item | Value |
|---|---|
| Framework and version | [Value or `Not established`] |
| Runner and execution command | [Command or `Not established`] |
| Continuous integration | [Workflow path or `Not established`] |
| Test location | [Path] |
| Coverage status | [What exists, and what does not] |

Record the actual execution command and its prerequisites. Do not report a configured toolchain as test coverage.

---

## 5. Persistence Decisions

Reference: `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md` (section 11).

| Item | Value |
|---|---|
| Save data location | [Path or `Not established`] |
| Format version field | [Field and type, or `Not established`] |
| Supported save versions | [List or `Not established`] |
| Migration registry | [Path or `Not established`] |
| Fixtures for older versions | [Path or `Not established`] |

---

## 6. Asset Import Defaults

Reference: `docs/02_technical_standards/ASSET_PIPELINE.md` (section 7.2).

| Asset category | Import defaults | Source of the decision |
|---|---|---|
| [Category] | [Settings or `Not established`] | [Owner decision or ADR] |

Record defaults only after they are decided. Project-wide import defaults are a project decision, not a studio standard.

---

## 7. Dependencies and Licensing

Reference: `docs/02_technical_standards/ENGINE_STANDARDS.md` (section 16).

| Dependency | Version or pin | Purpose | Licence | Licence record |
|---|---|---|---|---|
| [Name] | [Version] | [Purpose] | [Licence] | [Path] |

---

## 8. Architecture Summary and Decision Records

Reference: `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md` (sections 14 and 15).

Record:

- The project's features, and the boundary of each.
- Shared and infrastructure areas.
- The location of project ADRs (`game_project/docs/technical/adr/`).
- The project ADR index location.

Link to the ADRs; do not restate their decisions.

---

## 9. Open Technical Decisions

| ID | Decision | Options | Status | Owner |
|---|---|---|---|---|
| TECH-OPEN-01 | [Decision] | [Options] | [Open / Decided] | [Owner] |

Keep unresolved decisions visible. Do not close an item without a recorded owner decision.

---

## 10. Related Documents

**Studio standards:**

- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/ENGINE_STANDARDS.md`
- `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md`
- `docs/02_technical_standards/TESTING_STRATEGY.md`
- `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md`
- `docs/02_technical_standards/ASSET_PIPELINE.md`
- `docs/02_technical_standards/adr/ADR_PROCESS.md`

**Project documents:**

- [Project technical design documents]
- [Project ADRs]
