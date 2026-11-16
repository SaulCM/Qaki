# Engine Standards

## 1. Purpose

This document establishes reusable technical standards and guidelines for configuring, using, maintaining, and upgrading the Godot Engine across studio projects.

Its purpose is to ensure consistent and reliable engine usage while allowing individual games to make appropriate technical decisions based on their requirements.

These standards cover:

- Godot Engine version management.
- Project configuration.
- Rendering and display settings.
- Physics configuration.
- Scene and node lifecycle.
- Resource management.
- Input handling.
- Animation and audio systems.
- Engine debugging and diagnostics.
- Performance profiling.
- Export configuration.
- Engine upgrades and compatibility.

The objective is to establish a stable technical foundation without introducing unnecessary restrictions or complexity.

## 2. Scope

These standards apply to all studio projects developed using Godot Engine.

They primarily target:

- Godot Engine 4.x.
- GDScript.
- Godot's native scene, node, resource, rendering, physics, and input systems.

Specific engine capabilities and configuration options MUST be verified against the project's selected Godot version.

Individual projects MAY establish additional engine configuration requirements when justified by their technical or gameplay needs.

## 3. Engine Usage Principles

### 3.1 Version Consistency

Each project MUST use an explicitly defined Godot Engine version.

Developers MUST NOT independently upgrade the engine without evaluating compatibility and obtaining the required approval.

The selected engine version SHOULD be consistent across:

- Development environments.
- Automated validation.
- Build environments.
- Continuous integration workflows.
- Release processes.

### 3.2 Use Native Capabilities Appropriately

Developers SHOULD prefer built-in Godot capabilities when they satisfy the project requirements.

Examples include:

- Nodes and scenes.
- Resources.
- Signals.
- InputMap.
- AnimationPlayer and AnimationTree.
- ResourceLoader and ResourceSaver.
- FileAccess and ConfigFile.
- Built-in physics systems.
- Rendering and audio systems.

Custom implementations MAY be introduced when native functionality is insufficient or when a custom solution provides a clear benefit.

### 3.3 Configuration Consistency

Project-wide engine settings SHOULD be intentional, documented when necessary, and maintained consistently.

Developers MUST avoid unnecessary configuration changes that can affect unrelated systems.

### 3.4 Performance Awareness

Engine features SHOULD be used with an understanding of their runtime costs.

Developers SHOULD profile actual performance problems before introducing complex optimizations.

### 3.5 Compatibility

Engine-dependent implementations MUST remain compatible with the project's configured Godot version and supported target platforms.

Developers SHOULD avoid relying on undocumented or unstable engine behavior.

## 4. Godot Version Management

### 4.1 Version Selection

Each project MUST define its Godot Engine version.

The selected version SHOULD consider:

- Project requirements.
- Required engine features.
- Stability.
- Platform support.
- Plugin compatibility.
- Existing project dependencies.
- Maintenance expectations.

Stable releases SHOULD generally be preferred for production projects.

Pre-release, beta, and development builds MAY be used for experimentation but SHOULD NOT be adopted for production without explicit justification and approval.

### 4.2 Version Documentation

The selected engine version MUST be documented in the project repository.

The project SHOULD provide a clear and accessible indication of the required version, such as:

- Project documentation.
- A dedicated development setup document.
- Repository configuration.
- Continuous integration configuration.

Developers SHOULD avoid maintaining conflicting engine-version declarations.

### 4.3 Version Upgrades

Engine upgrades MUST be treated as controlled technical changes.

Before upgrading, developers SHOULD:

1. Identify the current and target versions.
2. Review relevant release notes and migration documentation.
3. Check plugin and dependency compatibility.
4. Identify potentially affected project systems.
5. Evaluate project and save-data compatibility.
6. Create an appropriate Git checkpoint or branch.
7. Perform the upgrade.
8. Validate imports, scenes, scripts, and resources.
9. Run relevant tests.
10. Document significant changes.

Major or potentially disruptive upgrades MUST receive project owner approval.

### 4.4 Version Rollback

Projects SHOULD maintain a recoverable state before engine upgrades.

Rollback procedures SHOULD consider:

