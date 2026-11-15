# Audio Pipeline

## 1. Purpose

This document defines the standard workflow for producing, sourcing, reviewing, preparing, integrating, and maintaining audio assets across studio game projects.

Its purpose is to establish a consistent and maintainable audio production process that supports:

- Consistent audio quality.
- Efficient asset production.
- Clear production responsibilities.
- Reliable handoffs.
- Controlled revisions.
- Reproducible audio exports.
- Reliable game engine integration.
- Licensing and source traceability.
- Collaboration between human contributors and AI agents.

These standards are reusable across projects. Individual games MUST define their own audio direction, asset requirements, production priorities, technical constraints, and delivery specifications.

## 2. Scope

This pipeline applies to:

- Sound effects.
- Environmental ambience.
- Music and musical compositions.
- Dialogue and voice recordings.
- Voice-over and narration.
- UI sounds.
- Foley.
- Cinematic audio.
- Audio variations and layers.
- Adaptive and interactive audio assets.
- Externally sourced and AI-generated audio.

This document covers the production lifecycle and delivery of audio assets.

Audio playback architecture, audio buses, mixing implementation, spatial audio configuration, resource loading, and engine-specific playback behavior MUST follow the relevant technical standards and project architecture.

## 3. Pipeline Principles

All audio production workflows SHOULD follow these principles.

### 3.1. Define Requirements Before Production

Audio assets SHOULD have a clear purpose and defined requirements before significant production work begins.

Avoid producing assets without understanding their intended gameplay, narrative, or environmental context.

### 3.2. Validate Early

Validate audio direction and technical feasibility before investing substantial production effort.

Use prototypes, rough recordings, temporary sound effects, and representative samples when appropriate.

### 3.3. Work Incrementally

Produce and review audio in manageable stages.

Prefer early validation of representative assets over completing large batches before identifying inconsistencies.

### 3.4. Preserve Source Materials

Maintain original recordings, editable sessions, composition files, and relevant production materials whenever possible and permitted.

Final exported assets SHOULD be reproducible from their source materials when practical.

### 3.5. Separate Production from Integration

Producing an audio asset and integrating it into the game are distinct activities.

An audio file is not considered fully integrated merely because it exists in the repository.

### 3.6. Maintain Traceability

Important audio sources, revisions, dependencies, licenses, and production decisions SHOULD be traceable.

### 3.7. Use Proportionate Process

The pipeline MUST remain practical for the project's size and production needs.

Do not introduce unnecessary approval stages, documentation, or tooling for simple audio assets.

## 4. Audio Production Lifecycle

The standard audio production lifecycle consists of:

1. Audio planning.
2. Requirements and reference gathering.
3. Audio concept and direction.
4. Recording or source acquisition.
5. Editing and sound design.
6. Preliminary review.
7. Mixing and processing.
8. Mastering and export preparation.
9. Engine integration.
10. Validation and acceptance.
11. Maintenance or retirement.

Not every asset requires a separate formal activity for every stage. Simple assets MAY combine stages when doing so does not compromise quality or traceability.

<escape>```mermaid
flowchart TD
    A[Audio Planning] --> B[Requirements and References]
    B --> C[Audio Concept and Direction]
    C --> D[Recording or Source Acquisition]
    D --> E[Editing and Sound Design]
    E --> F[Preliminary Review]
    F -->|Changes Required| E
    F -->|Accepted| G[Mixing and Processing]
    G --> H[Mastering and Export]
    H --> I[Engine Integration]
    I --> J[Playback and Context Validation]
    J -->|Issues Found| E
    J -->|Accepted| K[Audio Asset Acceptance]
    K --> L[Maintenance or Retirement]
```</escape>

## 5. Audio Planning

Before production begins, identify the asset's purpose and requirements.

### 5.1. Asset Identification

Define:

- Asset name or identifier.
- Audio category.
- Owning feature or system.
- Intended gameplay or presentation purpose.
- Target scene, character, environment, or interface.
- Whether the asset is new, a variation, or a replacement.
- Whether the asset is reusable.
- Whether the asset requires recording, composition, synthesis, or external sourcing.

### 5.2. Audio Requirements

Define the requirements relevant to the asset.

These MAY include:

- Intended sound or musical description.
- Emotional purpose.
- Gameplay function.
- Duration.
- Expected playback frequency.
- Loudness expectations.
- Frequency characteristics.
- Mono, stereo, or multichannel requirements.
- Looping requirements.
- Required variations.
- Spatial presentation.
- Target platform.
- Technical format.
- Dependencies.
- Licensing restrictions.

