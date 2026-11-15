# Progression Design Guidelines

## 1. Purpose

This document defines reusable guidelines for designing, implementing, and evaluating player progression systems in games developed by the studio.

Its purpose is to ensure progression systems provide meaningful advancement, reinforce the intended player experience, support gameplay depth, and maintain consistency throughout the game.

These guidelines apply to progression systems regardless of genre, platform, or progression model.

## 2. Scope

These guidelines cover:

- Player advancement and growth.
- Character and ability progression.
- Skill trees and specialization systems.
- Equipment and capability progression.
- Content and feature unlocks.
- Level-based and milestone-based progression.
- Narrative and world progression.
- Long-term progression and retention.
- Progression pacing and reward structures.
- Progression dependencies and prerequisites.
- Progression testing and validation.

These guidelines do not prescribe a specific progression model. Each game must select progression systems appropriate to its design goals and intended player experience.

## 3. Core Progression Principles

### 3.1 Meaningful Advancement

Progression MUST provide meaningful changes to the player's experience.

Advancement may provide:

- New capabilities.
- Improved existing capabilities.
- Access to new content.
- New gameplay options.
- Increased strategic possibilities.
- Greater understanding of the game world.
- Changes in player responsibilities or challenges.

Progression SHOULD create meaningful differences between the player's current and previous states.

Numerical increases alone SHOULD NOT be considered sufficient unless they support an intentional gameplay purpose.

### 3.2 Clear Progression Goals

Players SHOULD understand:

- What they are progressing toward.
- What actions contribute to advancement.
- What rewards or changes advancement provides.
- What requirements must be fulfilled.
- What remains unavailable and why.

Long-term goals MAY contain intermediate milestones to make progress easier to understand and evaluate.

### 3.3 Consistency

Progression systems MUST follow consistent rules.

Similar actions, achievements, and requirements SHOULD produce predictable results unless an intentional design exception exists.

Progression terminology, rewards, unlock conditions, and feedback MUST remain consistent throughout the game.

### 3.4 Player Agency

When appropriate, progression SHOULD allow players to influence their development.

Meaningful choices may include:

- Selecting abilities or upgrades.
- Choosing specializations.
- Prioritizing different capabilities.
- Unlocking alternative gameplay approaches.
- Deciding how to allocate limited progression resources.

Choices SHOULD have understandable consequences and support different playstyles where intended.

### 3.5 Appropriate Pacing

Progression MUST be paced according to the intended gameplay experience.

Advancement SHOULD provide a balance between:

- Frequent feedback and rewards.
- Meaningful milestones.
- Long-term objectives.
- Opportunities to master existing capabilities.
- Introduction of new challenges.

Progression SHOULD NOT rely on unnecessary repetition or excessive time requirements to create artificial engagement.

### 3.6 Integration With Gameplay

Progression SHOULD reinforce the game's core gameplay loop.

The actions required for advancement SHOULD encourage the intended player behaviors and interactions.

Progression systems MUST NOT unnecessarily undermine the central gameplay experience.

## 4. Progression Models

### 4.1 Linear Progression

Linear progression follows a predefined sequence of advancement.

Examples include:

- Sequential levels.
- Fixed ability unlocks.
- Story chapters.
- Mandatory equipment upgrades.

Use linear progression when controlled pacing, structured learning, or a specific sequence of experiences is important.

Linear progression SHOULD avoid unnecessary restrictions that prevent players from engaging with already available content.

### 4.2 Branching Progression

Branching progression allows players to choose between different advancement paths.

Examples include:

- Skill trees.
- Specialization paths.
- Alternative upgrades.
- Branching narrative developments.

Branches SHOULD represent meaningful differences rather than superficial variations.

Designers SHOULD evaluate whether branches create distinct gameplay possibilities and whether their choices are sufficiently understandable.

### 4.3 Open or Nonlinear Progression

Nonlinear progression allows players to advance through multiple available paths or activities.