- Project configuration changes.
- Resource format changes.
- Scene and script compatibility.
- Imported resource metadata.
- Plugin compatibility.

Developers MUST NOT assume that opening and saving a project in a newer engine version can always be safely reversed by reopening it in an older version.

## 5. Project Configuration

### 5.1 Project Settings

The `project.godot` file MUST be maintained as the authoritative configuration file for project-level Godot settings.

Developers SHOULD:

- Keep configuration values intentional.
- Avoid unnecessary configuration changes.
- Review changes to project settings.
- Preserve existing settings unless a change is required.
- Document non-obvious project-wide configuration decisions.

### 5.2 Configuration Organization

Project configuration SHOULD remain understandable and consistent.

Settings SHOULD be grouped according to their engine-defined categories whenever practical.

Project-specific configuration MAY be documented separately when it includes important technical constraints or decisions that are not self-explanatory.

### 5.3 Configuration Changes

Changes to project-wide settings SHOULD be reviewed for their effects on:

- Rendering.
- Physics.
- Input.
- Audio.
- Display behavior.
- Resource loading.
- Platform compatibility.
- Performance.

Changes with substantial architectural or technical consequences SHOULD be documented through an ADR when appropriate.

### 5.4 Generated Files

Godot-generated cache and temporary files MUST NOT be committed to version control.

The `.godot/` directory SHOULD remain excluded from source control.

The repository MUST retain the project files and source assets necessary to reconstruct the project through the normal Godot import process.

## 6. Rendering Standards

### 6.1 Rendering Method Selection

Each project SHOULD explicitly select an appropriate rendering method.

Godot rendering methods SHOULD be selected according to:

- Visual requirements.
- Target platforms.
- Hardware capabilities.
- Required rendering features.
- Performance expectations.
- Compatibility constraints.

Available rendering methods and their capabilities MUST be verified against the selected Godot version.

### 6.2 Rendering Configuration

Rendering settings SHOULD be configured intentionally.

Developers SHOULD consider:

- Rendering method.
- Rendering backend.
- Resolution and scaling.
- Texture filtering.
- Anti-aliasing.
- Shadow quality.
- Lighting configuration.
- Environment settings.
- Viewport configuration.

Settings SHOULD be evaluated under representative gameplay conditions.

### 6.3 2D Rendering

For 2D projects, developers SHOULD consider:

- Canvas rendering behavior.
- Texture filtering.
- Pixel-art requirements.
- Sprite scaling.
- Camera behavior.
- Z-index and canvas layering.
- Viewport scaling.
- Lighting and shadow requirements.

Pixel-art projects SHOULD use consistent rendering and scaling configurations to avoid unintended distortion or inconsistent pixel appearance.

### 6.4 3D Rendering

For 3D projects, developers SHOULD consider:

- Lighting and shadows.
- Materials and shaders.
- Environment settings.
- Mesh complexity.
- Camera configuration.
- Occlusion and visibility.
- Level of detail.
- Rendering scalability.

Rendering features SHOULD be selected according to the intended visual quality and target hardware.

### 6.5 Shader Usage

Shaders SHOULD be used when they provide necessary visual or performance benefits.

Developers SHOULD:

- Keep shader responsibilities focused.
- Avoid unnecessary shader complexity.
- Validate compatibility with the selected renderer.
- Consider shader compilation and runtime costs.
- Test shaders under representative lighting and rendering conditions.

Custom shaders SHOULD be documented when their behavior or constraints are not readily understandable.

## 7. Display and Resolution Standards

### 7.1 Display Configuration

Projects MUST define their intended display behavior.

Relevant settings MAY include:

- Window mode.
- Initial window size.
- Aspect ratio.
- Viewport dimensions.
- Content scaling.
- Stretch mode.
- Stretch aspect.
- Fullscreen behavior.

The selected configuration SHOULD support the game's intended presentation and target platforms.

### 7.2 Resolution Independence

Projects SHOULD consider different display resolutions and aspect ratios unless the game intentionally targets a fixed display configuration.

UI and gameplay presentation SHOULD remain usable under supported configurations.

### 7.3 Display Validation