Avoid specifying technical details that do not affect the asset's intended use.

### 5.3. Priority and Production Effort

Audio asset priority SHOULD reflect its impact on the game.

Consider:

- Gameplay importance.
- Player exposure and repetition frequency.
- Narrative importance.
- Contribution to game identity.
- Dependency on other assets.
- Production complexity.
- Technical risk.

Important gameplay feedback and frequently heard audio assets SHOULD receive early validation.

### 5.4. Dependencies

Identify dependencies before production.

Examples include:

- Character voice recordings requiring approved dialogue.
- Footsteps requiring defined surfaces.
- Combat sounds requiring established combat actions.
- Music requiring an approved musical direction.
- Environmental ambience requiring a defined location.
- Adaptive music requiring known gameplay states.

Dependencies SHOULD be resolved before they become production blockers.

## 6. Requirements and Reference Gathering

Collect the information necessary to guide audio production.

References MAY include:

- Approved audio direction.
- Reference recordings.
- Field recordings.
- Musical references.
- Sound design examples.
- Dialogue scripts.
- Gameplay recordings.
- Environmental descriptions.
- Existing approved game audio.
- Acoustic references.

### 6.1. Reference Management

References SHOULD be organized and associated with the relevant asset or feature.

Record their source when attribution, licensing, or traceability matters.

References MUST NOT be treated as unrestricted source material. Their usage rights and intended purpose must be respected.

### 6.2. Reference Evaluation

References SHOULD communicate the intended:

- Sound identity.
- Frequency characteristics.
- Duration.
- Dynamics.
- Acoustic environment.
- Musical style.
- Emotional character.
- Spatial characteristics.
- Recording quality.

Avoid collecting excessive references that do not contribute to a clear production direction.

### 6.3. Requirement Validation

Before production, verify that the available references and specifications are sufficient to begin.

If critical requirements are unclear, request clarification rather than making assumptions that could cause substantial rework.

## 7. Audio Concept and Direction

Audio concept development establishes the intended sound before full production.

### 7.1. Sound Concepts

Concepts MAY explore:

- Sound textures.
- Timbre.
- Frequency balance.
- Rhythm.
- Musical themes.
- Instrumentation.
- Environmental atmosphere.
- Character vocal characteristics.
- Sound effect layering.
- Acoustic spaces.

### 7.2. Prototype Audio

Use temporary audio when it can validate a design or technical requirement more efficiently than a finished asset.

Examples include:

- Placeholder sound effects.
- Temporary music tracks.
- Rough dialogue recordings.
- Synthesized ambience.
- Basic sound layers.
- Experimental sound variations.

Prototypes SHOULD answer specific design or technical questions.

### 7.3. Direction Validation

Before full production, validate:

- Alignment with project audio direction.
- Gameplay purpose.
- Emotional intent.
- Technical feasibility.
- Compatibility with existing audio.
- Production effort.

Significant audio direction changes require project owner approval.

## 8. Recording and Source Acquisition

Audio production MAY use original recordings, synthesized sounds, licensed libraries, commissioned material, or other approved sources.

### 8.1. Original Recording

When recording original audio, consider:

- Recording environment.
- Microphone selection and placement.
- Recording levels.
- Background noise.
- Room acoustics.
- Performance consistency.
- Recording duration.
- Channel configuration.
- Source file quality.

Avoid clipping and unnecessary processing during recording.

Preserve original recordings before destructive editing.

### 8.2. Field Recording

Field recordings SHOULD document relevant context when useful.

Record:

- Recording location at an appropriate level of detail.
- Recording date when relevant.
- Recording equipment or method.
- Environmental conditions.
- Recording permissions.
- Relevant licensing or usage restrictions.

Do not record private or restricted environments without appropriate authorization.

### 8.3. Voice Recording

Voice recordings SHOULD follow the approved dialogue and voice direction.

Before recording, confirm:

- Final or approved script.
- Character identity.
- Pronunciation.
- Intended emotional delivery.
- Required variations.
- Language and localization.
- Recording format.
- Naming and delivery requirements.

Multiple takes SHOULD be preserved when useful for editing and selection.

### 8.4. Music Production

Musical production MAY involve:

- Original composition.
- Instrument recording.
- MIDI programming.
- Sound synthesis.
- Arrangement.
- Performance recording.
- Licensed music acquisition.

Preserve relevant composition and production materials whenever possible and permitted.

