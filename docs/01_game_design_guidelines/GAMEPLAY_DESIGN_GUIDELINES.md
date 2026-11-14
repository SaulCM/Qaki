# Gameplay Design Guidelines

## 1. Purpose

This document establishes reusable guidelines for designing, developing, evaluating, and refining gameplay mechanics and player interactions.

Its purpose is to ensure gameplay systems are understandable, engaging, consistent, meaningful, and aligned with the intended player experience.

These guidelines provide a shared foundation for gameplay design across projects while allowing individual games to establish their own mechanics, rules, and creative identity.

## 2. Scope

These guidelines apply to:

- Core and secondary gameplay mechanics.
- Player actions and interactions.
- Character movement and controls.
- Combat and non-combat interactions.
- Exploration and environmental interactions.
- Abilities, skills, and equipment.
- Interaction between gameplay systems.
- Gameplay feedback and responsiveness.
- Gameplay prototyping and validation.
- Gameplay-related design documentation.

Specialized topics are covered by their corresponding guidelines:

- Core gameplay loop structure: `core_loop_design_guidelines.md`.
- Difficulty and challenge: `difficulty_design_guidelines.md`.
- Numerical and systemic balance: `balancing_guidelines.md`.
- Economic systems: `economy_design_guidelines.md`.

## 3. Gameplay Design Principles

### 3.1 Player Experience First

Gameplay mechanics MUST support the intended player experience.

Design decisions SHOULD consider:

- What the player should experience.
- What actions the player should perform.
- What decisions the player should make.
- What emotions or reactions the mechanics should encourage.
- How the mechanics contribute to the game's identity.

Mechanics SHOULD NOT exist solely because they are technically interesting or commonly found in other games.

### 3.2 Meaningful Player Agency

Players SHOULD have meaningful control over their actions and decisions.

Gameplay systems SHOULD:

- Offer choices with understandable consequences.
- Allow different approaches when appropriate.
- Communicate the results of player actions.
- Avoid unnecessary restrictions on player decisions.
- Ensure that player input produces predictable and understandable outcomes.

Not every action needs multiple alternatives. However, important decisions SHOULD provide meaningful agency.

### 3.3 Clarity and Understandability

Players SHOULD be able to understand the fundamental rules governing gameplay.

Designers SHOULD:

- Introduce mechanics progressively.
- Communicate important rules through gameplay.
- Use consistent interaction patterns.
- Provide clear visual, audio, or contextual feedback.
- Avoid unnecessary hidden rules.
- Distinguish intentional mystery from confusing implementation.

Complex mechanics SHOULD be introduced only when their depth justifies their learning cost.

### 3.4 Responsiveness and Feedback

Gameplay MUST provide appropriate feedback in response to player actions.

Feedback MAY include:

- Visual effects.
- Animation.
- Sound effects.
- Interface changes.
- Environmental reactions.
- Character reactions.
- Numerical or textual indicators.
- Changes in game state.

Feedback SHOULD be timely, recognizable, and consistent with the action performed.

Critical gameplay events MUST NOT depend exclusively on subtle or easily missed feedback.

### 3.5 Consistency

Similar gameplay situations SHOULD follow consistent rules.

For example:

- Similar interactions SHOULD produce comparable results.
- Controls SHOULD behave consistently across contexts.
- Gameplay systems SHOULD follow established conventions.
- Exceptions SHOULD be intentional and communicated when necessary.

Consistency reduces cognitive overhead and makes gameplay easier to learn.

### 3.6 Simplicity with Depth

Gameplay SHOULD be easy to understand while allowing sufficient depth for mastery.

Designers SHOULD prefer:

- A small number of meaningful mechanics over unnecessary complexity.
- Interactions between systems over excessive individual features.
- Clear rules with interesting consequences.
- Mechanics that support multiple situations.
- Complexity that emerges naturally from player decisions.

Depth SHOULD come from meaningful interactions, not arbitrary exceptions or excessive rules.

