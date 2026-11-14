# Mechanic Design Guidelines

## 1. Purpose

This document establishes reusable guidelines for conceptualizing, specifying, prototyping, evaluating, and refining gameplay mechanics.

Its purpose is to ensure that mechanics have clear design intent, understandable rules, meaningful player interactions, consistent behavior, and appropriate integration with other gameplay systems.

These guidelines provide a repeatable design approach while preserving creative flexibility across different game genres and projects.

## 2. Scope

These guidelines apply to:

- Core gameplay mechanics.
- Secondary and supporting mechanics.
- Player abilities and actions.
- Combat mechanics.
- Movement and traversal mechanics.
- Interaction mechanics.
- Resource-related mechanics.
- Crafting and production mechanics.
- Exploration mechanics.
- Progression-related mechanics.
- Environmental mechanics.
- Mechanics involving interactions between multiple gameplay systems.

These guidelines focus on individual mechanics and their internal design.

Related documents cover broader or specialized concerns:

- Overall gameplay experience and player interactions: `gameplay_design_guidelines.md`.
- Core gameplay loop structure: `core_loop_design_guidelines.md`.
- Level and spatial design: `level_design_guidelines.md`.
- Difficulty and challenge: `difficulty_design_guidelines.md`.
- Numerical and systemic balance: `balancing_guidelines.md`.
- Economy and resource flows: `economy_design_guidelines.md`.

## 3. Fundamental Design Principles

### 3.1 Clear Design Intent

Every significant mechanic MUST have a clearly defined purpose.

A mechanic SHOULD:

- Support the intended player experience.
- Address a specific gameplay need.
- Introduce a meaningful interaction or decision.
- Complement the game's identity.
- Justify its implementation and maintenance cost.

Mechanics SHOULD NOT be introduced solely because they are technically interesting, fashionable, or common in other games.

### 3.2 Meaningful Player Interaction

Mechanics SHOULD create meaningful interactions between the player and the game.

Designers SHOULD consider:

- What the player can do.
- Why the player would do it.
- What decisions are involved.
- What consequences follow.
- How the mechanic changes the player's available options.

A mechanic that produces no meaningful gameplay consequence SHOULD be reconsidered unless it serves a deliberate atmospheric, narrative, or accessibility purpose.

### 3.3 Understandable Rules

Mechanics MUST follow rules that can be understood through appropriate instruction, observation, or experimentation.

Designers SHOULD:

- Avoid unnecessary exceptions.
- Establish consistent behavior.
- Communicate important restrictions.
- Make cause-and-effect relationships understandable.
- Introduce complexity progressively.
- Distinguish intentional uncertainty from unclear rules.

A mechanic MAY contain hidden information when discovery is part of its intended experience.

### 3.4 Simplicity and Depth

Mechanics SHOULD achieve meaningful depth without unnecessary complexity.

Prefer:

- A small set of coherent rules.
- Multiple meaningful applications.
- Interactions with existing mechanics.
- Clear constraints and consequences.
- Emergent possibilities.

Avoid excessive parameters, exceptions, and special cases unless they materially improve the experience.

### 3.5 Consistency

Mechanics SHOULD behave consistently across equivalent situations.

When exceptions are necessary, their conditions and consequences SHOULD be intentional and understandable.

Consistency SHOULD be maintained across:

- Inputs.
- Outputs.
- State transitions.
- Resource consumption.
- Feedback.
- Failure conditions.
- Interactions with other mechanics.

## 4. Mechanic Classification

Mechanics MAY be classified according to their purpose to improve design organization.

Common categories include:

| Category | Description |
|---|---|
| Core | Fundamental mechanics that define the primary gameplay experience |
| Supporting | Mechanics that enhance or enable core mechanics |
| Movement | Mechanics governing player movement and traversal |
| Interaction | Mechanics governing interactions with objects, characters, or environments |
| Combat | Mechanics governing offensive, defensive, and tactical actions |
| Resource | Mechanics governing resource acquisition, consumption, or conversion |
| Progression | Mechanics governing player development and access to capabilities |
| Exploration | Mechanics encouraging discovery and environmental interaction |
| Environmental | Mechanics governing environmental behavior and conditions |
| Narrative | Mechanics supporting narrative delivery through player interaction |
| Meta-game | Mechanics operating outside the immediate gameplay activity |

A mechanic MAY belong to multiple categories.

Classification SHOULD help clarify responsibilities rather than impose unnecessary design restrictions.

