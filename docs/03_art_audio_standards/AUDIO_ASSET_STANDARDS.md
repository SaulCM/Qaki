# Audio Asset Standards

## 1. Purpose

This document defines the studio-wide standards for creating, sourcing, reviewing, organizing, integrating, and maintaining audio assets in game projects.

Its purpose is to ensure that audio assets:

- Support the intended player experience.
- Maintain a consistent audio identity.
- Communicate gameplay information effectively.
- Meet appropriate technical and quality requirements.
- Integrate reliably into the game.
- Respect licensing and attribution requirements.
- Remain maintainable throughout the project's lifecycle.

These standards are reusable across studio projects. Individual games MUST define their own audio direction, soundscape, technical specifications, audio priorities, and implementation requirements.

## 2. Scope

These standards apply to:

- Sound effects.
- Environmental ambience.
- Music and musical compositions.
- Character voices and dialogue recordings.
- Voice-over and narration.
- UI sounds.
- Gameplay feedback sounds.
- Cinematic audio.
- Foley and recorded sound.
- Audio variations and layers.
- Adaptive and interactive audio assets.
- Externally sourced and AI-generated audio.

This document focuses on the assets and their production quality.

Audio playback, mixing architecture, buses, resource loading, spatial audio configuration, and engine-specific implementation MUST follow the relevant technical standards and project architecture.

## 3. Audio Design Principles

All audio assets SHOULD follow these principles.

### 3.1. Support the Player Experience

Audio MUST contribute intentionally to the player's experience.

It MAY provide:

- Gameplay feedback.
- Environmental atmosphere.
- Emotional reinforcement.
- Narrative information.
- Spatial awareness.
- Character identity.
- Worldbuilding.
- Interface feedback.

Audio SHOULD have a clear purpose rather than exist solely to fill silence.

### 3.2. Clarity and Readability

Important audio cues MUST remain distinguishable from other sounds.

Players SHOULD be able to recognize relevant audio events without unnecessary ambiguity.

Audio MUST NOT consistently obscure important gameplay sounds or essential information.

### 3.3. Consistency

Audio assets SHOULD maintain consistency in:

- Loudness.
- Frequency balance.
- Tonal character.
- Spatial presentation.
- Reverb and acoustic treatment.
- Sound design style.
- Musical identity.
- Recording and processing quality.

Assets created independently SHOULD still feel as though they belong to the same game.

### 3.4. Purposeful Complexity

Audio complexity SHOULD be proportional to its contribution to the experience.

Avoid unnecessary layers, effects, processing, or variations that increase production and implementation costs without meaningful benefit.

### 3.5. Player Comfort

Audio MUST be designed with reasonable listening comfort in mind.

Avoid unnecessary:

- Excessive loudness.
- Harsh frequency content.
- Abrupt volume changes.
- Repetitive high-intensity sounds.
- Unintended clipping or distortion.
- Excessively repetitive or intrusive audio.

### 3.6. Technical Suitability

Audio assets MUST be appropriate for their intended use and target platforms.

Consider:

- Duration.
- Sample rate.
- Bit depth.
- Channel configuration.
- File format.
- Compression.
- Loudness.
- Dynamic range.
- Memory usage.
- Streaming requirements.
- Licensing restrictions.

Project-specific technical requirements MUST be documented separately.

## 4. Audio Direction and Identity

Each game project MUST establish an audio direction appropriate to its visual identity, gameplay, narrative, and intended emotional experience.

The project-specific audio direction SHOULD define:

- Overall audio identity.
- Musical style and influences.
- Sound design philosophy.
- Environmental soundscape.
- Character audio identity.
- Dialogue and voice-over direction.
- Audio feedback conventions.
- Intended dynamic range.
- Spatial audio approach.
- Loudness expectations.
- Accessibility requirements.

### 4.1. Audio References

Audio references MAY be used to communicate:

- Desired sound characteristics.
- Musical style.
- Instrumentation.
- Environmental atmosphere.
- Acoustic properties.
- Character vocal direction.
- Emotional intent.

References SHOULD clarify the intended result without implying unrestricted permission to reproduce copyrighted recordings or compositions.

### 4.2. Audio Consistency

New audio assets MUST be evaluated against the established audio direction.

When an asset conflicts with the existing direction:

1. Identify the inconsistency.
2. Determine whether the asset or audio direction requires revision.
3. Evaluate the impact on related assets.
4. Obtain project owner approval for significant changes.
5. Update relevant project documentation when necessary.

AI agents MUST NOT independently redefine the project's audio identity.

## 5. Audio Asset Categories

### 5.1. Sound Effects

Sound effects communicate actions, events, interactions, and environmental details.

Examples include:

- Weapon sounds.
- Footsteps.
- Impact sounds.
- Object interactions.
- Mechanical sounds.
- Creature sounds.
- Explosions.
- Environmental events.
- Ability and skill effects.

Sound effects SHOULD have a clear gameplay or atmospheric purpose.

Important gameplay sounds SHOULD be recognizable even when multiple effects occur simultaneously.

### 5.2. Environmental Ambience

Ambience establishes the acoustic identity of locations and environments.

Examples include:

- Wind.
- Rain.
- Water.
- Wildlife.
- Machinery.
- Crowds.
- Interior room tone.
- Distant environmental activity.

Ambient assets SHOULD support the location's identity without unnecessarily competing with gameplay audio.

### 5.3. Music

Music establishes emotional tone, reinforces identity, and supports pacing.

Examples include:

- Main theme.
- Exploration music.
- Combat music.
- Boss encounters.
- Narrative sequences.
- Menu music.
- Victory and defeat themes.
- Transitional music.

Music SHOULD support the intended experience without consistently overpowering gameplay feedback or dialogue.

### 5.4. Dialogue and Voice

Dialogue and voice assets communicate character identity, narrative information, and vocal feedback.

Examples include:

- Character dialogue.
- NPC conversations.
- Narration.
- Announcements.
- Character reactions.
- Combat vocalizations.
- Environmental voice recordings.

Voice assets SHOULD preserve intelligibility, consistent characterization, and appropriate recording quality.

### 5.5. UI Audio

UI audio provides feedback for interface interactions.

Examples include:

- Button interactions.
- Menu navigation.
- Selection and confirmation.
- Notifications.
- Warnings.
- Errors.
- Inventory interactions.

UI sounds SHOULD be recognizable, concise, and consistent with the interface's visual design.

They MUST NOT become unnecessarily repetitive or intrusive.

### 5.6. Foley

Foley reproduces physical interactions and movement.

Examples include:

- Footsteps.
- Clothing movement.
- Equipment handling.
- Object manipulation.
- Surface interactions.
- Body movement.

Foley SHOULD be consistent with the character, surface, environment, and action being represented.

### 5.7. Cinematic Audio

Cinematic audio supports scripted sequences and narrative presentation.

It MAY combine:

- Dialogue.
- Music.
- Sound effects.
- Environmental ambience.
- Transitions.
- Spatial audio.

Cinematic audio SHOULD maintain consistency with the game's overall audio direction.

## 6. Sound Effect Design Standards

### 6.1. Sound Identity

Each important sound effect SHOULD have a recognizable identity.

Its characteristics SHOULD support the event it represents.

Consider:

- Attack and decay.
- Duration.
- Frequency content.
- Tonal character.
- Transient response.
- Texture.
- Intensity.
- Spatial characteristics.

### 6.2. Gameplay Feedback

Gameplay sounds SHOULD reinforce the relationship between player actions and game responses.

Examples:

- A successful hit should sound different from a missed attack.
- An unavailable action should communicate failure clearly.
- A collectible should provide recognizable pickup feedback.
- A dangerous event should be distinguishable from ordinary ambience.

Important feedback sounds MUST NOT depend exclusively on audio. Critical gameplay information SHOULD also have appropriate visual or other accessible feedback.

### 6.3. Sound Variations

Frequently repeated sounds SHOULD have appropriate variation when repetition would become noticeable or fatiguing.

Variation MAY involve:

- Pitch.
- Volume.
- Timing.
- Layer combinations.
- Different recordings.
- Different sound samples.

Variations MUST preserve the recognizable identity of the underlying event.

Randomization SHOULD NOT create inconsistent or misleading gameplay feedback.

### 6.4. Sound Duration

Sound duration SHOULD match the event it represents.

Avoid:

- Unnecessarily long effects.
- Abruptly truncated sounds.
- Excessive silence.
- Unintended tails.
- Overlapping playback that produces unwanted buildup.

