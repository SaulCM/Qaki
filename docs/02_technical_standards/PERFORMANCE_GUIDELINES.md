# Performance Guidelines

## 1. Purpose

This document establishes studio-wide guidelines for measuring, evaluating, optimizing, and maintaining the runtime performance of Godot projects.

Its purpose is to ensure that games deliver a responsive and stable player experience while using CPU, GPU, memory, storage, and other system resources efficiently.

These guidelines establish consistent practices for:

- Performance requirements and targets.
- Profiling and performance measurement.
- CPU optimization.
- GPU and rendering optimization.
- GDScript performance.
- Physics optimization.
- Memory management.
- Resource loading and unloading.
- Scene and node optimization.
- Asset optimization.
- Performance testing.
- Regression prevention.

The objective is to encourage evidence-based optimization without introducing unnecessary complexity or compromising maintainability.

## 2. Scope

These guidelines apply to all studio Godot projects and their runtime systems, including:

- Gameplay features.
- Rendering and visual effects.
- Physics and collision systems.
- Scene management.
- Resource loading.
- Audio.
- UI.
- AI and simulation.
- Data processing.
- Runtime integrations.
- Automated performance tests.
- Exported builds.

These guidelines primarily target Godot 4.x projects implemented in GDScript.

Specific optimization techniques MUST be compatible with the project's configured Godot version and target platforms.

## 3. Fundamental Performance Principles

### 3.1 Player Experience First

Performance optimization MUST support the intended player experience.

Developers SHOULD prioritize:

- Responsive input.
- Stable frame pacing.
- Smooth gameplay.
- Acceptable loading times.
- Consistent simulation behavior.
- Reasonable memory usage.
- Reliable operation on target hardware.

Performance improvements SHOULD NOT unnecessarily compromise gameplay quality, visual clarity, accessibility, or maintainability.

### 3.2 Measure Before Optimizing

Optimization decisions SHOULD be based on profiling, measurements, reproducible observations, or clearly identified constraints.

Developers MUST NOT assume that code is a performance bottleneck merely because it appears complex or inefficient.

### 3.3 Optimize the Actual Bottleneck

Optimization SHOULD target the resource or operation responsible for the observed performance problem.

Developers SHOULD distinguish between:

- CPU-bound performance.
- GPU-bound performance.
- Memory pressure.
- Storage or loading bottlenecks.
- Physics processing.
- Network latency, when applicable.
- Frame pacing and synchronization issues.

Optimizing an unrelated subsystem MUST NOT be considered a valid solution to a measured bottleneck.

### 3.4 Simplicity Over Premature Optimization

Code SHOULD remain readable and maintainable.

Developers SHOULD NOT introduce complex caching, pooling, multithreading, custom rendering systems, or low-level optimizations without a justified performance requirement.

### 3.5 Performance Is Continuous

Performance SHOULD be considered throughout development rather than addressed only before release.

Important performance risks SHOULD be identified during design, implementation, integration, and validation.

### 3.6 Target Hardware Matters

Performance MUST be evaluated against the project's intended platforms and hardware requirements.

A feature that performs well on a development machine MUST NOT automatically be considered performant on all target devices.

## 4. Performance Requirements and Budgets

### 4.1 Project-Specific Targets

Each game project SHOULD define measurable performance targets during pre-production or technical planning.

Targets SHOULD reflect:

- Supported platforms.
- Minimum hardware specifications.
- Intended frame rate.
- Display resolution.
- Expected scene complexity.
- Maximum concurrent entities.
- Expected resource usage.
- Loading and transition requirements.

These targets MUST be documented in the relevant project technical documentation.

This studio standard does not prescribe universal frame-rate, memory, loading-time, or rendering budgets because those requirements depend on the game and its target hardware.

### 4.2 Frame Rate Targets

Projects SHOULD define an intended frame rate for each supported platform.

Common targets include:

- 30 FPS.
- 60 FPS.
- 120 FPS or higher when justified.

The selected target SHOULD reflect gameplay requirements, display characteristics, and hardware capabilities.

### 4.3 Frame Time

Developers SHOULD evaluate frame time in addition to frames per second.

Frame time represents the duration required to produce a frame.

The approximate frame-time budgets are:

| Target frame rate | Frame-time budget |
|---|---:|
| 30 FPS | 33.33 ms |
| 60 FPS | 16.67 ms |
| 120 FPS | 8.33 ms |
| 144 FPS | 6.94 ms |
| 240 FPS | 4.17 ms |