## 4. Gameplay Mechanics

### 4.1 Definition

A gameplay mechanic is a rule or system that defines how the player interacts with the game and how the game responds.

A mechanic SHOULD have:

- A clear purpose.
- Defined player interactions.
- Explicit rules.
- Defined inputs and outputs.
- Understandable feedback.
- Known dependencies.
- Appropriate failure and edge-case behavior.

### 4.2 Mechanic Design

Before implementing a mechanic, define:

1. What player experience does it support?
2. What problem or opportunity does it address?
3. What can the player do?
4. What rules govern the mechanic?
5. What happens when the player interacts with it?
6. What feedback communicates the result?
7. How does it interact with existing systems?
8. How will its effectiveness be evaluated?

A mechanic SHOULD be rejected, simplified, or redesigned if its purpose cannot be clearly justified.

### 4.3 Mechanic Lifecycle

Gameplay mechanics SHOULD follow an iterative development process:

1. Identify the intended player experience.
2. Define the mechanic's purpose and rules.
3. Create a minimal prototype.
4. Evaluate whether the mechanic supports its intended experience.
5. Refine interactions, feedback, and rules.
6. Validate integration with other systems.
7. Document the finalized behavior.
8. Monitor its performance during subsequent testing.

Designers SHOULD validate uncertain mechanics through prototypes before committing to extensive implementation.

### 4.4 Mechanical Interactions

Mechanics SHOULD interact with other systems in ways that create meaningful gameplay opportunities.

Designers SHOULD evaluate:

- Dependencies between mechanics.
- Shared resources and constraints.
- Conflicting rules.
- Emergent interactions.
- Potential exploits.
- Unintended combinations.
- Effects on existing gameplay.

Interactions SHOULD be intentional where they materially affect the player experience.

## 5. Player Actions and Interactions

### 5.1 Action Definition

Every significant player action SHOULD define:

- The action's purpose.
- The required input.
- The conditions under which it is available.
- Its execution behavior.
- Its immediate result.
- Its associated feedback.
- Its costs, risks, or consequences.
- Its interaction with other mechanics.

### 5.2 Action Availability

Gameplay MUST communicate when an action is available, unavailable, or interrupted when that information is relevant to the player.

Actions MAY depend on:

- Player state.
- Environmental conditions.
- Available resources.
- Equipment or abilities.
- Progression requirements.
- Interaction range.
- Game rules or restrictions.

Restrictions SHOULD be understandable and consistent.

### 5.3 Action Consequences

Actions SHOULD have consequences appropriate to their significance.

Consequences MAY include:

- Resource consumption.
- State changes.
- Progression.
- Environmental changes.
- Rewards.
- Risks.
- Opportunities.
- Reactions from other characters or systems.

Important consequences SHOULD be communicated before or immediately after the action, depending on the intended experience.

### 5.4 Interaction Prioritization

When multiple interactions are available simultaneously, the game SHOULD prioritize them predictably.

Designers SHOULD consider:

- Interaction distance.
- Contextual relevance.
- Player intention.
- Interaction visibility.
- Input consistency.
- Possibility of accidental activation.

The player SHOULD NOT need to fight the interface to perform common gameplay actions.

## 6. Controls and Input Design

### 6.1 Control Principles

Controls SHOULD be:

- Responsive.
- Consistent.
- Predictable.
- Comfortable for their intended platform.
- Appropriate for the game's mechanics.
- Configurable when reasonably practical.

Important gameplay actions SHOULD NOT require unnecessarily complicated input sequences.

### 6.2 Input Mapping

Input actions SHOULD be defined independently of device-specific physical inputs whenever supported by the engine.

This allows different devices and control schemes to trigger the same gameplay action.

Input design SHOULD consider:

- Keyboard and mouse.
- Game controllers.
- Remappable controls.
- Simultaneous inputs.
- Input conflicts.
- Input buffering.
- Input interruption.
- Context-sensitive actions.