## 7. Music Standards

### 7.1. Musical Identity

Music SHOULD reinforce the game's identity and emotional direction.

Composition and selection SHOULD consider:

- Genre and style.
- Instrumentation.
- Tempo.
- Harmony.
- Rhythm.
- Melody.
- Dynamics.
- Emotional intent.
- Relationship with gameplay.

### 7.2. Gameplay Integration

Music SHOULD support the intended gameplay experience.

Consider:

- Exploration and discovery.
- Combat intensity.
- Tension and release.
- Narrative pacing.
- Player progression.
- Transitions between game states.

Music transitions SHOULD feel intentional and avoid unnecessary abruptness.

### 7.3. Looping

Music intended for continuous playback MUST have appropriate loop points.

Verify:

- Seamless transitions.
- Consistent timing.
- No unintended clicks or gaps.
- No abrupt changes in loudness.
- Musical continuity across the loop boundary.

Not every musical asset needs to loop.

### 7.4. Dynamic and Adaptive Music

Adaptive music MAY respond to gameplay states or events.

Examples include:

- Combat intensity.
- Exploration states.
- Player danger.
- Narrative events.
- Location changes.
- Boss encounter phases.

Adaptive music SHOULD maintain musical coherence across transitions and variations.

Specific implementation behavior MUST be documented in the project audio design and implemented according to the technical architecture.

### 7.5. Musical Asset Integrity

Musical compositions MUST respect applicable copyright, licensing, and attribution requirements.

Preserve original composition sources and relevant production materials when available and permitted.

## 8. Dialogue and Voice Standards

### 8.1. Voice Direction

Voice recordings SHOULD follow the project's approved character and narrative direction.

Consider:

- Character identity.
- Emotional intent.
- Vocal delivery.
- Pronunciation.
- Pacing.
- Consistency between recordings.
- Language and localization requirements.

### 8.2. Recording Quality

Voice recordings MUST be sufficiently clean and intelligible for their intended use.

Check for:

- Unwanted background noise.
- Clipping.
- Distortion.
- Excessive room reverberation.
- Inconsistent recording levels.
- Unintended breaths or handling noise.
- Incorrect edits.
- Missing or truncated dialogue.

Intentional vocal effects MAY be used when they support the intended character or environment.

### 8.3. Dialogue Editing

Dialogue SHOULD be edited to preserve natural delivery and intelligibility.

Avoid unnatural cuts, inconsistent pauses, or abrupt endings unless intentionally required.

### 8.4. Dialogue Consistency

Recordings belonging to the same character SHOULD maintain consistent vocal characteristics.

When multiple recording sessions are required, use established references and recording conventions to minimize differences.

### 8.5. Localization

Localized dialogue MUST preserve the intended meaning, tone, and gameplay context.

Consider:

- Pronunciation.
- Translation accuracy.
- Character voice.
- Timing constraints.
- Subtitle compatibility.
- Cultural adaptation.
- Regional language differences.

Localized audio SHOULD be reviewed in its intended game context.

## 9. Environmental Audio Standards

### 9.1. Environmental Identity

Each environment SHOULD have an identifiable acoustic character.

Environmental audio MAY communicate:

- Location.
- Weather.
- Time of day.
- Nearby activity.
- Environmental danger.
- World scale.
- Narrative context.

### 9.2. Layering

Environmental soundscapes MAY combine:

- Background ambience.
- Mid-distance activity.
- Foreground events.
- Interactive environmental sounds.

Layers SHOULD have clear roles and should not unnecessarily compete with each other.

### 9.3. Variation

Repeated environmental sounds SHOULD use suitable variation when necessary to avoid obvious repetition.

Variation SHOULD remain consistent with the environment and intended acoustic identity.

### 9.4. Spatial Consistency

Spatially presented sounds SHOULD correspond to their intended sources and locations.

Sound placement MUST NOT mislead players when spatial information is important to gameplay.

## 10. Loudness and Dynamic Range

Audio assets MUST be prepared with appropriate loudness and dynamic characteristics.

### 10.1. Loudness Consistency

Assets intended to serve similar purposes SHOULD have reasonably consistent perceived loudness.

Consider the difference between:

- Sound effects.
- Dialogue.
- Music.
- Ambience.
- UI feedback.
- Cinematic audio.

Do not rely exclusively on peak amplitude to judge perceived loudness.