A stable frame time is generally more important to perceived smoothness than occasional high FPS peaks.

### 4.4 Performance Budgets

Projects SHOULD establish budgets for relevant resources, such as:

- CPU frame time.
- GPU frame time.
- Memory consumption.
- Texture memory.
- Active physics objects.
- Draw calls.
- Active particles.
- Concurrent audio voices.
- Loading and initialization time.

Budgets SHOULD be allocated according to feature requirements and overall project constraints.

Feature budgets SHOULD leave room for integration overhead and unexpected runtime costs.

### 4.5 Performance Margins

Systems SHOULD NOT consistently operate at the maximum available hardware capacity.

Projects SHOULD maintain reasonable performance margins to accommodate:

- Scene complexity variation.
- Temporary resource spikes.
- Background operations.
- Runtime state changes.
- Hardware differences.
- Future content additions.

## 5. Profiling and Performance Measurement

### 5.1 Profiling Requirements

Profiling SHOULD be performed before and after significant optimizations.

Developers SHOULD use Godot's available diagnostic and profiling tools, including:

- Debugger Profiler.
- Visual Profiler.
- Monitors.
- Rendering diagnostics.
- Performance monitors.
- Remote scene inspection.
- Platform-specific profiling tools when necessary.

External profiling tools MAY be used when Godot's built-in tools do not provide sufficient information.

### 5.2 Reproducible Measurements

Performance measurements SHOULD use reproducible test conditions.

Measurements SHOULD identify:

- Godot version.
- Export configuration.
- Target hardware.
- Operating system and platform.
- Display resolution.
- Rendering method.
- Scene or gameplay scenario.
- Test duration.
- Relevant runtime settings.

Comparisons SHOULD use equivalent conditions.

### 5.3 Debug and Release Builds

Developers SHOULD distinguish between debug and release performance.

Debug builds may introduce additional overhead through:

- Debugging instrumentation.
- Runtime checks.
- Logging.
- Editor integration.
- Development-only features.

Final performance validation SHOULD include an exported build configured for the intended release environment.

### 5.4 Baseline Measurements

Important systems SHOULD have baseline performance measurements.

Baselines MAY include:

- Average frame time.
- Frame-time percentiles.
- Peak memory usage.
- Loading duration.
- Physics processing time.
- Rendering workload.

Baselines SHOULD be updated when meaningful architectural or content changes alter expected performance characteristics.

### 5.5 Average and Worst-Case Performance

Developers SHOULD evaluate both typical and demanding gameplay conditions.

Measurements SHOULD consider:

- Average behavior.
- Peak resource usage.
- Frame-time spikes.
- Worst-case scene complexity.
- Long-running sessions.
- Transitions between scenes.
- Resource-intensive gameplay moments.

Average FPS alone MUST NOT be used as the only measure of performance quality.

### 5.6 Profiling Evidence

Significant performance changes SHOULD include before-and-after measurements.

Performance reports SHOULD explain:

- The original problem.
- The identified bottleneck.
- The optimization applied.
- The observed improvement.
- Any relevant trade-offs.
- The validation conditions.

## 6. CPU Optimization

### 6.1 General CPU Efficiency

Developers SHOULD reduce unnecessary CPU work while preserving correct behavior.

Areas to evaluate include:

- Script execution.
- Physics calculations.
- AI processing.
- Scene-tree operations.
- Resource management.
- Animation updates.
- Data processing.
- Event handling.

### 6.2 Per-Frame Processing

Per-frame callbacks SHOULD perform only the work required for the current frame.

Developers SHOULD avoid:

- Expensive calculations repeated every frame.
- Repeated scene-tree searches.
- Unnecessary object creation.
- Repeated resource loading.
- Excessive string operations.
- Unnecessary collection transformations.
- Redundant state updates.

### 6.3 Conditional Processing

Processing SHOULD be disabled when a node or system does not require continuous updates.

Godot's processing controls MAY be used to disable:

- `_process()`.
- `_physics_process()`.
- Input processing.
- Other unnecessary callbacks.

Example:

```gdscript
func set_active(active: bool) -> void:
	set_process(active)
	set_physics_process(active)
```

### 6.4 Update Frequency

Not all systems require frame-by-frame updates.

