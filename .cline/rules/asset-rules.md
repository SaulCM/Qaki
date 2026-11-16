# Asset Rules

> Status: Draft (pending owner review)
> Last updated: 2026-11-15

## 1. Purpose

This rule defines how Cline must handle scenes, resources, and assets in the Qaki Godot project.

It covers where files belong, how they are named and imported, what may be moved or deleted, how third-party content is treated, and which files must never be committed.

It does not define the game's art direction, audio direction, or content requirements. Those are project-specific decisions owned by the human maintainer and recorded under `game_project/docs/`.

## 2. Authoritative Documents

| Concern | Authoritative document |
|---|---|
| Import workflow, import settings, source preservation, optimization, dependency and version-control handling | `docs/02_technical_standards/ASSET_PIPELINE.md` |
| Visual asset requirements, naming, organization, licensing, integration, review | `docs/03_art_audio_standards/ART_ASSET_STANDARDS.md` |
| Art production lifecycle, review, and delivery | `docs/03_art_audio_standards/ART_PIPELINE.md` |
| Audio requirements, formats, loudness, naming, organization, licensing | `docs/03_art_audio_standards/AUDIO_ASSET_STANDARDS.md` |
| Audio production lifecycle | `docs/03_art_audio_standards/AUDIO_PIPELINE.md` |
| Animation asset requirements | `docs/03_art_audio_standards/ANIMATION_STANDARDS.md` |
| UI asset and layout requirements | `docs/03_art_audio_standards/UI_UX_STANDARDS.md` |
| File, directory, and asset naming | `docs/00_studio_standards/NAMING_CONVENTIONS.md` |
| Repository and project organization | `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md` |
| Resource ownership, loading, sharing, mutation | `docs/02_technical_standards/RESOURCE_MANAGEMENT.md` |
| Scene and node structure that references assets | `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md` |
| Engine-specific formats and configuration | `docs/02_technical_standards/ENGINE_STANDARDS.md` |

Read the documents relevant to the asset type being changed before modifying assets. Do not create an asset pipeline, directory layout, or naming scheme that contradicts these documents.

## 3. Where Assets Live

The Godot project root is `game_project/`. `res://` resolves there. The repository root is not a Godot project and never holds game assets.

Verified state of `game_project/` when this rule was last updated:

- `game_project/project.godot` — Godot project configuration.
- `game_project/icon.svg` and `game_project/icon.svg.import` — project icon plus its tracked import metadata.
- `game_project/PROJECT_STATUS.md` — project status.
- `game_project/addons/godot_mcp/` — editor plugin.

`game_project/assets/`, `game_project/features/`, `game_project/shared/`, `game_project/infrastructure/`, `game_project/tests/`, and `game_project/docs/` do not exist yet. Verify the current structure before assuming anything, and create only the directories that actual files require.

Placement rules:

- Feature-owned assets: `game_project/features/<feature>/assets/<category>/`, for example `game_project/features/player/assets/characters/`, `game_project/features/inventory/assets/icons/`, `game_project/features/world/assets/environments/`, and `game_project/features/combat/assets/audio/weapons/`.
- Assets not owned by a single feature: `game_project/assets/` or `game_project/shared/assets/`, as allowed by `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md` section 5.6. Feature-specific assets stay inside their owning feature rather than being copied into either location.
- Infrastructure-owned resources: `game_project/infrastructure/` only for project-level technical resources, not gameplay content.
- `game_project/addons/` contains third-party plugin content. It is not a home for game assets, and its contents must not be modified.
- Do not introduce a type-oriented asset root such as `game_project/sprites/`, `game_project/audio/`, or `game_project/textures/`.
- Do not create empty category directories in advance.

## 4. Naming

Follow `docs/00_studio_standards/NAMING_CONVENTIONS.md`, plus the asset-specific rules in `docs/03_art_audio_standards/ART_ASSET_STANDARDS.md` (section 9) and `docs/03_art_audio_standards/AUDIO_ASSET_STANDARDS.md` (section 12).

- Use lowercase `snake_case` filenames with descriptive, purpose-based names: `iron_sword.png`, `forest_tree_oak.glb`, `sword_swing_01.wav`, `combat_theme_loop.ogg`.
- No spaces, uppercase letters, or special characters in filenames.
- Use consistent variant suffixes: `footstep_grass_01.wav`, `goblin_idle.png`, `goblin_elite.glb`.
- Avoid temporary, ambiguous, or versioned names such as `new_sprite`, `final`, `icon2`, or `v3`.
- Keep internal identifiers separate from player-facing display names.
- Do not rename existing asset files unless the task requires it. Renaming breaks resource references; update every reference, validate the result, and request approval when the asset is shared or established.

## 5. Godot Formats and Import Settings

- Use formats the configured Godot version imports natively for the intended asset type. Confirm the format is supported before adding it.
- Import settings live next to each asset in its `*.import` file (for example `game_project/icon.svg.import`). These files are part of the project and are version controlled.
- Do not hand-edit `*.import` files unless the task is specifically about import settings. When you do, state which settings changed and why.
- Never edit or delete files inside `game_project/.godot/`; that directory is the generated import cache.
- Do not change project-wide import defaults, rendering settings, or texture defaults as a side effect of adding an asset. Request approval.
- Keep configuration data in resources rather than hardcoding values in scripts, following `docs/02_technical_standards/RESOURCE_MANAGEMENT.md`.