### 10.2. Peak Levels and Clipping

Audio MUST NOT contain unintended clipping or digital distortion.

Preserve sufficient headroom for the intended mixing and playback context.

### 10.3. Dynamic Range

Dynamic range SHOULD support the intended experience while remaining suitable for the target audience and listening conditions.

Excessive compression SHOULD be avoided unless justified by the audio direction or platform requirements.

### 10.4. Loudness Targets

Projects SHOULD define appropriate loudness targets for their audio categories and delivery platforms.

This studio standard does not impose universal LUFS, RMS, or peak values because suitable targets depend on the game's audio design, mix architecture, and distribution requirements.

Project-specific targets MUST be documented when needed.

## 11. Audio Quality and Technical Requirements

Audio assets MUST be technically suitable for their intended use.

### 11.1. File Formats

Choose file formats based on:

- Audio category.
- Required quality.
- File size.
- Compression.
- Streaming requirements.
- Engine support.
- Platform compatibility.
- Licensing or delivery restrictions.

Do not use an unnecessarily large or lossless format for every asset.

### 11.2. Sample Rate and Bit Depth

Sample rate and bit depth SHOULD be appropriate for the asset's recording, editing, and playback requirements.

Avoid unnecessary resampling or repeated format conversion.

### 11.3. Channel Configuration

Use mono, stereo, or multichannel audio according to the intended presentation.

Examples:

- Centered sound effects MAY use mono.
- Music commonly uses stereo.
- Environmental recordings MAY use stereo or multichannel formats.
- Spatially positioned sounds SHOULD use formats appropriate to the engine's spatial audio workflow.

### 11.4. Audio Integrity

Verify that assets do not contain:

- Unintended silence.
- Missing channels.
- Corrupted audio.
- Unexpected clicks or pops.
- Abrupt truncation.
- Unwanted noise.
- Incorrect playback speed.
- Incorrect pitch.
- Unexpected format conversion artifacts.

### 11.5. Performance

Audio assets SHOULD be appropriate for their expected playback frequency, duration, and loading behavior.

Consider:

- Memory usage.
- File size.
- Streaming requirements.
- Concurrent playback.
- Audio processing cost.
- Platform limitations.

Technical loading, compression, and playback configuration MUST follow the relevant engine and project technical standards.

## 12. Audio Asset Naming and Organization

Audio assets MUST follow the project's naming and directory conventions.

The studio-wide naming rules are defined in `docs/00_studio_standards/naming_conventions.md`.

### 12.1. Naming

Audio filenames SHOULD:

- Use descriptive names.
- Use lowercase `snake_case`.
- Identify the sound or musical purpose.
- Avoid unnecessary abbreviations.
- Avoid ambiguous names.
- Use consistent suffixes for variants.

Examples:

- `sword_swing_01.wav`
- `footstep_stone_02.wav`
- `door_wood_open.wav`
- `forest_ambience_day.ogg`
- `combat_theme_loop.ogg`
- `merchant_dialogue_greeting.wav`
- `ui_button_confirm.wav`

### 12.2. Feature-Oriented Organization

Audio assets MUST be organized according to the project's feature-oriented structure.

Example:

```text
features/
├── combat/
│   └── assets/
│       └── audio/
│           ├── weapons/
│           └── impacts/
├── player/
│   └── assets/
│       └── audio/
│           ├── footsteps/
│           └── movement/
├── world/
│   └── assets/
│       └── audio/
│           ├── ambience/
│           └── environment/
└── ui/
    └── assets/
        └── audio/
            └── interactions/
```

Music or audio assets shared across multiple features MAY be stored in an appropriate shared location.

Shared audio assets MUST have a clear ownership and reuse justification.

Do not create a separate type-oriented root hierarchy that conflicts with the approved feature-oriented project structure.

### 12.3. Asset Variants

Variants SHOULD use consistent identifiers.

Examples:

- `footstep_grass_01.wav`
- `footstep_grass_02.wav`
- `footstep_grass_03.wav`

Avoid inconsistent numbering or naming conventions within the same asset group.

## 13. Audio Source Files and Deliverables

Preserve editable source files whenever possible and permitted.

Source materials MAY include:

- Digital audio workstation projects.
- Original recordings.
- Unprocessed recordings.
- Edited audio sessions.
- Musical composition files.
- MIDI files.
- Synthesizer presets.
- Sound design sessions.
- Supporting samples.
- Relevant processing information.

Final exported assets SHOULD be reproducible from their source materials when practical.

### 13.1. Source Preservation

Do not replace original recordings or editable production files with exported versions.

Keep source materials separate from final game-ready assets.

### 13.2. Export Requirements

Exported assets MUST:

- Use an appropriate format.
- Have the correct duration.
- Have appropriate channel configuration.
- Avoid unintended clipping.
- Preserve required audio quality.
- Contain no unintended silence or artifacts.
- Be compatible with the target engine workflow.

### 13.3. Reproducibility

For complex or important audio assets, preserve relevant information about:

- Source recordings.
- Processing chains.
- Effects and plugins.
- Export settings.
- Version dependencies.
- Production revisions.

Avoid unnecessary documentation for simple assets when the source project and version history already provide sufficient traceability.

## 14. External and AI-Generated Audio

External and AI-generated audio MAY be used when it satisfies the project's quality, technical, artistic, and legal requirements.

### 14.1. External Audio

Before integrating externally sourced audio, verify:

- Source and creator, when available.
- License and permitted usage.
- Commercial-use restrictions.
- Attribution requirements.
- Modification and redistribution restrictions.
- Included dependencies.
- Technical compatibility.

An asset MUST NOT be integrated when its usage rights are unclear or incompatible with the project's intended distribution.

### 14.2. AI-Generated Audio

AI-generated audio MUST undergo the same quality and licensing review as other audio assets.

Review for:

- Audio artifacts.
- Unnatural transitions.
- Unintended distortion.
- Poor intelligibility.
- Inconsistent loudness.
- Repetitive or unnatural patterns.
- Unwanted background content.
- Inappropriate resemblance to protected recordings, compositions, or recognizable voices.
- Compatibility with the project's audio direction.

AI-generated music, dialogue, and sound effects MUST NOT be accepted solely because they sound convincing in a short preview.

Where appropriate, preserve generation information, relevant prompts, tool information, and editing history.

AI agents MUST NOT assume that generated audio is automatically free of licensing, ownership, or usage restrictions.

### 14.3. Synthetic and Replicated Voices

The use of synthetic voices or voice likenesses MUST respect applicable permissions and legal requirements.

Do not clone or imitate a real person's recognizable voice without appropriate authorization.

## 15. Audio Review and Acceptance

Audio assets SHOULD be reviewed before being considered complete.

### 15.1. Artistic Review

Verify that the asset:

- Supports the intended audio direction.
- Communicates its intended purpose.
- Has appropriate tonal and emotional characteristics.
- Fits its gameplay or narrative context.
- Is consistent with related audio assets.
- Does not create unnecessary listening fatigue.

### 15.2. Technical Review

Verify that the asset:

- Uses an appropriate format.
- Has correct duration and channel configuration.
- Contains no unintended clipping or corruption.
- Has acceptable loudness.
- Has no unintended clicks, pops, or artifacts.
- Is named and organized correctly.
- Imports and plays correctly in the target environment.

### 15.3. Contextual Review

Audio SHOULD be evaluated alongside other sounds that will play at the same time.

Consider:

- Dialogue intelligibility.
- Music interaction.
- Sound effect overlap.
- Ambient interference.
- Gameplay feedback priority.
- Repetition.
- Overall listening comfort.

An audio asset that sounds acceptable in isolation may still be unsuitable in the actual game mix.

### 15.4. Acceptance

An asset SHOULD be accepted when its applicable artistic, technical, licensing, and integration requirements are satisfied.

AI agents MAY perform preliminary reviews but MUST NOT independently approve subjective changes reserved for the project owner.

## 16. Audio Asset Replacement and Retirement

Before replacing or removing an audio asset:

1. Identify its current references and dependencies.
2. Determine which features or scenes use it.
3. Check whether it is shared.
4. Evaluate the impact of replacement or removal.
5. Preserve source files and licensing records when required.
6. Update affected references.
7. Validate the affected gameplay and audio mix.

Do not delete audio assets merely because they are not currently referenced by an open scene. They may be loaded dynamically or referenced through configuration.

Deprecated assets SHOULD be identified clearly and removed only after dependency validation.

## 17. Audio Documentation

