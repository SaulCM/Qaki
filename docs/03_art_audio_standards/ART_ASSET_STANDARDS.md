# Art Asset Standards

## 1. Purpose

This document defines the studio-wide standards for creating, organizing, reviewing, integrating, and maintaining visual art assets in game projects.

Its purpose is to ensure that art assets are visually consistent, technically suitable, maintainable, and aligned with the intended player experience.

These standards apply to original, commissioned, purchased, generated, and externally sourced visual assets.

This document establishes reusable studio practices. Individual game projects must define their own art direction, visual identity, style references, technical specifications, and asset requirements.

## 2. Scope

These standards cover:

- 2D and 3D visual assets.
- Characters, creatures, enemies, and NPCs.
- Environments, locations, and world elements.
- Props, objects, and interactive assets.
- Textures, materials, and surfaces.
- User interface visual assets.
- Icons, illustrations, and visual effects.
- Fonts and visual typography assets.
- Concept art and visual references.
- Asset consistency, quality, and review.
- Asset ownership, attribution, and licensing.

Animation-specific requirements are defined in `animation_standards.md`.

Technical importing, processing, compression, and engine integration are defined in `docs/02_technical_standards/asset_pipeline.md`.

## 3. Art Asset Principles

All art assets SHOULD follow these principles.

### 3.1. Visual Consistency

Assets MUST support the visual identity and art direction of the game.

They SHOULD maintain consistency in:

- Visual style.
- Shape language.
- Proportions.
- Color palette.
- Lighting and shading.
- Material appearance.
- Level of detail.
- Perspective and composition.
- Visual complexity.

Assets created independently MUST still feel as though they belong to the same game.

### 3.2. Gameplay Readability

Visual assets MUST communicate relevant gameplay information clearly.

Players SHOULD be able to distinguish important elements such as:

- Interactive and non-interactive objects.
- Friendly and hostile entities.
- Important environmental elements.
- Collectible objects.
- Hazards and obstacles.
- Different object states.
- Relevant points of interest.

Visual complexity MUST NOT unnecessarily interfere with gameplay readability.

### 3.3. Purposeful Detail

Every significant visual detail SHOULD contribute to at least one of the following:

- Game identity.
- Environmental storytelling.
- Character identity.
- Gameplay readability.
- Emotional impact.
- Visual composition.
- Worldbuilding.

Avoid unnecessary detail that increases production cost without improving the player experience.

### 3.4. Reusability

Assets SHOULD be designed for reuse when appropriate.

Reusable assets SHOULD:

- Avoid unnecessary dependencies on individual scenes.
- Support consistent use across relevant features.
- Have clear ownership and intended usage.
- Avoid introducing project-specific assumptions into shared assets.

Reuse MUST NOT compromise visual consistency or require excessive configuration.

### 3.5. Technical Suitability

Assets MUST satisfy the technical requirements of their intended use.

Consider:

- Target platform.
- Resolution and display requirements.
- Polygon and texture budgets.
- Material complexity.
- Rendering requirements.
- Memory usage.
- Asset format and import compatibility.
- Expected visibility and frequency of use.

Specific performance targets MUST be defined by the individual game project.

## 4. Art Direction and Visual Identity

Each game project MUST establish an approved art direction before large-scale asset production.

The project-specific art direction SHOULD define:

- Overall visual identity.
- Target visual experience.
- Art style and references.
- Color palette.
- Shape language.
- Character and environment proportions.
- Perspective and camera conventions.
- Lighting and shading approach.
- Material and surface treatment.
- Detail density.
- UI visual language.
- Technical constraints.

Visual references SHOULD communicate the intended direction rather than serve as unrestricted instructions to reproduce another creator's work.

### 4.1. Art Direction Authority

The approved project art direction is the primary reference for visual decisions.

When an asset conflicts with the established direction:

1. Identify the inconsistency.
2. Determine whether the asset or the art direction requires revision.
3. Evaluate the impact on related assets.
4. Obtain project owner approval for significant changes.
5. Update the relevant project documentation when necessary.

AI agents MUST NOT independently redefine the project's art direction.

### 4.2. Style Consistency

Assets SHOULD be evaluated in their intended game context.

An asset that looks good in isolation may still be unsuitable if it conflicts with the surrounding environment, character proportions, lighting, or visual hierarchy.

Review assets alongside representative project content whenever possible.

## 5. Asset Categories

Visual assets SHOULD be classified according to their primary purpose.

### 5.1. Characters and Creatures

Character assets SHOULD establish recognizable silhouettes, proportions, and visual identities.