## 6. Source Files, Generated Files, and Version Control

- Keep editable source files distinct from exported or imported assets. Do not treat an export as the authoritative source when an editable original exists (`docs/02_technical_standards/ASSET_PIPELINE.md`, section 3.1).
- Never commit Godot's generated cache. `.gitignore` excludes `.godot/`, `.import/`, `/export/`, `/builds/`, and `/export_presets.cfg`.
- `.gitattributes` normalizes text files to LF and marks `*.png`, `*.jpg`, `*.jpeg`, `*.webp`, `*.glb`, `*.gltf`, `*.blend`, `*.wav`, `*.ogg`, and `*.mp3` as binary.
- If a new binary format needs an attribute entry, report it for owner review instead of changing shared version-control configuration inside an unrelated asset task.
- Do not commit exported builds, signing material, credentials, or export presets. Do not commit Blender backup files (`*.blend1`, `*.blend2`) or temporary processing output.
- Do not add Git LFS or any large-file handling mechanism without owner approval.
- Review asset diffs for accidental size explosions, stray duplicates, and missing dependencies before a change is committed.

## 7. Reuse and Duplication

- Search for an existing asset with the same purpose before adding a new one.
- Reuse an asset when it genuinely serves the purpose. Do not duplicate an asset into another feature to avoid a dependency decision.
- Variants are appropriate for gameplay roles, states, factions, biome or location differences, and visual progression; they must share a recognizable foundation.
- Avoid near-duplicate assets, and avoid unnecessary proliferation of copies of the same source.

## 8. Moving, Replacing, and Deleting Assets

Before moving, replacing, or deleting an asset:

1. Search the project for every reference to the asset path, including scenes, resources, and scripts.
2. Identify which features and scenes depend on it.
3. Determine whether the asset is shared.
4. Evaluate the effect on import settings, dimensions, scale, and format.
5. Update all affected references in the same change.
6. Validate that affected scenes and resources still load.

Rules:

- Never delete, replace, or overwrite an existing asset without explicit authorization.
- Never leave unresolved or dangling references after a move or replacement.
- Preserve source files and licensing records when an asset is replaced or retired.
- Do not delete an asset merely because it is unused by the current task; it may be loaded dynamically or referenced by configuration.
- Do not move assets between features to "tidy up" unrelated to the task.

## 9. Third-Party and AI-Generated Assets

- Before integrating any external asset — image, model, font, audio, shader, plugin, or other resource — verify its source, license, permitted usage, attribution requirements, redistribution and modification restrictions, and technical compatibility.
- Never integrate an asset whose usage rights are unclear or incompatible with the project's intended distribution.
- Record licensing and attribution information in an appropriate project-level location when an external asset is added.
- AI-generated assets must meet the same quality, technical, consistency, and licensing requirements as original assets, and must be reviewed for artifacts, inconsistencies, unintended resemblance to protected material, and technical suitability.
- Never assume that generated or externally sourced content is free of licensing, ownership, or usage restrictions.
- Do not add third-party plugins, fonts, audio, or other external resources without owner approval, and never modify files inside `game_project/addons/`.
- Do not mark an asset as approved, final, or compliant with art direction. Those are human decisions.

## 10. Validation After Asset Changes

- Import the project in the Godot editor, or run the relevant scene, so the importer processes the new or changed files.
- Confirm that references resolve and that no missing-resource or import errors are reported.
- Confirm that affected scenes still open and behave as before unless the change was intended to alter them.
- Report what was actually validated and what was not. Do not claim an asset was visually or audibly reviewed when it was not inspected in context.

## 11. Request Owner Approval Before

- Deleting, replacing, or overwriting any existing asset.
- Renaming or moving assets that other scenes, resources, or features reference.
- Adding third-party or AI-generated assets, fonts, audio, or plugins.
- Changing import settings that affect multiple assets or project-wide defaults.
- Adding large binary assets, Git LFS, or new asset-processing tooling.
- Modifying `.gitignore`, `.gitattributes`, or export configuration.
- Introducing a new asset category, directory convention, or pipeline step.

## 12. Prohibited Actions

Cline must not:

- Delete, replace, or overwrite assets without authorization.
- Commit `.godot/` cache content, import artifacts, builds, or export presets.
- Edit generated import artifacts directly.
- Create duplicate assets instead of reusing an appropriately owned one.
- Place game assets outside `game_project/`, or create a type-oriented asset root.
- Modify `game_project/addons/` or other third-party content.
- Change project-wide import or rendering settings as a side effect of an asset task without approval.
- Add external assets without checking licensing and obtaining required approval.
- Claim that an asset was validated, imported, or reviewed when it was not.

## 13. Related Workspace Rules

- `.cline/rules/project-context.md` — repository roots, `game_project/` boundaries, directory responsibilities.
- `.cline/rules/gdscript-standards.md` — loading and referencing assets from scripts, notably `load()` validation.
- `.cline/rules/architecture-rules.md` — scene composition, resource ownership, and dependency rules.
- `.cline/rules/git-workflow.md` — commit and staging safety for binary and generated files.
- `.cline/rules/documentation-management.md` — documentation duties when asset conventions or project-specific asset records change.
