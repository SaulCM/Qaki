# Level Design Guidelines

## 1. Purpose

This document establishes reusable guidelines for designing, structuring, evaluating, and refining levels and playable spaces.

Its purpose is to ensure that game environments support intended gameplay, communicate information effectively, encourage exploration, and provide coherent spatial experiences.

These guidelines apply to both handcrafted and procedurally generated environments.

## 2. Scope

These guidelines cover:

- Level structure and spatial organization.
- Player navigation and orientation.
- Exploration and discovery.
- Environmental storytelling.
- Spatial progression and pacing.
- Encounters and gameplay spaces.
- Landmarks and points of interest.
- Environmental hazards and obstacles.
- Level readability and visual communication.
- Verticality and spatial relationships.
- Level prototyping and validation.
- Procedural level design considerations.

These guidelines do not prescribe a specific level editor, engine implementation, art style, or game genre.

Related specialized topics are covered by:

- Gameplay mechanics: `gameplay_design_guidelines.md`.
- Core gameplay loops: `core_loop_design_guidelines.md`.
- Difficulty and challenge: `difficulty_design_guidelines.md`.
- Game design principles: `design_principles.md`.
- Numerical and systemic balance: `balancing_guidelines.md`.

## 3. Level Design Principles

### 3.1 Gameplay First

Every significant playable space SHOULD support an intended gameplay purpose.

Level design SHOULD consider:

- What the player does in the space.
- What decisions the space encourages.
- What challenges or opportunities it presents.
- How it supports the game's core experience.
- How it connects to other gameplay spaces.
- What information the player needs to understand the environment.

Visual appeal SHOULD complement gameplay rather than compromise essential functionality.

### 3.2 Spatial Clarity

Players SHOULD be able to understand the spatial information necessary to navigate and interact with the environment.

Designers SHOULD consider:

- Readable paths and boundaries.
- Recognizable landmarks.
- Clear entrances and exits.
- Distinguishable interactive objects.
- Understandable elevation changes.
- Consistent environmental conventions.
- Appropriate visibility of important destinations.

Intentional disorientation MAY be used as a design tool, but it SHOULD support a deliberate gameplay or narrative purpose.

### 3.3 Meaningful Spatial Choices

Levels SHOULD provide meaningful spatial decisions when appropriate.

Examples include:

- Choosing between alternative routes.
- Taking a safer or more dangerous path.
- Exploring optional areas.
- Using environmental advantages.
- Selecting different approaches to an encounter.
- Deciding when to continue or retreat.

Alternative routes SHOULD offer distinguishable benefits, risks, or experiences rather than existing solely to increase map complexity.

### 3.4 Environmental Consistency

Playable spaces SHOULD follow coherent spatial and environmental rules.

Designers SHOULD maintain consistency in:

- Architecture and geography.
- Environmental logic.
- Traversal restrictions.
- Visual language.
- Navigation conventions.
- Interactive object placement.
- Connections between spaces.

Exceptions SHOULD be intentional and understandable within the game's context.

### 3.5 Purposeful Complexity

Level complexity SHOULD be proportional to the intended player experience.

Designers SHOULD avoid:

- Unnecessary corridors and dead ends.
- Repetitive spaces without meaningful variation.
- Excessive navigation complexity.
- Unclear progression.
- Decorative elements that obscure important gameplay information.
- Large spaces without sufficient gameplay purpose.

Complexity SHOULD create meaningful decisions, discoveries, or experiences.

## 4. Level Objectives and Design Intent

### 4.1 Define the Level's Purpose

Before designing a level, establish its primary purpose.

A level MAY be designed to support:

- Exploration.
- Combat.
- Traversal.
- Puzzle solving.
- Resource gathering.
- Narrative progression.
- Social interaction.
- Survival.
- A combination of several activities.

The primary purpose SHOULD be identifiable even when the level supports multiple activities.

### 4.2 Define Design Goals

Each significant level SHOULD establish measurable or observable design goals.

Examples include:

- Encourage exploration of optional areas.
- Teach a new traversal mechanic.
- Introduce a new enemy type.
- Create a memorable environmental landmark.
- Provide multiple approaches to an encounter.
- Establish a clear connection between two major areas.
- Support a specific narrative event.