Consider:

- Silhouette readability.
- Distinctive visual features.
- Character proportions.
- Facial and body details.
- Clothing, equipment, and accessories.
- Material consistency.
- Gameplay readability.
- Compatibility with the intended animation system.

Characters with different gameplay roles SHOULD have distinguishable visual characteristics when that distinction matters to the player.

### 5.2. Environments

Environment assets SHOULD support world identity, navigation, atmosphere, and gameplay.

Consider:

- Architectural and environmental consistency.
- Scale and proportions.
- Environmental storytelling.
- Navigation readability.
- Landmark visibility.
- Material and lighting consistency.
- Reusability of modular elements.
- Visual density and composition.

Environment assets MUST NOT obscure important gameplay information without an intentional design reason.

### 5.3. Props and Objects

Props SHOULD communicate their purpose through recognizable shape, scale, and visual treatment.

Interactive objects SHOULD be distinguishable when their interaction is relevant to the player.

Reusable props SHOULD have consistent proportions and material conventions.

### 5.4. User Interface Assets

UI assets MUST prioritize readability, usability, and consistency.

Consider:

- Visual hierarchy.
- Contrast.
- Icon recognition.
- Consistent spacing and proportions.
- Compatibility with supported resolutions.
- Visual states such as normal, hovered, pressed, disabled, and selected.
- Accessibility requirements.

UI-specific behavior, layout, interaction, and usability requirements are defined in `ui_ux_design_guidelines.md`.

### 5.5. Textures and Materials

Textures and materials SHOULD support the intended surface appearance and art direction.

Consider:

- Appropriate resolution.
- Consistent material response.
- Texture scale and tiling.
- Color and contrast.
- Surface detail.
- UV requirements.
- Shader complexity.
- Compatibility with the selected rendering approach.

Avoid unnecessarily large textures or complex materials when a simpler solution achieves the same visual result.

### 5.6. Icons and Illustrations

Icons SHOULD communicate their meaning clearly at their intended display size.

They SHOULD maintain consistency in:

- Silhouette.
- Stroke or edge treatment.
- Perspective.
- Detail density.
- Color usage.
- Proportions.

Important icons MUST remain recognizable at their smallest supported size.

### 5.7. Visual Effects

Visual effects SHOULD reinforce gameplay feedback and the intended atmosphere.

Consider:

- Readability.
- Timing and visual intensity.
- Color consistency.
- Screen-space coverage.
- Performance impact.
- Player comfort.
- Compatibility with other visual effects.

Effects MUST NOT obscure critical gameplay information.

## 6. Visual Quality Requirements

Art assets MUST meet the quality expectations appropriate to their intended role.

### 6.1. Shape and Proportions

Assets SHOULD have clear and intentional shapes.

Check for:

- Distorted proportions.
- Inconsistent scale.
- Unintended asymmetry.
- Broken silhouettes.
- Unwanted intersections.
- Incorrect perspective.
- Unclear visual boundaries.

Stylized exaggeration is acceptable when it supports the intended art direction.

### 6.2. Color and Contrast

Colors SHOULD support visual hierarchy and distinguish relevant elements.

Consider:

- Palette consistency.
- Contrast against surrounding elements.
- Readability under different lighting conditions.
- Color accessibility.
- Consistency between related assets.

Important gameplay information SHOULD NOT rely exclusively on color differences.

### 6.3. Lighting and Shading

Lighting and shading SHOULD follow the project's visual conventions.

Assets MUST be compatible with the intended lighting approach.

Avoid unintended:

- Harsh visual inconsistencies.
- Incorrect shadow direction.
- Incompatible material responses.
- Excessive highlights.
- Unwanted visual noise.

### 6.4. Detail and Resolution

The amount of detail SHOULD be appropriate for the asset's expected visibility and importance.

Do not spend disproportionate effort on details that players are unlikely to notice.

Assets MUST remain visually acceptable at their actual in-game size and viewing distance.

## 7. 2D Art Standards

2D assets MUST follow the project's approved conventions for resolution, proportions, perspective, and visual style.

### 7.1. Sprite Requirements

Sprites SHOULD:

- Use consistent proportions and visual density.
- Have intentional transparent boundaries.
- Maintain appropriate pivots and alignment.
- Avoid unintended cropping.
- Avoid unnecessary transparent padding.
- Remain readable at their intended display scale.

Sprite dimensions and resolutions SHOULD be consistent within related asset groups when practical.

### 7.2. Pixel Art

