# Art Pipeline

## 1. Purpose

This document defines the standard workflow for producing, reviewing, integrating, and maintaining visual art assets across studio game projects.

Its purpose is to establish a predictable and maintainable art production process that supports:

- Consistent visual quality.
- Efficient asset production.
- Clear production responsibilities.
- Reliable asset handoffs.
- Controlled revisions.
- Integration with the game engine.
- Traceability of asset sources and changes.
- Collaboration between human contributors and AI agents.

These standards are reusable across projects. Individual game projects MUST define their own art direction, asset specifications, production priorities, technical constraints, and delivery requirements.

## 2. Scope

This pipeline applies to visual asset production, including:

- Concept art and visual references.
- Characters and creatures.
- Environments and level art.
- Props and interactive objects.
- 2D sprites and illustrations.
- 3D models.
- Textures and materials.
- User interface graphics.
- Icons and visual effects.
- Asset variants and revisions.
- Externally sourced and AI-generated visual assets.

Animation production is covered by `ANIMATION_STANDARDS.md`. Animation assets MUST still follow the relevant production, review, source management, and integration stages defined in this document.

Audio production is outside the scope of this document.

## 3. Pipeline Principles

All art production workflows SHOULD follow these principles.

### 3.1. Plan Before Production

Assets SHOULD have a defined purpose and production requirement before significant work begins.

Avoid producing assets without understanding their intended use, visual direction, and technical constraints.

### 3.2. Validate Early

Validate visual direction and technical feasibility before investing substantial production effort.

Use prototypes, blockouts, grayboxes, and representative samples when appropriate.

### 3.3. Work Incrementally

Produce assets in manageable stages.

Prefer early review of representative assets over completing large batches before discovering inconsistencies.

### 3.4. Preserve Source Materials

Maintain editable source files and production references whenever possible.

Final exported assets SHOULD be reproducible from their source materials.

### 3.5. Separate Production from Integration

Creating an asset and integrating it into the game are related but distinct activities.

An asset is not considered fully integrated merely because its source file exists or its exported file has been delivered.

### 3.6. Maintain Traceability

Asset sources, revisions, dependencies, licensing information, and important production decisions SHOULD be traceable.

### 3.7. Use Proportionate Process

The pipeline MUST remain practical for the project's size and production needs.

Do not introduce unnecessary approval stages, documentation, or tooling for simple assets.

## 4. Asset Production Lifecycle

The standard asset lifecycle consists of the following stages:

1. Asset planning.
2. Reference and requirements gathering.
3. Concept and visual direction.
4. Production.
5. Internal review.
6. Revision.
7. Export and preparation.
8. Engine integration.
9. Validation and acceptance.
10. Maintenance or retirement.

Not every asset requires a separate formal activity for every stage. Small or straightforward assets MAY combine stages when doing so does not compromise quality or traceability.

<escape>```mermaid
flowchart TD
    A[Asset Planning] --> B[References and Requirements]
    B --> C[Concept and Visual Direction]
    C --> D[Asset Production]
    D --> E[Internal Review]
    E -->|Changes Required| F[Revision]
    F --> E
    E -->|Accepted| G[Export and Preparation]
    G --> H[Engine Integration]
    H --> I[Technical and Visual Validation]
    I -->|Issues Found| F
    I -->|Accepted| J[Asset Acceptance]
    J --> K[Maintenance or Retirement]
```</escape>

## 5. Asset Planning

Before production begins, identify the asset's purpose and requirements.

### 5.1. Asset Identification

Define:

- Asset name or identifier.
- Asset category.
- Owning feature or system.
- Intended gameplay or presentation purpose.
- Target scene, character, environment, or interface.
- Whether the asset is new, a variant, or a replacement.
- Whether the asset is reusable.

### 5.2. Asset Requirements

Define the requirements relevant to the asset.

These MAY include:

- Visual description.
- Reference images.
- Dimensions and proportions.
- Resolution or polygon budget.
- Perspective and camera requirements.
- Color and material requirements.
- Required visual states.
- Supported variations.
- Expected viewing distance.
- Target platform.
- Engine compatibility.
- Performance constraints.
- Source file requirements.