## 5. Mechanic Concept and Definition

### 5.1 Identify the Gameplay Opportunity

Before defining a mechanic, identify the gameplay opportunity or problem it addresses.

Consider:

- What experience is currently missing?
- What player behavior should be encouraged?
- What decision or interaction should become possible?
- What existing mechanic could already achieve this?
- Why is a new mechanic necessary?

Designers SHOULD avoid creating separate mechanics when an existing system can be extended without introducing unnecessary complexity.

### 5.2 Define the Concept

A mechanic concept SHOULD be expressible in a concise description.

The description SHOULD communicate:

- What the mechanic does.
- How the player interacts with it.
- What makes it interesting.
- Why it belongs in the game.

If the concept cannot be explained clearly, its design MAY require further refinement.

### 5.3 Define the Design Goals

Each significant mechanic SHOULD have explicit design goals.

Examples:

- Encourage deliberate resource management.
- Reward environmental awareness.
- Provide alternative approaches to encounters.
- Create meaningful timing decisions.
- Enable traversal through previously inaccessible areas.
- Encourage experimentation with different strategies.

Goals SHOULD describe intended player experiences or observable outcomes.

### 5.4 Define Non-Goals

When necessary, document what the mechanic is not intended to accomplish.

Non-goals help prevent scope expansion and misunderstandings.

Examples:

- The mechanic is not intended to replace the primary combat system.
- The mechanic does not provide unrestricted movement.
- The mechanic does not permanently modify the environment.
- The mechanic does not operate outside designated gameplay conditions.

## 6. Mechanic Specification

Significant mechanics SHOULD have a clear specification before substantial implementation begins.

### 6.1 Required Specification Elements

A mechanic specification SHOULD include:

1. **Name:** The mechanic's identifying name.
2. **Purpose:** Why the mechanic exists.
3. **Design intent:** The intended player experience.
4. **Category:** Its primary gameplay classification.
5. **Player interaction:** How the player engages with it.
6. **Inputs:** Required player or system inputs.
7. **Conditions:** Requirements for activation or execution.
8. **Rules:** The behavior governing the mechanic.
9. **Outputs:** Results produced by the mechanic.
10. **States:** Relevant operating states.
11. **Feedback:** How behavior is communicated.
12. **Consequences:** Costs, rewards, risks, or other effects.
13. **Dependencies:** Required systems or resources.
14. **Failure behavior:** How unsuccessful or interrupted actions are handled.
15. **Validation criteria:** How the mechanic's effectiveness will be evaluated.

Not every mechanic requires extensive documentation. The level of detail SHOULD be proportional to its complexity, importance, and risk.

### 6.2 Rules and Conditions

Mechanic rules MUST be explicit enough to support consistent implementation and testing.

Rules SHOULD define:

- Activation conditions.
- Execution conditions.
- Restrictions.
- Costs.
- Duration.
- Range.
- Targeting.
- Interruption behavior.
- Completion conditions.
- Cancellation behavior.
- Relevant exceptions.

Unspecified behavior SHOULD NOT be left to arbitrary implementation decisions when it affects gameplay.

### 6.3 Inputs and Outputs

Mechanics SHOULD define their inputs and outputs clearly.

Inputs MAY include:

- Player actions.
- Player state.
- Environmental conditions.
- Available resources.
- Equipment.
- Other gameplay systems.
- Timers or events.

Outputs MAY include:

- State changes.
- Resource changes.
- Movement.
- Damage or healing.
- Environmental changes.
- Rewards.
- Events.
- Unlocks.
- Feedback.

Inputs and outputs SHOULD have predictable relationships.

### 6.4 Costs and Consequences

Mechanics SHOULD define relevant costs and consequences.

Costs MAY include:

- Time.
- Currency.
- Consumable resources.
- Health.
- Equipment durability.
- Exposure to danger.
- Temporary restrictions.
- Opportunity costs.

Consequences MAY be immediate, delayed, reversible, or permanent.

Important costs and consequences SHOULD be communicated appropriately to the player.

Numerical tuning SHOULD follow `balancing_guidelines.md` and `economy_design_guidelines.md` where applicable.

## 7. Mechanic States and Transitions

### 7.1 State Definition

Mechanics involving different operating conditions SHOULD define their relevant states.

For example, a charging ability might use:

- Available.
- Charging.
- Ready.
- Executing.
- Recovering.
- Interrupted.
- Disabled.