Developers SHOULD consider whether an operation can be performed:

- Only when its input changes.
- Only when a relevant event occurs.
- At a lower update frequency.
- On demand.
- During initialization.

Update frequency SHOULD reflect gameplay and simulation requirements.

### 6.5 Data Structures and Algorithms

Developers SHOULD select data structures and algorithms appropriate to the expected workload.

Consider:

- Search complexity.
- Insertion and removal costs.
- Memory overhead.
- Iteration frequency.
- Data size.
- Access patterns.

More complex algorithms SHOULD only be introduced when their benefits justify their implementation and maintenance costs.

### 6.6 Scene-Tree Operations

Scene-tree operations SHOULD be minimized in performance-sensitive code.

Developers SHOULD avoid repeatedly performing expensive node lookups when stable references can be retained safely.

However, caching MUST NOT introduce invalid references or unnecessary lifecycle complexity.

### 6.7 String and Collection Operations

Frequent string construction, parsing, sorting, filtering, and collection copying SHOULD be evaluated when profiling identifies them as bottlenecks.

Developers SHOULD avoid unnecessary allocations and transformations in frequently executed code.

## 7. GDScript Performance

### 7.1 General Guidelines

GDScript implementations SHOULD prioritize clarity and correctness.

Developers SHOULD use profiling to identify expensive script operations rather than relying on assumptions about language performance.

### 7.2 Typed Variables

Static typing SHOULD be used according to:

`docs/02_technical_standards/GDSCRIPT_STANDARDS.md`

Typing improves code clarity and can help the engine optimize certain operations.

However, typing MUST NOT be treated as a substitute for profiling or algorithmic optimization.

### 7.3 Avoid Repeated Work

Developers SHOULD avoid repeated calculations when the result remains unchanged.

Caching MAY be used when:

- The calculation is expensive.
- The value is reused frequently.
- The invalidation conditions are clear.
- Memory overhead is acceptable.

### 7.4 Function Calls

Function calls SHOULD NOT be removed or consolidated solely based on assumptions about call overhead.

Developers SHOULD prioritize algorithmic efficiency and measured bottlenecks.

### 7.5 Dynamic Typing

Excessive dynamic typing and unnecessary Variant conversions SHOULD be avoided in performance-sensitive code when profiling demonstrates meaningful overhead.

Dynamic typing MAY remain appropriate when it improves flexibility and does not create a measurable problem.

### 7.6 GDScript and Native Extensions

GDScript SHOULD remain the default implementation language for project logic.

Native extensions or alternative technologies MUST NOT be introduced solely because they are assumed to be faster.

Such decisions SHOULD require:

- A demonstrated performance limitation.
- Evidence that the alternative addresses the bottleneck.
- Evaluation of integration complexity.
- Evaluation of platform compatibility.
- Human approval.
- An ADR when the decision has significant architectural consequences.

## 8. GPU and Rendering Optimization

### 8.1 Rendering Bottlenecks

Rendering optimization SHOULD be based on GPU profiling and rendering diagnostics.

Developers SHOULD distinguish between:

- Geometry processing.
- Draw-call overhead.
- Shader complexity.
- Texture sampling.
- Overdraw.
- Lighting.
- Shadows.
- Post-processing.
- Transparency.
- Rendering resolution.

### 8.2 Draw Calls

Projects SHOULD avoid unnecessary draw-call overhead.

Developers MAY use appropriate engine features such as:

- MultiMeshInstance2D.
- MultiMeshInstance3D.
- Batching where supported.
- Resource reuse.
- Appropriate scene organization.

Optimization SHOULD preserve correct rendering and culling behavior.

### 8.3 Visibility and Culling

Objects that do not need to be rendered SHOULD be excluded from unnecessary rendering work.

Developers SHOULD evaluate:

- Visibility ranges.
- Occlusion culling where supported.
- Viewport visibility.
- Distance-based visibility.
- Level-of-detail techniques.
- Appropriate scene partitioning.

Culling SHOULD NOT introduce distracting visual popping or remove content that players need to see.

### 8.4 Level of Detail

Level-of-detail techniques MAY be used when scene complexity and viewing distance justify them.

LOD systems SHOULD:

- Reduce unnecessary rendering complexity.
- Preserve visual readability.
- Avoid excessive transition artifacts.
- Use appropriate distance thresholds.
- Be validated on target hardware.

### 8.5 Shaders

