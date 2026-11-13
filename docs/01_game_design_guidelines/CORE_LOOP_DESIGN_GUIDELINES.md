# Core Loop Design Guidelines

## 1. Purpose

This document establishes the principles, methods, and quality expectations for designing and validating a game's core loop.

The core loop represents the recurring sequence of player actions, decisions, and outcomes that forms the foundation of the gameplay experience.

Its purpose is to ensure that the game's primary activities are understandable, engaging, meaningful, and sustainable throughout the intended player experience.

These guidelines provide a reusable framework for game development. They do not prescribe a specific genre, gameplay structure, or implementation architecture.

## 2. Scope

These guidelines apply to:

- Core gameplay loops.
- Moment-to-moment gameplay activities.
- Player actions and interactions.
- Gameplay decisions and consequences.
- Resource acquisition and consumption.
- Risk and reward relationships.
- Feedback and progression.
- Gameplay repetition and variation.
- Interactions between core mechanics.
- Supporting loops that extend the primary experience.

These guidelines SHOULD be considered during concept development, pre-production, prototyping, production, and gameplay evaluation.

## 3. Core Loop Definition

### 3.1 What Is a Core Loop?

A core loop is the recurring sequence of activities that defines what players primarily do during gameplay.

It describes how players interact with the game, make decisions, produce outcomes, and receive feedback that motivates further interaction.

A core loop generally contains:

1. **Player action:** The player performs an action or initiates an activity.
2. **Game response:** The game processes the action and produces an outcome.
3. **Feedback:** The player receives information about the outcome.
4. **Reward or consequence:** The action produces a benefit, cost, risk, or change in the game state.
5. **Next decision:** The player decides what to do next, continuing or changing the activity.

Not every game requires these elements to appear as separate steps. They describe functional aspects of a recurring gameplay experience.

### 3.2 Core Loop vs. Gameplay Loop

The core loop represents the fundamental recurring gameplay activity.

The broader gameplay loop may include multiple interconnected loops operating at different levels.

For example:

- **Moment-to-moment loop:** The player's immediate actions and reactions.
- **Core gameplay loop:** The primary recurring gameplay activity.
- **Meta-game loop:** Long-term progression, unlocks, upgrades, or persistent objectives.

These loops SHOULD support one another without making the overall experience unnecessarily complicated.

### 3.3 Core Loop vs. Game Progression

The core loop describes recurring gameplay activities.

Progression describes how the player's capabilities, opportunities, objectives, or game state evolve over time.

Progression MAY provide additional reasons to engage with the core loop, but it SHOULD NOT be confused with the loop itself.

A game can have a functional core loop before its complete progression system is designed.

## 4. Core Loop Design Principles

### 4.1 Clarity

The core loop MUST be understandable to the development team and, eventually, to the player.

Designers SHOULD be able to explain:

- What the player primarily does.
- Why the player performs those actions.
- What outcomes those actions produce.
- What motivates the player to continue.
- How the activity connects to the game's broader experience.

If the core loop cannot be explained clearly, its design may require further refinement.

### 4.2 Meaningful Player Agency

Players SHOULD make decisions that meaningfully influence gameplay outcomes.

Meaningful decisions MAY involve:

- Selecting an action.
- Choosing a strategy.
- Managing resources.
- Accepting or avoiding risks.
- Prioritizing objectives.
- Exploring alternative approaches.
- Responding to changing conditions.

Avoid loops that reduce the player to repeating actions without meaningful decisions or consequences, unless repetition is an intentional part of the experience.

### 4.3 Engaging Repetition

A core loop is inherently recurring, but repetition SHOULD remain engaging.

Variation MAY come from:

- Different player choices.
- Changing environments.
- Randomized conditions.
- New objectives.
- Different enemy behaviors.
- Resource availability.
- Increasing complexity.
- New abilities or tools.
- Emergent interactions between systems.

Variation SHOULD reinforce the core gameplay experience rather than distract from it.

### 4.4 Immediate and Understandable Feedback

Players SHOULD understand the consequences of their actions.

Feedback MAY be provided through:

- Visual effects.
- Animation.
- Sound.
- UI indicators.
- Character reactions.
- Changes in the environment.
- Resource or statistic changes.
- Narrative responses.

Important gameplay feedback SHOULD be timely, recognizable, and consistent.

### 4.5 Purposeful Rewards

The loop SHOULD provide outcomes that justify the player's effort.

