# Balancing Guidelines

## 1. Purpose

This document defines the principles, methods, and quality expectations for balancing gameplay systems.

Its purpose is to help ensure that game mechanics, player progression, difficulty, rewards, resources, and interconnected systems produce a coherent, engaging, and fair player experience.

These guidelines establish a reusable approach to game balance. They do not prescribe fixed numerical values or replace game-specific design decisions.

## 2. Scope

These guidelines apply to gameplay systems involving:

- Player abilities, attributes, and statistics.
- Character progression and advancement.
- Difficulty and challenge.
- Combat and encounters.
- Enemies, bosses, and AI behavior.
- Weapons, equipment, and upgrades.
- Resources, currencies, and economies.
- Rewards, loot, and item acquisition.
- Crafting, construction, and resource management.
- Player choices and competing strategies.
- Time-based mechanics and cooldowns.
- Multiplayer competitive or cooperative systems, when applicable.
- Interactions between multiple gameplay systems.

The guidelines apply during prototyping, pre-production, production, testing, and post-release balancing.

## 3. Balancing Principles

### 3.1 Player Experience First

Balance decisions MUST support the intended player experience and game identity.

A mechanic is not balanced merely because its numerical values are equal or mathematically symmetrical.

Designers SHOULD consider:

- Whether the mechanic is understandable.
- Whether the player has meaningful choices.
- Whether its outcomes feel fair and predictable.
- Whether it creates the intended level of challenge.
- Whether it contributes to the game's overall experience.

### 3.2 Meaningful Choices

Different strategies, abilities, equipment, and approaches SHOULD provide meaningful trade-offs.

When multiple options serve the same purpose, each SHOULD have a reasonable justification for existing.

Avoid situations where one option is consistently superior without meaningful drawbacks or situational limitations.

### 3.3 Fairness and Consistency

Gameplay outcomes SHOULD follow rules that players can understand and learn.

Challenge SHOULD come primarily from the intended gameplay mechanics rather than unclear rules, arbitrary outcomes, or unavoidable situations.

When randomness is involved, its influence SHOULD be understandable and appropriate to the intended experience.

### 3.4 Internal Consistency

Related systems MUST follow coherent design rules.

For example:

- More powerful equipment SHOULD have an appropriate acquisition cost, limitation, or trade-off.
- Higher-level enemies SHOULD present an appropriately increased challenge.
- Resource costs SHOULD be consistent with the value of their resulting benefits.
- Progression SHOULD reflect the intended growth in player capabilities.

Exceptions are acceptable when they serve a deliberate design purpose.

### 3.5 Avoid Unnecessary Complexity

Balancing models SHOULD be as simple as reasonably possible.

Do not introduce excessive modifiers, exceptions, hidden formulas, or interconnected parameters when a simpler model can produce the intended experience.

Complexity MUST be justified by meaningful gameplay value.

### 3.6 Balance Is Contextual

Balance MUST be evaluated in the context of the complete game.

A mechanic that is balanced in isolation may become problematic when combined with other systems.

Designers SHOULD evaluate both individual mechanics and their interactions.

## 4. Design Intent and Balance Targets

Before balancing a system, define its intended purpose and expected player experience.

Where applicable, document:

- The system's primary gameplay purpose.
- The experience it should create.
- Its intended strengths and weaknesses.
- Its relationship with other systems.
- Expected player behavior.
- Relevant constraints and assumptions.
- Measurable balance targets.
- Known risks and potential exploits.

Balance targets SHOULD be measurable whenever practical.

Examples include:

- Expected time to defeat an enemy.
- Expected resource consumption per encounter.
- Average progression time between upgrades.
- Expected reward relative to challenge.
- Maximum acceptable ability uptime.
- Expected survival rate for a particular encounter.
- Expected resource availability during a game segment.

Targets are design hypotheses until validated through testing.

## 5. Difficulty and Challenge

### 5.1 Intended Difficulty

Difficulty SHOULD reflect the intended audience, genre, and experience.

Designers SHOULD consider:

- Player skill and experience.
- Available player abilities.
- Enemy capabilities.
- Resource availability.
- Encounter complexity.
- Environmental conditions.
- Information available to the player.
- Consequences of failure.
- Opportunities to recover or retry.

### 5.2 Difficulty Progression

Difficulty SHOULD increase or change at a pace that supports player learning and progression.

Difficulty progression MAY be achieved through:

- Increased enemy capabilities.
- More complex enemy behaviors.
- Additional encounter mechanics.
- Environmental hazards.
- Reduced resource availability.
- More demanding objectives.
- Greater consequences for mistakes.
- Combinations of previously introduced mechanics.

Avoid increasing difficulty exclusively by inflating enemy health or damage when more meaningful alternatives are available.

### 5.3 Teaching Before Testing

Whenever practical, introduce mechanics in a relatively controlled context before requiring players to master them under pressure.

Players SHOULD have reasonable opportunities to understand and practice important mechanics.

### 5.4 Difficulty Spikes

Difficulty spikes SHOULD be intentional and justified.

Testing SHOULD identify:

- Unexpected increases in encounter difficulty.
- Progression barriers.
- Encounters requiring capabilities the player may not possess.
- Situations where failure provides insufficient learning opportunities.
- Difficulty differences caused by unintended system interactions.

### 5.5 Difficulty Options

When difficulty settings are implemented, their effects SHOULD be documented and consistent.

Difficulty settings SHOULD modify the intended aspects of gameplay without introducing unrelated inconsistencies.

## 6. Progression and Player Growth

### 6.1 Progression Purpose

Progression SHOULD provide a meaningful sense of advancement.

It MAY involve:

- New abilities.
- Improved attributes.
- Equipment upgrades.
- New mechanics.
- Access to additional areas.
- Expanded player options.
- Improved efficiency.
- New strategic possibilities.

Progression SHOULD not rely exclusively on increasing numerical statistics.

### 6.2 Progression Pace

The rate of progression SHOULD support the intended game length and player experience.

Designers SHOULD evaluate:

- Time between meaningful upgrades.
- Frequency of rewards.
- Difficulty of progression requirements.
- Player power growth.
- Content difficulty relative to player capabilities.
- Whether progression becomes repetitive or trivial.

### 6.3 Power Growth

Player power SHOULD grow at a rate compatible with the game's difficulty curve.

Excessive power growth may trivialize encounters or invalidate earlier mechanics.

Insufficient growth may make progression feel unrewarding or create artificial difficulty barriers.

### 6.4 Progression Choices

When players choose between upgrades or progression paths, those choices SHOULD provide meaningful differences.

Avoid presenting choices that appear meaningful but consistently produce one objectively superior result.

### 6.5 Progression Gating

Progression requirements SHOULD have a clear gameplay purpose.

Requirements MAY include skill challenges, resource costs, exploration, narrative milestones, or other objectives.

Avoid unnecessary grinding or artificial restrictions that do not contribute to the intended experience.

## 7. Combat and Encounter Balance

When the game includes combat, combat systems SHOULD be evaluated as interconnected systems rather than isolated statistics.

### 7.1 Combat Parameters

Relevant parameters MAY include:

- Health and damage.
- Attack speed.
- Movement speed.
- Attack range.
- Accuracy and critical chance.
- Armor and damage reduction.
- Resistance and vulnerability.
- Cooldowns.
- Stamina or energy consumption.
- Status effects.
- Healing and recovery.
- Enemy detection and reaction times.

### 7.2 Enemy Roles

Enemies SHOULD have distinguishable gameplay roles.

Examples include:

- Basic enemies that establish fundamental combat interactions.
- Durable enemies that test sustained damage.
- Fast enemies that pressure positioning.
- Ranged enemies that control space.
- Support enemies that modify encounter conditions.
- Elite enemies that combine multiple mechanics.

Enemy roles SHOULD be recognizable through their behavior and presentation.

### 7.3 Encounter Composition

Encounter difficulty depends on more than individual enemy statistics.

Evaluate:

- Number of enemies.
- Enemy combinations.
- Spatial arrangement.
- Available movement space.
- Environmental hazards.
- Player resources.
- Enemy behavior interactions.
- Opportunities for strategic responses.

### 7.4 Player Counterplay

Important enemy attacks and mechanics SHOULD provide reasonable opportunities for player response.

Counterplay MAY include movement, blocking, dodging, interruption, positioning, equipment, or exploiting enemy weaknesses.

Avoid unavoidable damage or failure conditions unless they are an intentional part of the experience.

## 8. Economy and Resource Balance

When the game includes resources or an economy, resource availability and consumption SHOULD support the intended gameplay loop.

### 8.1 Resource Definition

For each important resource, define:

- Its gameplay purpose.
- Sources of acquisition.
- Methods of consumption.
- Storage limitations, if applicable.
- Its relationship with progression.
- Its relative scarcity.
- Its potential for exploitation.

### 8.2 Resource Flow

Evaluate the complete resource lifecycle:

1. Acquisition.
2. Storage.
3. Consumption.
4. Conversion.
5. Reward or reinvestment.

The system SHOULD avoid unintended accumulation, shortages, or infinite generation loops.

### 8.3 Resource Value

Resource costs SHOULD be proportional to their gameplay value.

Designers SHOULD consider:

- Acquisition difficulty.
- Time investment.
- Opportunity cost.
- Alternative uses.
- Progression requirements.
- Availability at different game stages.

### 8.4 Economic Stability

When applicable, test for:

- Inflation or uncontrolled currency accumulation.
- Resource starvation.
- Dominant resource farming strategies.
- Infinite resource generation.
- Unintended item duplication.
- Excessive dependence on repetitive activities.
- Unbalanced conversion rates.

### 8.5 Resource Sinks

Resource sinks SHOULD provide meaningful reasons to consume accumulated resources.

Avoid adding costs solely to remove excess resources without considering their effect on player motivation and progression.

## 9. Rewards and Risk

Rewards SHOULD reflect the effort, difficulty, risk, and opportunity cost associated with obtaining them.

Evaluate:

- Reward frequency.
- Reward magnitude.
- Reward variety.
- Player expectations.
- Risk versus reward.
- Repeated activity efficiency.
- Long-term progression impact.

Rewards SHOULD encourage the intended gameplay behavior without forcing players into repetitive or undesirable activities.

Rare rewards MAY create excitement, but randomness SHOULD not make essential progression unreasonably inaccessible.

## 10. Abilities, Equipment, and Build Diversity

### 10.1 Ability Balance

Abilities SHOULD have identifiable purposes, strengths, and limitations.

Evaluate:

- Effectiveness.
- Resource consumption.
- Cooldown.
- Duration.
- Range.
- Frequency of use.
- Synergies.
- Situational value.
- Counterplay, where applicable.

### 10.2 Equipment Balance

Equipment SHOULD provide meaningful differences without making alternative options irrelevant.

Potential balancing factors include:

- Damage or defensive effectiveness.
- Weight or movement penalties.
- Resource requirements.
- Acquisition difficulty.
- Durability.
- Special effects.
- Situational advantages.

### 10.3 Build Diversity

When character builds or loadouts are supported, multiple viable approaches SHOULD exist.

Balance testing SHOULD identify:

- Dominant combinations.
- Abilities that are rarely selected.
- Strategies that require disproportionate investment.
- Combinations that create unintended effects.
- Options that become obsolete too early.

Not every build must be equally effective in every situation. Different builds SHOULD have meaningful strengths and weaknesses.

## 11. Mathematical and Statistical Balancing

### 11.1 Use Appropriate Models

Use mathematical models when they help understand or predict system behavior.

Possible techniques include:

- Linear and nonlinear scaling.
- Ratios and proportional relationships.
- Probability distributions.
- Expected value calculations.
- Resource-flow models.
- Time-to-kill calculations.
- Damage-per-second calculations.
- Progression curves.
- Simulation and statistical analysis.

The selected model SHOULD match the actual gameplay system.