Examples include:

- Open-world exploration.
- Optional objectives.
- Multiple progression activities.
- Player-directed development.

Nonlinear systems SHOULD communicate available opportunities without unnecessarily restricting player freedom.

Designers MUST consider whether different progression paths create unintended disparities in difficulty, rewards, or content accessibility.

### 4.4 Hybrid Progression

Hybrid progression combines multiple progression models.

For example, a game may use:

- Linear narrative progression.
- Branching character development.
- Nonlinear exploration rewards.
- Milestone-based equipment unlocks.

Hybrid systems MUST have clearly defined relationships between their individual progression mechanisms.

Additional complexity SHOULD be justified by the value it provides to the player experience.

## 5. Progression Categories

### 5.1 Character Progression

Character progression represents changes in the player's character or playable entity.

Possible elements include:

- Character levels.
- Attributes and statistics.
- Skills and abilities.
- Specializations.
- Passive improvements.
- New interactions or actions.

Character progression SHOULD reinforce the intended role and identity of the character.

Attribute growth MUST be evaluated against the game's balance requirements.

### 5.2 Ability and Skill Progression

Ability progression introduces new capabilities or improves existing ones.

Designers SHOULD consider:

- Ability purpose.
- Unlock requirements.
- Functional differences between upgrades.
- Resource or usage requirements.
- Interactions with existing mechanics.
- Potential combinations and synergies.
- Impact on difficulty and encounter design.

New abilities SHOULD expand player options or improve an existing gameplay experience.

Upgrades SHOULD NOT make previously relevant abilities automatically obsolete unless replacement is an intentional design decision.

### 5.3 Equipment Progression

Equipment progression allows players to acquire, improve, or replace equipment.

Possible models include:

- Equipment tiers.
- Equipment rarity.
- Upgrade levels.
- Crafting-based improvements.
- Equipment specialization.
- Equipment set bonuses.

Equipment progression SHOULD support the game's combat, exploration, survival, or other relevant gameplay systems.

Designers MUST evaluate how equipment affects player power, available strategies, resource requirements, and encounter difficulty.

Detailed equipment economy and reward valuation SHOULD follow the economy and balancing guidelines.

### 5.4 Content Progression

Content progression controls access to new gameplay experiences.

Examples include:

- New areas.
- Missions and quests.
- Enemies and encounters.
- Gameplay modes.
- Activities.
- Narrative chapters.
- Features and systems.

Unlock requirements SHOULD communicate why content becomes available and what the player must accomplish.

Restrictions MUST serve an intentional design purpose, such as pacing, learning, narrative structure, or challenge progression.

### 5.5 Narrative Progression

Narrative progression represents changes in story, characters, relationships, and world conditions.

Examples include:

- Story chapters.
- Character development.
- Relationship changes.
- Narrative choices.
- World-state changes.
- Discoveries and revelations.

Narrative progression SHOULD remain consistent with the game's narrative structure and established world rules.

Narrative advancement MUST be coordinated with gameplay requirements when both systems depend on the same events or conditions.

### 5.6 Knowledge and Mastery Progression

Some progression occurs through player learning rather than explicit character statistics.

Examples include:

- Learning enemy behaviors.
- Understanding environmental patterns.
- Mastering mechanics.
- Discovering strategies.
- Improving execution and decision-making.

Designers SHOULD recognize player knowledge and mastery as meaningful forms of advancement.

Systems SHOULD avoid unnecessarily invalidating knowledge-based progression through arbitrary changes to established rules.

## 6. Progression Structure and Dependencies

### 6.1 Progression Hierarchy

Progression systems SHOULD define their structure before implementation.

A progression hierarchy may contain:

1. Long-term objectives.
2. Major progression milestones.
3. Intermediate objectives.
4. Individual unlocks or rewards.
5. Requirements and conditions.

Each level SHOULD have a clear purpose and relationship with the others.

