# Reward Design Guidelines

## 1. Purpose

This document defines reusable guidelines for designing, implementing, and evaluating reward systems in games developed by the studio.

Its purpose is to ensure rewards reinforce intended player behaviors, provide meaningful feedback, support player motivation, and contribute positively to the overall gameplay experience.

Reward systems SHOULD provide value beyond simply distributing items or increasing numerical statistics.

## 2. Scope

These guidelines cover:

- Reward types and classifications.
- Reward sources and distribution.
- Reward value and significance.
- Reward frequency and pacing.
- Risk and reward relationships.
- Achievement and milestone rewards.
- Exploration and discovery rewards.
- Randomized and deterministic rewards.
- Reward feedback and presentation.
- Reward interactions with progression and economy systems.
- Reward testing and validation.

These guidelines apply to gameplay rewards, progression rewards, exploration rewards, narrative rewards, and other forms of positive reinforcement.

They do not prescribe a universal reward model. Each game MUST select reward structures appropriate to its intended experience.

## 3. Core Reward Design Principles

### 3.1 Purposeful Rewards

Every significant reward SHOULD have a defined design purpose.

Rewards may:

- Reinforce desired player behaviors.
- Recognize achievement or mastery.
- Encourage exploration and experimentation.
- Support character or equipment development.
- Introduce new gameplay opportunities.
- Provide narrative information.
- Encourage strategic decisions.
- Communicate progress.
- Create memorable experiences.

Rewards MUST support the game's design goals rather than exist solely to increase the quantity of obtainable content.

### 3.2 Meaningful Value

A reward SHOULD provide value that players can understand or experience.

Value may be:

- Functional: improves capabilities or provides useful resources.
- Strategic: introduces new choices or possibilities.
- Progression-based: contributes to long-term advancement.
- Narrative: reveals information or develops the world.
- Emotional: creates satisfaction, recognition, or attachment.
- Cosmetic: provides personalization or visual distinction.
- Social: recognizes participation or achievement in social contexts.

A reward does not need to increase player power to be meaningful.

### 3.3 Appropriate Expectations

Players SHOULD understand the relationship between an action and its expected reward.

The game MUST communicate important reward conditions clearly.

Unexpected rewards MAY be used to create surprise, but critical progression requirements SHOULD NOT depend on unclear or misleading reward expectations.

### 3.4 Fairness and Consistency

Reward distribution MUST follow consistent rules.

Similar actions under comparable conditions SHOULD provide reasonably consistent reward opportunities unless variation is an intentional design objective.

Rewards SHOULD reflect the effort, challenge, risk, or achievement involved.

### 3.5 Respect for Player Time

Reward systems SHOULD respect the time and effort invested by players.

Designers SHOULD avoid:

- Excessive repetitive activities with negligible rewards.
- Artificially inflated requirements.
- Unnecessary reward delays.
- Excessive dependence on random outcomes.
- Repeated rewards that have no meaningful use.
- Progression barriers created solely to encourage repetition.

Time investment SHOULD contribute to a meaningful gameplay experience.

### 3.6 Gameplay Integrity

Rewards MUST NOT undermine the intended gameplay experience.

Designers SHOULD evaluate whether reward structures encourage undesirable behavior, trivialize challenges, or create dominant strategies that reduce meaningful player decisions.

## 4. Reward Categories

### 4.1 Functional Rewards

Functional rewards directly affect gameplay capabilities.

Examples include:

- Weapons.
- Equipment.
- Consumables.
- Tools.
- Abilities.
- Upgrades.
- Defensive or offensive improvements.

Functional rewards SHOULD be evaluated for their impact on existing gameplay systems and balance.

### 4.2 Resource Rewards

Resource rewards provide materials or currencies used by other game systems.

Examples include:

- Currency.
- Crafting materials.
- Consumable resources.
- Upgrade materials.
- Building resources.
- Tradeable items.