Avoid specifying technical details that do not affect the asset's intended use.

### 5.3. Priority and Production Effort

Asset priority SHOULD reflect its impact on the game.

Consider:

- Gameplay importance.
- Player visibility.
- Frequency of use.
- Contribution to game identity.
- Dependencies on other assets.
- Production effort.
- Technical risk.

High-impact assets SHOULD receive earlier validation and review.

### 5.4. Dependencies

Identify dependencies before production.

Examples include:

- Character models requiring approved concept art.
- Materials requiring a base model.
- UI icons requiring an established visual language.
- Environment assets requiring modular dimensions.
- Animation assets requiring compatible rigs.
- Props requiring interaction specifications.

Dependencies SHOULD be resolved before they become production blockers.

## 6. Reference and Requirements Gathering

Collect the information necessary to guide asset creation.

References MAY include:

- Approved concept art.
- Project art direction.
- Photographs.
- Technical diagrams.
- Existing game assets.
- Licensed reference libraries.
- Historical or architectural references.
- Mood boards.
- Approved visual examples.

### 6.1. Reference Management

References SHOULD be organized and associated with the relevant asset or feature.

Record their source when attribution, licensing, or traceability matters.

References MUST NOT be treated as unrestricted source material. Their usage rights and intended purpose must be respected.

### 6.2. Reference Quality

References SHOULD communicate the intended:

- Shape.
- Proportions.
- Materials.
- Color.
- Lighting.
- Composition.
- Level of detail.
- Visual style.

Avoid collecting excessive references that do not contribute to a clear production direction.

### 6.3. Requirement Validation

Before production, verify that the available references and specifications are sufficient to begin.

If critical requirements are unclear, request clarification rather than making assumptions that could cause substantial rework.

## 7. Concept and Visual Direction

Concept development establishes the visual direction before full production.

### 7.1. Concept Art

Concept art MAY be used to explore:

- Silhouettes.
- Proportions.
- Color variations.
- Materials.
- Character identity.
- Environment composition.
- Prop designs.
- Visual states.

The amount of concept work SHOULD be proportional to the asset's importance and complexity.

### 7.2. Design Validation

Before full production, validate:

- Alignment with project art direction.
- Visual readability.
- Gameplay purpose.
- Technical feasibility.
- Compatibility with existing assets.
- Production effort.

Significant visual direction changes require project owner approval.

### 7.3. Blockouts and Prototypes

Use simplified representations when they can validate requirements more efficiently than finished assets.

Examples include:

- Graybox environment layouts.
- Primitive 3D models.
- Placeholder sprites.
- Basic UI wireframes.
- Temporary material samples.

Prototypes SHOULD answer specific design or technical questions.

## 8. Asset Production

Asset production converts approved requirements and visual direction into usable game assets.

### 8.1. Production Workflow

The production method depends on the asset category and selected tools.

Typical workflows include:

**2D assets**
- Sketching and composition.
- Shape and silhouette refinement.
- Color and shading.
- Cleanup.
- Layer organization.
- Export preparation.

**3D assets**
- Modeling.
- Topology refinement.
- UV preparation.
- Material creation.
- Texture authoring.
- Optimization.
- Export preparation.

**UI assets**
- Visual component design.
- Icon and graphic creation.
- State variations.
- Resolution and scaling validation.
- Export preparation.

These are examples rather than mandatory sequences. Production SHOULD use the workflow most appropriate to the asset.

### 8.2. Production Consistency

During production:

- Follow the approved visual direction.
- Use established naming conventions.
- Maintain consistent proportions and visual treatment.
- Reuse existing assets and materials where appropriate.
- Avoid unnecessary duplication.
- Preserve editable source materials.
- Validate the asset at its intended display size.
- Document significant deviations from requirements.

### 8.3. Asset Variants

When creating variants:

- Identify the shared base asset.
- Define the differences between variants.
- Reuse compatible source materials where appropriate.
- Maintain consistent naming.
- Avoid accidental changes to other variants.
- Validate each variant in its intended context.

### 8.4. Production Checkpoints

For complex or high-impact assets, use intermediate checkpoints.

Examples include:

- Initial silhouette.
- First visual pass.
- Material and texture pass.
- Detail refinement.
- Final production version.

Review checkpoints SHOULD identify meaningful problems early without introducing unnecessary approvals for every minor adjustment.

## 9. Internal Review

Produced assets SHOULD undergo a review before final export and integration.

### 9.1. Review Objectives

The review evaluates:

- Visual consistency.
- Compliance with asset requirements.
- Gameplay readability.
- Technical suitability.
- Production completeness.
- Source and licensing information.

### 9.2. Review Outcomes

An asset review SHOULD result in one of the following outcomes:

- **Accepted:** The asset satisfies its applicable requirements.
- **Changes Required:** The asset needs corrections before proceeding.
- **Blocked:** Missing information, dependencies, or technical issues prevent further work.
- **Rejected:** The asset is unsuitable for its intended purpose.

### 9.3. Review Feedback

Feedback SHOULD be:

- Specific.
- Actionable.
- Related to an identified requirement.
- Prioritized by impact.
- Clear about expected corrections.

Avoid vague feedback such as "make it better" without identifying the problem.

### 9.4. Review Authority

The project owner or designated reviewer is responsible for approving significant artistic decisions.

AI agents MAY prepare assets and perform preliminary reviews but MUST NOT independently approve changes to established art direction.

## 10. Revision Management

Assets requiring changes MUST return to the appropriate production stage.

### 10.1. Revision Process

When revising an asset:

1. Identify the review feedback.
2. Determine the affected source files and exported files.
3. Make the required changes.
4. Preserve unrelated approved work.
5. Regenerate affected outputs.
6. Validate the revised asset.
7. Submit it for review when required.

### 10.2. Revision Scope

Changes SHOULD be limited to the identified problem unless broader improvements are justified.

Avoid introducing unrelated modifications during a revision.

### 10.3. Revision History

Significant revisions SHOULD be traceable through version control or production records.

Do not maintain unnecessary manual version histories when the repository already provides reliable history.

### 10.4. Approved Asset Changes

Changes to an accepted asset SHOULD be evaluated for their impact on:

- Existing scenes.
- Gameplay behavior.
- Other asset variants.
- Materials and dependencies.
- Performance.
- Previously approved visual content.

Changes to shared or high-impact assets SHOULD receive appropriate review.

## 11. Export and Preparation

Once an asset is ready for integration, prepare its final deliverables.

### 11.1. Export Requirements

Verify:

- Correct file format.
- Correct dimensions or model scale.
- Correct orientation.
- Correct transparency.
- Correct color settings.
- Appropriate compression.
- Appropriate texture and material settings.
- No unintended cropping or missing elements.
- No unnecessary embedded content.

### 11.2. Source and Export Separation

Maintain a clear distinction between:

- Editable source files.
- Final exported assets.
- Temporary working files.
- Generated files.
- Engine-imported resources.

Temporary files SHOULD NOT be committed unless they are required for production or reproducibility.

### 11.3. Export Validation

Before integration, open or inspect the exported asset to verify that the export process did not introduce defects.

For complex assets, validate the result in the target application or engine.

### 11.4. Technical Pipeline

Technical importing, processing, compression, resource settings, and engine-specific asset handling MUST follow:

`docs/02_technical_standards/ASSET_PIPELINE.md`

This document defines production workflow and does not replace the technical pipeline.

## 12. Engine Integration

Assets MUST be integrated into the game project before they can be considered fully delivered.

### 12.1. Integration Preparation

Before integration:

- Verify the target feature and destination.
- Confirm asset naming and directory conventions.
- Check dependencies.
- Confirm required source files and licensing records.
- Identify scenes or resources that will reference the asset.

### 12.2. Integration in Godot

When integrating assets into Godot:

- Store assets in the appropriate feature-oriented directory.
- Follow project naming conventions.
- Configure import settings according to project standards.
- Verify resource references.
- Check material and texture assignments.
- Verify scene and node compatibility.
- Avoid unnecessary duplicated resources.
- Keep generated engine cache files out of version control.

### 12.3. Feature Ownership

Assets SHOULD be integrated into their owning feature.

