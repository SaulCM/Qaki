# Difficulty Design Guidelines

## 1. Purpose

This document establishes the principles, methods, and quality expectations for designing and evaluating game difficulty.

Its purpose is to ensure that challenges are engaging, understandable, fair, and consistent with the intended player experience.

Difficulty is not limited to numerical parameters such as enemy health or damage. It emerges from the interaction between player capabilities, game mechanics, available information, environmental conditions, resource constraints, and the consequences of failure.

These guidelines provide a reusable framework for difficulty design across different game genres and platforms.

## 2. Scope

These guidelines apply to:

- Overall game difficulty.
- Moment-to-moment gameplay challenge.
- Enemy and encounter difficulty.
- Boss and special encounter design.
- Level and environmental challenges.
- Puzzle and problem-solving difficulty.
- Resource and survival pressure.
- Player skill requirements.
- Difficulty progression.
- Failure and recovery systems.
- Difficulty settings and accessibility options.
- Dynamic difficulty adjustment, when applicable.

These guidelines SHOULD be considered during concept development, prototyping, production, playtesting, and post-release balancing.

## 3. Difficulty Design Principles

### 3.1 Difficulty Must Support the Intended Experience

Difficulty MUST reinforce the approved game vision and intended player experience.

Different games may intentionally provide:

- Relaxed and accessible experiences.
- Skill-based challenges.
- High-pressure survival experiences.
- Strategic and analytical challenges.
- Punishing experiences with significant failure consequences.
- Gradually increasing challenges.
- Player-controlled difficulty.

There is no universally correct difficulty level.

Designers MUST establish what kind of challenge the game intends to deliver before defining its difficulty systems.

### 3.2 Challenge Should Be Meaningful

A challenge SHOULD require the player to apply relevant knowledge, skills, decisions, or strategies.

Difficulty SHOULD emerge from meaningful gameplay requirements rather than arbitrary restrictions.

Examples include:

- Recognizing enemy behavior.
- Managing limited resources.
- Understanding environmental hazards.
- Choosing appropriate equipment.
- Planning an approach.
- Executing actions with precision.
- Responding to changing conditions.
- Combining previously learned mechanics.

### 3.3 Fairness and Understandability

Players SHOULD have reasonable opportunities to understand the rules governing a challenge.

A difficult situation is not necessarily unfair, but its important rules and consequences SHOULD be consistent with what the player can reasonably perceive or learn.

Avoid difficulty caused by:

- Uncommunicated mechanics.
- Inconsistent rules.
- Unavoidable damage without appropriate justification.
- Unclear attack indicators.
- Unreasonable input requirements.
- Unpredictable outcomes unrelated to meaningful gameplay.
- Insufficient information for important decisions.

Uncertainty MAY be intentional when it creates tension, discovery, or strategic decision-making.

### 3.4 Challenge Should Encourage Learning

Difficulty SHOULD provide opportunities for players to improve.

Players SHOULD be able to develop skills, recognize patterns, understand mechanics, and refine strategies through experience.

Failure MAY be part of this learning process when its consequences and feedback support improvement.

### 3.5 Avoid Artificial Difficulty

Avoid increasing difficulty exclusively through numerical inflation.

Increasing enemy health, damage, or enemy count can be appropriate, but SHOULD NOT be the default solution to every difficulty problem.

Consider introducing more meaningful challenges through:

- New behaviors.
- Different enemy combinations.
- Environmental interactions.
- Additional mechanics.
- More demanding objectives.
- Resource-management decisions.
- Alternative encounter conditions.

## 4. Defining Difficulty

Before designing a challenge, identify what makes it difficult.

### 4.1 Difficulty Dimensions

Difficulty MAY emerge from several dimensions:

| Dimension | Description |
|---|---|
| Mechanical | Precision, timing, reaction speed, and control execution |
| Cognitive | Understanding rules, solving problems, and making decisions |
| Strategic | Planning, adapting, and selecting effective approaches |
| Resource | Managing limited resources, equipment, or consumables |
| Environmental | Navigating hazards, terrain, visibility, or spatial constraints |
| Tactical | Responding to enemies, positioning, and encounter conditions |
| Temporal | Completing objectives within time constraints |
| Emotional | Handling pressure, uncertainty, and consequences |

A challenge MAY combine multiple dimensions.

Designers SHOULD identify which dimensions are essential to the intended experience and avoid increasing unrelated dimensions unnecessarily.

### 4.2 Player Capability