Display behavior SHOULD be tested at representative:

- Resolutions.
- Aspect ratios.
- Window sizes.
- Fullscreen configurations.
- UI scaling configurations.

Developers SHOULD identify layout or rendering problems before release.

## 8. Physics Standards

### 8.1 Physics System Selection

Projects SHOULD use Godot's built-in physics systems unless specific requirements justify an alternative.

The selected physics approach MUST be compatible with the project's gameplay and target platforms.

### 8.2 Physics Configuration

Physics settings SHOULD be configured intentionally.

Developers SHOULD consider:

- Physics tick rate.
- Collision layers.
- Collision masks.
- Collision shapes.
- Gravity.
- Physics materials.
- Continuous collision detection.
- Physics interpolation where supported.
- Performance implications.

Project-wide physics settings SHOULD remain consistent unless a justified exception exists.

### 8.3 Collision Design

Collision shapes SHOULD represent gameplay requirements rather than automatically reproducing visual geometry.

Developers SHOULD:

- Prefer simple collision shapes when appropriate.
- Avoid unnecessarily complex collision geometry.
- Configure collision layers and masks deliberately.
- Prevent unintended collision interactions.
- Validate collision behavior in representative scenes.

### 8.4 Physics and Frame Updates

Physics-dependent behavior SHOULD use the appropriate physics processing callbacks.

Developers MUST avoid relying on variable frame timing for operations that require consistent physics simulation.

Physics-related logic SHOULD be tested under different frame-rate conditions where appropriate.

## 9. Scene and Node Lifecycle

### 9.1 Scene Responsibilities

Scenes SHOULD represent meaningful game objects, interfaces, environments, or cohesive functional units.

Scenes SHOULD follow the studio's architecture and feature-oriented project structure standards.

### 9.2 Node Lifecycle

Developers MUST understand Godot's node lifecycle when implementing initialization, processing, and cleanup behavior.

Relevant lifecycle callbacks include:

- `_init()`
- `_enter_tree()`
- `_ready()`
- `_process()`
- `_physics_process()`
- `_exit_tree()`
- `_notification()`

Developers SHOULD use lifecycle callbacks according to their intended responsibilities.

### 9.3 Node References

Node references SHOULD be established in a predictable and safe manner.

Developers SHOULD:

- Avoid accessing nodes before they are ready.
- Validate references when necessary.
- Avoid retaining references to freed nodes.
- Use appropriate node ownership and lifecycle management.
- Avoid unnecessary dependence on fragile scene-tree paths.

### 9.4 Processing

Continuous processing SHOULD be enabled only when required.

Developers SHOULD:

- Avoid unnecessary `_process()` and `_physics_process()` execution.
- Disable processing when functionality is inactive.
- Prefer event-driven updates when appropriate.
- Avoid expensive operations inside frequently executed callbacks.

### 9.5 Scene Transitions

Scene transitions SHOULD be managed through a clearly defined mechanism.

Developers SHOULD consider:

- Scene initialization.
- Loading behavior.
- Resource dependencies.
- Transition feedback.
- Cleanup of previous scenes.
- Persistence of required state.

Scene transitions MUST NOT unintentionally discard required persistent or session data.

## 10. Resource Management

### 10.1 Native Resource Usage

Godot Resources SHOULD be used for reusable data and configuration when appropriate.

Developers SHOULD prefer native resource mechanisms over custom serialization or data containers when native capabilities satisfy the requirements.

### 10.2 Resource Loading

Resource loading SHOULD follow the intended lifecycle and performance requirements.

Developers MAY use:

- `preload()`.
- `load()`.
- `ResourceLoader`.
- `ResourceLoader.load_threaded_request()`.
- Other supported resource-loading mechanisms.

The selected approach SHOULD consider loading frequency, resource size, and runtime behavior.

### 10.3 Resource Sharing

Developers MUST understand that multiple objects may reference the same Resource instance.

Shared resources SHOULD NOT be modified at runtime when such changes could unintentionally affect other users of the resource.

Developers SHOULD duplicate resources when independent mutable instances are required.

### 10.4 Resource Lifetime

