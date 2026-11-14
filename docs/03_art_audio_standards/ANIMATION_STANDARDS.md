# Animation Standards

## 1. Purpose

This document establishes studio-wide standards for creating, implementing, organizing, and maintaining animations in Godot projects.

Its purpose is to ensure that animations:

- Communicate gameplay information clearly.
- Support the intended player experience.
- Maintain visual consistency.
- Provide responsive feedback.
- Integrate correctly with gameplay systems.
- Remain performant and maintainable.
- Follow consistent technical and organizational practices.

These standards apply to both artistic animation production and technical animation implementation.

## 2. Scope

These standards apply to animations used in studio game projects, including:

- 2D character animation.
- 3D character animation.
- Environmental animation.
- Object and prop animation.
- Gameplay and combat animation.
- UI animation.
- Visual effects animation.
- Cutscenes and scripted sequences.
- Procedural animation.
- Skeletal and sprite-based animation.
- Animation-driven transitions and interactions.

Projects MAY establish additional art direction, animation style, technical constraints, and production requirements.

Such project-specific decisions SHOULD be documented in the respective game repository.

## 3. Animation Principles

### 3.1 Purposeful Animation

Every animation SHOULD serve a clear purpose.

Animations MAY:

- Communicate character actions.
- Provide gameplay feedback.
- Establish personality.
- Convey weight and physicality.
- Improve visual readability.
- Support atmosphere.
- Communicate state changes.
- Guide player attention.
- Enhance emotional expression.

Animations SHOULD NOT exist solely to add unnecessary visual activity.

### 3.2 Gameplay Readability

Gameplay animations MUST communicate important actions and states clearly.

Players SHOULD be able to recognize relevant visual information without relying exclusively on text or audio.

Examples include:

- Attack preparation.
- Attack execution.
- Damage reception.
- Recovery.
- Movement state.
- Interaction availability.
- Ability activation.
- Death or defeat.

### 3.3 Responsiveness

Player-controlled actions SHOULD provide timely visual feedback.

Animation transitions MUST NOT introduce unnecessary input delays or make gameplay controls feel unresponsive.

When gameplay requires immediate feedback, appropriate visual responses SHOULD take priority over elaborate animation transitions.

### 3.4 Consistency

Animations SHOULD maintain consistent visual language across related characters, objects, interfaces, and gameplay systems.

Consistency SHOULD consider:

- Timing.
- Movement style.
- Acceleration and deceleration.
- Weight.
- Anticipation.
- Follow-through.
- Impact.
- Exaggeration.
- Visual effects.

### 3.5 Intentional Motion

Motion SHOULD communicate meaningful changes rather than create visual noise.

Developers and artists SHOULD avoid excessive movement, unnecessary secondary animation, and distracting effects.

### 3.6 Performance Awareness

Animation quality MUST be balanced against runtime performance.

Animation systems SHOULD use appropriate techniques for the number of animated objects, target platforms, and expected gameplay conditions.

## 4. Animation Design Fundamentals

### 4.1 Timing

Timing determines how long an action takes and how its motion is perceived.

Animation timing SHOULD support:

- Character weight.
- Action intensity.
- Gameplay responsiveness.
- Emotional expression.
- Visual readability.
- Interaction feedback.

Critical gameplay timing MUST be coordinated with the underlying gameplay logic.

### 4.2 Spacing

Spacing describes how an animated object moves between positions over time.

Animation SHOULD use appropriate spacing to communicate:

- Acceleration.
- Deceleration.
- Impact.
- Weight.
- Smooth movement.
- Sudden changes in direction.

### 4.3 Anticipation

Anticipation prepares the player to recognize an upcoming action.

Examples include:

- A character preparing to attack.
- An object compressing before launching.
- A character shifting weight before jumping.
- A UI element indicating an imminent transition.

Anticipation SHOULD improve readability without unnecessarily delaying gameplay actions.

### 4.4 Follow-Through and Overlapping Action

Follow-through and overlapping motion SHOULD be used when they improve the perception of weight, momentum, and natural movement.

Examples include:

- Clothing movement.
- Hair movement.
- Weapon motion.
- Secondary character movement.
- Environmental reactions.