Design goals SHOULD describe intended player experiences and behaviors rather than merely listing environmental assets.

### 4.3 Establish Constraints

Level design SHOULD account for relevant constraints, including:

- Gameplay mechanics.
- Player movement capabilities.
- Camera perspective.
- Character and object scale.
- Technical performance.
- Available assets.
- Platform limitations.
- Narrative requirements.
- Accessibility requirements.
- Production scope.

Important constraints SHOULD be identified before extensive level production.

## 5. Spatial Structure and Layout

### 5.1 Level Structure

A level SHOULD have an understandable spatial organization.

Common structural patterns include:

- Linear: progression follows a primarily directed path.
- Branching: the player chooses between alternative paths.
- Hub-and-spoke: a central area connects to several destinations.
- Open-ended: multiple directions and destinations are available.
- Loop-based: paths reconnect to previously visited areas.
- Layered: spaces connect through different elevations or vertical routes.
- Hybrid: combines multiple structural patterns.

The selected structure SHOULD support the intended gameplay experience.

No structural pattern is inherently superior to another.

### 5.2 Spatial Hierarchy

Levels SHOULD establish a recognizable hierarchy of spaces.

A level MAY contain:

- Main areas.
- Secondary areas.
- Transition spaces.
- Encounter spaces.
- Safe spaces.
- Optional areas.
- Secret areas.
- Landmarks.
- Critical progression locations.

The hierarchy SHOULD communicate the relative importance of spaces through layout, visual design, navigation, or gameplay context.

### 5.3 Area Connections

Connections between spaces SHOULD be intentional and understandable.

Designers SHOULD consider:

- Entry and exit locations.
- Direction of travel.
- Visibility between connected spaces.
- Traversal requirements.
- Transition duration.
- Gameplay consequences.
- Potential backtracking.
- Spatial continuity.

Connections SHOULD avoid creating unnecessary confusion or breaking the player's understanding of the environment.

### 5.4 Scale and Proportion

Level dimensions SHOULD be appropriate for:

- Player movement speed.
- Interaction distance.
- Camera behavior.
- Encounter requirements.
- Environmental storytelling.
- Expected traversal time.
- Available gameplay activities.

Large environments SHOULD justify their scale through exploration, gameplay opportunities, atmosphere, or narrative purpose.

Small spaces SHOULD provide sufficient room for their intended interactions.

## 6. Navigation and Player Orientation

### 6.1 Navigation Principles

Players SHOULD be able to determine where they are and identify reasonable ways to reach relevant destinations.

Navigation SHOULD be supported through:

- Spatial layout.
- Environmental landmarks.
- Lighting and contrast.
- Distinctive architecture.
- Environmental composition.
- Signage or symbols.
- Camera framing.
- Interface indicators when appropriate.

The level SHOULD communicate important navigation information through the environment whenever practical.

### 6.2 Landmarks

Landmarks SHOULD help players recognize and remember important locations.

Effective landmarks are generally:

- Visually distinctive.
- Easy to recognize from relevant viewpoints.
- Consistent with the environment.
- Useful for orientation.
- Appropriate to the level's scale.

Landmarks MAY also provide narrative context or gameplay opportunities.

### 6.3 Wayfinding

Wayfinding is the process through which players understand where to go and how to reach a destination.

Designers SHOULD use environmental cues to guide players without unnecessarily removing exploration.

Examples include:

- Distinctive paths.
- Changes in lighting.
- Framing important destinations.
- Recognizable architectural features.
- Environmental movement.
- Visual contrasts.
- Sound cues.
- Consistent object placement.

Important routes SHOULD be distinguishable from inaccessible or purely decorative spaces.

### 6.4 Navigation Difficulty

Navigation complexity SHOULD match the intended experience.

Designers SHOULD evaluate:

- How easily players identify the main route.
- Whether optional routes are discoverable.
- Whether backtracking is understandable.
- Whether players can recover from taking an unintended path.
- Whether the environment provides enough orientation cues.