### 6.2 Prerequisites and Unlock Conditions

Every progression element with prerequisites MUST define its unlock conditions.

Possible conditions include:

- Reaching a specific level.
- Completing an objective.
- Discovering a location.
- Acquiring a required item.
- Spending progression resources.
- Reaching a narrative milestone.
- Completing another progression element.

Prerequisites MUST be valid, achievable, and understandable.

Designers SHOULD avoid unnecessarily complicated dependency chains.

### 6.3 Dependency Management

Progression dependencies MUST be evaluated for:

- Circular requirements.
- Unreachable unlocks.
- Missing prerequisites.
- Unintended sequence restrictions.
- Conflicting progression states.
- Softlocks and progression blockers.

Systems SHOULD define how dependent progression elements respond when their prerequisites change or become unavailable.

### 6.4 Optional and Mandatory Progression

Mandatory progression controls advancement required to continue the primary game experience.

Optional progression provides additional rewards, capabilities, content, or alternative experiences.

Both types SHOULD have clearly defined purposes.

Mandatory progression MUST NOT require optional activities unless that requirement is intentional and communicated.

Optional progression SHOULD provide value without making the primary experience unnecessarily difficult or incomplete for players who do not pursue it.

## 7. Progression Pacing

### 7.1 Advancement Frequency

Designers MUST define the intended frequency of progression rewards.

Consider:

- Time between meaningful milestones.
- Frequency of minor improvements.
- Length of progression stages.
- Expected player session duration.
- Complexity of newly introduced systems.
- Time required to understand and use new capabilities.

Progression SHOULD provide appropriate feedback without overwhelming players with constant unlocks.

### 7.2 Early, Mid, and Late Game

Progression SHOULD be evaluated across the entire intended game experience.

**Early game:**

- Introduce foundational systems.
- Provide understandable objectives.
- Encourage experimentation.
- Establish basic player capabilities.
- Avoid overwhelming players with too many choices.

**Mid game:**

- Expand available options.
- Introduce greater complexity.
- Encourage specialization.
- Create meaningful interactions between systems.
- Reinforce previously learned mechanics.

**Late game:**

- Provide appropriate long-term goals.
- Support advanced mastery.
- Maintain meaningful decisions.
- Avoid excessive numerical inflation.
- Preserve challenge and player engagement.

These stages are conceptual guidelines and SHOULD be adapted to the game's structure.

### 7.3 Progression Bottlenecks

A progression bottleneck occurs when advancement becomes significantly slower or is blocked by a specific requirement.

Bottlenecks MAY be used intentionally to create challenge, anticipation, or meaningful decisions.

Designers MUST verify that bottlenecks:

- Have a clear design purpose.
- Are achievable.
- Provide understandable requirements.
- Do not create unintended dead ends.
- Do not require disproportionate repetition.
- Do not undermine the intended pacing.

### 7.4 Progression Fatigue

Progression fatigue occurs when advancement becomes repetitive, predictable, excessively slow, or insufficiently rewarding.

Designers SHOULD monitor:

- Repeated objectives with little variation.
- Long periods without meaningful advancement.
- Excessive prerequisite chains.
- Rewards that no longer influence player decisions.
- Repetitive resource collection.
- Unnecessary progression resets.

Progression systems SHOULD evolve alongside the player's growing knowledge and capabilities.

## 8. Rewards and Advancement Feedback

### 8.1 Reward Purpose

Every progression reward SHOULD have a defined purpose.

Rewards may provide:

- Increased capability.
- New gameplay options.
- Access to content.
- Narrative information.
- Cosmetic customization.
- Recognition of achievement.
- Additional strategic choices.

Rewards SHOULD reinforce the value of the player's actions.

### 8.2 Reward Significance

Reward significance SHOULD be proportional to the effort, challenge, or achievement required.

Designers SHOULD distinguish between:

- Minor rewards.
- Intermediate rewards.
- Major milestones.
- Exceptional achievements.

Not every action requires a substantial reward. However, important progression milestones SHOULD feel distinguishable from routine advancement.

### 8.3 Progression Feedback

Players SHOULD receive appropriate feedback when progression occurs.

Feedback may include:

- Unlock notifications.
- Progress indicators.
- Updated objectives.
- Character or equipment changes.
- New available content.
- Visual or audio effects.
- Updated journals or progression screens.

Feedback MUST communicate the result of advancement without unnecessary interruption.

### 8.4 Progress Visibility

When progression depends on measurable requirements, the game SHOULD communicate relevant progress.

Examples include:

- Experience progress.
- Objective completion.
- Unlock prerequisites.
- Skill point availability.
- Milestone completion.
- Remaining requirements.

Hidden progression MAY be used when discovery is an intentional design objective, but hidden requirements SHOULD NOT create avoidable confusion.

## 9. Progression Resources and Costs

Some progression systems require resources, currency, experience, or other forms of investment.

Designers MUST define:

- Resource requirements.
- Acquisition methods.
- Spending rules.
- Upgrade costs.
- Resource limits.
- Refund or respec behavior, if applicable.
- Interactions with other game systems.

Progression costs SHOULD support meaningful decisions.

Designers MUST evaluate whether resource requirements create unintended progression barriers or dominant strategies.

Detailed resource generation, consumption, pricing, and economic balance MUST follow `ECONOMY_DESIGN_GUIDELINES.md`.

## 10. Progression and Difficulty

Progression and difficulty MUST be designed together.

Player advancement may affect:

- Combat effectiveness.
- Survival capabilities.
- Available strategies.
- Encounter duration.
- Resource consumption.
- Environmental challenges.
- Access to difficult content.

Designers SHOULD ensure that progression does not unintentionally eliminate challenge or make previously reasonable encounters disproportionately difficult.

When difficulty scales with player progression, the scaling model MUST have an explicit design purpose.

Designers SHOULD avoid automatically increasing every challenge in response to player advancement, as this can reduce the perceived value of progression.

Detailed difficulty and numerical balance decisions SHOULD follow the relevant game design guidelines.

## 11. Progression Persistence and State Management

Progression data MUST be stored and restored reliably when the game supports persistent player progress.

Designers and developers MUST define:

- Which progression states are persistent.
- Which states are temporary.
- How unlocks are recorded.
- How progression changes are saved.
- How progression is restored after loading.
- How interrupted progression actions are handled.
- How invalid or inconsistent progression data is handled.

Progression systems SHOULD avoid duplicating authoritative state across unrelated systems.

When multiple features depend on progression state, communication SHOULD use clearly defined interfaces or events.

Progression changes that affect saved data MUST consider backward compatibility and save migration requirements.

## 12. Progression Resets and Reversibility

Some games allow players to reset, redistribute, or replace progression choices.

Examples include:

- Skill respecs.
- Character resets.
- Prestige systems.
- New Game Plus.
- Seasonal progression resets.
- Temporary progression modes.

Before implementing a reset mechanism, designers MUST define:

- What is reset.
- What is preserved.
- Whether the reset is optional or mandatory.
- Whether it has a cost.
- Whether it can be reversed.
- How it affects unlocks and dependencies.
- How it affects saved data and achievements.

Reset systems SHOULD communicate their consequences before the player confirms the action.

Irreversible progression decisions MUST be clearly identified.

## 13. Long-Term and Meta-Progression

Meta-progression refers to advancement that persists beyond an individual mission, level, run, or gameplay session.

Examples include:

- Permanent upgrades.
- Account-wide unlocks.
- Persistent collections.
- Hub development.
- New Game Plus progression.
- Long-term achievement systems.

Meta-progression SHOULD provide a meaningful connection between individual gameplay sessions and the broader game experience.