When a project uses pixel art, assets SHOULD follow consistent rules for:

- Pixel density.
- Grid alignment.
- Resolution.
- Color palette.
- Outline thickness.
- Shading clusters.
- Scaling behavior.

Avoid unintended subpixel positioning or filtering that introduces inconsistent visual artifacts.

### 7.3. 2D Layering

2D assets MUST be compatible with the intended rendering and layering conventions.

Consider:

- Draw order.
- Transparency.
- Occlusion.
- Parallax.
- Z-index conventions.
- Sorting behavior.

Layering decisions SHOULD be predictable and documented when they affect multiple features.

## 8. 3D Art Standards

3D assets MUST follow the project's approved conventions for scale, orientation, geometry, materials, and rendering.

### 8.1. Modeling

Models SHOULD have geometry appropriate to their intended visual importance and viewing distance.

Consider:

- Silhouette quality.
- Polygon density.
- Topology.
- Scale and proportions.
- Mesh intersections.
- Unnecessary geometry.
- Deformation requirements.
- Compatibility with the target rendering pipeline.

Avoid unnecessary geometric complexity.

### 8.2. Scale and Orientation

3D assets MUST follow the project's coordinate, scale, and orientation conventions.

Assets intended to interact or connect SHOULD use compatible dimensions and alignment.

### 8.3. UVs and Textures

Models requiring textures SHOULD have appropriate UV layouts.

Check for:

- Unintended stretching.
- Overlapping UVs where not intended.
- Inconsistent texel density.
- Visible seams.
- Incorrect texture orientation.
- Unnecessary texture space waste.

### 8.4. Materials

Materials SHOULD use consistent naming, parameters, and visual conventions.

Avoid unnecessary material duplication and excessive shader complexity.

### 8.5. Level of Detail

Assets that occupy significant screen space or appear frequently SHOULD be evaluated for appropriate level-of-detail requirements.

LOD implementation MUST be justified by visual and performance needs rather than applied indiscriminately.

## 9. Asset Naming and Organization

Art assets MUST follow the project's naming and directory conventions.

The studio-wide naming rules are defined in `docs/00_studio_standards/naming_conventions.md`.

### 9.1. Naming

Asset filenames SHOULD:

- Use descriptive names.
- Use lowercase `snake_case`.
- Avoid unnecessary abbreviations.
- Avoid temporary or ambiguous names.
- Reflect the asset's identity or purpose.

Examples:

- `iron_sword.png`
- `forest_tree_oak.glb`
- `stone_wall_material.tres`
- `merchant_portrait.png`
- `health_potion_icon.svg`

Asset variants SHOULD use consistent suffixes or identifiers.

Examples:

- `goblin_idle.png`
- `goblin_portrait.png`
- `goblin_elite.glb`

### 9.2. Feature-Oriented Organization

Art assets MUST be organized according to the project's feature-oriented structure.

Assets owned by a feature SHOULD be stored within that feature's asset directories.

Example:

```text
features/
├── player/
│   └── assets/
│       ├── characters/
│       ├── textures/
│       └── materials/
├── inventory/
│   └── assets/
│       └── icons/
└── world/
    └── assets/
        ├── environments/
        ├── props/
        └── materials/
```

Assets genuinely shared across multiple features MAY be stored in the project's shared asset locations.

Do not create a separate type-oriented root structure that conflicts with the approved feature-oriented project organization.

### 9.3. Asset Ownership

Each asset SHOULD have a clear owning feature or system.

Shared assets MUST have a clear reason for being shared.

Avoid duplicating assets when a single appropriately owned resource can serve multiple consumers.

## 10. Source Files and Deliverables

When creating or acquiring art assets, preserve source files whenever possible.

Source files may include:

- Original illustration files.
- Layered image documents.
- 3D modeling project files.
- Texture authoring files.
- Vector graphics source files.
- Procedural generation source files.
- Relevant project files and dependencies.

Final exported assets SHOULD be accompanied by their editable sources when those sources are available and permitted to be stored.

Do not replace original source files with exported versions unless the source is intentionally disposable.

### 10.1. Export Requirements

Exported assets MUST:

- Use an appropriate format.
- Preserve required visual quality.
- Have correct dimensions and color settings.
- Avoid unintended cropping or transparency issues.
- Be compatible with the target engine workflow.

Export settings SHOULD be reproducible.

Technical import and processing requirements are defined in `asset_pipeline.md`.

## 11. External and AI-Generated Assets

External and AI-generated assets MUST follow the same quality, consistency, technical, and ownership requirements as original assets.