### 6.3 Input Feedback

The game SHOULD communicate when an input is:

- Accepted.
- Rejected.
- Buffered.
- Interrupted.
- Unavailable.
- Successfully executed.

Input feedback SHOULD match the actual game state.

### 6.4 Input Configuration

When appropriate for the game's scope, players SHOULD be able to configure:

- Key bindings.
- Controller mappings.
- Sensitivity.
- Input inversion.
- Hold versus toggle behavior.
- Other relevant accessibility options.

Configuration changes MUST NOT create invalid or conflicting input mappings without appropriate handling.

## 7. Movement and Spatial Gameplay

Movement mechanics SHOULD support the game's intended interaction model and spatial design.

Designers SHOULD define:

- Movement capabilities.
- Movement restrictions.
- Acceleration and deceleration behavior.
- Collision behavior.
- Traversal options.
- Environmental interactions.
- Movement feedback.
- Camera relationships.
- Relevant movement states.

Movement SHOULD feel consistent with the game's perspective, scale, and intended player experience.

### 7.1 Spatial Interaction

Spatial mechanics SHOULD establish understandable relationships between:

- Player position.
- Interaction range.
- Collision boundaries.
- Obstacles.
- Traversable areas.
- Environmental hazards.
- Relevant objects and characters.

Collision and interaction boundaries SHOULD be consistent with player expectations.

### 7.2 Camera and Movement

Camera behavior SHOULD support player awareness and control.

Designers SHOULD consider:

- Visibility of relevant gameplay information.
- Obstruction and occlusion.
- Camera movement responsiveness.
- Spatial orientation.
- Motion discomfort.
- Transitions between camera states.

Camera behavior MUST NOT unnecessarily prevent the player from understanding or executing important actions.

## 8. Gameplay States and Rules

### 8.1 State Definition

Gameplay systems SHOULD define the states that materially affect their behavior.

Examples include:

- Idle.
- Moving.
- Attacking.
- Interacting.
- Stunned.
- Disabled.
- Dead.
- Recovering.

State definitions SHOULD be based on actual gameplay requirements rather than creating states for every minor implementation detail.

### 8.2 State Transitions

State transitions SHOULD define:

- The conditions that trigger the transition.
- The resulting state.
- Any associated actions.
- Restrictions during the transition.
- Feedback provided to the player.
- Conditions for leaving the resulting state.

Invalid or contradictory transitions MUST be prevented or handled safely.

### 8.3 Rule Ownership

Each gameplay rule SHOULD have a clear authoritative owner.

Systems SHOULD avoid implementing conflicting versions of the same rule.

When multiple mechanics depend on the same gameplay rule, designers and developers SHOULD establish a shared contract or clearly defined interface.

## 9. Gameplay Progression and Mastery

Gameplay SHOULD provide opportunities for players to develop their understanding and mastery of its mechanics.

Progression MAY introduce:

- New mechanics.
- Additional abilities.
- New interactions.
- More complex situations.
- Expanded player options.
- New environmental challenges.
- Greater strategic possibilities.

New mechanics SHOULD build on established knowledge whenever practical.

### 9.1 Learning Curve

Gameplay SHOULD introduce complexity at a pace appropriate to the intended audience.

Designers SHOULD:

- Establish fundamental interactions early.
- Introduce advanced mechanics progressively.
- Provide opportunities to practice.
- Reinforce important concepts.
- Avoid introducing too many unrelated mechanics simultaneously.

### 9.2 Mastery

Mechanics SHOULD reward player understanding and skill when mastery is part of the intended experience.

Mastery MAY result from:

- Better timing.
- Improved execution.
- Understanding system interactions.
- Strategic planning.
- Environmental awareness.
- Efficient resource usage.

Mastery SHOULD emerge from understandable rules rather than arbitrary hidden requirements.