Resource rewards MUST have a defined relationship with the game's economy.

Designers SHOULD consider how resource availability affects acquisition, consumption, scarcity, and long-term progression.

Detailed resource generation and consumption MUST follow `ECONOMY_DESIGN_GUIDELINES.md`.

### 4.3 Progression Rewards

Progression rewards contribute directly to player advancement.

Examples include:

- Experience points.
- Skill points.
- Character levels.
- Permanent upgrades.
- Progression unlocks.
- New specializations.

Progression rewards SHOULD reinforce the intended advancement structure.

Their impact on progression pacing MUST be evaluated using `PROGRESSION_DESIGN_GUIDELINES.md`.

### 4.4 Cosmetic Rewards

Cosmetic rewards modify appearance without necessarily affecting gameplay performance.

Examples include:

- Character outfits.
- Visual effects.
- Decorations.
- Weapon appearances.
- Animations.
- Customization options.

Cosmetic rewards SHOULD provide desirable personalization or recognition.

When cosmetic and functional rewards coexist, their differences MUST be clear to players.

### 4.5 Narrative Rewards

Narrative rewards provide story-related information or developments.

Examples include:

- Documents.
- Character interactions.
- Lore discoveries.
- Story revelations.
- Relationship developments.
- Environmental storytelling.
- New narrative scenes.

Narrative rewards SHOULD contribute to worldbuilding, character development, or player understanding.

They SHOULD NOT unnecessarily interrupt gameplay or hide essential information behind poorly communicated requirements.

### 4.6 Access and Opportunity Rewards

These rewards provide access to additional gameplay possibilities.

Examples include:

- New areas.
- Missions.
- Gameplay modes.
- Special encounters.
- Activities.
- Vendors or services.
- New interaction opportunities.

Access rewards SHOULD be integrated with the game's progression and content structure.

### 4.7 Recognition Rewards

Recognition rewards acknowledge player accomplishments.

Examples include:

- Achievements.
- Titles.
- Badges.
- Records.
- Collections.
- Completion milestones.
- Special visual recognition.

Recognition SHOULD reflect meaningful accomplishments rather than encourage unnecessary activity without a clear purpose.

### 4.8 Knowledge and Discovery Rewards

Some rewards provide information or understanding rather than tangible items.

Examples include:

- Discovering hidden mechanics.
- Learning enemy weaknesses.
- Finding shortcuts.
- Understanding environmental patterns.
- Revealing secrets.
- Discovering alternative solutions.

Knowledge rewards SHOULD preserve the satisfaction of discovery while providing sufficient feedback for players to recognize meaningful findings.

## 5. Reward Sources

Every reward SHOULD have a clearly defined source.

Common reward sources include:

### 5.1 Objective Completion

Rewards granted for completing defined objectives, missions, quests, or tasks.

Designers SHOULD ensure that rewards reflect the importance and intended challenge of the objective.

### 5.2 Combat and Encounters

Rewards granted for defeating enemies, completing encounters, or overcoming combat challenges.

Reward structures SHOULD avoid encouraging unnecessary combat when it conflicts with the intended gameplay experience.

### 5.3 Exploration

Rewards granted for discovering locations, secrets, landmarks, hidden paths, or environmental information.

Exploration rewards SHOULD encourage curiosity and observation.

They MAY be placed outside the primary path, provided their discovery is reasonably achievable and consistent with the game's exploration design.

### 5.4 Skill and Mastery

Rewards granted for demonstrating skill, completing challenges, or mastering mechanics.

Examples include:

- Performance-based rewards.
- Optional challenge completion.
- Advanced combat achievements.
- Time-based objectives.
- No-damage or limited-resource challenges.

Performance rewards SHOULD be based on clear and consistent criteria.

### 5.5 Collection and Completion

Rewards granted for collecting items, completing sets, discovering content, or fulfilling collection objectives.

Collection systems SHOULD provide meaningful feedback about progress and remaining objectives.