### 11.2 Document Formulas

Important balancing formulas SHOULD be documented with:

- Variable definitions.
- Units.
- Expected input ranges.
- Constraints.
- Assumptions.
- Example calculations.
- Known limitations.

Avoid unexplained constants and arbitrary multipliers.

### 11.3 Avoid False Precision

Numerical precision does not guarantee good gameplay balance.

Mathematical results MUST be validated through gameplay testing.

Use numerical models to guide decisions, not replace player experience.

### 11.4 Boundary Testing

Test relevant parameter boundaries, including:

- Minimum and maximum values.
- Zero or near-zero values.
- Extreme combinations.
- Repeated application of modifiers.
- Stacking effects.
- Rounding behavior.
- Overflow or invalid values.

## 12. Balance Testing and Validation

Balancing SHOULD follow an iterative, evidence-based process.

### 12.1 Initial Analysis

Before implementation or major adjustments:

- Review the system's design intent.
- Identify relevant parameters.
- Identify dependencies and interactions.
- Establish initial balance hypotheses.
- Define measurable observations.
- Identify potential exploits and edge cases.

### 12.2 Controlled Testing

Where practical, modify a limited number of parameters at a time.

This makes it easier to identify which changes caused an observed result.

For complex systems, controlled experiments or simulation MAY be used to compare alternative configurations.

### 12.3 Playtesting

Playtesting SHOULD include:

- Normal intended gameplay.
- Skilled and unskilled player behavior, where relevant.
- Alternative strategies.
- Unusual but valid player actions.
- Edge cases.
- Repeated encounters or progression cycles.

Observe actual player behavior rather than relying exclusively on design assumptions.

### 12.4 Metrics and Observations

Relevant metrics MAY include:

- Win and failure rates.
- Encounter completion time.
- Damage dealt and received.
- Resource consumption.
- Reward acquisition.
- Progression time.
- Ability usage frequency.
- Equipment selection.
- Player deaths.
- Retry frequency.
- Strategy diversity.

Metrics SHOULD be interpreted in context. A high usage rate does not automatically indicate that an ability is overpowered.

### 12.5 Qualitative Feedback

Quantitative data SHOULD be complemented by qualitative observations.

Consider whether players report:

- Frustration.
- Confusion.
- Repetition.
- Lack of meaningful choices.
- Excessive difficulty.
- Lack of challenge.
- Unsatisfying rewards.
- Unexpected or unfair outcomes.

### 12.6 Regression Testing

After changing balance parameters, verify that related systems remain functional and within acceptable ranges.

A change to one mechanic MAY affect multiple other systems.

Important balance adjustments SHOULD include regression checks for known dependencies.

## 13. Iterative Balancing Workflow

Use the following workflow when designing or adjusting a gameplay system:

1. **Define intent:** Establish the intended player experience and system purpose.
2. **Identify variables:** List the parameters that influence the system.
3. **Establish hypotheses:** Describe expected behavior and potential problems.
4. **Set initial values:** Implement reasonable starting values.
5. **Analyze:** Use calculations, models, or simulations where useful.
6. **Test:** Validate the system through gameplay and relevant metrics.
7. **Evaluate:** Compare observed results against the intended experience.
8. **Adjust:** Change parameters or mechanics based on evidence.
9. **Regression test:** Verify related systems and previously validated behavior.
10. **Document:** Record important decisions, assumptions, and unresolved issues.

Balancing is continuous. A system SHOULD be revisited when new mechanics, content, or progression paths change its context.

## 14. Balance Configuration and Data Management

Where practical, balance-related values SHOULD be separated from gameplay logic.

In Godot projects, consider using appropriate resources, configuration files, or other data-driven approaches for tunable gameplay parameters.

Examples include:

- Enemy statistics.
- Weapon damage.
- Ability costs.
- Cooldowns.
- Reward tables.
- Progression thresholds.
- Difficulty modifiers.

The implementation SHOULD:

- Use clear and consistent parameter names.
- Define appropriate value ranges.
- Avoid unnecessary duplication.
- Preserve a clear source of truth.
- Make important values easy to inspect and adjust.
- Validate configuration data where practical.

Do not introduce data-driven architecture solely for the sake of abstraction. The approach SHOULD be proportional to the complexity and expected evolution of the system.

## 15. Balance Documentation

Significant gameplay systems SHOULD document their balancing assumptions and important decisions.

Documentation MAY include:

- System purpose.
- Balance targets.
- Important formulas.
- Parameter definitions.
- Expected ranges.
- Progression curves.
- Test scenarios.
- Observed results.
- Known balance issues.
- Accepted trade-offs.
- Unresolved risks.

Major balance changes SHOULD include a brief explanation of:

- What changed.
- Why it changed.
- What evidence supported the change.
- Which related systems were evaluated.
- What remains uncertain.

Avoid documenting every minor numerical adjustment when it provides no meaningful long-term value.

## 16. Balance Issues and Prioritization

Balance issues SHOULD be prioritized according to their impact on the intended player experience.

### Critical

Issues that make important gameplay systems unusable, enable severe exploits, or prevent intended progression.

### High

Issues that significantly undermine challenge, progression, fairness, or strategic diversity.

### Medium

Issues that create noticeable imbalance but do not substantially prevent normal gameplay.

### Low

Minor tuning opportunities, isolated inconsistencies, or improvements with limited player impact.

Prioritization SHOULD consider frequency, severity, affected content, and available workarounds.

## 17. AI-Assisted Balancing Requirements

AI agents assisting with game design or implementation MUST follow these requirements:

1. Read relevant game-specific design documentation before proposing balance changes.
2. Follow the intended game identity and player experience.
3. Inspect existing mechanics and dependencies before modifying values.
4. Avoid inventing undocumented design assumptions.
5. Distinguish calculated results from estimated or hypothetical values.
6. Explain important formulas and assumptions.
7. Avoid changing unrelated balance parameters.
8. Identify potential interactions and regression risks.
9. Recommend testing when a change cannot be validated analytically.
10. Document significant balance changes and their rationale.
11. Never claim that a system is balanced without appropriate validation evidence.
12. Seek project owner approval before making significant changes to approved gameplay direction or progression design.

AI-generated balance recommendations are proposals until reviewed and validated.

## 18. Balance Review Checklist

Before considering a gameplay system sufficiently balanced for its current development stage, evaluate the following:

- [ ] The system has a clearly defined gameplay purpose.
- [ ] Its intended player experience is documented.
- [ ] Important parameters and assumptions are understood.
- [ ] Its values are consistent with related systems.
- [ ] Its strengths and limitations are meaningful.
- [ ] Its difficulty and progression impact are appropriate.
- [ ] Its resource and reward interactions have been evaluated.
- [ ] Potential exploits and dominant strategies have been considered.
- [ ] Relevant edge cases have been tested.
- [ ] Gameplay testing supports the intended behavior.
- [ ] Significant changes have been regression tested.
- [ ] Known issues and unresolved assumptions are documented.

Not every item applies to every system. Mark non-applicable items accordingly rather than introducing unnecessary work.

## 19. Related Documents

This document SHOULD be used alongside relevant documents that exist in the repository, including:

- Game vision and design documentation.
- Game design principles and guidelines.
- Gameplay mechanics specifications.
- Progression design documentation.
- Economy design documentation.
- Difficulty design documentation.
- Game development lifecycle.
- Quality standards.
- Definition of Done.
- QA and playtesting standards.

Game-specific balancing specifications and numerical configurations belong in the relevant game project's documentation and implementation, not in this reusable guideline.

## 20. Maintenance

These guidelines SHOULD be reviewed when:

- The studio's game design approach changes.
- New balancing practices are adopted.
- Repeated balancing problems reveal gaps in the guidelines.
- New tools or techniques materially improve balancing workflows.

Changes MUST preserve the document's purpose as a reusable guideline rather than turning it into a specification for a particular game.

The project owner is responsible for approving changes to studio-wide design guidelines.