Intentional maze-like structures or disorientation SHOULD be validated through playtesting.

## 7. Exploration and Discovery

### 7.1 Exploration Design

Exploration SHOULD reward player curiosity with meaningful discoveries.

Discoveries MAY include:

- Resources.
- Hidden areas.
- Environmental stories.
- Collectibles.
- Optional encounters.
- Shortcuts.
- New gameplay opportunities.
- World information.
- Unique visual experiences.

Exploration SHOULD offer value appropriate to the time and effort required.

### 7.2 Optional Areas

Optional areas SHOULD provide a distinguishable experience or reward.

Designers SHOULD consider:

- Why the player would explore the area.
- How the area is discovered.
- What makes it different.
- What risks or costs it introduces.
- Whether its reward justifies the effort.

Optional areas SHOULD NOT exist solely to increase level size.

### 7.3 Secrets

Secrets SHOULD be discoverable through understandable environmental clues, patterns, or interactions.

Their difficulty SHOULD be appropriate to their importance and the intended audience.

Secret placement SHOULD avoid relying exclusively on arbitrary or invisible interaction requirements unless that behavior is an intentional part of the design.

### 7.4 Backtracking

Backtracking MAY support exploration, progression, and spatial familiarity.

When used, designers SHOULD consider:

- Whether returning through an area remains interesting.
- Whether new routes or shortcuts become available.
- Whether the environment changes.
- Whether previously inaccessible locations become reachable.
- Whether repeated traversal creates unnecessary friction.

Backtracking SHOULD have a clear purpose.

## 8. Spatial Progression and Pacing

### 8.1 Progression Structure

Levels SHOULD organize spaces to support an intentional progression of player experiences.

Progression MAY involve:

- Introducing a mechanic.
- Allowing the player to practice.
- Increasing environmental complexity.
- Combining previously introduced mechanics.
- Presenting a major challenge.
- Providing a recovery or transition space.

The order of spaces SHOULD support the intended learning and experience progression.

### 8.2 Pacing Variation

Levels SHOULD balance different types of gameplay spaces.

Depending on the game, these MAY include:

- Exploration areas.
- Combat encounters.
- Traversal sections.
- Puzzle spaces.
- Safe zones.
- Narrative sequences.
- Resource management areas.
- Rest or recovery spaces.

Variation SHOULD serve the intended experience rather than follow a rigid formula.

### 8.3 Intensity and Transitions

Transitions between spaces SHOULD consider changes in:

- Gameplay intensity.
- Player attention.
- Environmental scale.
- Threat level.
- Narrative context.
- Available resources.
- Player expectations.

Important transitions SHOULD provide enough context for players to understand the change in situation.

### 8.4 Player Time

Level traversal and exploration SHOULD respect the player's time.

Designers SHOULD evaluate:

- Repeated travel distances.
- Unnecessary waiting.
- Excessive empty spaces.
- Repetitive traversal.
- Frequency of meaningful interactions.
- Opportunities to reduce unnecessary navigation friction.

Traversal time SHOULD contribute to the intended experience.

## 9. Encounter and Combat Space Design

### 9.1 Encounter Purpose

Encounter spaces SHOULD support the intended gameplay challenge.

Designers SHOULD consider:

- Available movement space.
- Enemy and player positioning.
- Cover and obstacles.
- Sightlines.
- Entrances and exits.
- Environmental hazards.
- Available resources.
- Tactical opportunities.
- Camera limitations.

Encounter spaces SHOULD be designed around actual gameplay mechanics rather than relying exclusively on visual composition.

### 9.2 Spatial Variety

Different encounters SHOULD use spatial arrangements appropriate to their objectives.

Possible arrangements include:

- Open arenas.
- Narrow corridors.
- Multi-level spaces.
- Chokepoints.
- Defensive positions.
- Flanking routes.
- Environmental hazard zones.
- Mixed open and enclosed areas.

Spatial variety SHOULD create meaningful differences in player decisions.

### 9.3 Tactical Opportunities

Encounter spaces MAY provide opportunities for:

- Positioning.
- Flanking.
- Retreating.
- Taking cover.
- Using environmental hazards.
- Controlling access points.
- Exploiting elevation.
- Approaching from different directions.

These opportunities SHOULD be understandable and compatible with the game's mechanics.

### 9.4 Encounter Readability

Players SHOULD be able to identify relevant threats, obstacles, and tactical opportunities.

Important gameplay information SHOULD remain visible or otherwise communicated through appropriate feedback.

Encounter geometry MUST NOT unintentionally prevent essential interactions or create unfair situations.

Detailed encounter difficulty and numerical tuning SHOULD follow the corresponding gameplay and balancing guidelines.

## 10. Environmental Storytelling

### 10.1 Environmental Narrative

The environment MAY communicate narrative information without requiring direct exposition.

Designers SHOULD consider how the following elements contribute to world understanding:

- Architecture.
- Object placement.
- Environmental damage.
- Lighting.
- Signs of previous activity.
- Character presence.
- Spatial relationships.
- Changes in environmental conditions.

Environmental storytelling SHOULD be consistent with the world's established logic.

### 10.2 Narrative Through Space

Spatial composition MAY communicate:

- Historical events.
- Cultural identity.
- Social structures.
- Character relationships.
- Environmental conditions.
- Conflict.
- Progression.
- World changes.

Important narrative spaces SHOULD be designed with attention to player viewpoint, movement, and opportunities for observation.

### 10.3 Environmental Consistency

Environmental details SHOULD reinforce the identity of the location.

Repeated architectural, material, lighting, and object-placement patterns MAY help establish a recognizable visual language.

Visual variation SHOULD remain coherent with the setting.

## 11. Verticality and Three-Dimensional Spaces

When levels include meaningful elevation or three-dimensional traversal, designers SHOULD account for vertical relationships.

Consider:

- Visibility between elevations.
- Traversal connections.
- Fall consequences.
- Accessible and inaccessible surfaces.
- Vertical combat opportunities.
- Camera limitations.
- Navigation between levels.
- Spatial readability.

Vertical spaces SHOULD communicate which surfaces are traversable, interactive, or decorative.

### 11.1 Vertical Navigation

Players SHOULD understand how to move between different elevations when vertical navigation is important.

Possible navigation elements include:

- Stairs.
- Ladders.
- Elevators.
- Ramps.
- Jumps.
- Climbing surfaces.
- Lifts.
- Traversal abilities.

Vertical transitions SHOULD be consistent with the game's movement mechanics.

### 11.2 Camera Considerations

In games with fixed, isometric, or constrained camera perspectives, designers MUST consider how elevation and geometry affect visibility.

Important gameplay elements SHOULD NOT become unintentionally hidden behind environmental objects or terrain.

## 12. Environmental Hazards and Obstacles

### 12.1 Hazard Design

Environmental hazards SHOULD have clear gameplay purposes.

Hazards MAY:

- Create traversal challenges.
- Restrict movement.
- Encourage route selection.
- Introduce timing decisions.
- Require specific abilities.
- Modify encounter spaces.
- Communicate environmental danger.

### 12.2 Hazard Communication

Players SHOULD receive appropriate indications of relevant hazards.

Communication MAY use:

- Visual indicators.
- Audio cues.
- Environmental behavior.
- Animation.
- Interface warnings.
- Contextual clues.

Hazard behavior SHOULD be consistent with the information provided to the player.

### 12.3 Obstacle Design

Obstacles SHOULD support navigation, gameplay, or environmental composition.

Designers SHOULD distinguish between:

- Traversable obstacles.
- Interactive obstacles.
- Destructible obstacles.
- Blocking geometry.
- Decorative geometry.

Visual appearance SHOULD accurately communicate relevant collision and interaction behavior.

## 13. Safe Spaces and Recovery Areas

Safe spaces MAY provide opportunities for players to:

- Recover.
- Prepare.
- Manage resources.
- Interact with characters.
- Review progression.
- Save progress.
- Learn new information.
- Plan future actions.

Their placement SHOULD consider the surrounding gameplay intensity and the intended player experience.

Safe spaces SHOULD have clearly defined gameplay rules, particularly when threats or environmental hazards may affect them.