Rewards MAY include:

- Resources.
- Progression.
- New opportunities.
- Information.
- Access to content.
- Improved capabilities.
- Narrative developments.
- Strategic advantages.
- Player satisfaction from successful execution.

Rewards do not need to be exclusively numerical or material.

### 4.6 Appropriate Complexity

The core loop SHOULD contain only the mechanics necessary to create the intended gameplay experience.

Avoid introducing additional steps, systems, or dependencies without a clear design purpose.

Complexity SHOULD emerge from meaningful interactions between mechanics rather than unnecessary procedural overhead.

### 4.7 Consistency with Game Identity

The core loop MUST reinforce the intended game vision and player experience.

Its activities, pacing, decisions, and rewards SHOULD be consistent with the game's identity.

A mechanic that works well in another game is not automatically appropriate for the current project.

## 5. Identifying the Core Gameplay Activity

Before designing a loop, identify the primary activity that players will repeatedly engage in.

Consider:

- What is the player's primary role?
- What actions define the experience?
- What challenges does the player face?
- What decisions make the activity interesting?
- What outcomes motivate continued play?
- What makes the activity distinctive?
- Which mechanics are essential to delivering the experience?

The primary activity SHOULD be specific enough to guide prototyping and evaluation.

Avoid defining the core loop using vague descriptions such as "explore, fight, and progress" without explaining what the player actually does and how those activities connect.

## 6. Designing the Core Loop

### 6.1 Define the Player Action

Identify the primary actions available to the player.

For each important action, consider:

- Its purpose.
- Its input or activation method.
- Its expected result.
- Its cost or risk.
- Its relationship with other actions.
- Its frequency of use.

Actions SHOULD be understandable and provide an appropriate level of control.

### 6.2 Define the Game Response

Determine how the game reacts to player actions.

Consider:

- State changes.
- System interactions.
- Success and failure conditions.
- Environmental responses.
- Enemy or NPC reactions.
- Resource changes.
- Consequences for future decisions.

The game response SHOULD be consistent with the rules communicated to the player.

### 6.3 Define Feedback

Determine how the player recognizes the result of an action.

Important outcomes SHOULD provide sufficient feedback for the player to understand what happened and why.

Feedback SHOULD distinguish meaningful outcomes from ordinary background activity.

### 6.4 Define Rewards and Consequences

Identify what the player gains, loses, or changes through the activity.

Consider:

- Immediate rewards.
- Delayed rewards.
- Resource consumption.
- Risk exposure.
- Opportunity costs.
- Failure consequences.
- Long-term implications.

The relationship between effort and outcome SHOULD support the intended experience.

### 6.5 Define the Next Decision

Determine what motivates or enables the next player action.

The next decision MAY result from:

- A new objective.
- An available opportunity.
- A resource requirement.
- A changing situation.
- A strategic choice.
- A consequence of the previous action.
- The player's own initiative.

The loop SHOULD create a natural continuation rather than relying exclusively on arbitrary instructions or artificial delays.

## 7. Loop Structure and Relationships

### 7.1 Supporting Loops

A game MAY contain multiple supporting loops that contribute to the core loop.

Examples include:

- Resource management.
- Crafting and equipment.
- Exploration and discovery.
- Combat and encounters.
- Base construction.
- Trading and economy.
- Character progression.
- Quest and objective completion.

Supporting loops SHOULD have clear relationships with the core loop.

They SHOULD contribute meaningful decisions, rewards, or opportunities rather than exist as disconnected activities.

### 7.2 Loop Dependencies

When loops depend on one another, their relationships SHOULD be documented.

For example:

- Exploration provides resources.
- Resources enable crafting.
- Crafting improves player capabilities.
- Improved capabilities create new exploration opportunities.

Dependencies SHOULD be evaluated for unnecessary bottlenecks, circular requirements, and progression deadlocks.

### 7.3 Loop Boundaries

Each loop SHOULD have a reasonably clear scope.

Designers SHOULD identify:

- What initiates the loop.
- What actions belong to it.
- What state changes it produces.
- What conditions allow it to continue.
- What conditions end or interrupt it.
- Which other systems it depends on.

Clear boundaries help prevent unrelated mechanics from becoming unnecessarily coupled.

## 8. Pacing and Repetition

### 8.1 Loop Duration

The duration of a core loop SHOULD be appropriate for its gameplay purpose.

Some loops are completed within seconds, while others may take several minutes or longer.