Designers MUST evaluate whether permanent progression creates excessive power accumulation or undermines the challenge of individual gameplay sessions.

When temporary and permanent progression coexist, their responsibilities and interactions MUST be clearly defined.

## 14. Progression Exploits and Edge Cases

Progression systems SHOULD be evaluated for unintended advancement methods and inconsistent states.

Potential issues include:

- Repeating an activity to gain unintended rewards.
- Farming progression through low-risk actions.
- Bypassing prerequisites.
- Receiving duplicate unlocks.
- Spending the same progression resource multiple times.
- Losing progression after interrupted actions.
- Unlocking content in an invalid order.
- Exploiting reset or respec behavior.
- Reaching progression limits unexpectedly.

Designers and developers SHOULD define expected behavior for relevant edge cases.

Progression integrity MUST be preserved across saving, loading, scene transitions, and other relevant system boundaries.

## 15. Progression Documentation

Every significant progression system SHOULD have a documented specification.

A progression specification SHOULD include:

| Element | Description |
|---|---|
| Purpose | Why the progression system exists |
| Progression model | Linear, branching, nonlinear, or hybrid |
| Scope | Which gameplay elements it affects |
| Progression categories | Character, ability, equipment, content, narrative, or other |
| Milestones | Major advancement points |
| Requirements | Conditions needed for advancement |
| Rewards | Changes provided by advancement |
| Costs | Required resources or investments |
| Dependencies | Relationships with other progression elements |
| Pacing | Expected advancement frequency and duration |
| Feedback | How advancement is communicated |
| Persistence | What progression data is saved |
| Reset behavior | Whether progression can be reversed or reset |
| Edge cases | Relevant exceptional conditions |
| Validation | How the system will be evaluated |

Progression specifications SHOULD include diagrams, tables, or examples when they make complex relationships easier to understand.

## 16. Testing and Validation

Progression systems MUST be validated throughout development.

### 16.1 Functional Validation

Verify that:

- Progression requirements are evaluated correctly.
- Rewards are granted correctly.
- Unlocks occur under the intended conditions.
- Prerequisites are enforced.
- Progression states remain consistent.
- Progression data persists correctly.
- Reset and respec operations behave as specified.
- Progression limits are handled correctly.

### 16.2 Progression Path Validation

Test representative progression paths, including:

- Expected progression sequences.
- Alternative progression paths.
- Optional content paths.
- Unusual but valid player decisions.
- Maximum and minimum progression states.
- Interrupted progression sequences.
- Save and load transitions.

### 16.3 Pacing and Balance Validation

Evaluate:

- Time required to reach milestones.
- Frequency of meaningful rewards.
- Player power growth.
- Availability of progression resources.
- Difficulty changes caused by advancement.
- Differences between progression paths.
- Potential bottlenecks and repetitive activities.

### 16.4 Player Experience Validation

Playtesting SHOULD evaluate whether players:

- Understand their progression goals.
- Recognize the value of advancement.
- Understand unlock requirements.
- Feel appropriately rewarded.
- Have meaningful development choices.
- Experience an appropriate progression pace.
- Can identify available opportunities for advancement.

Feedback SHOULD be used to identify problems rather than treated as automatic proof that a particular design change is necessary.

## 17. Iterative Progression Design

Progression systems SHOULD be developed and refined iteratively.

A recommended workflow is:

1. Define the intended player experience.
2. Identify the purpose of progression.
3. Select an appropriate progression model.
4. Define progression categories and milestones.
5. Establish prerequisites, rewards, and dependencies.
6. Define expected pacing.
7. Prototype the progression system.
8. Validate functionality and progression paths.
9. Evaluate player experience and balance.
10. Refine the system based on evidence.
11. Update the progression specification.

Designers SHOULD prototype complex progression systems before committing to extensive content or implementation.

Changes to progression MUST be evaluated for their impact on connected gameplay systems.

## 18. Godot Implementation Considerations