Resource references SHOULD be managed according to their intended lifecycle.

Developers SHOULD avoid unnecessary long-lived references that prevent resources from being released when no longer required.

### 10.5 Resource Paths

Resource references MUST resolve correctly within the project.

Developers SHOULD avoid fragile path assumptions and verify resource references after moving or renaming assets.

## 11. Input Standards

### 11.1 InputMap

Godot's InputMap SHOULD be used for managing gameplay and application input actions.

Input actions SHOULD:

- Have meaningful names.
- Represent player intentions rather than hardware-specific keys.
- Support the project's intended input devices.
- Avoid unnecessary duplication.
- Be documented when their behavior is not obvious.

### 11.2 Input Abstraction

Gameplay systems SHOULD respond to logical input actions rather than directly depending on specific keyboard keys, mouse buttons, or controller buttons.

This approach SHOULD support remapping and additional input devices when required.

### 11.3 Input Handling

Input handling SHOULD use the appropriate Godot input mechanisms.

Developers SHOULD consider:

- `_input()`.
- `_unhandled_input()`.
- `_unhandled_key_input()`.
- Input action polling.
- GUI input handling.
- Input consumption and propagation.

Input SHOULD be handled at the appropriate layer to prevent unintended interactions between gameplay and UI.

### 11.4 Input Validation

Input behavior SHOULD be tested with the devices and configurations supported by the project.

Developers SHOULD verify:

- Action registration.
- Input propagation.
- Input remapping when supported.
- Controller behavior.
- UI navigation.
- Simultaneous input handling where relevant.

## 12. Animation Standards

### 12.1 Animation Systems

Godot's animation systems SHOULD be selected according to the intended behavior.

Available mechanisms include:

- AnimationPlayer.
- AnimationTree.
- AnimatedSprite2D.
- AnimatedSprite3D.
- Tween.
- Other supported animation mechanisms.

Developers SHOULD avoid introducing multiple competing animation systems for the same responsibility without justification.

### 12.2 Animation Responsibilities

Animation logic SHOULD remain appropriately separated from unrelated gameplay responsibilities.

Developers SHOULD define which system owns:

- Animation selection.
- Animation transitions.
- Animation playback.
- Gameplay state synchronization.
- Animation completion events.

### 12.3 Animation Validation

Animations SHOULD be tested for:

- Correct playback.
- Expected transitions.
- Timing.
- Looping.
- Animation resource references.
- Interaction with gameplay state.

## 13. Audio Standards

### 13.1 Audio Configuration

Godot's audio system SHOULD be configured according to project requirements.

Developers SHOULD consider:

- Audio buses.
- Bus routing.
- Volume control.
- Effects.
- Spatial audio.
- Audio stream configuration.
- Playback lifecycle.

### 13.2 Audio Bus Organization

Audio buses SHOULD have clear responsibilities.

Common examples include:

- Master.
- Music.
- Sound Effects.
- Dialogue.
- Ambience.
- UI.

The exact organization SHOULD reflect the project's audio requirements.

### 13.3 Audio Playback

Audio playback SHOULD be managed through appropriate components and ownership boundaries.

Developers SHOULD avoid uncontrolled creation of audio players or unnecessary duplication of audio resources.

Audio behavior SHOULD be tested during scene transitions, pause states, and other relevant gameplay conditions.

### 13.4 Audio Bus Layout and Volume Categories

Before a player-facing audio options menu or any player-facing audio settings interface is implemented, the project MUST define and document:

- The audio bus layout and bus routing.
- The player-facing volume categories and the buses they control.
- The default volume values and the supported volume range.

These project-specific values MUST be recorded in the game project's documentation under `game_project/docs/` and MUST NOT be hardcoded into interface scripts.

## 14. Engine Debugging and Diagnostics

### 14.1 Debugging Tools

Developers SHOULD use Godot's built-in debugging and diagnostic tools when investigating engine-related problems.

Examples include:

- Debugger.
- Output panel.
- Errors and warnings.
- Remote scene tree.
- Profiler.
- Monitors.
- Visible collision shapes.
- Rendering diagnostics.

### 14.2 Error Handling