Designers SHOULD avoid excessive collection requirements that add little gameplay value.

### 5.6 Narrative Events

Rewards granted through story progression, character interactions, decisions, or narrative milestones.

Narrative rewards MUST remain consistent with established story conditions and consequences.

### 5.7 Recurring Activities

Rewards granted through repeatable activities, challenges, or gameplay cycles.

Recurring reward systems MUST be evaluated for repetitive behavior, reward inflation, and long-term sustainability.

## 6. Reward Structure

### 6.1 Immediate Rewards

Immediate rewards are provided directly after an action or achievement.

Examples include:

- Collecting an item.
- Defeating an enemy.
- Completing a small objective.
- Discovering a resource.

Immediate rewards SHOULD provide clear feedback and reinforce the relationship between player action and outcome.

### 6.2 Milestone Rewards

Milestone rewards are provided after reaching significant objectives or accomplishments.

Examples include:

- Completing a chapter.
- Reaching a progression milestone.
- Defeating a major encounter.
- Completing a collection.
- Unlocking a major feature.

Milestone rewards SHOULD feel distinguishable from routine rewards.

### 6.3 Long-Term Rewards

Long-term rewards require sustained effort or completion of multiple objectives.

Examples include:

- Rare equipment.
- Major unlocks.
- Permanent upgrades.
- Special achievements.
- Significant narrative outcomes.

Long-term rewards SHOULD provide intermediate feedback so players can recognize their progress.

### 6.4 Composite Rewards

Composite rewards combine multiple reward types.

For example, completing a major mission may provide:

- Currency.
- Equipment.
- Experience.
- Narrative information.
- Access to a new area.

Composite rewards SHOULD be structured so that each component has a meaningful purpose.

## 7. Reward Value and Significance

### 7.1 Perceived Value

Reward value is determined not only by its numerical or functional properties but also by how players perceive its usefulness and significance.

Designers SHOULD consider:

- Immediate usefulness.
- Long-term usefulness.
- Rarity and availability.
- Player preferences.
- Gameplay context.
- Opportunity cost.
- Existing inventory or capabilities.
- Emotional or narrative significance.

A reward with high numerical value may still feel insignificant if it does not improve the player's experience.

### 7.2 Contextual Value

Reward value SHOULD be evaluated in the context where the reward is obtained.

The same reward may have different significance depending on:

- Player progression.
- Available resources.
- Current challenges.
- Equipment and abilities.
- Game stage.
- Player objectives.

Designers SHOULD avoid assuming that a reward has equal value throughout the entire game.

### 7.3 Reward Hierarchy

Games MAY establish reward tiers to communicate differences in significance.

A reward hierarchy could distinguish:

- Common rewards.
- Uncommon rewards.
- Rare rewards.
- Exceptional rewards.
- Unique or milestone rewards.

Tier names and classifications MUST remain consistent.

Rarity SHOULD represent an intentional design property rather than serve as a substitute for meaningful reward design.

### 7.4 Redundant Rewards

A redundant reward provides something the player already has or cannot meaningfully use.

Redundant rewards MAY be intentional when they support collection, resource conversion, or other established systems.

When duplicates are possible, designers SHOULD define their behavior.

Possible solutions include:

- Resource conversion.
- Upgrade materials.
- Alternative uses.
- Collection tracking.
- Duplicate compensation.
- Explicit duplicate restrictions.

## 8. Reward Frequency and Pacing

### 8.1 Reward Frequency

Reward frequency MUST support the intended gameplay rhythm.

Designers SHOULD consider:

- Frequency of player actions.
- Expected session duration.
- Encounter length.
- Objective difficulty.
- Progression pacing.
- Reward significance.
- Player expectations.

Frequent rewards SHOULD NOT make significant milestones feel ordinary.

Infrequent rewards SHOULD NOT create extended periods where player actions feel unrewarded.