Assets used by multiple features MAY be placed in shared locations when there is a clear ownership and reuse justification.

Avoid moving assets into shared storage merely because they might be reused in the future.

### 12.4. Integration Changes

When integration requires modifications to existing scenes, resources, or scripts:

- Inspect existing dependencies.
- Keep changes within the intended scope.
- Follow the relevant technical standards.
- Validate affected features.
- Report any additional changes or dependencies.

## 13. Validation and Acceptance

Integrated assets MUST be validated before final acceptance.

### 13.1. Visual Validation

Verify the asset:

- Appears correctly in the game.
- Matches the approved visual direction.
- Has correct proportions and scale.
- Has appropriate color and material appearance.
- Is readable in its intended context.
- Does not contain unintended visual artifacts.
- Does not obscure important gameplay information.

### 13.2. Technical Validation

Verify:

- The engine imports the asset correctly.
- Required resources load successfully.
- No missing resource references exist.
- Materials and textures render correctly.
- Scene dependencies work as expected.
- Relevant performance requirements are satisfied.
- No new engine errors or warnings are introduced.

### 13.3. Gameplay Validation

When applicable, verify:

- The asset appears in the correct gameplay context.
- Interactive elements remain readable.
- Collision and interaction behavior are correct.
- Visual states correspond to gameplay states.
- The asset does not interfere with navigation or player feedback.

### 13.4. Acceptance Criteria

An asset MAY be accepted when:

- Applicable visual requirements are satisfied.
- Technical integration is successful.
- Required review has been completed.
- Licensing and attribution requirements are satisfied.
- Relevant source files and documentation are preserved.
- Known limitations are recorded.

Acceptance MUST reflect actual validation. Assets that have not been tested MUST NOT be reported as fully validated.

## 14. Asset Delivery

A completed asset delivery SHOULD contain only the files and information necessary for its intended use and future maintenance.

Depending on the asset, deliverables MAY include:

- Final exported asset.
- Editable source file.
- Supporting textures and materials.
- Required dependencies.
- Reference materials.
- Licensing and attribution information.
- Relevant production notes.
- Integration information.

### 14.1. Delivery Completeness

Before delivery, verify that:

- Required files are present.
- Files use the correct names and locations.
- No required dependencies are missing.
- Source files are preserved when required.
- Exported files have been validated.
- Licensing records are available.
- The intended feature or consumer is identified.

### 14.2. Delivery Status

Use clear statuses when tracking asset production:

| Status | Meaning |
|---|---|
| Planned | Requirements identified, production not started. |
| In Progress | Asset production is underway. |
| In Review | Awaiting review or feedback. |
| Changes Required | Revisions are needed. |
| Blocked | Progress is prevented by an unresolved dependency or issue. |
| Ready for Integration | Production and review are complete; engine integration remains. |
| Integrated | Asset has been added to the game project. |
| Accepted | Applicable visual, technical, and delivery requirements are satisfied. |
| Deprecated | Asset is no longer intended for active use. |

Projects MAY use a simpler status model when appropriate, provided that the meaning of each status remains clear.

## 15. Asset Maintenance and Retirement

Assets MUST be maintained when changes to the project affect their continued use.

### 15.1. Maintenance

Maintenance activities MAY include:

- Updating source files.
- Correcting visual defects.
- Updating export settings.
- Replacing outdated formats.
- Updating material dependencies.
- Improving performance.
- Revising asset variants.
- Updating licensing information.

### 15.2. Replacement

Before replacing an asset:

1. Identify its current consumers.
2. Check dependencies and shared usage.
3. Confirm that the replacement satisfies the relevant requirements.
4. Update affected references.
5. Validate affected scenes and features.
6. Preserve historical source materials when required.

### 15.3. Retirement

When retiring an asset:

- Confirm that it is no longer required.
- Identify references and dependencies.
- Remove or replace active usages.
- Preserve source and licensing records when required.
- Update relevant asset documentation.
- Remove obsolete files only after dependency validation.

Do not remove an asset solely because it is not currently visible in the active scene.

## 16. Asset Pipeline and Production Tracking