Shaders SHOULD be designed with rendering cost in mind.

Developers SHOULD avoid unnecessary:

- Expensive per-pixel calculations.
- Texture samples.
- Branching.
- Complex lighting calculations.
- Repeated mathematical operations.
- Screen-space effects.

Shader complexity SHOULD be evaluated on the intended target hardware.

### 8.6 Transparency and Overdraw

Excessive transparency and overlapping visual effects SHOULD be avoided when they create significant rendering costs.

Developers SHOULD evaluate:

- Large transparent surfaces.
- Particle overlap.
- UI layering.
- Alpha blending.
- Transparent materials.
- Screen-space effects.

### 8.7 Lighting and Shadows

Lighting and shadow complexity SHOULD reflect the visual requirements of the game.

Developers SHOULD evaluate:

- Number of active lights.
- Shadow-casting lights.
- Shadow resolution.
- Shadow distance.
- Light range.
- Dynamic versus baked lighting where applicable.

Expensive lighting configurations SHOULD be justified by their visual contribution.

### 8.8 Resolution and Viewports

Rendering resolution SHOULD be selected according to the project's visual requirements and performance targets.

Developers MAY use resolution scaling or viewport techniques when appropriate.

Resolution changes SHOULD be tested for:

- Visual clarity.
- UI readability.
- Aspect-ratio behavior.
- Rendering performance.
- Platform compatibility.

### 8.9 Particle Systems

Particle systems SHOULD use appropriate limits and emission settings.

Developers SHOULD evaluate:

- Maximum particle count.
- Particle lifetime.
- Simulation cost.
- Transparency.
- Collision behavior.
- Shader complexity.

Particle systems SHOULD be disabled or reduced when they are no longer needed.

## 9. Physics Optimization

### 9.1 Physics Workload

Physics complexity SHOULD be proportional to gameplay requirements.

Developers SHOULD evaluate:

- Active rigid bodies.
- Character bodies.
- Area nodes.
- Collision shapes.
- Physics queries.
- Collision layer configuration.
- Collision mask configuration.
- Continuous collision detection.
- Physics processing frequency.

### 9.2 Collision Shapes

Collision shapes SHOULD be as simple as practical while maintaining gameplay correctness.

Developers SHOULD avoid unnecessarily complex collision geometry.

### 9.3 Collision Layers and Masks

Collision layers and masks SHOULD be configured to prevent irrelevant collision checks.

Systems SHOULD only interact with the collision categories they actually require.

### 9.4 Physics Queries

Physics queries SHOULD be performed only when necessary.

Developers SHOULD avoid redundant queries within the same physics frame when results can safely be reused.

### 9.5 Physics Processing

Physics-related logic MUST follow Godot's physics execution requirements.

Developers MUST NOT move physics-related operations into inappropriate callbacks solely to improve apparent performance.

### 9.6 Physics Object Management

Inactive physics objects SHOULD be managed appropriately.

Depending on gameplay requirements, developers MAY:

- Disable collision.
- Disable processing.
- Remove inactive objects from the scene.
- Use simpler collision representations.
- Reduce unnecessary simulation.

## 10. Memory Management

### 10.1 Memory Awareness

Projects SHOULD monitor memory usage throughout development.

Developers SHOULD consider:

- Object allocation.
- Resource retention.
- Texture memory.
- Audio memory.
- Scene instances.
- Large collections.
- Cached data.
- Temporary allocations.

### 10.2 Resource Reuse

Reusable Resources SHOULD be shared when their data is intended to be shared and remains appropriately immutable.

Developers MUST understand the implications of shared mutable Resources.

### 10.3 Object Lifetime

Objects SHOULD have clear ownership and lifecycle expectations.

Developers SHOULD avoid retaining references to objects that are no longer needed.

Node destruction SHOULD use appropriate Godot lifecycle mechanisms.

### 10.4 Object Pooling

Object pooling MAY be used when:

- Objects are created and destroyed frequently.
- Allocation overhead is measurable.
- Object reuse produces a meaningful improvement.
- Pool lifecycle complexity is manageable.

Pooling SHOULD NOT be introduced by default.

Pooled objects MUST be reset to a valid initial state before reuse.

### 10.5 Memory Leaks

Developers SHOULD investigate:

- Unreleased references.
- Long-lived signal connections.
- Unbounded collections.
- Unnecessary Resource retention.
- Repeated scene instantiation.
- Persistent caches without limits.