Engine errors and warnings SHOULD be investigated rather than ignored.

Developers SHOULD:

- Identify the source of errors.
- Resolve relevant warnings.
- Validate affected systems.
- Avoid suppressing diagnostics without justification.
- Provide useful logging for non-obvious failures.

### 14.3 Logging

Logging and diagnostics SHOULD be meaningful and proportional to the importance of the operation.

Godot does not expose configurable log severity levels. Use the available diagnostics as follows:

- `print()` — temporary development output. It MUST NOT be the mechanism for reporting errors, and unnecessary output MUST be removed before release.
- `push_warning()` — a recoverable condition that should be noticed but does not prevent the operation from continuing.
- `push_error()` — an operation that failed or a contract that was violated and that the caller or developer must address.
- `assert()` — a violated development assumption. Assertions MUST NOT replace validation of external input or recoverable failures.

Developers SHOULD:

- Avoid excessive per-frame logging.
- Avoid logging sensitive information.
- Provide useful context for failures.
- Remove unnecessary debugging output before release.

### 14.4 Runtime Validation

Important engine-dependent behavior SHOULD be validated in the running game.

Successful script parsing or scene import alone MUST NOT be considered sufficient validation for runtime-dependent functionality.

## 15. Performance and Profiling

### 15.1 Performance Measurement

Performance problems SHOULD be identified through measurement rather than assumptions.

Developers SHOULD use Godot's profiler and relevant platform tools when investigating:

- CPU usage.
- Rendering performance.
- Physics performance.
- Memory consumption.
- Resource loading.
- Frame-time instability.

### 15.2 Processing Efficiency

Developers SHOULD:

- Avoid unnecessary per-frame calculations.
- Use signals or event-driven updates where appropriate.
- Avoid excessive node creation.
- Reuse resources where beneficial.
- Keep frequently executed operations lightweight.

### 15.3 Rendering Performance

Rendering optimization SHOULD consider:

- Draw calls.
- Overdraw.
- Texture memory.
- Shader complexity.
- Visibility.
- Mesh complexity.
- Lighting and shadow costs.

### 15.4 Physics Performance

Physics optimization SHOULD consider:

- Active collision objects.
- Collision shape complexity.
- Physics processing frequency.
- Unnecessary collision checks.
- Physics-related script execution.

### 15.5 Optimization Requirements

Significant performance optimizations SHOULD be supported by measurements or reproducible evidence.

Developers MUST verify that optimizations do not introduce functional regressions.

## 16. Plugins and Extensions

### 16.1 Plugin Selection

Third-party plugins MAY be used when they provide meaningful functionality or reduce justified development effort.

Before adopting a plugin, developers SHOULD evaluate:

- Compatibility with the project's Godot version.
- Maintenance activity.
- Documentation quality.
- Licensing.
- Security implications.
- Performance impact.
- Dependency requirements.
- Long-term replacement cost.

### 16.2 Plugin Management

Plugins SHOULD be introduced and maintained deliberately.

Developers SHOULD:

- Keep plugin versions identifiable.
- Document important dependencies.
- Avoid unnecessary plugins.
- Review plugin configuration changes.
- Validate plugins after engine upgrades.

### 16.3 Custom Extensions

Custom engine modules, GDExtensions, and other native extensions MAY be used when requirements justify their additional complexity.

They MUST be evaluated for:

- Build requirements.
- Platform compatibility.
- Version compatibility.
- Runtime reliability.
- Maintenance requirements.
- Distribution implications.

Native extensions SHOULD NOT be introduced when an adequate GDScript or built-in engine solution exists.

## 17. Export and Platform Standards

### 17.1 Export Configuration

Export configurations SHOULD be maintained intentionally.

Projects SHOULD define:

- Target platforms.
- Export presets.
- Required export templates.
- Included resources.
- Platform-specific settings.
- Required permissions.
- Release configuration.

### 17.2 Export Validation

Exported builds MUST be validated independently of editor execution.

Validation SHOULD include:

- Successful export.
- Application startup.
- Scene and resource loading.
- Input behavior.
- Audio behavior.
- Display configuration.
- Save and load functionality.
- Platform-specific functionality.