Projects SHOULD maintain enough production tracking to understand asset status, ownership, dependencies, and outstanding work.

Tracking MAY use:

- Issue trackers.
- Project boards.
- Asset lists.
- Version control history.
- Production documents.
- Lightweight metadata.

### 16.1. Asset Records

For important or complex assets, record:

- Asset identifier.
- Asset name.
- Owning feature.
- Asset category.
- Production status.
- Assigned contributor, when applicable.
- Relevant references.
- Dependencies.
- Source location.
- Final asset location.
- Licensing information, when applicable.
- Review outcome.
- Known limitations.

Do not create separate asset records for every minor asset unless doing so provides meaningful production value.

### 16.2. Production Visibility

The project owner SHOULD be able to identify:

- Which assets are planned.
- Which assets are being produced.
- Which assets are awaiting review.
- Which assets are blocked.
- Which assets are ready for integration.
- Which assets have been accepted.
- Which assets require replacement or maintenance.

## 17. AI-Assisted Art Production

AI agents MAY assist with asset planning, reference organization, concept exploration, asset creation, revision, export preparation, and integration.

AI-assisted work MUST follow the same quality and production requirements as other asset work.

### 17.1. Agent Responsibilities

AI agents MUST:

1. Read the relevant project art direction and asset specifications.
2. Identify the owning feature and intended asset usage.
3. Follow the established production and naming conventions.
4. Preserve existing source files.
5. Verify available licensing and attribution information.
6. Avoid unapproved changes to established visual direction.
7. Validate exported and integrated assets where possible.
8. Identify missing requirements and unresolved dependencies.
9. Report incomplete work and known limitations.
10. Request human review when artistic judgment or approval is required.

### 17.2. Controlled Autonomy

AI agents MAY perform routine asset preparation and integration within an approved task's scope.

They MUST request approval before:

- Changing the established art direction.
- Replacing important approved assets.
- Modifying widely shared assets in ways that affect multiple features.
- Introducing substantial new asset dependencies.
- Making irreversible production changes.
- Accepting subjective artistic decisions reserved for the project owner.

### 17.3. Honest Reporting

AI agents MUST distinguish between:

- Asset created.
- Asset exported.
- Asset reviewed.
- Asset integrated.
- Asset technically validated.
- Asset accepted.

Completing one stage MUST NOT be reported as completing all subsequent stages.

## 18. Exceptions

Exceptions MAY be permitted when justified by:

- Project-specific production requirements.
- Artistic experimentation.
- Technical constraints.
- External production dependencies.
- Platform limitations.
- Production schedule constraints.

Exceptions MUST have a clear justification and identify relevant risks.

Significant or lasting exceptions SHOULD be documented and approved by the project owner.

## 19. Art Pipeline Completion Checklist

Before considering an asset production task complete, verify the applicable requirements:

- [ ] Asset purpose and requirements are defined.
- [ ] Relevant references are available.
- [ ] Production follows the approved art direction.
- [ ] Required visual review is complete.
- [ ] Requested revisions are addressed.
- [ ] Source files are preserved where required.
- [ ] Exported assets are validated.
- [ ] Naming and directory conventions are followed.
- [ ] Licensing and attribution requirements are satisfied.
- [ ] Asset is integrated into the intended feature.
- [ ] Visual and technical validation is complete.
- [ ] Dependencies and references are correct.
- [ ] Relevant documentation or tracking records are updated.
- [ ] Known limitations are reported.

Non-applicable requirements SHOULD be identified rather than treated as failures.

## 20. Related Documents

- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/02_technical_standards/ASSET_PIPELINE.md`
- `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md`
- `docs/03_art_audio_standards/ART_ASSET_STANDARDS.md`
- `docs/03_art_audio_standards/ANIMATION_STANDARDS.md`

## 21. Maintenance

This document SHOULD be reviewed periodically and updated when:

- Art production workflows change.
- New asset categories are introduced.
- Production tools or workflows change significantly.
- Recurring production issues are identified.
- Engine integration requirements change.
- Improvements to review and delivery practices are identified.

Changes MUST preserve the distinction between reusable studio production practices and project-specific asset requirements.

The project owner is responsible for approving changes to these standards.