### 8.5. External Source Acquisition

Before using external audio, verify:

- Source and creator, when available.
- License and permitted usage.
- Commercial-use restrictions.
- Attribution requirements.
- Modification and redistribution restrictions.
- Included dependencies.
- Technical compatibility.

An asset MUST NOT proceed to integration when its usage rights are unclear or incompatible with the project's intended distribution.

## 9. Editing and Sound Design

Editing transforms recordings and source materials into usable audio assets.

### 9.1. Editing Activities

Editing MAY include:

- Trimming.
- Noise removal.
- Silence removal.
- Timing adjustments.
- Fades.
- Crossfades.
- Pitch adjustment.
- Time stretching.
- Layering.
- Reversal.
- Sound shaping.
- Segmentation.
- Dialogue cleanup.

Use processing appropriate to the asset's intended purpose.

### 9.2. Non-Destructive Editing

Prefer non-destructive workflows when practical.

Preserve original recordings and source materials.

Avoid permanently overwriting source recordings during editing.

### 9.3. Sound Design

Sound design MAY combine multiple recordings, synthesized elements, and processed layers.

Each layer SHOULD have a clear purpose.

Avoid unnecessary layering that increases complexity without improving the final sound.

### 9.4. Loop Preparation

Assets intended for continuous playback MUST be prepared with appropriate loop points.

Verify:

- No audible clicks or pops at the loop boundary.
- No unintended gaps.
- Consistent timing.
- Appropriate fades or crossfades.
- Musical or environmental continuity.

Not every audio asset needs to loop.

### 9.5. Variations

Frequently repeated sounds SHOULD have appropriate variations when repetition would become noticeable or fatiguing.

Variations MAY be created through:

- Different source recordings.
- Pitch adjustments.
- Timing changes.
- Layer combinations.
- Processing variations.
- Different performances.

Variations MUST preserve the identity and intended function of the underlying event.

## 10. Preliminary Review

Before mixing and final processing, audio assets SHOULD undergo a preliminary review.

### 10.1. Review Objectives

Verify:

- Correct sound identity.
- Alignment with the intended purpose.
- Appropriate duration.
- Recording or source quality.
- Absence of major artifacts.
- Appropriate variations.
- Correct loop behavior, when applicable.
- Compatibility with project audio direction.

### 10.2. Review Outcomes

A preliminary review SHOULD result in one of the following:

- **Accepted:** The asset is ready for mixing and processing.
- **Changes Required:** Editing or sound design corrections are needed.
- **Blocked:** Missing information, dependencies, or technical issues prevent further work.
- **Rejected:** The source or concept is unsuitable for its intended purpose.

### 10.3. Review Feedback

Feedback SHOULD be:

- Specific.
- Actionable.
- Related to an identified requirement.
- Prioritized by impact.
- Clear about expected corrections.

Avoid vague feedback without identifying the problem.

## 11. Mixing and Processing

Mixing establishes the asset's final sonic characteristics and prepares it for its intended playback context.

### 11.1. Mixing Objectives

Mixing SHOULD consider:

- Perceived loudness.
- Frequency balance.
- Dynamic range.
- Stereo image.
- Channel configuration.
- Tonal consistency.
- Dialogue intelligibility.
- Relationship with other audio categories.

### 11.2. Audio Processing

Processing MAY include:

- Equalization.
- Compression.
- Limiting.
- Reverb.
- Delay.
- Distortion.
- Filtering.
- Modulation.
- Stereo processing.
- Spatial processing.

Processing SHOULD serve an intentional purpose.

Avoid excessive processing that introduces unwanted artifacts or compromises clarity.

### 11.3. Loudness Consistency

Assets intended for similar purposes SHOULD have reasonably consistent perceived loudness.

Consider the intended relationship between:

- Sound effects.
- Dialogue.
- Music.
- Ambience.
- UI feedback.
- Cinematic audio.

Do not rely exclusively on peak amplitude to judge perceived loudness.

### 11.4. Headroom and Clipping

Audio MUST NOT contain unintended clipping or digital distortion.

Preserve appropriate headroom for the intended playback and mixing context.

### 11.5. Contextual Mixing

Audio SHOULD be evaluated alongside other sounds that may play simultaneously.

Consider:

- Dialogue intelligibility.
- Music interference.
- Sound effect overlap.
- Ambient masking.
- Gameplay feedback priority.
- Repetition.
- Overall listening comfort.