## 14. Level Design for Procedural Generation

Procedurally generated levels MUST preserve the fundamental gameplay and spatial requirements of the game.

Randomness alone does not guarantee interesting or functional level design.

### 14.1 Generation Constraints

Procedural generation SHOULD define constraints for:

- Valid spatial layouts.
- Connectivity.
- Traversability.
- Player starting positions.
- Important destinations.
- Required progression elements.
- Encounter placement.
- Resource distribution.
- Environmental boundaries.
- Difficulty requirements.

### 14.2 Connectivity and Reachability

Generated levels MUST ensure that required destinations are reachable through valid paths.

Generation SHOULD validate:

- Connected gameplay areas.
- Valid entrances and exits.
- Required progression paths.
- Reachable critical resources.
- Accessible interaction points.
- Absence of unintended isolated areas.

### 14.3 Controlled Variation

Procedural systems SHOULD produce meaningful variation rather than arbitrary differences.

Variation MAY involve:

- Room or area arrangements.
- Encounter configurations.
- Resource placement.
- Environmental composition.
- Optional routes.
- Environmental hazards.
- Narrative details.

Generated content SHOULD preserve the intended gameplay identity.

### 14.4 Validation and Failure Handling

Procedural generation SHOULD include validation mechanisms to detect invalid layouts.

When generation fails, the system SHOULD use an appropriate fallback strategy, such as:

- Regenerating the affected section.
- Selecting a validated alternative.
- Applying corrective constraints.
- Rejecting the generated layout.

Critical progression requirements MUST NOT depend on unvalidated random placement.

### 14.5 Repeatability

When useful for testing and debugging, procedural generation SHOULD support reproducible results through controlled random seeds.

This allows developers to:

- Reproduce reported issues.
- Compare generation changes.
- Validate specific layouts.
- Investigate edge cases.

## 15. Performance and Technical Considerations

Level design SHOULD consider the technical limitations of the target platform and the engine.

Designers and developers SHOULD evaluate:

- Geometry complexity.
- Object and node counts.
- Lighting and shadow costs.
- Physics and collision complexity.
- Visibility and occlusion.
- Texture and material usage.
- Audio source distribution.
- Loading and streaming requirements.
- Navigation and pathfinding costs.
- Runtime memory consumption.

Optimization SHOULD be based on measured performance rather than assumptions.

Visual and spatial quality SHOULD be preserved while addressing demonstrated performance problems.

Godot-specific implementation MUST follow the project's technical standards.

## 16. Level Prototyping and Validation

### 16.1 Blockout First

Significant levels SHOULD begin with a functional blockout before detailed visual production.

Blockouts MAY use:

- Primitive geometry.
- Simple materials.
- Placeholder objects.
- Basic lighting.
- Temporary navigation indicators.
- Simplified encounter elements.

The blockout SHOULD communicate the intended spatial layout and support actual gameplay testing.

### 16.2 Functional Validation

Before committing to detailed production, validate:

- Player movement through the level.
- Spatial scale and proportions.
- Navigation and orientation.
- Route connectivity.
- Encounter functionality.
- Interaction placement.
- Camera behavior.
- Progression requirements.
- Intended pacing.

### 16.3 Playtesting

Levels SHOULD be evaluated through actual player interaction.

Testing SHOULD observe:

- Where players move.
- Where they stop.
- Which routes they choose.
- Whether they recognize landmarks.
- Whether they discover optional areas.
- Where they become confused.
- Whether encounters function as intended.
- Whether traversal feels appropriate.
- Whether the level supports its design goals.

Developers SHOULD distinguish between intended challenge and unintended navigation or spatial confusion.

### 16.4 Iteration

Level design SHOULD be refined through an iterative process:

1. Define design goals.
2. Create a blockout.
3. Validate basic traversal and functionality.
4. Conduct playtesting.
5. Identify spatial and gameplay problems.
6. Modify the layout.
7. Repeat validation.
8. Add environmental detail and visual polish.
9. Perform integration and regression testing.

Detailed production SHOULD NOT proceed on the assumption that an untested blockout is already successful.