Detailed progression and difficulty tuning SHOULD follow their corresponding specialized guidelines.

## 10. Gameplay Feedback and Communication

### 10.1 Feedback Requirements

Gameplay feedback SHOULD communicate:

- What happened.
- Why it happened, when relevant.
- Whether the action succeeded.
- Whether the game state changed.
- What the player can do next, when necessary.

Feedback SHOULD be proportional to the importance of the event.

### 10.2 Feedback Channels

Designers SHOULD select feedback channels based on the information being communicated.

| Channel | Typical use |
|---|---|
| Visual | State changes, movement, impact, interaction |
| Audio | Events, confirmation, warnings, atmosphere |
| Animation | Character intent, action execution, reactions |
| Interface | Resources, status, objectives, available actions |
| Environmental | World changes, consequences, contextual clues |
| Haptic | Physical confirmation or impact, when supported |

Important information SHOULD NOT rely on a single sensory channel when doing so would unnecessarily exclude players.

### 10.3 Feedback Consistency

Similar events SHOULD use recognizable feedback patterns.

Critical warnings, confirmations, and state changes SHOULD be distinguishable from ordinary background feedback.

## 11. Gameplay System Integration

Gameplay mechanics SHOULD integrate into a coherent overall experience.

Before introducing a mechanic, evaluate its impact on:

- Existing mechanics.
- Player capabilities.
- Game progression.
- Resource systems.
- World interactions.
- User interface.
- Narrative context.
- Save and load behavior.
- Other active gameplay systems.

### 11.1 System Boundaries

Gameplay systems SHOULD have clearly defined responsibilities.

Designers and developers SHOULD:

- Avoid unnecessary coupling.
- Define ownership of shared gameplay rules.
- Use clear communication between systems.
- Avoid duplicated authoritative state.
- Keep system responsibilities understandable.

Implementation architecture MUST follow the project's approved technical standards and feature-oriented project structure.

### 11.2 Emergent Gameplay

Emergent gameplay MAY be encouraged through interactions between understandable mechanics.

However, designers SHOULD distinguish:

- Intended emergent behavior.
- Acceptable unexpected interactions.
- Exploits.
- Broken or contradictory rules.

Unexpected behavior SHOULD be evaluated according to its impact on the intended player experience rather than automatically being treated as a defect.

## 12. Failure, Recovery, and Player Consequences

Gameplay SHOULD define how unsuccessful actions and failure conditions affect the player.

Designers SHOULD consider:

- What constitutes failure.
- How failure is communicated.
- Whether failure is temporary or permanent.
- What progress is retained or lost.
- Available recovery options.
- Whether the player understands what caused the failure.
- Whether the player can reasonably learn from the experience.

Failure SHOULD be consistent with the game's intended experience.

Punishment SHOULD be proportionate to the intended challenge and communicated expectations.

Detailed difficulty and recovery considerations SHOULD follow `difficulty_design_guidelines.md`.

## 13. Gameplay Prototyping and Validation

Gameplay mechanics SHOULD be validated through practical interaction rather than relying exclusively on design descriptions.

### 13.1 Prototyping

Prototypes SHOULD prioritize the uncertain or essential parts of a mechanic.

A prototype MAY use:

- Placeholder assets.
- Simplified animations.
- Temporary interface elements.
- Basic collision geometry.
- Simplified rules.
- Debug information.

Visual polish SHOULD NOT be prioritized over validating the mechanic's fundamental behavior.

### 13.2 Validation Criteria

Gameplay validation SHOULD evaluate:

- Is the mechanic understandable?
- Does it support its intended purpose?
- Are controls responsive?
- Is feedback sufficient?
- Are outcomes predictable?
- Are decisions meaningful?
- Does the mechanic interact correctly with existing systems?
- Does it create unintended behavior?
- Does it remain enjoyable after repeated use?

### 13.3 Playtesting

Playtesting SHOULD observe actual player behavior rather than relying exclusively on developer expectations.