Projects SHOULD document significant audio requirements and decisions.

Documentation MAY include:

- Audio direction.
- Music specifications.
- Sound effect requirements.
- Character voice specifications.
- Recording standards.
- Loudness targets.
- Audio asset inventories.
- Licensing records.
- Localization requirements.
- Audio review results.
- Known limitations.

Project-specific audio design and implementation decisions MUST be maintained in the game repository.

Studio-wide standards MUST NOT become a repository for individual game recordings, compositions, or project-specific audio specifications.

## 18. Accessibility and Player Comfort

Audio design SHOULD account for different player needs and listening environments.

Consider:

- Dialogue intelligibility.
- Clear gameplay sound cues.
- Avoiding excessive loudness.
- Avoiding unnecessarily harsh frequencies.
- Managing repetitive sounds.
- Providing appropriate volume controls.
- Supporting subtitles or visual alternatives for important audio information.
- Avoiding dependence on audio alone for critical gameplay information.
- Providing suitable options for spatial audio where relevant.

Projects SHOULD define their own accessibility requirements and validate them during audio and gameplay testing.

## 19. AI-Assisted Audio Work

AI agents assisting with audio production MUST:

1. Read the project's approved audio direction and asset requirements.
2. Identify the intended purpose and owning feature.
3. Follow naming and directory conventions.
4. Preserve available source materials.
5. Verify licensing and attribution information.
6. Avoid unapproved changes to established audio direction.
7. Validate audio exports where possible.
8. Check integration and playback when possible.
9. Identify missing requirements and unresolved dependencies.
10. Report known limitations honestly.
11. Request human review when artistic judgment or approval is required.

AI agents MUST NOT:

- Claim audio has been listened to or validated when it has not.
- Assume generated audio has unrestricted usage rights.
- Replace approved audio without checking dependencies and obtaining appropriate approval.
- Introduce unauthorized voice likenesses.
- Mark subjective audio decisions as approved without the appropriate authority.

## 20. Audio Asset Review Checklist

Before accepting an audio asset, verify the applicable requirements:

- [ ] The asset has a defined purpose.
- [ ] It follows the approved audio direction.
- [ ] It is appropriate for its intended gameplay or presentation context.
- [ ] Its sound identity is clear.
- [ ] Its loudness and dynamic range are appropriate.
- [ ] It contains no unintended clipping, noise, or artifacts.
- [ ] Its duration and transitions are correct.
- [ ] Its format and channel configuration are appropriate.
- [ ] It is named and stored correctly.
- [ ] Source files are preserved when required.
- [ ] Licensing and attribution requirements are satisfied.
- [ ] It imports and plays correctly in the target environment.
- [ ] It has been evaluated alongside relevant audio assets.
- [ ] It does not create unnecessary listening fatigue.
- [ ] Relevant documentation has been updated.

Not every checklist item applies to every asset. Non-applicable requirements SHOULD be identified rather than treated as failures.

## 21. Exceptions

Exceptions to these standards MAY be permitted when justified by:

- Artistic requirements.
- Technical limitations.
- Platform constraints.
- Accessibility requirements.
- Production priorities.
- Experimental audio approaches.

Exceptions MUST:

- Have a clear justification.
- Identify affected assets or features.
- Describe relevant risks and consequences.
- Receive project owner approval when they affect established studio or project standards.
- Be documented when they have lasting impact.

Temporary exceptions SHOULD be reviewed before final release.

## 22. Related Documents

- `docs/00_studio_standards/naming_conventions.md`
- `docs/00_studio_standards/project_structure_standards.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/02_technical_standards/engine_standards.md`
- `docs/02_technical_standards/performance_guidelines.md`
- `docs/02_technical_standards/resource_management.md`
- `docs/03_art_audio_standards/art_pipeline.md`
- `docs/03_art_audio_standards/art_asset_standards.md`

## 23. Maintenance

These standards SHOULD be reviewed periodically and updated when:

- Studio audio production practices change.
- New audio categories or workflows are introduced.
- Engine capabilities or technical requirements change.
- Recurring audio quality issues are identified.
- Licensing or distribution requirements change.
- Accessibility requirements evolve.
- Improvements to audio production and review are identified.

Changes MUST preserve the distinction between reusable studio standards and project-specific audio direction.

The project owner is responsible for approving changes to these standards.