An asset that sounds acceptable in isolation may still be unsuitable in the actual game mix.

### 11.6. Processing Consistency

Assets belonging to the same group SHOULD maintain consistent processing where appropriate.

Avoid applying identical processing indiscriminately when different assets have different purposes.

## 12. Mastering and Export Preparation

Mastering prepares final audio assets for their intended delivery and playback environment.

### 12.1. Mastering Objectives

Verify:

- Appropriate loudness.
- Suitable peak levels.
- Acceptable dynamic range.
- Consistent tonal balance.
- Absence of unintended distortion.
- Appropriate stereo or channel configuration.
- Correct duration and loop boundaries.

Mastering requirements MAY differ between individual sound effects, music tracks, dialogue, and other audio categories.

### 12.2. Loudness Targets

Projects SHOULD define appropriate loudness targets for relevant audio categories and delivery platforms.

This studio standard does not impose universal LUFS, RMS, or peak values because suitable targets depend on the project's audio design and delivery requirements.

Project-specific targets MUST be documented when necessary.

### 12.3. Export Settings

Export settings SHOULD be appropriate for:

- Audio category.
- Intended playback.
- Quality requirements.
- File size.
- Compression.
- Engine support.
- Target platform.
- Streaming or loading requirements.

Avoid unnecessary format conversion and repeated lossy compression.

### 12.4. Export Validation

Before integration, inspect and listen to the exported asset.

Verify:

- Correct file format.
- Correct sample rate and bit depth where applicable.
- Correct channel configuration.
- Correct duration.
- Appropriate loudness.
- No unintended clipping.
- No unexpected silence.
- No clicks, pops, or artifacts.
- Correct loop behavior.
- No export corruption.

### 12.5. Source and Export Separation

Maintain a clear distinction between:

- Original recordings.
- Editable production sessions.
- Intermediate exports.
- Final game-ready audio.
- Temporary working files.
- Generated files.

Temporary files SHOULD NOT be committed unless they are required for production or reproducibility.

## 13. Engine Integration

Audio assets MUST be integrated into the game project before they can be considered fully delivered.

### 13.1. Integration Preparation

Before integration:

- Verify the target feature and destination.
- Confirm naming and directory conventions.
- Check dependencies.
- Confirm required source files and licensing records.
- Identify scenes, resources, or systems that will use the asset.
- Confirm the expected playback behavior.

### 13.2. Integration in Godot

When integrating audio assets into Godot:

- Store assets in the appropriate feature-oriented directory.
- Follow project naming conventions.
- Configure import settings according to project standards.
- Verify resource references.
- Confirm that audio resources load correctly.
- Check loop and playback settings.
- Validate channel and spatial requirements.
- Avoid unnecessary duplicated resources.
- Keep generated engine cache files out of version control.

### 13.3. Feature Ownership

Audio assets SHOULD be integrated into their owning feature.

Assets used by multiple features MAY be stored in appropriate shared locations when there is a clear ownership and reuse justification.

Avoid moving audio into shared storage merely because it might be reused in the future.

### 13.4. Integration Changes

When integration requires modifications to existing scenes, resources, or scripts:

- Inspect existing dependencies.
- Keep changes within the intended scope.
- Follow the relevant technical standards.
- Validate affected features.
- Report additional changes or dependencies.

### 13.5. Audio Behavior Configuration

Playback behavior SHOULD be defined by the relevant project feature or audio system.

Examples include:

- Trigger conditions.
- Playback priority.
- Looping behavior.
- Variation selection.
- Volume control.
- Spatial positioning.
- State transitions.
- Interruption behavior.

The production pipeline defines the asset deliverables, not the complete runtime audio architecture.

## 14. Playback and Context Validation

Integrated audio MUST be validated in its intended gameplay context.

### 14.1. Functional Validation

Verify:

- Audio triggers correctly.
- Playback starts and stops as intended.
- Looping behaves correctly.
- Variations work as expected.
- No unintended overlapping playback occurs.
- Audio transitions are appropriate.
- Resources load without errors.

### 14.2. Artistic Validation

Verify:

- The asset fits the approved audio direction.
- The sound communicates its intended purpose.
- Loudness is appropriate.
- It does not mask important audio.
- It works with relevant music and ambience.
- It does not create unnecessary repetition or listening fatigue.

### 14.3. Platform Validation

When relevant, verify audio on representative target hardware and output configurations.

Consider:

- Headphones.
- Stereo speakers.
- Mono playback.
- Different output levels.
- Platform-specific limitations.
- Performance and memory constraints.