Useful observations include:

- Player confusion.
- Repeated mistakes.
- Unexpected strategies.
- Unused mechanics.
- Frustrating interactions.
- Successful discoveries.
- Engagement and disengagement.
- Differences between intended and actual behavior.

Design changes SHOULD be based on observed problems and clearly identified design objectives.

## 14. Gameplay Documentation

Significant gameplay mechanics SHOULD have documentation sufficient to guide implementation, testing, and future maintenance.

Documentation SHOULD include, when applicable:

- Mechanic name and purpose.
- Design intent.
- Player actions.
- Rules and conditions.
- Gameplay states.
- Inputs and outputs.
- Feedback requirements.
- Dependencies.
- Edge cases.
- Failure behavior.
- Validation criteria.
- Open design questions.

Documentation SHOULD describe intended behavior rather than unnecessarily prescribing implementation details.

Implementation-specific decisions belong in the relevant technical documentation.

## 15. AI-Assisted Gameplay Design

AI agents assisting with gameplay design MUST:

1. Read the relevant game-specific design documents before proposing changes.
2. Follow these reusable gameplay guidelines.
3. Preserve approved gameplay decisions.
4. Avoid introducing mechanics without a clear design purpose.
5. Identify assumptions and unresolved design questions.
6. Evaluate interactions with existing gameplay systems.
7. Avoid silently changing established mechanics.
8. Recommend prototypes when design uncertainty is significant.
9. Document proposed changes and their expected player impact.
10. Request human approval for significant changes to approved gameplay direction.

AI-generated gameplay proposals MUST be treated as recommendations until reviewed and approved by the project owner.

Agents MUST NOT claim that a mechanic has been validated through playtesting unless actual testing has been performed.

## 16. Gameplay Design Review Checklist

Before approving a significant gameplay mechanic, evaluate the following:

### Design Intent
- [ ] The mechanic has a clear purpose.
- [ ] It supports the intended player experience.
- [ ] Its contribution to the game's identity is understood.

### Rules and Interactions
- [ ] Player actions are clearly defined.
- [ ] Gameplay rules are understandable.
- [ ] Availability and restrictions are defined.
- [ ] Outcomes and consequences are clear.
- [ ] Important state transitions are defined.
- [ ] Interactions with other mechanics are evaluated.

### Player Experience
- [ ] Controls are appropriate and responsive.
- [ ] Feedback communicates important events.
- [ ] Player decisions are meaningful where intended.
- [ ] The mechanic does not introduce unnecessary complexity.
- [ ] Failure and recovery behavior are appropriate.

### Validation
- [ ] Important uncertainties have been identified.
- [ ] The mechanic has been prototyped when appropriate.
- [ ] Validation criteria are defined.
- [ ] Actual testing results are documented when available.
- [ ] Unintended interactions have been evaluated.

### Documentation and Integration
- [ ] Relevant design documentation is updated.
- [ ] Dependencies and system ownership are clear.
- [ ] Existing approved gameplay decisions are preserved.
- [ ] Technical implementation follows project standards.

## 17. Related Documents

Refer to the following documents when they exist in the repository:

- `design_principles.md`
- `core_loop_design_guidelines.md`
- `balancing_guidelines.md`
- `difficulty_design_guidelines.md`
- `economy_design_guidelines.md`
- `../00_studio_standards/development_philosophy.md`
- `../00_studio_standards/quality_standards.md`
- `../00_studio_standards/project_structure_standards.md`
- `../02_technical_standards/architecture_guidelines.md`

## 18. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- New gameplay design practices are adopted.
- Existing guidelines become unclear or contradictory.
- Repeated gameplay design problems reveal missing guidance.
- Changes to the studio's development philosophy affect gameplay design.

Updates MUST preserve the document's reusable nature and avoid introducing requirements that belong exclusively to a single game.

The project owner is responsible for approving changes to these studio-wide guidelines.