### 10.6 Memory Budgets

Projects SHOULD define memory budgets appropriate to their target platforms.

Peak memory usage SHOULD be evaluated during demanding gameplay and scene transitions.

## 11. Resource Loading and Scene Management

### 11.1 Resource Loading Strategy

Resource loading SHOULD balance responsiveness, memory usage, and implementation complexity.

Developers SHOULD distinguish between:

- Resources required at startup.
- Resources required immediately.
- Resources that can be loaded on demand.
- Resources that can be loaded asynchronously.
- Resources that can be released after use.

### 11.2 Synchronous Loading

Synchronous loading MAY be used for small resources or situations where blocking execution is acceptable.

Large or expensive resource loading SHOULD be evaluated for its impact on frame time.

### 11.3 Asynchronous Loading

Godot's threaded resource loading capabilities MAY be used when loading large resources would otherwise cause noticeable interruptions.

Asynchronous loading SHOULD:

- Provide appropriate loading feedback.
- Handle loading failures.
- Validate completion.
- Respect object and scene lifecycles.
- Avoid unnecessary concurrent loading.

### 11.4 Resource Caching

Caching SHOULD be used when it reduces repeated loading or processing costs.

Developers SHOULD understand Godot's resource caching behavior and avoid building redundant custom caches.

Caches MUST have appropriate ownership and invalidation rules.

### 11.5 Scene Transitions

Scene transitions SHOULD avoid unnecessary loading spikes and memory pressure.

Developers SHOULD consider:

- Loading the next scene.
- Releasing unused scene resources.
- Transition effects.
- Persistent services.
- Temporary resource retention.
- Initialization workload.

### 11.6 Resource Cleanup

Resources SHOULD be released when they are no longer required and no longer referenced.

Cleanup logic SHOULD respect Godot's resource ownership and reference-counting behavior.

## 12. Asset Performance

### 12.1 Asset Optimization

Assets SHOULD be optimized according to their actual usage and target platform.

Developers SHOULD evaluate:

- Texture dimensions.
- Texture formats.
- Compression.
- Audio formats.
- Mesh complexity.
- Animation data.
- Material complexity.
- Import settings.

### 12.2 Texture Memory

Texture dimensions and formats SHOULD be appropriate for their intended visual contribution.

Developers SHOULD avoid unnecessarily large textures.

Texture optimization MUST preserve acceptable visual quality.

### 12.3 Audio

Audio resources SHOULD use formats and import settings appropriate to their purpose.

Developers SHOULD consider:

- Streaming versus loading into memory.
- Audio compression.
- Sample rate.
- Bit depth.
- Number of simultaneous voices.
- Audio bus effects.

Long audio assets SHOULD be evaluated for streaming where appropriate.

### 12.4 Meshes and Models

3D assets SHOULD use appropriate geometric complexity.

Developers SHOULD consider:

- Polygon count.
- LOD.
- Mesh reuse.
- Material count.
- Skeleton complexity.
- Animation complexity.
- Visibility and culling.

### 12.5 Asset Pipeline

Asset import and optimization MUST follow:

`docs/02_technical_standards/ASSET_PIPELINE.md`

## 13. UI and Audio Performance

### 13.1 UI Processing

UI elements SHOULD avoid unnecessary per-frame updates.

Developers SHOULD update interface elements in response to relevant state changes whenever practical.

### 13.2 UI Complexity

Complex UI scenes SHOULD be evaluated for:

- Excessive node counts.
- Repeated layout calculations.
- Unnecessary animations.
- Frequent text updates.
- Expensive visual effects.
- Large numbers of active controls.

### 13.3 UI Visibility

Inactive or hidden UI components SHOULD avoid unnecessary processing where appropriate.

Developers SHOULD ensure that visibility and processing behavior remain correct when UI elements are reopened.

### 13.4 Audio Performance

Audio systems SHOULD manage active playback and processing efficiently.

Developers SHOULD avoid:

- Unnecessary simultaneous audio playback.
- Unused audio effects.
- Excessive audio bus processing.
- Repeated loading of identical audio resources.

Audio quality MUST remain appropriate for the intended experience.

## 14. AI, Simulation, and Large-Scale Systems

### 14.1 AI Processing

AI systems SHOULD avoid unnecessary full-frequency updates.

Developers MAY consider:

- Event-driven state changes.
- Reduced update frequency.
- Distance-based update rates.
- Simplified distant behavior.
- Appropriate navigation update frequency.
- Efficient perception queries.

Optimization MUST preserve required gameplay behavior.

### 14.2 Entity Management

Large numbers of entities SHOULD be evaluated for their combined processing and memory costs.

Developers SHOULD consider:

- Active versus inactive entities.
- Visibility.
- Update frequency.
- Physics participation.
- AI complexity.
- Resource usage.

### 14.3 Navigation

Navigation operations SHOULD be evaluated when they become a measurable bottleneck.

Developers SHOULD avoid unnecessary navigation queries or repeated path calculations.

### 14.4 Simulation Scaling

Systems simulating many objects SHOULD use appropriate update strategies.

Possible approaches include:

- Event-driven updates.
- Time slicing.
- Reduced update frequency.
- Spatial partitioning.
- Simplified simulation for distant objects.

These techniques SHOULD be introduced only when justified by workload and gameplay requirements.

## 15. Multithreading and Asynchronous Processing

### 15.1 General Principles

Multithreading MAY be used when independent workloads can be processed safely and meaningfully in parallel.

Developers MUST consider:

- Thread safety.
- Shared data ownership.
- Synchronization.
- Main-thread restrictions.
- Resource access.
- Task cancellation.
- Object lifetime.

### 15.2 Main Thread Restrictions

Godot scene-tree operations and many engine APIs have thread-safety restrictions.

Developers MUST follow the engine's documented thread-safety requirements.

Scene-tree modifications SHOULD be performed on the appropriate thread.

### 15.3 Worker Tasks

Worker threads SHOULD process independent calculations or data operations when practical.

Developers SHOULD avoid unnecessary thread creation and excessive synchronization.

### 15.4 Thread Safety

Shared mutable data MUST have a clear synchronization strategy.

Developers MUST NOT assume that GDScript objects, Resources, or scene nodes are safe for concurrent modification.

### 15.5 Complexity

Multithreading SHOULD NOT be introduced merely to appear more performant.

The performance benefit MUST justify the additional debugging, testing, and maintenance complexity.

## 16. Performance Testing and Validation

### 16.1 Performance Testing

Important systems SHOULD receive performance validation when their workload or complexity could affect runtime targets.

Testing SHOULD reflect realistic gameplay scenarios.

### 16.2 Test Scenarios

Projects SHOULD identify representative performance scenarios, including:

- Normal gameplay.
- High entity counts.
- Complex scenes.
- Combat or interaction peaks.
- Large UI screens.
- Resource-intensive effects.
- Scene transitions.
- Long-running sessions.
- Worst-case gameplay conditions.

### 16.3 Performance Regression Testing

Important performance baselines SHOULD be checked after changes to performance-sensitive systems.

Performance regressions SHOULD be investigated before integration when they violate established project budgets.

### 16.4 Automated Performance Tests

Automated performance tests MAY be introduced for stable, measurable workloads.

Automated tests SHOULD:

- Use controlled scenarios.
- Define meaningful thresholds.
- Avoid unreliable timing assumptions.
- Distinguish environmental noise from genuine regressions.
- Record relevant measurements.

Automated performance checks SHOULD NOT create false confidence when the actual target platform is not represented.

### 16.5 Platform Validation

Performance SHOULD be validated on representative target hardware.

Testing only on development hardware MUST NOT be considered sufficient when target devices have materially different capabilities.

### 16.6 Long-Session Testing

Projects SHOULD evaluate performance over extended sessions when memory growth, resource retention, or long-running simulation could create problems.

## 17. Optimization Workflow

Performance optimization SHOULD follow a structured, evidence-based process.

### Step 1: Identify the Problem

Describe the observed performance issue.

Examples:

- Unstable frame rate.
- Long loading times.
- Excessive memory consumption.
- Frame-time spikes.
- Physics slowdown.

### Step 2: Establish a Baseline

Measure the behavior under reproducible conditions.

Record relevant hardware, build configuration, and test scenario.

### Step 3: Profile

Use appropriate tools to identify the bottleneck.

Determine whether the issue is related to CPU, GPU, memory, loading, physics, or another subsystem.

### Step 4: Identify the Cause

Inspect the responsible implementation or resource.

Avoid changing unrelated systems.

### Step 5: Select an Optimization