Difficulty MUST be evaluated in relation to the capabilities available to the player.

Consider:

- Available actions and abilities.
- Equipment and upgrades.
- Player knowledge.
- Available resources.
- Control complexity.
- Movement and interaction capabilities.
- Previous opportunities to learn relevant mechanics.

A challenge SHOULD NOT assume capabilities the player has not reasonably been given an opportunity to acquire.

### 4.3 Context Matters

The same challenge can have different difficulty depending on context.

Evaluate:

- Player progression.
- Available equipment.
- Current resources.
- Previous encounters.
- Environmental conditions.
- Available recovery options.
- Supporting mechanics.
- Player preparation.

Difficulty SHOULD be assessed in the context in which the challenge occurs.

## 5. Difficulty Progression

### 5.1 Progressive Learning

Difficulty SHOULD generally introduce complexity at a pace that allows players to understand and apply previously learned mechanics.

A useful progression pattern is:

1. Introduce a mechanic.
2. Provide an opportunity to understand it.
3. Allow the player to practice it.
4. Combine it with known mechanics.
5. Introduce additional complexity.
6. Test the player's understanding through more demanding situations.

This is a general design approach, not a mandatory sequence for every game.

### 5.2 Gradual Escalation

Difficulty SHOULD evolve intentionally throughout the game.

Escalation MAY involve:

- Increased mechanical demands.
- More complex enemy behaviors.
- New environmental conditions.
- Additional simultaneous threats.
- Reduced opportunities for mistakes.
- More demanding resource decisions.
- Combinations of previously introduced mechanics.

Avoid increasing several difficulty dimensions simultaneously without evaluating their combined impact.

### 5.3 Difficulty Variation

Difficulty does not always need to increase continuously.

The experience MAY alternate between:

- High-intensity encounters.
- Exploration.
- Preparation.
- Recovery.
- Low-pressure activities.
- Optional challenges.
- Skill-testing encounters.

Variation helps establish pacing and gives players opportunities to process, prepare, and recover.

### 5.4 Difficulty Spikes

Significant increases in difficulty SHOULD be intentional.

Before introducing a major difficulty spike, evaluate:

- Whether the player has learned the required mechanics.
- Whether the challenge is consistent with previous expectations.
- Whether the player has access to appropriate tools.
- Whether the challenge is clearly communicated.
- Whether failure consequences are appropriate.
- Whether the difficulty increase serves a meaningful purpose.

Unexpected difficulty spikes SHOULD be treated as potential design issues until validated.

## 6. Challenge and Player Skill

### 6.1 Skill-Based Challenge

When skill is central to the experience, challenges SHOULD reward mastery of relevant mechanics.

Skill MAY involve:

- Timing.
- Precision.
- Reaction.
- Observation.
- Planning.
- Resource management.
- Spatial awareness.
- Pattern recognition.
- Strategic adaptation.

The relationship between player skill and success SHOULD be understandable.

### 6.2 Knowledge-Based Challenge

Some challenges depend on understanding game rules, recognizing patterns, or discovering information.

The game SHOULD provide appropriate opportunities to acquire necessary knowledge.

Important information MAY be discovered through:

- Observation.
- Exploration.
- Dialogue.
- Tutorials.
- Environmental clues.
- Experimentation.
- Previous encounters.

Avoid requiring obscure external knowledge unless that requirement is an intentional part of the experience.

### 6.3 Strategic Challenge

Strategic challenges SHOULD provide meaningful alternatives.

Players SHOULD have opportunities to evaluate different approaches, understand relevant trade-offs, and make informed decisions.

A challenge SHOULD NOT become strategically meaningless because only one approach is viable without a deliberate design reason.

### 6.4 Execution Versus Understanding

Designers SHOULD distinguish between challenges that test understanding and challenges that test execution.

For example:

- A puzzle may test whether the player understands a mechanic.
- A combat encounter may test whether the player can execute a learned mechanic under pressure.

Combining both is valid, but the intended source of difficulty SHOULD be clear.

## 7. Enemy and Encounter Difficulty

When the game includes enemies or combat, difficulty SHOULD be evaluated through enemy behavior, encounter composition, and player capabilities.

### 7.1 Enemy Capabilities

Relevant enemy parameters MAY include:

- Health.
- Damage.
- Movement speed.
- Attack frequency.
- Attack range.
- Detection range.
- Accuracy.
- Defense.
- Resistance.
- Reaction time.
- Behavior complexity.
- Ability usage.