States SHOULD represent meaningful differences in mechanic behavior.

Avoid creating unnecessary states that do not affect gameplay or system behavior.

### 7.2 State Transitions

Each relevant transition SHOULD define:

- Source state.
- Trigger or condition.
- Destination state.
- Associated effects.
- Required feedback.
- Restrictions during transition.

Invalid transitions MUST be prevented or handled safely.

### 7.3 State Consistency

Mechanics SHOULD NOT enter contradictory states.

For example:

- An unavailable ability SHOULD NOT execute.
- A completed interaction SHOULD NOT remain indefinitely active.
- A consumed resource SHOULD NOT be available to another operation unless explicitly restored.
- An interrupted action SHOULD NOT incorrectly produce its full completion effects.

State behavior SHOULD remain consistent during pauses, interruptions, scene transitions, and other relevant gameplay events.

## 8. Player Interaction and Feedback

### 8.1 Interaction Requirements

Mechanics SHOULD communicate when they are:

- Available.
- Unavailable.
- Active.
- Executing.
- Completed.
- Interrupted.
- Failed.

The communication method SHOULD match the mechanic's importance and complexity.

### 8.2 Feedback Design

Feedback MAY include:

- Animation.
- Visual effects.
- Sound.
- Interface indicators.
- Character reactions.
- Environmental reactions.
- Text or numerical information.
- Haptic feedback.

Feedback SHOULD communicate the actual mechanic state.

Important feedback SHOULD be recognizable and timely.

### 8.3 Player Expectations

Mechanics SHOULD behave in ways consistent with the expectations established by their presentation and previous use.

When behavior differs from established expectations, the difference SHOULD be intentional and communicated.

## 9. Mechanic Constraints and Edge Cases

### 9.1 Define Constraints

Mechanics SHOULD establish relevant constraints.

Examples include:

- Maximum range.
- Minimum range.
- Duration limits.
- Resource requirements.
- Target restrictions.
- Environmental restrictions.
- Cooldowns.
- Capacity limits.
- Usage frequency.
- Progression requirements.

Constraints SHOULD support the mechanic's design purpose rather than exist arbitrarily.

### 9.2 Identify Edge Cases

Designers SHOULD identify situations that could produce ambiguous or unintended behavior.

Depending on the mechanic, consider:

- Insufficient resources.
- Invalid targets.
- Missing dependencies.
- Simultaneous inputs.
- Interrupted execution.
- Conflicting states.
- Repeated activation.
- Boundary conditions.
- Scene transitions.
- Saving and loading.
- Multiplayer interactions, if applicable.

Not every edge case requires a special gameplay rule, but relevant behavior MUST be defined.

### 9.3 Exploit Considerations

Mechanics SHOULD be evaluated for unintended combinations or repeated actions that undermine their intended behavior.

Examples include:

- Infinite resource generation.
- Repeated reward acquisition.
- Unintended invulnerability.
- State manipulation.
- Skipping required progression.
- Circumventing intended restrictions.

Unexpected strategies SHOULD be evaluated according to their impact on the intended experience rather than automatically being classified as defects.

## 10. Mechanic Dependencies and Interactions

### 10.1 Dependency Identification

Mechanics SHOULD identify their dependencies on other systems.

Dependencies MAY include:

- Player state.
- Inventory.
- Equipment.
- Resources.
- Combat systems.
- Movement systems.
- Environmental systems.
- Progression.
- User interface.
- Save and load systems.

Dependencies SHOULD be documented when they materially affect behavior or implementation.

### 10.2 Interaction Between Mechanics

Mechanics SHOULD be evaluated in combination with existing mechanics.

Consider:

- Whether they complement each other.
- Whether they create conflicting rules.
- Whether they introduce unintended advantages.
- Whether they enable new strategies.
- Whether they invalidate existing mechanics.
- Whether they create additional player complexity.

Interactions that materially affect the game's identity or balance SHOULD be explicitly evaluated.

### 10.3 Ownership and Responsibility

Each mechanic SHOULD have clearly defined responsibility.

Designers and developers SHOULD avoid:

- Multiple systems owning the same authoritative rule.
- Duplicate resource calculations.
- Contradictory state definitions.
- Unnecessary circular dependencies.
- Unclear responsibility for gameplay outcomes.

Technical implementation SHOULD follow the project's approved architecture and feature-oriented structure.

## 11. Mechanic Progression and Complexity