Progression implementation MUST follow the project's approved technical and architectural standards.

The following principles SHOULD guide implementation:

- Keep progression logic within the feature that owns the progression system.
- Use clearly defined interfaces when other features need progression information.
- Separate progression data from presentation logic where appropriate.
- Represent configurable progression content using suitable Godot resources or data structures.
- Avoid hardcoding large progression tables into unrelated scripts.
- Validate progression requirements before applying rewards.
- Preserve authoritative progression state.
- Handle save and load operations consistently.
- Avoid circular dependencies between progression and gameplay features.
- Use signals or other established communication mechanisms for progression events where appropriate.

The implementation SHOULD remain understandable, testable, and extensible without introducing unnecessary abstraction.

## 19. AI-Assisted Progression Design Requirements

AI agents assisting with progression design MUST:

1. Read this document and relevant game-specific design specifications.
2. Identify the intended player experience before proposing progression mechanics.
3. Respect approved progression models and existing design decisions.
4. Avoid introducing progression systems without a defined gameplay purpose.
5. Check dependencies with existing gameplay, economy, difficulty, and balancing systems.
6. Identify potential progression bottlenecks and exploit opportunities.
7. Avoid duplicating existing progression responsibilities.
8. Document assumptions and unresolved design questions.
9. Propose significant structural or progression model changes for human approval.
10. Never mark unapproved progression decisions as approved.

AI-generated progression structures, calculations, and recommendations MUST be reviewed and validated before implementation.

## 20. Progression Design Review Checklist

Before approving a progression system, verify the following:

### Design Intent
- [ ] The progression system has a clear purpose.
- [ ] It supports the intended player experience.
- [ ] Its progression model is appropriate for the game.
- [ ] Its relationship with the core gameplay loop is defined.

### Structure
- [ ] Progression categories are identified.
- [ ] Major milestones are defined.
- [ ] Unlock requirements are understandable.
- [ ] Dependencies are valid and achievable.
- [ ] Mandatory and optional progression are distinguished.

### Rewards and Pacing
- [ ] Rewards provide meaningful advancement.
- [ ] Advancement frequency is appropriate.
- [ ] Early, mid, and late-game progression have been considered.
- [ ] Bottlenecks have been evaluated.
- [ ] Progression does not rely on unnecessary repetition.

### Integration
- [ ] Progression interactions with difficulty are evaluated.
- [ ] Resource requirements are defined.
- [ ] Related gameplay systems are considered.
- [ ] Persistence and reset behavior are specified where applicable.

### Validation
- [ ] Progression paths have been tested.
- [ ] Relevant edge cases have been considered.
- [ ] Progression exploits have been evaluated.
- [ ] Player feedback has been considered.
- [ ] The progression specification is up to date.

## 21. Related Documents

Consult the following documents when relevant:

- `DESIGN_PRINCIPLES.md`
- `CORE_LOOP_DESIGN_GUIDELINES.md`
- `GAMEPLAY_DESIGN_GUIDELINES.md`
- `MECHANIC_DESIGN_GUIDELINES.md`
- `PLAYER_EXPERIENCE_GUIDELINES.md`
- `BALANCING_GUIDELINES.md`
- `DIFFICULTY_DESIGN_GUIDELINES.md`
- `ECONOMY_DESIGN_GUIDELINES.md`
- `NARRATIVE_DESIGN_GUIDELINES.md`

Technical implementation MUST also follow the applicable studio technical standards and project-specific architecture documentation.

## 22. Maintenance

This document SHOULD be reviewed periodically and updated when:

- Studio-wide progression design practices change.
- New progression models become relevant.
- Existing guidance becomes unclear or outdated.
- Repeated design or implementation problems reveal missing guidance.

Changes MUST preserve consistency with the studio documentation hierarchy and other game design guidelines.

Game-specific progression decisions MUST be documented in the relevant game project documentation rather than added to this reusable guideline.