### 8.2 Reward Density

Reward density describes how frequently meaningful rewards occur relative to gameplay time or activity.

Designers SHOULD evaluate reward density across:

- Individual encounters.
- Gameplay sessions.
- Major progression stages.
- Exploration activities.
- Long-term objectives.

Reward density SHOULD be appropriate to the game's pacing and intended experience.

### 8.3 Reward Escalation

Reward escalation occurs when reward significance or quantity increases as the player advances.

Escalation MAY communicate increasing challenge or achievement.

However, designers SHOULD avoid uncontrolled reward inflation.

Increasing reward quantities MUST be evaluated against the game's economy and progression systems.

### 8.4 Reward Fatigue

Reward fatigue occurs when repeated rewards lose their perceived significance.

Potential causes include:

- Excessive notifications.
- Repetitive reward structures.
- Too many low-value items.
- Constant numerical increases.
- Predictable reward outcomes.
- Lack of meaningful choices.

Designers SHOULD vary reward experiences where appropriate and ensure that significant rewards remain distinguishable.

## 9. Risk and Reward

### 9.1 Meaningful Risk

Risk/reward systems offer potential benefits in exchange for uncertainty, difficulty, resource expenditure, or potential loss.

Risk SHOULD be understandable and proportionate to the possible reward.

Players SHOULD have sufficient information to make informed decisions unless uncertainty itself is an intentional gameplay element.

### 9.2 Reward Proportionality

Higher-risk activities MAY provide greater rewards, but reward value MUST be evaluated in relation to:

- Difficulty.
- Time investment.
- Probability of failure.
- Resource expenditure.
- Potential losses.
- Available alternatives.

Risk/reward relationships SHOULD create interesting decisions rather than obvious dominant choices.

### 9.3 Failure and Compensation

Designers MUST define whether failure provides partial rewards, no rewards, or alternative outcomes.

Failure rewards MAY recognize:

- Partial objective completion.
- Progress toward a larger goal.
- Information gained.
- Resources recovered.
- Skill or performance milestones.

Failure SHOULD NOT automatically grant rewards that undermine the purpose of the challenge.

## 10. Deterministic and Randomized Rewards

### 10.1 Deterministic Rewards

Deterministic rewards provide known outcomes when specified conditions are met.

Examples include:

- Fixed mission rewards.
- Guaranteed milestone unlocks.
- Defined achievement rewards.
- Known crafting outputs.

Deterministic rewards are appropriate when players should be able to plan around predictable outcomes.

### 10.2 Randomized Rewards

Randomized rewards introduce variation into reward outcomes.

Examples include:

- Random item drops.
- Loot tables.
- Procedurally generated rewards.
- Randomized reward selections.

Randomized systems MUST define:

- Possible outcomes.
- Probability distributions.
- Eligibility conditions.
- Duplicate behavior.
- Guaranteed rewards, if applicable.
- Relevant limits or exclusions.

Randomness SHOULD create variety without making important progression dependent on unreasonable luck.

### 10.3 Probability Transparency

When probabilities materially affect player decisions, the game SHOULD communicate relevant probability information.

Designers MUST ensure that displayed probabilities accurately reflect actual reward behavior.

Randomized reward systems SHOULD be tested statistically where appropriate.

### 10.4 Protection Against Unreasonable Randomness

Designers MAY use mechanisms such as:

- Guaranteed milestone rewards.
- Duplicate protection.
- Pity systems.
- Reward pools.
- Controlled randomization.
- Minimum reward guarantees.

These mechanisms SHOULD address identifiable player experience or balance problems rather than add unnecessary complexity.

## 11. Reward Choice and Player Agency

Some reward systems allow players to select from multiple possible rewards.

Meaningful reward choices SHOULD provide understandable differences.

Designers SHOULD consider:

- Different playstyles.
- Immediate versus long-term value.
- Specialization opportunities.
- Opportunity costs.
- Resource requirements.
- Compatibility with existing capabilities.