### 11.1. External Assets

Before integrating an external asset, verify:

- Source and creator, when available.
- License and permitted usage.
- Attribution requirements.
- Commercial-use restrictions.
- Modification and redistribution restrictions.
- Included dependencies.
- Technical compatibility.
- Visual consistency with the project.

An asset MUST NOT be integrated when its usage rights are unclear or incompatible with the project's intended distribution.

### 11.2. AI-Generated Assets

AI-generated assets MAY be used when they satisfy project requirements and applicable legal, licensing, and platform constraints.

They MUST be reviewed for:

- Visual consistency.
- Anatomical or geometric errors.
- Unintended artifacts.
- Inconsistent details.
- Incorrect text or symbols.
- Transparency and edge defects.
- Unwanted resemblance to protected or recognizable third-party material.
- Technical suitability.

AI-generated assets MUST NOT be accepted solely because they appear visually convincing at first glance.

Where appropriate, preserve the generation source, relevant prompts, editing history, and tool information.

AI agents MUST NOT invent or assume licensing rights for generated or externally sourced assets.

## 12. Asset Licensing and Attribution

Every externally sourced or third-party asset MUST have its usage rights verified before integration.

Maintain relevant licensing information, including:

- Asset name or identifier.
- Original source.
- Creator or publisher.
- License type.
- Required attribution.
- Modifications made.
- Usage restrictions.
- Relevant purchase or acquisition records, when applicable.

Keep licensing records in an appropriate project-level location.

Do not remove attribution or licensing information required by the applicable license.

When licensing terms are unclear, request human review before using the asset.

## 13. Asset Reuse and Variants

Reuse SHOULD be preferred when it supports consistency and reduces unnecessary production effort.

Variants MAY be created to support:

- Different gameplay roles.
- Environmental variation.
- Visual progression.
- Faction or character identity.
- Different states or conditions.
- Biome or location differences.

Variants SHOULD share a recognizable visual foundation when they represent the same underlying asset.

Avoid creating unnecessary near-duplicate assets.

When using shared source assets, avoid modifications that unintentionally affect unrelated features.

## 14. Asset Integration and Gameplay Context

Art assets MUST be evaluated in the context in which they will appear.

Before accepting an asset, verify:

- Correct scale and orientation.
- Correct positioning and alignment.
- Appropriate visual hierarchy.
- Compatibility with the scene.
- Compatibility with lighting and materials.
- Appropriate visibility and contrast.
- Correct interaction or visual state, where applicable.
- Absence of unintended rendering artifacts.

Assets SHOULD be reviewed in representative gameplay conditions rather than only in an editor preview or isolated image viewer.

## 15. Accessibility and Player Comfort

Visual assets SHOULD support accessibility and player comfort.

Consider:

- Sufficient contrast.
- Readable silhouettes.
- Avoiding reliance on color alone.
- Visual clarity at different display sizes.
- Excessive brightness or flashing.
- Repetitive high-intensity visual effects.
- Patterns or textures that reduce readability.
- Motion and visual effects that may cause discomfort.

Project-specific accessibility requirements MUST be documented and applied consistently.

## 16. Performance Considerations

Art assets MUST be appropriate for the project's performance requirements.

Consider:

- Texture dimensions and memory usage.
- Model complexity.
- Material and shader complexity.
- Transparency and overdraw.
- Draw calls.
- Asset reuse.
- Visibility and loading behavior.
- Platform limitations.

Do not optimize assets blindly. Use profiling and project performance targets to identify meaningful issues.

Performance optimization MUST preserve acceptable visual quality and gameplay readability.

Detailed technical optimization requirements are defined in `docs/02_technical_standards/performance_guidelines.md`.

## 17. Asset Review and Acceptance

Art assets SHOULD be reviewed before being considered complete or integrated into production content.

### 17.1. Visual Review

Verify that the asset:

- Matches the approved art direction.
- Has appropriate proportions and silhouette.
- Uses consistent colors and materials.
- Has suitable detail density.
- Is readable in its intended context.
- Has no obvious visual defects.
- Supports its intended gameplay or presentation purpose.

### 17.2. Technical Review

Verify that the asset:

- Uses an appropriate file format.
- Has correct dimensions and orientation.
- Imports correctly into Godot.
- Has appropriate resource settings.
- Does not introduce unnecessary dependencies.
- Meets relevant performance requirements.
- Is stored in the correct feature-oriented location.

### 17.3. Licensing Review

Verify that:

- The asset's source is known when applicable.
- Usage rights are understood.
- Required attribution is preserved.
- Restrictions are documented.
- Source files and dependencies are available when required.

### 17.4. Acceptance

An asset SHOULD be considered accepted when it satisfies its visual, technical, and licensing requirements.

Incomplete or partially validated assets MUST be identified accurately.

AI agents MUST NOT mark assets as approved when human art direction or project owner approval is required.

## 18. Asset Replacement and Removal

Before replacing or removing an asset:

1. Identify its current references and dependencies.
2. Determine which features or scenes use it.
3. Check whether the asset is shared.
4. Evaluate the impact of replacement or removal.
5. Preserve source files and licensing records when required.
6. Update affected references and documentation.
7. Validate affected scenes and gameplay.

Avoid deleting assets merely because they are not immediately visible or used in the current development task.

Unused assets SHOULD be evaluated before removal, especially when they may be used by dynamically loaded content or project configuration.

## 19. Documentation Requirements

Projects SHOULD document significant art decisions and asset requirements.

Documentation MAY include:

- Art direction.
- Visual references.
- Character design specifications.
- Environment design specifications.
- Asset lists.
- Asset dimensions and technical requirements.
- Material conventions.
- Licensing records.
- Asset review results.
- Approved exceptions.

Project-specific art documentation MUST be maintained in the game repository.

Studio-wide standards MUST NOT become a repository for individual game assets or project-specific art direction.

## 20. AI-Assisted Art Asset Work

AI agents assisting with art asset tasks MUST:

1. Read the relevant project art direction and asset requirements.
2. Follow the studio naming and feature-oriented organization standards.
3. Preserve existing assets and source files.
4. Verify licensing and attribution information when using external assets.
5. Avoid introducing unapproved visual styles or major design changes.
6. Validate assets in their intended game context when possible.
7. Avoid unnecessary asset duplication.
8. Report technical and visual limitations honestly.
9. Identify assets that require human artistic review.
10. Request approval before making significant changes to established art direction or shared assets.

AI agents MUST NOT:

- Claim an asset is tested when it has not been tested.
- Assume that generated assets are automatically free of licensing concerns.
- Delete or replace existing assets without checking their dependencies.
- Introduce unapproved changes to the project's visual identity.
- Mark subjective artistic decisions as approved without the appropriate authority.

## 21. Art Asset Review Checklist

Before accepting an art asset, verify the following where applicable:

- [ ] The asset supports the approved art direction.
- [ ] Its purpose and intended usage are clear.
- [ ] Its proportions and silhouette are appropriate.
- [ ] Its colors, materials, and details are consistent.
- [ ] It is readable at its intended in-game size.
- [ ] It does not obscure important gameplay information.
- [ ] It uses appropriate dimensions and file formats.
- [ ] It is stored in the correct feature-oriented location.
- [ ] Its filename follows the naming conventions.
- [ ] Source files are preserved when available and required.
- [ ] Licensing and attribution requirements are satisfied.
- [ ] It imports correctly into the project.
- [ ] Its performance impact is acceptable.
- [ ] It has been reviewed in its intended context.
- [ ] Relevant documentation has been updated.

Not every checklist item applies to every asset. Non-applicable requirements SHOULD be identified rather than treated as failures.

## 22. Exceptions

Exceptions to these standards MAY be permitted when justified by:

- Specific artistic requirements.
- Technical limitations.
- Platform constraints.
- Production priorities.
- Accessibility requirements.
- Experimental visual approaches.

Exceptions MUST:

- Have a clear justification.
- Identify affected assets or features.
- Describe relevant risks and consequences.
- Receive project owner approval when they affect established studio or project standards.
- Be documented when they have lasting impact.

Temporary exceptions SHOULD be reviewed before final release.

## 23. Related Documents

- `docs/00_studio_standards/naming_conventions.md`
- `docs/00_studio_standards/project_structure_standards.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/02_technical_standards/asset_pipeline.md`
- `docs/02_technical_standards/performance_guidelines.md`
- `docs/02_technical_standards/resource_management.md`
- `docs/03_art_audio_standards/animation_standards.md`

## 24. Maintenance

These standards SHOULD be reviewed periodically and updated when:

- Studio art production practices change.
- New asset types or workflows are introduced.
- Engine capabilities or technical requirements change.
- Recurring visual quality issues are identified.
- Licensing or distribution requirements change.
- Improvements to asset creation and review are identified.

Changes MUST preserve the distinction between reusable studio standards and project-specific art direction.

The project owner is responsible for approving changes to these standards.