Do not assume that audio that works correctly in the editor will behave identically on every target platform.

## 15. Audio Asset Acceptance

An audio asset MAY be accepted when:

- Applicable artistic requirements are satisfied.
- Required production and review stages are complete.
- The final export is valid.
- Technical integration is successful.
- Playback behavior is correct.
- Licensing and attribution requirements are satisfied.
- Required source materials are preserved.
- Known limitations are documented.

Acceptance MUST reflect actual validation.

Assets that have not been listened to or tested in their intended context MUST NOT be reported as fully validated.

## 16. Audio Delivery

A completed audio delivery SHOULD contain only the files and information necessary for its intended use and future maintenance.

Depending on the asset, deliverables MAY include:

- Final game-ready audio file.
- Editable production session.
- Original recording.
- Supporting samples.
- Composition or MIDI files.
- Relevant processing information.
- Required dependencies.
- Licensing and attribution information.
- Production notes.
- Integration information.

### 16.1. Delivery Completeness

Before delivery, verify:

- Required files are present.
- Files use correct names and locations.
- No required dependencies are missing.
- Source materials are preserved when required.
- Exported audio has been validated.
- Licensing records are available.
- Intended feature or consumer is identified.

### 16.2. Delivery Status

Use clear statuses when tracking audio production:

| Status | Meaning |
|---|---|
| Planned | Requirements identified, production not started. |
| In Progress | Recording, composition, editing, or sound design is underway. |
| In Review | Awaiting review or feedback. |
| Changes Required | Revisions are needed. |
| Blocked | Progress is prevented by an unresolved dependency or issue. |
| Ready for Integration | Production and review are complete; engine integration remains. |
| Integrated | Asset has been added to the game project. |
| Accepted | Applicable artistic, technical, licensing, and delivery requirements are satisfied. |
| Deprecated | Asset is no longer intended for active use. |

Projects MAY use a simpler status model when appropriate, provided the meaning of each status remains clear.

## 17. Revision Management

Audio assets requiring changes MUST return to the appropriate production stage.

### 17.1. Revision Process

When revising an asset:

1. Identify the review feedback.
2. Determine the affected source and exported files.
3. Make the required changes.
4. Preserve unrelated approved work.
5. Regenerate affected exports.
6. Validate the revised audio.
7. Submit it for review when required.
8. Revalidate engine integration when the change affects the final asset.

### 17.2. Revision Scope

Changes SHOULD be limited to the identified problem unless broader improvements are justified.

Avoid introducing unrelated modifications during a revision.

### 17.3. Revision History

Significant revisions SHOULD be traceable through version control or production records.

Do not maintain unnecessary manual version histories when the repository already provides reliable history.

### 17.4. Approved Asset Changes

Changes to accepted audio SHOULD be evaluated for their impact on:

- Existing playback systems.
- Other audio assets.
- Loudness consistency.
- Gameplay feedback.
- Dialogue and music balance.
- Performance.
- Previously validated scenes.

Changes to shared or high-impact audio assets SHOULD receive appropriate review.

## 18. Audio Maintenance and Retirement

Audio assets MUST be maintained when changes to the project affect their continued use.

### 18.1. Maintenance

Maintenance activities MAY include:

- Correcting audio defects.
- Updating source recordings.
- Revising processing.
- Updating export settings.
- Replacing outdated formats.
- Improving loudness consistency.
- Updating dependencies.
- Revising audio variations.
- Updating licensing information.

### 18.2. Replacement

Before replacing an audio asset:

1. Identify its current consumers.
2. Check dependencies and shared usage.
3. Confirm that the replacement satisfies relevant requirements.
4. Update affected references.
5. Validate affected features and audio mixes.
6. Preserve source and licensing records when required.

### 18.3. Retirement

When retiring an asset:

- Confirm that it is no longer required.
- Identify references and dependencies.
- Remove or replace active usages.
- Preserve source and licensing records when required.
- Update relevant documentation.
- Remove obsolete files only after dependency validation.

Do not remove audio assets solely because they are not currently referenced by an open scene. They may be loaded dynamically or referenced through configuration.

## 19. Audio Production Tracking

Projects SHOULD maintain enough production tracking to understand audio asset status, ownership, dependencies, and outstanding work.

Tracking MAY use:

- Issue trackers.
- Project boards.
- Audio asset inventories.
- Version control history.
- Production documents.
- Lightweight metadata.

### 19.1. Audio Asset Records