Secondary animation MUST NOT obscure critical gameplay information.

### 4.5 Exaggeration

Exaggeration MAY be used to strengthen readability, personality, or emotional impact.

Its application SHOULD remain consistent with the project's visual identity.

### 4.6 Ease and Interpolation

Animation curves SHOULD reflect the intended motion.

Common approaches include:

- Linear interpolation.
- Ease-in.
- Ease-out.
- Ease-in-out.
- Custom curves.

Linear interpolation SHOULD be used when constant movement is intended.

Nonlinear interpolation SHOULD be used when acceleration or deceleration improves the result.

### 4.7 Holds and Pauses

Intentional pauses MAY improve readability, emphasize impact, or establish character expression.

Holds SHOULD be used deliberately rather than introduced accidentally through poorly configured animation timing.

## 5. Animation Style and Consistency

### 5.1 Project Art Direction

Each project SHOULD define an animation direction appropriate to its visual identity.

This MAY include:

- Realistic animation.
- Stylized animation.
- Exaggerated animation.
- Pixel-art animation.
- Hand-drawn animation.
- Low-frame-rate animation.
- Hybrid animation styles.

These standards MUST NOT impose one universal animation style across all studio projects.

### 5.2 Character Consistency

Characters SHOULD maintain consistent proportions, movement characteristics, and animation language across their actions.

Changes in animation style SHOULD be intentional.

### 5.3 Animation Quality

Animations SHOULD be evaluated for:

- Silhouette clarity.
- Pose readability.
- Timing.
- Spacing.
- Weight.
- Continuity.
- Visual appeal.
- Gameplay relevance.
- Technical correctness.

### 5.4 Animation Reuse

Reusable animations MAY be shared when their requirements and visual style are compatible.

Artists and developers SHOULD avoid forcing identical animations onto characters with significantly different proportions, movement characteristics, or gameplay responsibilities.

## 6. Animation Types and Requirements

### 6.1 Character Animation

Character animation SHOULD communicate movement, personality, physicality, and gameplay state.

Depending on the project, character animation MAY include:

- Idle.
- Walking.
- Running.
- Jumping.
- Falling.
- Landing.
- Turning.
- Attacking.
- Blocking.
- Dodging.
- Taking damage.
- Interacting.
- Climbing.
- Swimming.
- Death.
- Victory.

Not every character requires every animation.

Animation requirements SHOULD be defined according to the character's gameplay responsibilities.

### 6.2 Environment Animation

Environmental animation MAY include:

- Moving objects.
- Vegetation.
- Water.
- Machinery.
- Weather effects.
- Destructible objects.
- Environmental hazards.
- Ambient movement.

Environmental animations SHOULD support atmosphere and world readability without distracting from gameplay.

### 6.3 Object Animation

Interactive and animated objects SHOULD communicate their current state.

Examples include:

- Doors opening and closing.
- Containers unlocking.
- Switches activating.
- Machinery operating.
- Collectibles appearing.
- Objects breaking.

Important state transitions SHOULD provide clear visual feedback.

### 6.4 UI Animation

UI animations SHOULD improve feedback, hierarchy, and interaction clarity.

Examples include:

- Panel transitions.
- Button feedback.
- Menu navigation.
- Notifications.
- Loading indicators.
- Inventory interactions.
- Dialog transitions.

UI animations SHOULD remain brief and purposeful.

They MUST NOT make navigation unnecessarily slow or prevent important interactions without justification.

Refer to the project's UI/UX design guidelines for additional interaction and presentation requirements.

### 6.5 Visual Effects Animation

Animated effects MAY communicate:

- Impacts.
- Explosions.
- Damage.
- Magic or abilities.
- Environmental events.
- Interactions.
- Status changes.

Effects SHOULD communicate their intended meaning without obscuring important gameplay information.

### 6.6 Cinematic Animation

Cutscenes and scripted sequences MAY use more elaborate animation techniques.

Cinematic animation SHOULD maintain continuity with the game's visual identity.

Projects SHOULD define how cinematic sequences interact with:

- Player input.
- Gameplay state.
- Camera control.
- Audio.
- Scene transitions.
- Skipping and interruption.

## 7. Gameplay and Animation Integration

### 7.1 Gameplay State Ownership

Gameplay systems MUST remain authoritative for gameplay state.

Animation systems SHOULD represent and communicate gameplay state rather than independently determine critical gameplay outcomes.

For example:

- Health systems determine whether a character is alive.
- Combat systems determine whether an attack is valid.
- Movement systems determine movement state.
- Animation systems visually represent those states.

### 7.2 Animation State Management

Complex animation behavior SHOULD use an explicit state model.

Possible states include:

- Idle.
- Moving.
- Attacking.
- Taking damage.
- Stunned.
- Interacting.
- Dead.

State transitions SHOULD be understandable and consistent with gameplay rules.

### 7.3 Animation Transitions

Transitions SHOULD avoid unintended visual discontinuities.

Transition configuration SHOULD consider:

- Source and destination states.
- Transition duration.
- Interruption behavior.
- Priority.
- Blending.
- Gameplay responsiveness.

### 7.4 Animation-Driven Gameplay

Animation MAY trigger gameplay events when the design requires precise synchronization.

Examples include:

- Attack impact frames.
- Footstep events.
- Interaction completion.
- Projectile release.
- Sound synchronization.

However, critical gameplay state SHOULD NOT depend exclusively on animation playback completing successfully.

Gameplay logic MUST handle interruption, cancellation, and unexpected animation termination where relevant.

### 7.5 Animation Events

Animation events SHOULD have clear ownership and responsibilities.

Developers SHOULD use appropriate signals, method tracks, or explicit gameplay coordination mechanisms.

Animation events MUST NOT introduce hidden dependencies between unrelated systems.

### 7.6 Interruptions

Gameplay animations SHOULD define how they respond to relevant interruptions.

Examples include:

- Taking damage during an attack.
- Canceling an interaction.
- Changing movement direction.
- Entering a disabled state.
- Transitioning to death.
- Changing scenes.

Interruption behavior SHOULD be consistent with gameplay design.

### 7.7 Animation and Physics

Animation MUST NOT unintentionally conflict with physics-driven movement.

Projects SHOULD clearly define which system controls:

- Position.
- Rotation.
- Velocity.
- Collision.
- Root motion.
- Visual deformation.

Physics and animation responsibilities MUST remain explicit.

## 8. 2D Animation Standards

### 8.1 Sprite Animation

2D sprite animation SHOULD maintain consistent:

- Sprite dimensions where appropriate.
- Character alignment.
- Pivot points.
- Visual proportions.
- Frame composition.
- Animation direction.

### 8.2 Sprite Sheets

Sprite sheets SHOULD use consistent frame dimensions and organization when the chosen workflow requires them.

Sprite sheets SHOULD avoid:

- Unnecessary transparent padding.
- Inconsistent frame alignment.
- Unintended visual cropping.
- Ambiguous frame ordering.

### 8.3 Animation Frames

Frame counts SHOULD reflect the project's intended animation style and performance requirements.

Projects MAY use different frame rates for different animation categories.

The selected approach SHOULD remain consistent within related animation sets.

### 8.4 Pivot and Alignment

Sprite pivot points SHOULD remain consistent across frames unless the animation intentionally changes the apparent point of rotation.

Incorrect pivot placement SHOULD be corrected at the source rather than compensated for through excessive runtime adjustments.

### 8.5 Animated Sprites

Godot's `AnimatedSprite2D` and `SpriteFrames` MAY be used for straightforward frame-based animation.

`AnimationPlayer` MAY be used when animation requires coordinated property changes, multiple nodes, or timeline-based behavior.

The selected approach SHOULD match the complexity of the animation.

## 9. 3D Animation Standards

### 9.1 Rigging

Character rigs SHOULD be designed to support the required animation set without unnecessary complexity.

Rig structures SHOULD maintain consistent naming and hierarchy conventions.

### 9.2 Skeletons

Skeletons SHOULD use clear bone names and logical hierarchies.

Bone naming and structure SHOULD remain consistent across related characters when animation reuse is required.