Designers SHOULD consider:

- Frequency of meaningful decisions.
- Time between rewards.
- Time spent waiting.
- Player attention.
- Gameplay intensity.
- Opportunities for variation.
- The intended session length.

There is no universal ideal loop duration.

### 8.2 Pacing Variation

A core loop MAY alternate between different levels of intensity.

For example:

- Preparation followed by execution.
- Exploration followed by confrontation.
- Risk-taking followed by recovery.
- Resource gathering followed by spending.
- Planning followed by experimentation.

Pacing variation SHOULD create a deliberate rhythm without unnecessarily interrupting the core experience.

### 8.3 Repetition Fatigue

Testing SHOULD identify whether repeated engagement becomes monotonous.

Potential causes include:

- Excessive repetitive actions.
- Predictable outcomes.
- Insufficient player agency.
- Slow or unresponsive feedback.
- Unnecessary waiting.
- Repeated content without meaningful variation.
- Rewards that no longer feel valuable.

Solutions SHOULD address the underlying design issue rather than simply adding more content or increasing rewards.

## 9. Risk, Reward, and Player Motivation

The core loop SHOULD establish a meaningful relationship between player effort, decisions, risks, and outcomes.

Consider:

- What motivates the player to engage?
- What makes an action worthwhile?
- What can the player lose?
- What opportunities are available?
- What happens when the player succeeds?
- What happens when the player fails?
- How do outcomes influence future decisions?

Risk and reward SHOULD be appropriate to the intended level of challenge.

Players SHOULD generally have enough information to make informed decisions, unless uncertainty is an intentional gameplay mechanic.

## 10. Failure and Recovery

Failure SHOULD have a deliberate role in the core loop.

Designers SHOULD define:

- What constitutes failure.
- What causes failure.
- How failure is communicated.
- What consequences follow.
- Whether progress is preserved.
- What recovery options exist.
- How the player can learn from the outcome.

Failure MAY result in resource loss, temporary setbacks, altered conditions, restarting an activity, or other consequences.

Consequences SHOULD support the intended experience without creating unnecessary frustration.

Where appropriate, failure SHOULD provide useful feedback or opportunities to change strategy.

## 11. Progression Integration

The core loop SHOULD remain relevant as the player progresses.

Progression MAY introduce:

- Additional actions.
- New strategic options.
- More complex challenges.
- New resources.
- Expanded environments.
- Additional objectives.
- Alternative ways to complete activities.

Progression SHOULD enrich the core loop without making its original mechanics irrelevant.

Designers SHOULD evaluate whether progression creates meaningful changes in how players engage with the loop, rather than only increasing numerical values.

## 12. Prototyping and Validation

The core loop SHOULD be validated through early playable prototypes.

A complete game is not required to evaluate whether its primary gameplay activity is engaging.

### 12.1 Prototype Objectives

An initial core loop prototype SHOULD focus on:

- The primary player action.
- The game response.
- Feedback.
- The immediate outcome.
- The next decision.
- The basic conditions for repetition.

Supporting systems SHOULD be excluded unless they are necessary to evaluate the core experience.

### 12.2 Prototype Evaluation

Evaluate whether:

- The player understands what to do.
- Actions produce understandable outcomes.
- Decisions are meaningful.
- The loop is engaging when repeated.
- The player has sufficient agency.
- Rewards and consequences are appropriate.
- The loop supports the intended game identity.
- The experience remains interesting without extensive supporting content.

### 12.3 Testing Without Assumptions

Designers SHOULD observe actual gameplay rather than relying exclusively on their expectations.

During playtesting, consider:

- What players do without guidance.
- Where they hesitate or become confused.
- Which actions they repeat.
- Which mechanics they ignore.
- Which decisions they find meaningful.
- Where engagement decreases.
- Whether players understand outcomes.

Feedback SHOULD be evaluated critically. Individual preferences are useful observations but do not automatically represent universal player needs.

### 12.4 Iterative Refinement

When problems are identified:

1. Identify the underlying issue.
2. Determine which part of the loop causes it.
3. Formulate a design hypothesis.
4. Change the smallest relevant set of mechanics.
5. Test the revised loop.
6. Compare the results.
7. Record significant decisions.

Avoid expanding the prototype before the fundamental gameplay experience has been validated.

## 13. Core Loop Documentation

Every significant game project SHOULD document its core loop.

The documentation SHOULD include:

- Core loop description.
- Primary player activity.
- Main player actions.
- Game responses.
- Feedback mechanisms.
- Rewards and consequences.
- Loop continuation conditions.
- Supporting loops.
- Important system dependencies.
- Intended pacing.
- Known design risks.
- Validation status.

A visual diagram MAY be used when it communicates the loop more clearly than text.

Diagrams SHOULD show meaningful relationships and direction of flow. Avoid adding visual complexity that does not improve understanding.

## 14. Core Loop Design Template

The following structure MAY be used when documenting a game-specific core loop.

### Core Loop Overview

**Loop Name:**

**Design Purpose:**

**Player Activity:**

**Intended Player Experience:**

**Loop Description:**

Describe the recurring sequence of gameplay activities in plain language.

### Loop Sequence

| Stage | Description | Player Interaction | Game Response |
|---|---|---|---|
| 1. Action | | | |
| 2. Response | | | |
| 3. Feedback | | | |
| 4. Outcome | | | |
| 5. Next Decision | | | |

### Loop Characteristics

| Aspect | Description |
|---|---|
| Primary Objective | |
| Main Player Actions | |
| Resources Involved | |
| Rewards | |
| Risks and Consequences | |
| Failure Conditions | |
| Recovery Options | |
| Expected Duration | |
| Supporting Systems | |
| Dependencies | |

### Validation

**Design Hypotheses:**

- 

**Success Criteria:**

- 

**Test Scenarios:**

- 

**Known Risks:**

- 

**Current Validation Status:**

- Not Validated
- Prototype Validated
- Requires Refinement
- Validated for Current Development Stage

## 15. AI-Assisted Core Loop Design Requirements

AI agents assisting with game design MUST follow these requirements:

1. Read the approved game vision and relevant game-specific design documentation.
2. Identify the intended player experience before proposing a core loop.
3. Distinguish the core loop from supporting loops and long-term progression.
4. Avoid introducing mechanics that do not support the intended experience.
5. Describe player actions, game responses, outcomes, and continuation conditions explicitly.
6. Identify important dependencies between gameplay systems.
7. Consider repetition, pacing, player agency, and meaningful decisions.
8. Identify potential deadlocks, unnecessary bottlenecks, and exploit opportunities.
9. Recommend prototyping and playtesting before treating design assumptions as validated.
10. Clearly distinguish proposed design decisions from approved decisions.
11. Preserve established game design decisions unless authorized to change them.
12. Seek project owner approval before making significant changes to the approved core gameplay direction.

AI-generated diagrams, loop descriptions, and design proposals MUST remain consistent with the approved game vision.

## 16. Core Loop Review Checklist

Before considering a core loop sufficiently defined for its current development stage, evaluate the following:

- [ ] The primary player activity is clearly defined.
- [ ] The loop supports the intended game identity.
- [ ] Player actions are understandable.
- [ ] Game responses are consistent and meaningful.
- [ ] Feedback communicates important outcomes.
- [ ] Rewards and consequences support continued engagement.
- [ ] The next player decision is clear.
- [ ] The loop provides meaningful player agency.
- [ ] Repetition remains engaging or intentionally supports the experience.
- [ ] Supporting loops have clear purposes.
- [ ] Important dependencies have been identified.
- [ ] Failure and recovery are considered.
- [ ] Progression does not invalidate the core loop.
- [ ] The loop has been tested through an appropriate prototype.
- [ ] Known risks and unresolved assumptions are documented.

Not every item applies to every game. Non-applicable items SHOULD be identified rather than treated as mandatory implementation work.

## 17. Related Documents

This document SHOULD be used alongside relevant documents that exist in the repository, including:

- Game vision documentation.
- Game design principles and guidelines.
- Balancing guidelines.
- Gameplay mechanics specifications.
- Progression design documentation.
- Economy design documentation.
- Level and encounter design guidelines.
- Game development lifecycle.
- Quality standards.
- Definition of Done.
- QA and playtesting standards.

Game-specific core loop diagrams, mechanics, and design decisions belong in the individual game's documentation.

## 18. Maintenance

These guidelines SHOULD be reviewed when:

- The studio's game design approach changes.
- New core loop design practices are adopted.
- Repeated design problems reveal gaps in the guidelines.
- New tools or techniques materially improve prototyping and validation.

Changes MUST preserve the document's purpose as a reusable design guideline rather than turning it into a specification for a particular game.

The project owner is responsible for approving changes to studio-wide game design guidelines.