Numerical adjustments SHOULD be evaluated alongside behavioral changes.

### 7.2 Enemy Readability

Players SHOULD have reasonable opportunities to recognize important enemy behaviors and threats.

Consider:

- Attack anticipation.
- Animation readability.
- Visual indicators.
- Sound cues.
- Movement patterns.
- Attack timing.
- Distinction between enemy types.

Enemy behavior SHOULD communicate enough information for players to learn and respond.

### 7.3 Encounter Composition

Encounter difficulty depends on more than individual enemy statistics.

Evaluate:

- Enemy quantity.
- Enemy combinations.
- Spatial arrangement.
- Available movement space.
- Environmental hazards.
- Enemy coordination.
- Player resources.
- Available cover or escape opportunities.
- Encounter objectives.

A group of individually weak enemies MAY produce an unexpectedly difficult encounter when their abilities interact.

### 7.4 Boss and Special Encounters

Boss encounters SHOULD provide distinctive challenges that justify their importance.

Consider:

- Recognizable mechanics.
- Attack patterns.
- Phases or behavior changes.
- Environmental interactions.
- Player counterplay.
- Resource requirements.
- Appropriate encounter duration.
- Failure and retry conditions.

Boss difficulty SHOULD test relevant skills and knowledge rather than rely exclusively on excessive health or damage.

## 8. Environmental and Puzzle Difficulty

### 8.1 Environmental Challenges

Environmental difficulty MAY involve:

- Terrain.
- Navigation.
- Visibility.
- Hazards.
- Weather.
- Limited movement.
- Environmental interactions.
- Resource availability.

Environmental challenges SHOULD be readable and consistent with the rules of the game world.

### 8.2 Puzzle Difficulty

Puzzle difficulty SHOULD reflect the intended reasoning process.

Consider:

- Clarity of the objective.
- Information available.
- Number of relevant variables.
- Required deductions.
- Feedback after player actions.
- Possibility of experimentation.
- Consequences of incorrect attempts.

Avoid solutions that depend primarily on arbitrary guessing when reasoning is intended to be the central challenge.

### 8.3 Information and Discovery

When discovery is part of the challenge, designers SHOULD distinguish between intentional uncertainty and insufficient communication.

Players MAY be required to interpret clues, explore, or experiment.

However, important information SHOULD be discoverable through reasonable gameplay interactions.

## 9. Resource and Survival Difficulty

When resource management or survival is part of the game, resource constraints MAY contribute to difficulty.

Consider:

- Resource availability.
- Consumption rates.
- Carrying capacity.
- Recovery opportunities.
- Environmental scarcity.
- Crafting requirements.
- Equipment durability.
- Consequences of resource depletion.

Resource pressure SHOULD create meaningful decisions.

Avoid resource constraints that make normal progression dependent on excessive repetitive activities unless that is an intentional part of the game experience.

## 10. Failure and Recovery

### 10.1 Purpose of Failure

Failure SHOULD have a deliberate role in the gameplay experience.

It MAY:

- Teach mechanics.
- Encourage strategic adaptation.
- Create tension.
- Introduce consequences.
- Change the game state.
- Reinforce the significance of player decisions.

Failure SHOULD NOT exist solely to punish players without contributing to the intended experience.

### 10.2 Failure Communication

When practical, players SHOULD understand:

- What caused the failure.
- Which mechanic was involved.
- What could have been done differently.
- What consequences follow.

The level of explanation SHOULD reflect the game's design.

Some games intentionally require players to discover failure conditions through experimentation.

### 10.3 Recovery Opportunities

Recovery systems SHOULD be consistent with the intended difficulty and consequences.

Recovery MAY involve:

- Checkpoints.
- Healing.
- Retreat.
- Respawning.
- Resource recovery.
- Alternative routes.
- Reattempting an encounter.
- Temporary protection.

Recovery SHOULD provide an appropriate balance between preserving challenge and preventing unnecessary repetition.

### 10.4 Failure Costs

Failure consequences MAY include:

- Lost resources.
- Lost progress.
- Equipment damage.
- Temporary setbacks.
- Changed world conditions.
- Restarting an activity.
- Permanent consequences.

The severity of failure costs SHOULD be proportionate to the intended experience and communicated appropriately.

### 10.5 Checkpoints and Save Systems

Checkpoint placement SHOULD consider:

- Challenge duration.
- Difficulty spikes.
- Repeated execution requirements.
- Player time.
- Progress preservation.
- Consequences of failure.