Reward choices SHOULD avoid presenting several options that are functionally identical or contain one obviously superior option without an intentional reason.

When choices are irreversible, their consequences MUST be communicated clearly.

## 12. Reward Presentation and Feedback

### 12.1 Reward Recognition

Players SHOULD be able to recognize when they receive a meaningful reward.

Presentation may include:

- Visual effects.
- Audio feedback.
- Notifications.
- Item descriptions.
- Progress indicators.
- Updated objectives.
- Collection updates.
- Character or environment changes.

Presentation SHOULD reinforce reward significance without overwhelming the player.

### 12.2 Reward Information

Reward descriptions SHOULD communicate relevant information.

Depending on the reward, this may include:

- Name.
- Description.
- Function.
- Quantity.
- Rarity.
- Requirements.
- Effects.
- Restrictions.
- Usage instructions.

Information MUST be accurate and consistent with the actual reward behavior.

### 12.3 Reward Delivery

Designers MUST define how rewards are delivered.

Possible delivery methods include:

- Direct inventory addition.
- World pickup.
- Unlock notification.
- Mail or storage systems.
- Reward selection screens.
- Automatic progression updates.

Reward delivery MUST be reliable and SHOULD avoid unnecessary interruptions.

### 12.4 Inventory and Capacity Constraints

When rewards occupy limited inventory or storage space, designers MUST define what happens when capacity is insufficient.

Possible behaviors include:

- Blocking the reward claim.
- Sending rewards to temporary storage.
- Dropping items into the world.
- Converting rewards into resources.
- Allowing controlled overflow.

The selected behavior MUST be communicated clearly and MUST NOT silently discard important rewards.

## 13. Reward Interactions With Other Systems

### 13.1 Progression

Rewards SHOULD support the intended progression structure.

Designers MUST evaluate whether rewards:

- Accelerate progression appropriately.
- Unlock new capabilities.
- Introduce new decisions.
- Create progression bottlenecks.
- Make other progression activities irrelevant.

Progression-related reward decisions SHOULD follow `PROGRESSION_DESIGN_GUIDELINES.md`.

### 13.2 Economy

Resource and currency rewards MUST be evaluated against the game's economic model.

Designers SHOULD consider:

- Resource availability.
- Resource consumption.
- Inflation.
- Scarcity.
- Reward farming.
- Existing resource sources.
- Long-term economic sustainability.

Reward generation and resource sinks SHOULD remain balanced.

### 13.3 Gameplay Mechanics

Rewards MUST interact correctly with gameplay mechanics.

Designers SHOULD evaluate whether rewards:

- Change combat strategies.
- Enable new interactions.
- Affect exploration.
- Modify survival capabilities.
- Introduce new system dependencies.
- Create unintended exploits.

### 13.4 Difficulty

Reward availability and power MUST be considered when designing challenge progression.

Rewards SHOULD reinforce player advancement without unintentionally trivializing future challenges.

### 13.5 Narrative

Narrative rewards SHOULD respect story continuity, world logic, and established character motivations.

Reward presentation MUST NOT contradict important narrative events or player decisions.

## 14. Reward Exploits and Farming

Reward systems SHOULD be evaluated for unintended repeatability and exploitation.

Potential issues include:

- Repeating an activity for disproportionate rewards.
- Exploiting respawning enemies or resources.
- Resetting encounters to duplicate rewards.
- Receiving rewards multiple times from one-time objectives.
- Bypassing reward prerequisites.
- Manipulating randomized reward conditions.
- Combining reward sources to generate excessive resources.
- Exploiting save and load behavior.

Designers SHOULD distinguish intentional farming opportunities from unintended reward exploits.

Repeatable reward sources MUST have a defined purpose and acceptable long-term impact.

## 15. Reward Persistence and Integrity

When rewards persist across gameplay sessions, their acquisition and storage MUST be reliable.