For important or complex assets, record:

- Asset identifier.
- Asset name.
- Owning feature.
- Audio category.
- Production status.
- Assigned contributor, when applicable.
- Relevant references.
- Dependencies.
- Source location.
- Final asset location.
- Licensing information, when applicable.
- Review outcome.
- Known limitations.

Do not create separate asset records for every minor sound when doing so provides no meaningful production value.

### 19.2. Production Visibility

The project owner SHOULD be able to identify:

- Which audio assets are planned.
- Which assets are being produced.
- Which assets are awaiting review.
- Which assets are blocked.
- Which assets are ready for integration.
- Which assets have been accepted.
- Which assets require replacement or maintenance.

## 20. AI-Assisted Audio Production

AI agents MAY assist with audio planning, reference organization, sound generation, editing, production preparation, review, and integration.

AI-assisted work MUST follow the same production and quality requirements as other audio work.

### 20.1. Agent Responsibilities

AI agents MUST:

1. Read the project's approved audio direction and asset requirements.
2. Identify the intended purpose and owning feature.
3. Follow naming and directory conventions.
4. Preserve available source materials.
5. Verify licensing and attribution information.
6. Avoid unapproved changes to established audio direction.
7. Validate exported audio where possible.
8. Check playback and integration when possible.
9. Identify missing requirements and unresolved dependencies.
10. Report known limitations honestly.
11. Request human review when artistic judgment or approval is required.

### 20.2. Controlled Autonomy

AI agents MAY perform routine audio preparation and integration within an approved task's scope.

They MUST request approval before:

- Changing established audio direction.
- Replacing important approved audio.
- Modifying shared audio assets in ways that affect multiple features.
- Introducing substantial new audio dependencies.
- Making irreversible production changes.
- Accepting subjective audio decisions reserved for the project owner.

### 20.3. Honest Reporting

AI agents MUST distinguish between:

- Audio source acquired.
- Audio recorded or generated.
- Audio edited.
- Audio mixed.
- Audio mastered.
- Audio exported.
- Audio reviewed.
- Audio integrated.
- Audio playback validated.
- Audio accepted.

Completing one stage MUST NOT be reported as completing all subsequent stages.

AI agents MUST NOT claim to have listened to, mixed, mastered, or validated audio when those activities have not actually been performed.

## 21. Audio Pipeline Completion Checklist

Before considering an audio production task complete, verify the applicable requirements:

- [ ] Asset purpose and requirements are defined.
- [ ] Relevant references are available.
- [ ] Audio direction is approved.
- [ ] Recording or source acquisition is complete.
- [ ] Editing and sound design are complete.
- [ ] Required review is complete.
- [ ] Mixing and processing are complete.
- [ ] Mastering and export preparation are complete.
- [ ] Exported audio has been inspected and listened to.
- [ ] Source materials are preserved when required.
- [ ] Naming and directory conventions are followed.
- [ ] Licensing and attribution requirements are satisfied.
- [ ] Asset is integrated into the intended feature.
- [ ] Playback and contextual validation are complete.
- [ ] Dependencies and references are correct.
- [ ] Relevant documentation or tracking records are updated.
- [ ] Known limitations are reported.

Non-applicable requirements SHOULD be identified rather than treated as failures.

## 22. Exceptions

Exceptions MAY be permitted when justified by:

- Artistic requirements.
- Technical constraints.
- Platform limitations.
- External production dependencies.
- Accessibility requirements.
- Production schedule constraints.
- Experimental audio approaches.

Exceptions MUST have a clear justification and identify relevant risks.

Significant or lasting exceptions SHOULD be documented and approved by the project owner.

## 23. Related Documents

- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/02_technical_standards/ENGINE_STANDARDS.md`
- `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md`
- `docs/02_technical_standards/RESOURCE_MANAGEMENT.md`
- `docs/03_art_audio_standards/AUDIO_ASSET_STANDARDS.md`
- `docs/03_art_audio_standards/ART_PIPELINE.md`

## 24. Maintenance

This document SHOULD be reviewed periodically and updated when:

- Studio audio production workflows change.
- New audio categories or production methods are introduced.
- Recording or production tools change significantly.
- Engine integration requirements change.
- Recurring audio production issues are identified.
- Licensing or distribution requirements change.
- Improvements to production, review, and delivery practices are identified.

Changes MUST preserve the distinction between reusable studio production practices and project-specific audio requirements.

The project owner is responsible for approving changes to these standards.