## 17. Level Design Documentation

Significant levels SHOULD have documentation sufficient to communicate their intended structure and gameplay.

Documentation MAY include:

- Level name and purpose.
- Design goals.
- Spatial structure.
- Area descriptions.
- Player starting location.
- Critical destinations.
- Main and optional routes.
- Landmarks.
- Encounter locations.
- Progression requirements.
- Environmental hazards.
- Narrative elements.
- Technical constraints.
- Validation criteria.
- Open design questions.

Useful supporting materials MAY include:

- Top-down layout diagrams.
- Blockout screenshots.
- Flow diagrams.
- Reference images.
- Encounter sketches.
- Navigation maps.
- Procedural generation constraints.

Documentation SHOULD remain consistent with the actual implemented level.

## 18. AI-Assisted Level Design

AI agents assisting with level design MUST:

1. Read relevant game-specific design documents before proposing changes.
2. Follow these reusable level design guidelines.
3. Preserve approved level design decisions.
4. Respect established gameplay mechanics and movement capabilities.
5. Consider navigation, connectivity, and player orientation.
6. Evaluate the impact of proposed changes on adjacent spaces.
7. Identify assumptions and unresolved spatial requirements.
8. Avoid introducing unnecessary level complexity.
9. Recommend blockouts and playtesting when spatial uncertainty is significant.
10. Document significant design changes.
11. Request human approval for significant changes to approved level structure or progression.

AI agents MUST NOT claim that a level is playable, navigable, balanced, or validated without appropriate implementation and testing evidence.

## 19. Level Design Review Checklist

### Design Intent
- [ ] The level has a clear purpose.
- [ ] Design goals are defined.
- [ ] The layout supports intended gameplay.
- [ ] Spatial complexity is justified.
- [ ] Relevant technical and production constraints are identified.

### Layout and Navigation
- [ ] The spatial structure is understandable.
- [ ] Important areas are connected appropriately.
- [ ] Required destinations are reachable.
- [ ] Navigation cues are sufficient.
- [ ] Landmarks support orientation.
- [ ] Optional routes provide meaningful value.
- [ ] Backtracking is intentional.

### Gameplay
- [ ] Spaces support their intended activities.
- [ ] Encounter areas provide appropriate geometry.
- [ ] Hazards and obstacles are communicated.
- [ ] Progression is coherent.
- [ ] Safe spaces and transitions are appropriately placed.
- [ ] Environmental interactions behave consistently.

### Environmental Quality
- [ ] Environmental composition supports the setting.
- [ ] Visual language is coherent.
- [ ] Environmental storytelling is intentional.
- [ ] Important gameplay information remains readable.
- [ ] Camera and visibility limitations are considered.

### Validation
- [ ] A functional blockout has been evaluated.
- [ ] Traversal and connectivity have been tested.
- [ ] Navigation has been evaluated.
- [ ] Encounter functionality has been tested.
- [ ] Playtesting observations are documented when available.
- [ ] Performance risks have been considered.
- [ ] Unresolved issues are documented.

### Documentation and Integration
- [ ] Level design documentation is updated.
- [ ] Dependencies on gameplay systems are identified.
- [ ] Approved design decisions are preserved.
- [ ] Implemented behavior matches documented intent.

## 20. Related Documents

Refer to the following documents when they exist in the repository:

- `design_principles.md`
- `gameplay_design_guidelines.md`
- `core_loop_design_guidelines.md`
- `difficulty_design_guidelines.md`
- `balancing_guidelines.md`
- `../00_studio_standards/development_philosophy.md`
- `../00_studio_standards/quality_standards.md`
- `../00_studio_standards/project_structure_standards.md`
- `../02_technical_standards/architecture_guidelines.md`

## 21. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- New level design practices are adopted.
- Existing guidelines become unclear or contradictory.
- Repeated level design problems reveal missing guidance.
- Changes to the studio's development philosophy affect level design.
- New production or procedural generation requirements emerge.

Updates MUST preserve the document's reusable nature and avoid introducing requirements that apply exclusively to a single game.

The project owner is responsible for approving changes to these studio-wide guidelines.