### 9.3 Skinning

Skinning SHOULD avoid visible deformation problems during expected gameplay movement.

Validation SHOULD include:

- Extreme poses.
- Joint deformation.
- Intersections.
- Weight distribution.
- Important silhouette changes.

### 9.4 Animation Clips

Animation clips SHOULD have descriptive names and clearly defined purposes.

Examples include:

- `idle`
- `walk`
- `run`
- `jump`
- `attack`
- `hit_reaction`
- `death`

Actual resource naming MUST follow the applicable naming conventions.

### 9.5 Root Motion

Root motion MAY be used when the project requires animation-driven displacement.

Projects MUST define how root motion interacts with:

- Character movement.
- Physics.
- Collision.
- Navigation.
- Gameplay control.
- Network synchronization, if applicable.

Root motion SHOULD NOT be introduced when it adds unnecessary complexity.

### 9.6 Animation Retargeting

Animation retargeting MAY be used when source and target rigs are compatible.

Retargeted animations MUST be validated for:

- Bone alignment.
- Joint orientation.
- Motion quality.
- Foot placement.
- Body proportions.
- Unintended deformation.

### 9.7 Animation Blending

Blending SHOULD be used when transitions between animation states require smooth visual continuity.

Blend configuration SHOULD avoid unintended motion, pose distortion, or delayed gameplay feedback.

## 10. Animation Implementation in Godot

### 10.1 AnimationPlayer

`AnimationPlayer` SHOULD be used for timeline-based animation involving one or more properties or nodes.

Appropriate uses include:

- Character animation.
- UI transitions.
- Object animation.
- Environmental animation.
- Coordinated property changes.

### 10.2 AnimationTree

`AnimationTree` MAY be used when a project requires complex animation state management, blending, or layered animation behavior.

It SHOULD NOT be introduced for simple animation requirements that `AnimationPlayer` or `AnimatedSprite2D` can handle adequately.

### 10.3 AnimatedSprite2D

`AnimatedSprite2D` SHOULD be considered for straightforward 2D frame-based animation using `SpriteFrames`.

### 10.4 Tween

Godot's `Tween` system MAY be used for temporary property interpolation.

Appropriate uses include:

- UI transitions.
- Simple object movement.
- Feedback effects.
- Temporary visual changes.
- Procedural presentation.

Tweens SHOULD NOT replace a structured animation system when the behavior requires complex reusable animation states.

### 10.5 Animation Resources

Animation resources SHOULD be organized and referenced according to the project's asset pipeline and Resource management standards.

### 10.6 Script-Controlled Animation

GDScript MAY control animation playback and state transitions.

Scripts SHOULD coordinate animation rather than reproduce complex animation timelines through large collections of manually updated properties.

### 10.7 Animation Naming

Animation names MUST follow the project's naming conventions.

Names SHOULD describe the action or state clearly.

### 10.8 Engine Compatibility

Animation implementation MUST use APIs and capabilities supported by the project's selected Godot version.

Refer to `docs/02_technical_standards/engine_standards.md`.

## 11. Animation Organization and Assets

### 11.1 Feature Ownership

Animation assets MUST follow the feature-oriented project structure.

Animations specific to a feature SHOULD be stored within that feature's asset organization.

Reusable assets MAY be placed in `shared/` when they are genuinely independent of individual features.

### 11.2 Source Files

Original animation source files SHOULD be preserved when the production workflow uses external authoring tools.

Exported runtime assets SHOULD remain distinguishable from editable source files when necessary.

### 11.3 Naming

Animation files and resources MUST follow:

`docs/00_studio_standards/naming_conventions.md`

Names SHOULD communicate:

- The associated character or object.
- The action or animation purpose.
- Relevant variants when necessary.

### 11.4 Animation Metadata

Important animation assets SHOULD have sufficient metadata to identify:

- Intended use.
- Associated character or object.
- Required rig or sprite configuration.
- Animation timing.
- Looping behavior.
- Relevant technical constraints.

### 11.5 Asset Import

Animation assets MUST follow the applicable import and resource management practices.

Refer to:

- `docs/02_technical_standards/asset_pipeline.md`
- `docs/02_technical_standards/resource_management.md`

## 12. Looping and Playback

### 12.1 Looping Animations

Animations SHOULD loop only when continuous repetition is intended.

Examples include:

- Idle.
- Walking.
- Running.
- Environmental ambient motion.

Loop boundaries SHOULD avoid visible jumps, timing discontinuities, or unintended changes in pose.

### 12.2 Non-Looping Animations

One-shot animations SHOULD define their completion behavior.

Examples include:

- Attacks.
- Interactions.
- Impact reactions.
- Explosions.
- Death sequences.

### 12.3 Playback Control

Animation playback SHOULD have a clear owner.

Multiple unrelated systems SHOULD NOT compete to control the same animation player without an explicit coordination mechanism.

### 12.4 Playback Speed

Animation speed MAY be adjusted when gameplay or design requires it.

Speed changes SHOULD preserve visual quality and gameplay readability.

### 12.5 Animation Completion

Systems depending on animation completion SHOULD handle cases where playback is interrupted, stopped, or replaced.

Critical gameplay transitions MUST NOT rely on an animation finishing under every possible condition.

## 13. Accessibility and Player Comfort

### 13.1 Motion Sensitivity

Projects SHOULD consider players who may experience discomfort from excessive motion or visual effects.

Depending on the project, accessibility options MAY include:

- Reduced camera shake.
- Reduced screen flashes.
- Reduced motion intensity.
- Simplified UI transitions.
- Reduced visual effects.
- Alternative feedback presentation.

### 13.2 Flashing Effects

Flashing animations SHOULD be used carefully.

Rapid or intense flashes MUST be evaluated for accessibility and player comfort.

### 13.3 Camera Motion

Camera animation and shake SHOULD be intentional and proportionate.

Important gameplay information SHOULD remain readable during camera movement.

### 13.4 Animation Duration

UI and interaction animations SHOULD respect player time.

Animations that delay essential navigation or repeated interactions SHOULD provide an appropriate alternative when practical.

## 14. Performance Standards

### 14.1 Animation Complexity

Animation complexity SHOULD be appropriate for the target platform and number of simultaneously animated objects.

### 14.2 Runtime Evaluation

Projects SHOULD evaluate animation performance in representative gameplay conditions.

### 14.3 Optimization

Optimization MAY include:

- Reducing unnecessary animated objects.
- Disabling irrelevant processing.
- Simplifying animation tracks.
- Reducing unnecessary skeletal complexity.
- Reusing animation resources.
- Reducing excessive simultaneous effects.
- Avoiding unnecessary runtime animation updates.

Optimization MUST be based on actual performance requirements or measured bottlenecks.

### 14.4 Resource Usage

Animation assets SHOULD use appropriate formats, resolutions, compression settings, and import configurations.

### 14.5 Performance Validation

Performance evaluation MUST follow:

`docs/02_technical_standards/performance_guidelines.md`

## 15. Animation Review and Validation

### 15.1 Visual Review

Animations SHOULD be reviewed for:

- Motion clarity.
- Timing.
- Spacing.
- Pose quality.
- Weight.
- Continuity.
- Visual consistency.
- Intended emotional expression.

### 15.2 Gameplay Review

Gameplay animations SHOULD be validated within their actual gameplay context.

Review SHOULD consider:

- Input responsiveness.
- State transitions.
- Gameplay readability.
- Collision and physics interaction.
- Animation interruption.
- Feedback timing.
- Interaction consistency.

### 15.3 Technical Review

Technical validation SHOULD consider:

- Correct animation resource references.
- Valid node and property tracks.
- Correct playback configuration.
- Proper looping behavior.
- Signal and method track behavior.
- Resource loading.
- Runtime errors.
- Performance impact.

### 15.4 Integration Review

Animations SHOULD be validated with their associated:

- Character or object.
- Gameplay systems.
- Audio.
- Visual effects.
- Camera behavior.
- UI.
- Scene transitions.

### 15.5 Revision

Animation feedback SHOULD identify specific issues and expected improvements.

Revisions SHOULD preserve approved animation direction unless a change is explicitly justified.

