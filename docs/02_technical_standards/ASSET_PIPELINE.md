# Asset Pipeline

## 1. Purpose

This document establishes reusable technical guidelines for managing the asset pipeline across studio Godot projects.

It defines the expected workflow for:

- Acquiring and preparing source assets.
- Importing assets into Godot.
- Configuring import settings.
- Processing and optimizing assets.
- Managing asset dependencies.
- Validating imported assets.
- Maintaining asset consistency across development environments.
- Preparing assets for builds and releases.

The objective is to establish a reliable, repeatable, and maintainable asset pipeline while minimizing unnecessary processing, import errors, and resource waste.

## 2. Scope

These guidelines apply to technical asset workflows involving:

- 2D textures and sprites.
- 3D models and meshes.
- Materials and shaders.
- Animations and animation data.
- Audio files.
- Fonts.
- TileSets and TileMaps.
- Particle and visual effects.
- UI assets.
- Other resources imported or consumed by Godot.

These guidelines primarily target Godot projects using GDScript.

Artistic direction, visual quality, asset naming, licensing, and source ownership are governed by their respective studio standards.

## 3. Asset Pipeline Principles

### 3.1 Source Asset Preservation

Original source assets SHOULD be preserved whenever practical.

Developers SHOULD:

- Keep original files separate from generated or processed outputs when the workflow requires it.
- Avoid destructively modifying source files.
- Preserve editable source formats when available.
- Maintain a clear relationship between source assets and their in-game versions.
- Reprocess assets from their original sources when necessary.

Generated or imported files MUST NOT be treated as the authoritative source when an editable original exists.

### 3.2 Reproducibility

Asset processing SHOULD produce consistent results across development environments.

Developers SHOULD:

- Use documented import settings.
- Avoid undocumented manual processing steps.
- Keep required source assets in version control.
- Avoid relying on local-only generated files.
- Validate asset imports after changes to project configuration or engine versions.

### 3.3 Appropriate Optimization

Assets SHOULD be optimized according to their intended use and target platform.

Optimization SHOULD consider:

- Visual quality.
- Runtime memory usage.
- Storage size.
- Loading time.
- Rendering performance.
- Platform compatibility.

Optimization MUST NOT unnecessarily compromise the intended visual or audio experience.

### 3.4 Consistency

Assets of the same type and intended use SHOULD follow consistent import and processing settings.

Import configurations SHOULD be reviewed when an asset is used in an unusual context or has specific technical requirements.

### 3.5 Minimal Processing

The pipeline SHOULD perform only the processing necessary for the intended use.

Developers SHOULD avoid unnecessary conversion, duplication, compression, or processing stages.

## 4. Asset Lifecycle

The standard asset lifecycle consists of the following stages:

1. Acquisition or creation.
2. Source validation.
3. Organization and placement.
4. Import into Godot.
5. Import configuration.
6. Processing and optimization.
7. In-engine validation.
8. Integration into features.
9. Build validation.
10. Maintenance or replacement.

Not every asset requires a complex workflow. Processing SHOULD remain proportional to the asset's complexity and intended use.

## 5. Source Asset Management

### 5.1 Source Formats

Source assets SHOULD use formats appropriate to their content and editing requirements.

Examples include:

| Asset type | Common source formats |
|---|---|
| 2D images | PNG, JPEG, WebP, SVG |
| 3D models | GLB, glTF, FBX, OBJ |
| Audio | WAV, FLAC, OGG, MP3 |
| Fonts | TTF, OTF |
| Textures | PNG, TIFF, EXR |
| Animation | Supported source formats and Godot-native resources |

Format selection MUST consider compatibility with the project's Godot version and intended import workflow.

### 5.2 Source Validation

Before importing an asset, developers SHOULD verify:

- The file is valid and readable.
- The format is supported by the project workflow.
- The dimensions and resolution are appropriate.
- The asset does not contain unnecessary data.
- The file is not corrupted.
- Its licensing and provenance are documented when required.
- Any external dependencies are available.

### 5.3 External Tools

External tools MAY be used to create, convert, compress, or optimize assets.

When external tools are part of a repeatable pipeline, developers SHOULD document:

- Tool name and version.
- Processing purpose.
- Required input formats.
- Expected output formats.
- Important configuration settings.
- Any manual steps that cannot be automated.

Critical processing steps SHOULD NOT depend on undocumented local configurations.

## 6. Asset Organization and Integration

### 6.1 Feature Ownership

Assets MUST follow the studio's feature-oriented project structure standards.

Assets used exclusively by one feature SHOULD be stored within that feature's directory.

Assets genuinely shared by multiple features MAY be stored in the shared asset area.

Developers MUST NOT duplicate assets across features without a clear technical or design justification.

### 6.2 Source and Imported Asset Separation

Projects SHOULD maintain a clear distinction between source assets, Godot-imported resources, and generated outputs.

Godot's import system manages imported artifacts through its generated cache.

The `.godot/` directory MUST NOT be treated as a source asset directory and MUST NOT be committed to version control.

Source assets and project-owned resources required to reconstruct the project MUST be version controlled according to repository standards.

### 6.3 Dependencies

Assets MAY depend on other resources, such as:

- Materials.
- Textures.
- Animation libraries.
- Skeletons.
- Audio streams.
- Shader resources.
- Other imported or native Godot resources.

Dependencies SHOULD be explicit and valid.

Developers SHOULD avoid unnecessary external dependencies and duplicated resource chains.

## 7. Godot Import Pipeline

### 7.1 General Import Workflow

When an asset is added or modified:

1. Place the source file in its appropriate project directory.
2. Allow Godot to detect and import the asset.
3. Review the generated import configuration.
4. Configure import options when necessary.
5. Verify the imported resource.
6. Test the asset in its intended scene or feature.
7. Validate that dependent resources remain functional.

Import settings SHOULD be committed when Godot generates project metadata required to preserve those settings.

### 7.2 Import Settings

Import settings MUST be selected according to the intended use of the asset.

Developers SHOULD avoid changing import settings without understanding their effects.

Import settings MAY affect:

- Compression.
- Filtering.
- Mipmaps.
- Texture dimensions.
- Mesh processing.
- Material generation.
- Animation import.
- Audio compression.
- Looping and playback behavior.

Project-specific defaults SHOULD be established for commonly used asset categories.

### 7.3 Import Configuration Changes

When changing import settings, developers SHOULD:

- Identify affected resources.
- Understand whether reimporting is required.
- Verify that the new settings produce the intended result.
- Test dependent scenes and resources.
- Review changes to generated metadata.
- Avoid committing unnecessary generated artifacts.

### 7.4 Reimporting Assets

Assets SHOULD be reimported when:

- Their source files change.
- Relevant import settings change.
- The engine requires reimporting after a version change.
- Imported data becomes invalid or inconsistent.

Developers MUST NOT manually modify Godot-generated imported artifacts as a substitute for changing the source asset or its import configuration.

## 8. Asset-Type Guidelines

### 8.1 2D Textures and Sprites

Developers SHOULD consider:

- Texture dimensions.
- Transparency requirements.
- Filtering mode.
- Mipmap requirements.
- Compression method.
- Sprite sheet layout.
- Texture atlas usage.
- Intended display resolution.

Texture filtering SHOULD be consistent with the project's visual style.

Mipmaps SHOULD be enabled when they provide benefits for scaled or distant textures and disabled when they are unnecessary.

Texture compression SHOULD balance memory usage, visual quality, and platform compatibility.

Sprite sheets SHOULD use consistent frame dimensions and layouts when required by the animation workflow.

### 8.2 3D Models and Meshes

3D assets SHOULD be validated for:

- Scale and orientation.
- Mesh integrity.
- Polygon complexity.
- Material assignments.
- UV coordinates.
- Normals and tangents.
- Skeleton structure.
- Animation compatibility.
- Collision requirements.

Developers SHOULD remove unnecessary geometry and unused model data when appropriate.

Collision geometry SHOULD be designed for gameplay and physics requirements rather than automatically reusing complex visual meshes.

Model import settings SHOULD be consistent with the project's rendering and animation requirements.

### 8.3 Materials and Shaders

Materials SHOULD be reusable when their visual and technical responsibilities are shared.