### 11.1 Introduction

Mechanics SHOULD be introduced in a way that allows players to understand their fundamental behavior.

When appropriate, introduction SHOULD follow this sequence:

1. Establish the mechanic's purpose.
2. Introduce its basic interaction.
3. Communicate its fundamental rules.
4. Allow the player to experiment.
5. Introduce additional applications.
6. Combine it with previously learned mechanics.

### 11.2 Mechanical Depth

Depth MAY emerge through:

- Different applications.
- Context-dependent decisions.
- Resource trade-offs.
- Timing.
- Positioning.
- Environmental interactions.
- Combinations with other mechanics.
- Player skill and mastery.

Designers SHOULD prefer meaningful depth over simply increasing the number of rules.

### 11.3 Complexity Management

When a mechanic becomes difficult to explain or maintain, consider:

- Removing unnecessary rules.
- Combining redundant behavior.
- Clarifying state transitions.
- Separating unrelated responsibilities.
- Improving feedback.
- Revising the mechanic's scope.

Complexity SHOULD be justified by the experience it creates.

## 12. Prototyping and Iteration

### 12.1 Prototype Objectives

Prototypes SHOULD validate the most uncertain or important assumptions behind a mechanic.

Examples include:

- Whether the interaction feels satisfying.
- Whether the mechanic is understandable.
- Whether its rules create meaningful decisions.
- Whether it works with existing mechanics.
- Whether its costs and consequences are appropriate.
- Whether it supports the intended player experience.

### 12.2 Prototype Scope

Prototypes SHOULD implement only what is necessary to evaluate the design hypothesis.

They MAY use:

- Placeholder visuals.
- Temporary audio.
- Simplified animations.
- Basic geometry.
- Debug controls.
- Temporary interface elements.
- Simplified rules.

Production-quality assets and extensive architecture SHOULD NOT be required before fundamental design assumptions are validated.

### 12.3 Iteration Process

Mechanic development SHOULD follow an iterative process:

1. Define the design problem.
2. Establish the mechanic's purpose.
3. Specify its fundamental rules.
4. Identify uncertainties and risks.
5. Build a minimal prototype.
6. Test the mechanic in context.
7. Collect observations.
8. Refine the design.
9. Validate interactions with other systems.
10. Document approved behavior.

### 12.4 Design Decisions

Significant changes SHOULD be documented with:

- The original design assumption.
- The observed problem or opportunity.
- The proposed change.
- The expected player impact.
- Relevant dependencies.
- Validation requirements.

Changes that significantly affect approved game direction MUST receive project owner approval.

## 13. Mechanic Validation

### 13.1 Validation Criteria

Each significant mechanic SHOULD have criteria appropriate to its design goals.

Validation SHOULD evaluate:

- Does the mechanic serve its intended purpose?
- Is its behavior understandable?
- Are its rules consistent?
- Are player interactions responsive?
- Are costs and consequences appropriate?
- Does it produce meaningful decisions?
- Does it integrate with existing systems?
- Does it create unintended behavior?
- Does it remain useful in repeated gameplay?
- Does it support the intended player experience?

### 13.2 Testing Approaches

Validation MAY include:

- Developer testing.
- Playtesting.
- Controlled experiments.
- Boundary testing.
- State transition testing.
- Interaction testing.
- Regression testing.
- Quantitative analysis.
- Qualitative feedback.

The testing approach SHOULD match the mechanic's complexity and risk.

### 13.3 Evidence-Based Evaluation

Design decisions SHOULD distinguish between:

- Intended behavior.
- Observed behavior.
- Player feedback.
- Measured results.
- Unverified assumptions.

A mechanic MUST NOT be considered validated merely because it works technically.

Technical correctness and gameplay effectiveness are separate evaluation criteria.

## 14. Mechanic Documentation Template

Significant mechanics MAY use the following template:

```markdown
# [Mechanic Name]

## 1. Overview

**Category:**
**Status:**
**Priority:**

### Purpose
[Why this mechanic exists.]

### Design Intent
[What experience or player behavior it should support.]

### Description
[Concise explanation of the mechanic.]

## 2. Player Interaction

### Player Actions
[What the player can do.]

### Inputs
[Required inputs.]

### Availability Conditions
[When the mechanic can be used.]

### Feedback
[How the game communicates its behavior.]

## 3. Rules and Behavior

### Core Rules
[Rules governing the mechanic.]

### Costs and Consequences
[Relevant costs, rewards, and effects.]

### Constraints
[Restrictions and boundaries.]

### States
[Relevant operating states.]

### State Transitions
[Conditions and resulting transitions.]

## 4. Dependencies and Interactions

### Dependencies
[Systems required by the mechanic.]

### Interactions
[How it interacts with other mechanics.]

### Restrictions
[Known compatibility limitations.]

## 5. Failure and Edge Cases

[Expected behavior for invalid, interrupted, or exceptional situations.]

## 6. Validation

### Design Goals
[Expected gameplay outcomes.]

### Validation Criteria
[How the mechanic will be evaluated.]

### Known Risks
[Uncertainties and potential problems.]

## 7. Decisions and Open Questions

[Approved decisions and unresolved questions.]
```

This template SHOULD be adapted to the mechanic's complexity. Trivial mechanics do not require unnecessary documentation.

## 15. AI-Assisted Mechanic Design

AI agents assisting with mechanic design MUST:

1. Read relevant game-specific design documents before proposing changes.
2. Follow these reusable mechanic design guidelines.
3. Preserve approved gameplay decisions.
4. Identify the mechanic's purpose and design intent.
5. Define assumptions and unresolved questions.
6. Evaluate inputs, outputs, rules, states, and constraints.
7. Identify dependencies and interactions with existing mechanics.
8. Consider edge cases and unintended behavior.
9. Recommend prototypes when design uncertainty is significant.
10. Document proposed changes and expected player impact.
11. Request human approval for significant changes to approved mechanics.

AI agents MUST NOT:

- Introduce unnecessary mechanics without justification.
- Silently modify approved gameplay rules.
- Treat technical implementation as proof of gameplay quality.
- Claim that a mechanic has been playtested without actual testing.
- Make significant design decisions on behalf of the project owner.

AI-generated proposals MUST be treated as recommendations until reviewed and approved.

## 16. Mechanic Design Review Checklist

### Design Intent
- [ ] The mechanic has a clear purpose.
- [ ] Its design intent is documented.
- [ ] It supports the intended player experience.
- [ ] Its inclusion is justified.
- [ ] Its scope and non-goals are understood where necessary.

### Rules and Behavior
- [ ] Player interactions are defined.
- [ ] Inputs and outputs are understood.
- [ ] Activation conditions are explicit.
- [ ] Core rules are consistent.
- [ ] Relevant states and transitions are defined.
- [ ] Costs and consequences are understood.
- [ ] Constraints are documented.
- [ ] Failure behavior is defined.

### Integration
- [ ] Dependencies are identified.
- [ ] Interactions with existing mechanics are evaluated.
- [ ] Responsibility and rule ownership are clear.
- [ ] Potential exploits and edge cases are considered.
- [ ] Existing gameplay systems remain coherent.

### Player Experience
- [ ] The mechanic is understandable.
- [ ] Feedback communicates relevant behavior.
- [ ] The mechanic creates meaningful interactions.
- [ ] Complexity is justified.
- [ ] Player expectations are respected.

### Validation
- [ ] Important assumptions are identified.
- [ ] A prototype has been created when appropriate.
- [ ] Validation criteria are defined.
- [ ] Actual testing results are documented when available.
- [ ] Unresolved issues and risks are recorded.

### Documentation and Approval
- [ ] Relevant documentation is updated.
- [ ] Approved design decisions are preserved.
- [ ] Significant changes have received appropriate approval.
- [ ] Technical implementation follows project standards.

## 17. Related Documents

Refer to the following documents when they exist in the repository:

- `design_principles.md`
- `gameplay_design_guidelines.md`
- `core_loop_design_guidelines.md`
- `level_design_guidelines.md`
- `balancing_guidelines.md`
- `difficulty_design_guidelines.md`
- `economy_design_guidelines.md`
- `../00_studio_standards/development_philosophy.md`
- `../00_studio_standards/quality_standards.md`
- `../00_studio_standards/project_structure_standards.md`
- `../02_technical_standards/architecture_guidelines.md`

## 18. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- New mechanic design practices are adopted.
- Existing guidelines become unclear or contradictory.
- Repeated design problems reveal missing guidance.
- Changes to the studio's development philosophy affect mechanic design.
- New gameplay development requirements emerge.

Updates MUST preserve the document's reusable nature and avoid introducing requirements that apply exclusively to a single game.

The project owner is responsible for approving changes to these studio-wide guidelines.
```