## 16. Documentation

Significant animation systems SHOULD document:

- Animation purpose.
- Associated gameplay states.
- Playback ownership.
- Animation names.
- Looping behavior.
- Transition rules.
- Gameplay events.
- Interruption behavior.
- Required resources.
- Technical constraints.

Documentation SHOULD be maintained close to the relevant feature or asset when practical.

Project-specific animation specifications and animation lists SHOULD be maintained in the game repository.

## 17. AI-Assisted Animation Development

AI agents MUST follow these standards when creating, modifying, importing, or integrating animation assets and systems.

Agents MUST:

- Inspect existing animation assets and conventions.
- Respect project art direction.
- Follow feature-oriented asset organization.
- Preserve source assets when applicable.
- Follow naming conventions.
- Maintain existing animation contracts.
- Verify animation resource references.
- Consider gameplay state and animation ownership.
- Validate animation transitions and interruption behavior.
- Check runtime errors and relevant performance implications.
- Report validation results accurately.

Agents MUST NOT:

- Change approved animation direction without authorization.
- Replace source assets without preserving required originals.
- Introduce unnecessary animation systems.
- Modify shared animation resources without evaluating their consumers.
- Make gameplay correctness depend on unverified animation completion.
- Claim an animation has been visually validated when it has not been inspected.

Agents SHOULD request owner approval before making significant changes to shared animation conventions, project art direction, or established character rigs.

## 18. Animation Review Checklist

Before approving animation-related work, verify:

- [ ] The animation has a clear purpose.
- [ ] It follows the project's visual identity.
- [ ] Timing and spacing support the intended motion.
- [ ] Important gameplay actions remain readable.
- [ ] Character and object proportions remain consistent.
- [ ] Animation transitions behave correctly.
- [ ] Looping behavior is intentional.
- [ ] Playback has a clear owner.
- [ ] Gameplay state remains authoritative.
- [ ] Interruptions are handled correctly.
- [ ] Physics and animation responsibilities do not conflict.
- [ ] Animation assets follow naming and organization standards.
- [ ] Resource references are valid.
- [ ] Accessibility concerns have been considered.
- [ ] Performance is appropriate for the intended use.
- [ ] Relevant visual and runtime validation has been completed.
- [ ] Documentation has been updated when necessary.

## 19. Exceptions

Exceptions MAY be introduced when project-specific artistic or technical requirements justify alternative animation practices.

Exceptions SHOULD:

- Have a clear justification.
- Identify affected assets or systems.
- Explain relevant trade-offs.
- Preserve gameplay readability and maintainability.
- Receive project owner approval when they establish a significant departure from studio conventions.
- Be documented when they introduce a reusable exception.

## 20. Related Documents

These standards SHOULD be used alongside:

- `docs/00_studio_standards/development_philosophy.md`
- `docs/00_studio_standards/naming_conventions.md`
- `docs/00_studio_standards/project_structure_standards.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/02_technical_standards/engine_standards.md`
- `docs/02_technical_standards/asset_pipeline.md`
- `docs/02_technical_standards/resource_management.md`
- `docs/02_technical_standards/gdscript_standards.md`
- `docs/02_technical_standards/performance_guidelines.md`
- `docs/02_technical_standards/scene_and_node_convention.md`
- `docs/02_technical_standards/event_and_signal_guidelines.md`
- `docs/01_game_design_guidelines/gameplay_design_guidelines.md`
- `docs/01_game_design_guidelines/mechanic_design_guidelines.md`
- `docs/01_game_design_guidelines/player_experience_guidelines.md`
- `docs/01_game_design_guidelines/ui_ux_design_guidelines.md`
- Applicable documents in `docs/05_qa_standards/`

## 21. Maintenance

These standards SHOULD be reviewed when:

- Godot introduces relevant animation capabilities.
- The studio adopts new animation production workflows.
- Repeated animation integration issues reveal gaps in the standards.
- New target platforms introduce different animation constraints.
- Accessibility requirements evolve.
- Production experience identifies more effective animation practices.

Changes MUST preserve the purpose of this document as a reusable studio-wide animation standard.