Developers SHOULD:

- Avoid unnecessary material duplication.
- Keep material parameters understandable.
- Validate shader compatibility with the selected renderer.
- Consider shader complexity and runtime cost.
- Avoid excessive shader variants without a clear need.

Shaders SHOULD be tested under relevant rendering conditions.

### 8.4 Animations

Animation assets SHOULD be validated for:

- Correct frame or keyframe timing.
- Valid animation names.
- Expected looping behavior.
- Correct skeleton or node paths.
- Consistent animation transitions.
- Compatibility with their target scenes.

Animation resources SHOULD avoid unnecessary duplication.

Developers SHOULD ensure that animation ownership and playback responsibilities are clear.

### 8.5 Audio

Audio assets SHOULD be processed according to their intended use.

Developers SHOULD consider:

- Sample rate.
- Channel count.
- Bit depth.
- Compression format.
- File size.
- Playback latency.
- Looping requirements.
- Spatial audio requirements.
- Streaming versus in-memory playback.

Short sound effects and long-form music MAY require different import configurations.

Audio import settings SHOULD balance quality, memory consumption, storage, and playback requirements.

Looping audio SHOULD be tested for audible discontinuities.

### 8.6 Fonts

Font resources SHOULD be validated for:

- Required character coverage.
- Readability.
- Licensing restrictions.
- Font rendering compatibility.
- File size.
- Supported language requirements.

Font assets SHOULD be tested with the actual UI text and supported languages.

### 8.7 UI Assets

UI assets SHOULD be tested at the intended interface sizes and display configurations.

Developers SHOULD consider:

- Texture scaling.
- Filtering.
- Nine-patch configuration.
- Theme compatibility.
- Readability.
- Stretching behavior.
- Resolution independence.

UI assets SHOULD remain consistent with the project's UI/UX guidelines.

### 8.8 TileSets and TileMaps

Tile-based assets SHOULD be validated for:

- Tile dimensions.
- Atlas coordinates.
- Texture region consistency.
- Collision configuration.
- Navigation configuration.
- Terrain and alternative tile settings.
- Rendering and layering behavior.

Changes to TileSet resources SHOULD be tested in affected scenes.

### 8.9 Particles and Visual Effects

Particle and visual effect resources SHOULD be configured according to their intended visual and performance requirements.

Developers SHOULD consider:

- Particle count.
- Lifetime.
- Emission rate.
- Material complexity.
- Collision behavior.
- Simulation cost.
- Screen-space coverage.

Effects SHOULD be tested under representative gameplay conditions rather than only in isolated editor previews.

## 9. Asset Optimization

### 9.1 General Optimization

Optimization SHOULD be based on actual project requirements and measured constraints.

Developers SHOULD consider:

- Texture memory.
- Mesh complexity.
- Audio memory.
- Resource loading time.
- Draw calls and material usage.
- Shader complexity.
- Particle counts.
- Asset storage size.

### 9.2 Texture Optimization

Developers SHOULD:

- Avoid unnecessarily large textures.
- Select suitable compression settings.
- Use texture atlases when they provide measurable benefits.
- Avoid redundant texture copies.
- Consider platform-specific compression requirements.

### 9.3 Model Optimization

Developers SHOULD:

- Remove unnecessary geometry.
- Avoid excessive material assignments.
- Use appropriate levels of detail when justified.
- Simplify collision meshes.
- Reuse meshes and materials where appropriate.

### 9.4 Audio Optimization

Developers SHOULD:

- Use suitable compression for long-form audio.
- Avoid unnecessarily high sample rates or channel counts.
- Select streaming or in-memory playback appropriately.
- Validate quality after compression.

### 9.5 Optimization Validation

Optimization changes MUST be validated to ensure they do not introduce:

- Visible artifacts.
- Broken materials.
- Incorrect animation.
- Audio degradation.
- Missing resources.
- Unexpected rendering behavior.
- Gameplay regressions.

## 10. Resource Loading and Memory Management

### 10.1 Resource Loading

Resources SHOULD be loaded according to their expected usage and lifecycle.

Developers SHOULD consider:

- Preloading for frequently accessed resources.
- Runtime loading for large or infrequently used resources.
- Background loading where supported and appropriate.
- Loading screens or transitions when necessary.
- Resource reuse.

Loading strategies SHOULD be proportional to actual performance requirements.

### 10.2 Resource Reuse

Reusable resources SHOULD be shared when appropriate.

Developers MUST understand whether a resource is shared between instances before modifying it at runtime.

Runtime-specific data SHOULD be duplicated or instantiated when shared mutation would produce unintended side effects.

### 10.3 Resource Unloading

Developers SHOULD understand how resource references affect resource lifetime.

Unnecessary references SHOULD be released when their owning systems no longer require them.

Memory-sensitive features SHOULD be tested during repeated loading and unloading.

## 11. Asset Dependencies and Compatibility

### 11.1 Dependency Integrity

Asset dependencies MUST resolve correctly.

Developers SHOULD verify:

- Referenced files exist.
- Resource paths are valid.
- External dependencies are available.
- Materials and textures are correctly assigned.
- Animation references remain valid.
- Scenes load without missing-resource errors.

### 11.2 Engine Compatibility

Asset formats and import settings MUST be compatible with the project's configured Godot version.

Engine upgrades SHOULD include validation of affected imported resources.

Developers SHOULD review import changes after upgrading Godot rather than assuming existing settings remain identical.

### 11.3 Platform Compatibility

Assets SHOULD be validated against the project's target platforms.

Developers SHOULD consider platform-specific limitations involving:

- Texture formats.
- Audio formats.
- Rendering capabilities.
- Memory constraints.
- File size.
- Resource loading.

Platform-specific processing MAY be introduced when required.

## 12. Version Control

### 12.1 Source Assets

Source assets required to reconstruct the project MUST be tracked according to repository standards.

Large binary assets SHOULD be evaluated for appropriate version-control handling.

Git Large File Storage (Git LFS) MAY be used when asset size and repository requirements justify it.

### 12.2 Generated Files

Godot's generated cache and temporary processing files MUST NOT be committed.

The repository MUST preserve the source assets and project metadata required to reproduce imports.

Developers SHOULD inspect changes before committing asset updates.

### 12.3 Asset Changes

Asset changes SHOULD be reviewed for:

- Correct file placement.
- Source integrity.
- Import configuration changes.
- Unexpected file size increases.
- Unnecessary duplicates.
- Missing dependencies.
- Licensing and provenance documentation.

### 12.4 Binary Asset Review

Binary asset changes SHOULD include enough context for reviewers to understand their purpose.

When practical, pull requests SHOULD provide:

- Preview images or screenshots.
- Description of the change.
- Relevant source file information.
- Import setting changes.
- Performance or size implications.

## 13. Asset Validation and Quality Control

### 13.1 Import Validation

New or modified assets MUST be checked for successful import.

Validation SHOULD confirm:

- No import errors.
- No missing resources.
- Correct resource type.
- Expected dimensions and properties.
- Correct material and dependency references.
- Appropriate runtime behavior.

### 13.2 In-Engine Validation

Assets SHOULD be tested in their intended context.

Examples include:

- Sprites in gameplay scenes.
- Models in their target environments.
- Animations on the intended characters.
- Audio during representative gameplay.
- UI assets in their actual interface layouts.
- Materials under relevant lighting conditions.

An asset that imports successfully is not necessarily an asset that works correctly in the game.

### 13.3 Build Validation

Important asset changes SHOULD be validated in a project build.

Build validation SHOULD confirm that:

- Required assets are included.
- Resource references resolve.
- Imported resources function correctly.
- No required files depend on local-only data.
- Platform-specific resources are available.

### 13.4 Automated Validation

Automated asset validation MAY be introduced when it provides meaningful benefits.

Examples include:

- Checking for missing resource references.
- Detecting invalid asset paths.
- Checking naming conventions.
- Detecting oversized textures.
- Detecting unexpected asset duplication.
- Verifying required source files.
- Running headless import checks.

Automation SHOULD remain maintainable and SHOULD NOT create unnecessary pipeline complexity.

## 14. Asset Replacement and Removal

### 14.1 Asset Replacement

When replacing an asset, developers SHOULD verify:

- All references to the original asset.
- Compatibility with existing scenes and resources.
- Import settings of the replacement.
- Differences in dimensions, scale, or format.
- Effects on animation, materials, and gameplay.
- Whether existing resource identifiers or references require migration.

Replacement MUST NOT leave unresolved references.

### 14.2 Asset Removal

Before deleting an asset, developers MUST verify that it is no longer required.

Developers SHOULD:

- Search for references.
- Check scene and resource dependencies.
- Validate related features.
- Remove obsolete import metadata when appropriate.
- Verify the project still imports and runs correctly.

### 14.3 Deprecation

Assets MAY be marked as deprecated when they should no longer be used but cannot yet be removed safely.

Deprecated assets SHOULD have a documented replacement or removal plan when applicable.

## 15. Build and Release Considerations

Before a release, the asset pipeline SHOULD be validated to ensure that all required resources are included and correctly processed.

Release validation SHOULD include:

- Clean project import.
- Missing-resource checks.
- Asset dependency validation.
- Representative scene loading.
- Texture and audio quality checks.
- Target platform compatibility.
- Build size review.
- Runtime memory checks where relevant.

Release builds MUST NOT depend on undocumented local files or manually generated resources that are absent from the repository.

## 16. AI-Assisted Asset Pipeline Requirements

AI agents MUST follow these guidelines when creating, importing, modifying, or removing assets.

Agents MUST:

- Inspect the existing asset organization before adding files.
- Follow feature-oriented asset ownership.
- Preserve source assets when practical.
- Respect existing import settings and conventions.
- Verify asset compatibility with the project Godot version.
- Avoid modifying generated import artifacts directly.
- Validate asset references after changes.
- Check for duplicate assets before introducing new ones.
- Report significant changes to import settings or resource dependencies.
- Identify assets requiring licensing or provenance verification.

Agents MUST NOT:

- Delete source assets without authorization.
- Commit generated `.godot/` cache files.
- Introduce undocumented local-only processing steps.
- Replace assets without checking their dependencies.
- Claim an asset is validated merely because it exists in the project.
- Change project-wide import settings without evaluating their impact.

Agents SHOULD request human approval before introducing significant asset-processing tools, changing project-wide import conventions, or performing destructive asset migrations.

## 17. Asset Pipeline Review Checklist

Before completing an asset-related task, verify:

- [ ] The asset has an appropriate source format.
- [ ] The source file is valid and preserved when required.
- [ ] The asset is stored in the correct feature or shared directory.
- [ ] Import settings are appropriate for its intended use.
- [ ] The asset imports successfully.
- [ ] Dependencies and resource references are valid.
- [ ] Runtime behavior has been tested in the intended context.
- [ ] Optimization is appropriate and does not compromise quality.
- [ ] No generated cache files have been committed.
- [ ] Version-control changes are intentional.
- [ ] Licensing and provenance requirements are addressed.
- [ ] Relevant documentation has been updated.
- [ ] Build validation has been performed when applicable.

## 18. Exceptions

Exceptions MAY be introduced when specific project requirements justify an alternative asset workflow.

Exceptions SHOULD:

- Have a clear technical justification.
- Identify affected assets and platforms.
- Document relevant processing requirements.
- Be reviewed by the project owner when they affect shared pipeline conventions.
- Include validation appropriate to the associated risks.

## 19. Related Documents

These guidelines SHOULD be used alongside:

- `docs/00_studio_standards/project_structure_standards.md`
- `docs/00_studio_standards/naming_conventions.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/documentation_standards.md`
- `docs/02_technical_standards/architecture_guidelines.md`
- `docs/02_technical_standards/adr/README.md`
- `docs/03_art_audio_standards/`

Only documents that exist in the repository should be registered as active references in the documentation inventory.

## 20. Maintenance

These guidelines SHOULD be reviewed when:

- Godot changes its import or resource pipeline.
- The studio adopts new asset formats or processing tools.
- Target platforms introduce new technical constraints.
- Repeated project experience reveals pipeline problems.
- Asset validation or optimization practices evolve.

Changes MUST preserve the document's purpose as a reusable studio-wide technical standard.