### 17.3 Platform Compatibility

Engine features SHOULD be evaluated against the project's supported platforms.

Developers MUST NOT assume that functionality available in the editor behaves identically in every exported environment.

### 17.4 Release Builds

Release builds SHOULD use the appropriate export configuration and templates.

Debug-only functionality SHOULD NOT unintentionally remain enabled in production builds.

## 18. Engine Documentation and Technical Decisions

### 18.1 Official Documentation

Developers SHOULD use the official Godot documentation corresponding to the project's engine version.

Documentation from another engine version SHOULD NOT be treated as authoritative without verifying compatibility.

### 18.2 Engine-Dependent Decisions

Significant engine configuration and technology decisions SHOULD be documented when they have long-term technical consequences.

Examples include:

- Selecting a rendering method.
- Selecting a physics approach.
- Introducing a major engine plugin.
- Adopting GDExtension.
- Changing resource-loading strategy.
- Upgrading the engine major version.

Significant architectural or technical decisions MUST follow the studio's ADR process.

### 18.3 Documentation Accuracy

Technical documentation SHOULD identify engine versions when behavior or configuration is version-dependent.

Developers SHOULD avoid documenting engine behavior based on assumptions or outdated references.

## 19. AI-Assisted Engine Usage Requirements

AI agents MUST follow these standards when modifying Godot projects.

Agents MUST:

- Inspect the project's configured Godot version.
- Use documentation compatible with that version.
- Respect existing project configuration.
- Follow established architecture and project structure standards.
- Verify engine APIs and methods before using them.
- Avoid introducing unsupported or deprecated functionality.
- Validate relevant scenes, scripts, and resources.
- Report engine warnings and errors discovered during implementation.
- Evaluate compatibility before changing project-wide engine settings.
- Request approval before major engine upgrades or disruptive configuration changes.

Agents MUST NOT:

- Assume all Godot versions expose identical APIs.
- Change engine versions without authorization.
- Modify project settings without understanding their effects.
- Ignore engine errors or warnings without justification.
- Introduce unnecessary plugins or native extensions.
- Claim runtime validation when only static inspection was performed.

When uncertain about version-specific engine behavior, agents SHOULD consult the official documentation for the configured version and clearly report unresolved uncertainty.

## 20. Engine Compliance Checklist

Before completing significant engine-related work, verify:

- [ ] The correct Godot version is being used.
- [ ] Project configuration changes are intentional.
- [ ] Engine APIs are compatible with the configured version.
- [ ] Rendering settings are appropriate.
- [ ] Display behavior is valid for supported configurations.
- [ ] Physics behavior is correct.
- [ ] Scene and node lifecycle responsibilities are respected.
- [ ] Resource loading and sharing are handled appropriately.
- [ ] Input behavior follows the project's input configuration.
- [ ] Animation and audio behavior are validated where affected.
- [ ] Engine errors and relevant warnings are resolved.
- [ ] Performance implications have been considered.
- [ ] Plugin and extension compatibility has been verified.
- [ ] Exported builds have been validated when applicable.
- [ ] Relevant technical documentation has been updated.

## 21. Exceptions

Exceptions MAY be introduced when project requirements justify alternative engine usage.

Exceptions SHOULD:

- Have a clear technical justification.
- Identify affected engine systems.
- Document compatibility and maintenance implications.
- Be reviewed by the project owner when they affect studio-wide standards.
- Be recorded through an ADR when they represent significant architectural decisions.

## 22. Related Documents

These standards SHOULD be used alongside:

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/ASSET_PIPELINE.md`
- `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md`
- `docs/02_technical_standards/adr/ADR_PROCESS.md`

Only documents that exist in the repository should be registered as active references in the documentation inventory.

## 23. Maintenance

These standards SHOULD be reviewed when:

- Godot releases introduce relevant engine changes.
- The studio changes its supported engine versions.
- New target platforms introduce technical requirements.
- Engine usage practices evolve.
- Repeated project experience reveals weaknesses in the standards.

Changes MUST preserve the document's purpose as a reusable studio-wide engine standard.