Systems MUST define:

- When a reward is considered earned.
- When it is delivered.
- How it is saved.
- How it is restored.
- How duplicate delivery is handled.
- How interrupted reward transactions are handled.
- How invalid reward states are recovered.

Important rewards MUST NOT be silently lost because of scene transitions, saving interruptions, or inconsistent system states.

Reward delivery SHOULD be idempotent where repeated processing could otherwise grant the same reward more than once.

## 16. Reward Design Documentation

Every significant reward system SHOULD have a documented specification.

A reward specification SHOULD include:

| Element | Description |
|---|---|
| Purpose | Why the reward exists |
| Reward category | Functional, resource, progression, cosmetic, narrative, access, recognition, or knowledge |
| Source | Activity, objective, encounter, event, or achievement that grants it |
| Eligibility | Conditions required to receive it |
| Reward content | Items, resources, unlocks, or other outcomes |
| Value | Intended usefulness or significance |
| Frequency | How often it can be obtained |
| Distribution | Deterministic, randomized, or conditional |
| Probability | Defined probabilities when applicable |
| Limits | Caps, restrictions, and duplicate behavior |
| Delivery | How the reward reaches the player |
| Persistence | Whether and how the reward is saved |
| Dependencies | Related gameplay, economy, and progression systems |
| Edge cases | Exceptional conditions and failure behavior |
| Validation | How reward behavior and player experience will be evaluated |

Complex reward tables SHOULD be maintained in structured data rather than duplicated across unrelated documentation.

## 17. Testing and Validation

Reward systems MUST be tested for functional correctness and intended player experience.

### 17.1 Functional Validation

Verify that:

- Rewards are granted under the correct conditions.
- Ineligible players cannot claim restricted rewards.
- Reward quantities are correct.
- Randomized outcomes follow their defined rules.
- Duplicate behavior is correct.
- Inventory constraints are handled correctly.
- Rewards persist when required.
- Interrupted reward delivery does not cause loss or duplication.
- Repeatable rewards follow their intended limits.

### 17.2 Balance Validation

Evaluate:

- Reward value relative to effort.
- Reward frequency.
- Resource generation.
- Progression impact.
- Risk/reward relationships.
- Reward distribution across gameplay stages.
- Potential farming strategies.
- Differences between reward sources.

### 17.3 Player Experience Validation

Playtesting SHOULD evaluate whether players:

- Understand why they received a reward.
- Recognize meaningful rewards.
- Consider rewards useful or desirable.
- Understand reward requirements.
- Feel appropriately recognized.
- Have meaningful reward choices.
- Experience an appropriate reward frequency.
- Can identify the consequences of reward decisions.

### 17.4 Randomized Reward Validation

For randomized rewards, verify:

- Probability calculations.
- Outcome distribution.
- Boundary conditions.
- Duplicate handling.
- Guaranteed reward behavior.
- Long-term statistical behavior where relevant.

Testing MUST distinguish between an implementation defect and normal statistical variation.

## 18. Iterative Reward Design

Reward systems SHOULD be refined through an iterative process.

A recommended workflow is:

1. Define the intended player behavior or experience.
2. Identify the purpose of the reward.
3. Select an appropriate reward category.
4. Define reward sources and eligibility conditions.
5. Determine reward value and significance.
6. Establish frequency and distribution rules.
7. Evaluate interactions with progression, economy, and gameplay.
8. Prototype the reward system.
9. Validate functional behavior.
10. Playtest reward perception and pacing.
11. Refine the system based on evidence.
12. Update the reward specification.

Changes to reward values, probabilities, or availability MUST be evaluated for their impact on connected systems.

## 19. Godot Implementation Considerations

Reward implementation MUST follow the project's approved technical and architectural standards.

The following principles SHOULD guide implementation:

- Keep reward logic within the feature that owns the reward system.
- Separate reward definitions from reward presentation where appropriate.
- Use suitable Godot resources or structured data for configurable reward definitions.
- Avoid hardcoding large reward tables into unrelated scripts.
- Validate reward eligibility before granting rewards.
- Centralize shared reward distribution rules when multiple features use them.
- Ensure reward delivery is reliable and consistent.
- Handle inventory capacity and persistence explicitly.
- Use clear interfaces or signals when other features need to react to reward events.
- Avoid circular dependencies between reward, progression, inventory, and economy features.

Reward implementation SHOULD remain testable and maintainable without introducing unnecessary abstractions.

## 20. AI-Assisted Reward Design Requirements

AI agents assisting with reward design MUST:

1. Read this document and relevant game-specific design specifications.
2. Identify the intended purpose of each proposed reward.
3. Respect approved reward structures and existing design decisions.
4. Evaluate interactions with progression, economy, difficulty, and gameplay.
5. Identify potential exploits and unintended farming opportunities.
6. Avoid introducing redundant or meaningless rewards.
7. Document assumptions about values, probabilities, and reward frequency.
8. Validate calculations and distribution rules before presenting them as correct.
9. Propose significant changes to reward structures for human approval.
10. Never mark unapproved reward decisions as approved.

AI-generated reward tables, probability distributions, and balance recommendations MUST be reviewed and validated before implementation.

## 21. Reward Design Review Checklist

Before approving a reward system, verify the following:

### Design Intent
- [ ] Every significant reward has a defined purpose.
- [ ] Rewards reinforce the intended player experience.
- [ ] Reward categories are appropriate.
- [ ] Rewards support meaningful player behavior.

### Reward Structure
- [ ] Reward sources are clearly defined.
- [ ] Eligibility conditions are specified.
- [ ] Reward values are appropriate to their context.
- [ ] Reward frequency supports gameplay pacing.
- [ ] Major rewards are distinguishable from routine rewards.

### Player Experience
- [ ] Players can understand important reward conditions.
- [ ] Reward feedback is clear and appropriate.
- [ ] Reward choices are meaningful where applicable.
- [ ] Reward systems respect player time.
- [ ] Reward fatigue has been considered.

### System Integration
- [ ] Progression interactions have been evaluated.
- [ ] Economy impact has been evaluated.
- [ ] Difficulty impact has been evaluated.
- [ ] Gameplay and narrative consistency have been considered.
- [ ] Persistence and inventory behavior are defined where applicable.

### Validation
- [ ] Reward distribution has been tested.
- [ ] Randomized outcomes have been validated where applicable.
- [ ] Duplicate and farming behavior have been evaluated.
- [ ] Edge cases have been considered.
- [ ] The reward specification is up to date.

## 22. Related Documents

Consult the following documents when relevant:

- `DESIGN_PRINCIPLES.md`
- `CORE_LOOP_DESIGN_GUIDELINES.md`
- `GAMEPLAY_DESIGN_GUIDELINES.md`
- `MECHANIC_DESIGN_GUIDELINES.md`
- `PLAYER_EXPERIENCE_GUIDELINES.md`
- `PROGRESSION_DESIGN_GUIDELINES.md`
- `BALANCING_GUIDELINES.md`
- `DIFFICULTY_DESIGN_GUIDELINES.md`
- `ECONOMY_DESIGN_GUIDELINES.md`
- `NARRATIVE_DESIGN_GUIDELINES.md`

Technical implementation MUST also follow the applicable studio technical standards and project-specific architecture documentation.

## 23. Maintenance

This document SHOULD be reviewed periodically and updated when:

- Studio-wide reward design practices change.
- New reward models become relevant.
- Existing guidance becomes unclear or outdated.
- Repeated design or implementation problems reveal missing guidance.

Changes MUST preserve consistency with the studio documentation hierarchy and other game design guidelines.

Game-specific reward decisions MUST be documented in the relevant game project documentation rather than added to this reusable guideline.