Avoid requiring players to repeat excessive amounts of previously completed content when repetition does not serve a deliberate design purpose.

## 11. Difficulty Settings

### 11.1 Purpose

Difficulty settings MAY be provided to accommodate different player preferences and skill levels.

When implemented, settings SHOULD have clearly differentiated gameplay effects.

Examples include:

- Enemy effectiveness.
- Resource availability.
- Damage received.
- Puzzle assistance.
- Time constraints.
- Recovery opportunities.
- Encounter complexity.

### 11.2 Consistency

Difficulty settings SHOULD modify the intended aspects of the experience without introducing unrelated inconsistencies.

The relationship between settings SHOULD be understandable.

### 11.3 Player Expectations

Difficulty descriptions SHOULD accurately communicate their expected experience.

Avoid labels that misrepresent the actual challenge.

Where appropriate, explain whether difficulty affects:

- Combat.
- Resource management.
- Enemy behavior.
- Progression.
- Failure consequences.
- Rewards.
- Achievements or completion requirements.

### 11.4 Changing Difficulty

Whether players can change difficulty during gameplay SHOULD be an explicit design decision.

Consider:

- Player freedom.
- Challenge integrity.
- Progression consequences.
- Save-state consistency.
- Competitive fairness, if applicable.

Do not assume that every game needs adjustable difficulty.

## 12. Dynamic Difficulty Adjustment

Dynamic difficulty adjustment (DDA) refers to systems that modify gameplay difficulty in response to player performance or other gameplay conditions.

DDA MAY be appropriate when it supports the intended experience.

Before implementing it, evaluate:

- Whether dynamic adjustment is necessary.
- Which player behaviors are measured.
- Which parameters may change.
- How adjustments are triggered.
- How quickly adjustments occur.
- Whether players can perceive the changes.
- Whether the system can produce unintended outcomes.

DDA SHOULD:

- Preserve the game's intended challenge.
- Avoid unpredictable or contradictory behavior.
- Avoid undermining player mastery.
- Avoid penalizing skilled players without justification.
- Avoid making failure feel manipulated.
- Be validated across different player behaviors.

Dynamic adjustment MUST NOT be introduced merely because it is technically feasible.

## 13. Accessibility and Difficulty

Difficulty design SHOULD consider different player capabilities and accessibility needs.

Where appropriate, consider:

- Adjustable reaction-time requirements.
- Remappable controls.
- Input alternatives.
- Reduced precision requirements.
- Visual and audio indicators.
- Clearer attack telegraphs.
- Optional assistance.
- Adjustable puzzle hints.
- Reduced-motion options.
- Readability improvements.
- Alternative ways to receive important information.

Accessibility options SHOULD be evaluated in the context of the game's intended experience.

They SHOULD NOT automatically be treated as compromises to design quality.

## 14. Difficulty Testing and Validation

Difficulty MUST be evaluated through appropriate testing rather than design assumptions alone.

### 14.1 Establish Difficulty Targets

For significant challenges, define:

- Intended player skill level.
- Expected challenge dimensions.
- Required player knowledge.
- Available capabilities.
- Expected encounter duration, where applicable.
- Expected resource consumption.
- Failure conditions.
- Acceptable completion outcomes.

Targets SHOULD be measurable where practical.

### 14.2 Playtesting

Playtesting SHOULD include different player skill levels when relevant to the target audience.

Observe:

- Completion rates.
- Failure frequency.
- Encounter duration.
- Player decisions.
- Resource consumption.
- Repeated attempts.
- Common mistakes.
- Player understanding.
- Frustration and satisfaction.
- Unexpected strategies.

### 14.3 Quantitative Analysis

Relevant metrics MAY include:

- Win and failure rates.
- Damage dealt and received.
- Time to complete an encounter.
- Number of attempts.
- Resource consumption.
- Ability usage.
- Enemy detection and reaction times.
- Progression completion rates.
- Checkpoint retry frequency.

Metrics MUST be interpreted in context.

For example, a high failure rate does not automatically mean an encounter is too difficult. It may be appropriate for an optional challenge or a game centered on mastery.

### 14.4 Qualitative Analysis

Quantitative metrics SHOULD be complemented by qualitative feedback.

Evaluate whether players:

- Understand why they failed.
- Recognize important threats.
- Feel appropriately challenged.
- Have meaningful opportunities to improve.
- Consider the challenge fair.
- Feel motivated to continue.
- Experience unnecessary frustration.

### 14.5 Regression Testing