Choose the simplest solution that addresses the measured problem.

Consider correctness, maintainability, platform compatibility, and trade-offs.

### Step 6: Implement Incrementally

Apply focused changes.

Avoid combining unrelated optimizations into one change when doing so makes results difficult to evaluate.

### Step 7: Validate

Repeat the original measurements.

Confirm that:

- The intended improvement occurred.
- No functional behavior was broken.
- No new performance bottleneck was introduced.
- Memory usage remains acceptable.
- Target platform requirements are respected.

### Step 8: Document

Record significant optimizations and their measured outcomes.

### Step 9: Monitor

Continue monitoring the affected system as new features and content are introduced.

## 18. Performance Documentation

Significant performance requirements, bottlenecks, and optimizations SHOULD be documented.

Documentation MAY include:

- Performance targets.
- Hardware assumptions.
- Resource budgets.
- Profiling results.
- Known bottlenecks.
- Optimization decisions.
- Performance trade-offs.
- Validation scenarios.
- Outstanding performance risks.

Project-specific targets and measurements MUST be stored in the relevant game repository.

Studio-wide guidelines SHOULD NOT contain project-specific benchmark results.

## 19. AI-Assisted Performance Requirements

AI agents MUST follow these guidelines when implementing or optimizing performance-sensitive systems.

Agents MUST:

- Inspect the relevant implementation before proposing optimizations.
- Identify the actual performance concern.
- Prefer profiling evidence over assumptions.
- Preserve intended functionality.
- Consider CPU, GPU, memory, and loading implications.
- Respect Godot's lifecycle and thread-safety requirements.
- Evaluate the impact of caching and object pooling.
- Validate changes using appropriate measurements.
- Report performance results accurately.
- Identify trade-offs and remaining limitations.

Agents MUST NOT:

- Claim performance improvements without supporting measurements.
- Introduce unnecessary complexity for hypothetical optimization.
- Add multithreading without evaluating thread safety.
- Introduce native extensions without owner approval.
- Remove functionality merely to improve benchmark results unless explicitly authorized.
- Treat average FPS as the only performance metric.
- Ignore target hardware constraints.

Agents SHOULD request owner approval before introducing major performance architecture changes, custom rendering infrastructure, or platform-specific optimization systems.

## 20. Performance Review Checklist

Before completing performance-sensitive work, verify:

- [ ] Performance requirements are understood.
- [ ] Relevant target hardware is considered.
- [ ] A measurable baseline exists when appropriate.
- [ ] The actual bottleneck has been identified.
- [ ] The optimization addresses the identified cause.
- [ ] CPU workload has been considered.
- [ ] GPU and rendering workload has been considered.
- [ ] Memory usage has been considered.
- [ ] Resource loading behavior has been considered.
- [ ] Physics workload has been considered.
- [ ] Asset complexity has been considered.
- [ ] Per-frame processing is justified.
- [ ] Caching and pooling have clear lifecycle rules.
- [ ] Multithreading follows engine restrictions.
- [ ] Gameplay correctness is preserved.
- [ ] Performance has been remeasured.
- [ ] Target platform requirements are satisfied.
- [ ] No unexplained performance regressions remain.
- [ ] Significant results and trade-offs are documented.

## 21. Exceptions

Exceptions MAY be introduced when project-specific requirements justify alternative performance practices.

Exceptions SHOULD:

- Have a clear technical justification.
- Identify the affected systems and platforms.
- Explain expected performance benefits.
- Document relevant risks and trade-offs.
- Include validation evidence when practical.
- Receive project owner approval when they introduce significant architectural changes.

## 22. Related Documents

These guidelines SHOULD be used alongside:

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/ENGINE_STANDARDS.md`
- `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`
- `docs/02_technical_standards/ASSET_PIPELINE.md`
- `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md`
- `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md`
- `docs/02_technical_standards/adr/README.md`
- Applicable documents in `docs/05_qa_standards/`

Only documents that physically exist in the repository SHOULD be registered as active references in the documentation inventory.

## 23. Maintenance

These guidelines SHOULD be reviewed when:

- Godot introduces significant performance-related changes.
- The studio adopts new profiling or optimization tools.
- Target platform requirements evolve.
- Repeated performance issues reveal weaknesses in current practices.
- New project experience identifies more effective optimization approaches.

Changes MUST preserve the document's purpose as a reusable studio-wide performance standard.