Difficulty adjustments MAY affect multiple systems.

After significant changes, evaluate relevant dependencies, including:

- Player progression.
- Equipment effectiveness.
- Resource availability.
- Enemy behavior.
- Encounter composition.
- Reward distribution.
- Difficulty settings.
- Previously validated content.

## 15. Difficulty Iteration Workflow

Use the following workflow when designing or adjusting a challenge:

1. **Define intent:** Establish the intended player experience.
2. **Identify challenge dimensions:** Determine what makes the challenge difficult.
3. **Evaluate player capabilities:** Identify the tools and knowledge available.
4. **Define expectations:** Establish measurable targets where practical.
5. **Implement:** Create the challenge using appropriate mechanics.
6. **Test:** Evaluate actual player performance and experience.
7. **Analyze:** Identify whether problems originate from mechanics, communication, tuning, or context.
8. **Adjust:** Modify the smallest relevant set of parameters or mechanics.
9. **Regression test:** Evaluate related systems.
10. **Document:** Record important decisions and unresolved issues.

Difficulty SHOULD be refined iteratively as the game and player capabilities evolve.

## 16. Difficulty Documentation

Significant difficulty systems and challenges SHOULD document:

- Intended difficulty.
- Target player capabilities.
- Relevant challenge dimensions.
- Required player knowledge.
- Important mechanics.
- Available counterplay.
- Failure conditions.
- Recovery options.
- Difficulty progression.
- Relevant parameters.
- Test scenarios.
- Observed results.
- Known risks.

Major difficulty changes SHOULD include a brief explanation of:

- What changed.
- Why it changed.
- What evidence supported the change.
- Which related systems were evaluated.
- What remains uncertain.

## 17. AI-Assisted Difficulty Design Requirements

AI agents assisting with difficulty design MUST follow these requirements:

1. Read the approved game vision and relevant game-specific design documentation.
2. Identify the intended player experience before proposing difficulty changes.
3. Evaluate challenge dimensions rather than relying exclusively on numerical values.
4. Consider player capabilities, available information, and counterplay.
5. Avoid artificial difficulty increases without a design justification.
6. Identify potential difficulty spikes and progression barriers.
7. Consider failure consequences and recovery opportunities.
8. Evaluate interactions with progression, resources, and other gameplay systems.
9. Distinguish design hypotheses from validated results.
10. Recommend playtesting when difficulty cannot be reliably evaluated analytically.
11. Document significant changes and their rationale.
12. Seek project owner approval before making significant changes to approved difficulty direction or game design.

AI-generated difficulty recommendations are proposals until reviewed and validated.

## 18. Difficulty Review Checklist

Before considering a challenge sufficiently designed for its current development stage, evaluate:

- [ ] Its intended difficulty and purpose are defined.
- [ ] Its challenge dimensions are understood.
- [ ] Required player capabilities are available.
- [ ] Important mechanics are understandable.
- [ ] Player actions have appropriate feedback.
- [ ] The challenge provides meaningful opportunities for response.
- [ ] Difficulty is consistent with the surrounding gameplay.
- [ ] Failure consequences are intentional.
- [ ] Recovery opportunities are appropriate.
- [ ] Difficulty spikes have been evaluated.
- [ ] Accessibility considerations have been reviewed.
- [ ] Relevant test scenarios have been completed.
- [ ] Observed results support the intended experience.
- [ ] Known issues and assumptions are documented.

Not every item applies to every challenge. Non-applicable items SHOULD be identified rather than treated as mandatory implementation work.

## 19. Related Documents

This document SHOULD be used alongside relevant documents that exist in the repository, including:

- Game vision documentation.
- Design principles.
- Core loop design guidelines.
- Balancing guidelines.
- Gameplay mechanics specifications.
- Enemy and encounter design documentation.
- Level design guidelines.
- Progression design documentation.
- Quality standards.
- Definition of Done.
- QA and playtesting standards.

Game-specific difficulty curves, encounter values, enemy statistics, and difficulty configurations belong in the individual game's documentation and implementation.

## 20. Maintenance

These guidelines SHOULD be reviewed when:

- The studio's approach to difficulty design changes.
- New difficulty design practices are adopted.
- Repeated difficulty-related problems reveal gaps in the guidelines.
- New tools or techniques materially improve difficulty testing and validation.

Changes MUST preserve the document's purpose as a reusable design guideline rather than turning it into a specification for a particular game.

The project owner is responsible for approving changes to studio-wide game design guidelines.