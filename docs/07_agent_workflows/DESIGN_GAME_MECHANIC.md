# Design Game Mechanic

## 1. Purpose

This workflow defines how an AI agent should design, evaluate, document, and validate an individual gameplay mechanic.

The objective is to produce a clear, coherent, implementable, and testable mechanic specification that supports the game's vision, core pillars, gameplay systems, and intended player experience.

The workflow should help transform a gameplay idea into a structured design that can be reviewed before implementation.

## 2. Scope

Use this workflow when:

- Creating a new gameplay mechanic.
- Significantly redesigning an existing mechanic.
- Defining the behavior of an individual player interaction.
- Exploring how a mechanic supports a gameplay system.
- Documenting rules, interactions, states, consequences, and feedback.
- Evaluating whether a proposed mechanic fits the game's design direction.

Do not use this workflow for:

- Designing an entire game concept or vision.
- Defining the complete core gameplay loop.
- Designing an entire gameplay system when a system-level specification is more appropriate.
- Producing technical implementation designs.
- Making minor adjustments that do not require a new mechanic specification.

For complex mechanics involving multiple interacting subsystems, consider whether a gameplay system specification or technical design document is also necessary.

## 3. Authoritative References

Before designing a mechanic, inspect the relevant project documentation and studio standards.

### Studio references

- `docs/01_game_design_guidelines/MECHANIC_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/GAMEPLAY_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/DESIGN_PRINCIPLES.md`
- `docs/01_game_design_guidelines/PLAYER_EXPERIENCE_GUIDELINES.md`
- `docs/01_game_design_guidelines/BALANCING_GUIDELINES.md`
- `docs/06_templates/MECHANIC_TEMPLATE.md`

Read only the references relevant to the proposed mechanic when the full set is unnecessary.

### Project references

Inspect available project documents, prioritizing:

- `game_project/docs/game_design/game_concept.md`
- `game_project/docs/game_design/game_vision.md`
- `game_project/docs/game_design/core_pillars.md`
- `game_project/docs/game_design/game_design_document.md`
- `game_project/docs/game_design/core_game_loop.md`
- Relevant gameplay system specifications.
- Relevant mechanic specifications.
- Relevant character, world, quest, progression, economy, and UI/UX documents.

These are reference locations, not assumptions that every document already exists.

The agent MUST inspect the actual project structure and available documentation before proceeding.

## 4. Workflow Overview

Follow these stages:

1. Understand the mechanic request.
2. Inspect project context.
3. Define the mechanic's purpose.
4. Establish its rules and behavior.
5. Define player interaction and feedback.
6. Evaluate interactions, consequences, and edge cases.
7. Evaluate balance and player experience.
8. Define implementation considerations.
9. Generate the mechanic specification.
10. Review and validate the design.
11. Present the document for human approval.

Do not skip stages that materially affect the mechanic's quality. Keep the process proportional to the mechanic's complexity.

## 5. Stage 1: Understand the Request

Identify what the user wants to design.

Extract the available information:

- Mechanic concept or initial idea.
- Intended player action.
- Desired gameplay outcome.
- Problem the mechanic should solve.
- Relevant gameplay context.
- Known constraints.
- Related mechanics or systems.
- Expected level of detail.

If the request is incomplete, distinguish between information that can reasonably be inferred and information that requires clarification.

Ask focused questions when missing information would materially change the design.

Do not invent requirements or present assumptions as confirmed decisions.

## 6. Stage 2: Inspect Project Context

Examine the game's existing design before proposing the mechanic.

Determine:

- How the mechanic supports the game vision.
- Which core pillars it reinforces.
- Where it fits within the core gameplay loop.
- Which gameplay systems it interacts with.
- Which player abilities or resources it requires.
- Whether similar mechanics already exist.
- Whether the mechanic conflicts with established rules.
- Whether the project has relevant technical or production constraints.

Check existing mechanic specifications to avoid duplication.

If the mechanic already exists, determine whether the request is an extension, refinement, replacement, or redesign.

### 6.1 Resolve conflicts

When project information conflicts:

1. Identify the conflicting documents or decisions.
2. Determine which source has authority over the subject.
3. Preserve explicitly approved design decisions.
4. Do not silently overwrite established requirements.
5. Present unresolved conflicts to the user.

The agent MUST NOT change the game's vision, core pillars, or other approved high-level design decisions as a side effect of designing a mechanic.

## 7. Stage 3: Define the Mechanic's Purpose

Establish the mechanic's identity and intended contribution to gameplay.

Define:

- **Name:** A clear, descriptive name.
- **Description:** A concise explanation of the mechanic.
- **Design intent:** Why the mechanic exists.
- **Player experience:** What the player should experience when using or encountering it.
- **Gameplay purpose:** What gameplay problem or opportunity it addresses.
- **Player actions:** What the mechanic allows or requires the player to do.
- **Design goals:** What the mechanic must achieve.
- **Non-goals:** What the mechanic is not intended to accomplish.
- **Related pillars:** Which core pillars it supports.
- **Dependencies:** Which existing mechanics or systems it requires.

The mechanic should have a recognizable purpose rather than existing solely because it seems interesting.

## 8. Stage 4: Establish Rules and Behavior

Define the mechanic's rules precisely enough that designers, developers, and testers can understand its expected behavior.

Consider the following elements where applicable:

### 8.1 Activation conditions

Define:

- How the mechanic is activated.
- Required player actions or inputs.
- Required resources, equipment, or abilities.
- Environmental conditions.
- Prerequisites.
- Conditions that prevent activation.

### 8.2 States and transitions

Identify relevant mechanic states.

For each state, describe:

- What the state represents.
- How the mechanic enters the state.
- What actions are permitted.
- What actions are prohibited.
- What conditions cause a transition.
- What happens when the state ends.

Represent complex state transitions in a diagram when it improves clarity.

### 8.3 Rules and constraints

Specify:

- Core rules.
- Limits and restrictions.
- Costs and resource consumption.
- Cooldowns or durations.
- Range and targeting conditions.
- Success and failure conditions.
- Interruptions and cancellation behavior.
- Interactions with other mechanics.

Use measurable values where known.

If values have not been decided, mark them as proposed or undecided rather than inventing final values.

### 8.4 Inputs and outputs

Define the mechanic's relevant inputs and outputs.

Inputs may include:

- Player input.
- Game state.
- Character attributes.
- Resources.
- Environmental conditions.
- Other system events.

Outputs may include:

- State changes.
- Resource changes.
- Player feedback.
- World changes.
- Events or signals.
- Effects on other gameplay systems.

## 9. Stage 5: Define Player Interaction and Feedback

Describe how the player interacts with the mechanic.

Consider:

- Input methods and controls.
- Interaction sequence.
- Available actions.
- Required timing or precision.
- Interaction range.
- Target selection.
- Visual feedback.
- Audio feedback.
- Animation and movement.
- UI information.
- Confirmation of success or failure.
- Accessibility considerations.

Feedback should make the mechanic understandable and communicate important changes in its state.

Avoid interactions that are unnecessarily confusing, inconsistent, or difficult to control.

## 10. Stage 6: Evaluate Consequences and Interactions

Determine how the mechanic affects the rest of the game.

Consider:

- Immediate consequences.
- Long-term consequences.
- Resource consumption or generation.
- Character progression.
- Player capabilities.
- Enemy or NPC behavior.
- World state.
- Quest progression.
- Economy and inventory.
- Other gameplay mechanics.
- Save and persistence requirements.

Identify dependencies and possible conflicts.

For complex interactions, describe representative scenarios to demonstrate how the mechanic behaves in context.

### 10.1 Edge cases

Identify relevant exceptional situations, including:

- Missing prerequisites.
- Insufficient resources.
- Invalid targets.
- Interrupted interactions.
- Repeated activation.
- Simultaneous events.
- Player death or incapacitation.
- Scene transitions.
- Loading and unloading.
- Save and load during or after interaction.
- Unexpected or invalid game states.

Define expected behavior rather than leaving important cases ambiguous.

## 11. Stage 7: Evaluate Balance and Player Experience

Evaluate whether the mechanic produces the intended gameplay experience.

Consider:

- Player agency.
- Meaningful decisions.
- Risk and reward.
- Difficulty and accessibility.
- Learning curve.
- Player feedback.
- Frequency of use.
- Resource costs.
- Potential exploits.
- Interactions with progression.
- Long-term gameplay consequences.

Identify tunable parameters and their intended effects.

Where numerical balance is relevant, document:

- Proposed values.
- Expected ranges.
- Relevant formulas.
- Dependencies between parameters.
- Assumptions.
- Validation methods.

Do not treat untested balance assumptions as established facts.

## 12. Stage 8: Define Implementation Considerations

Describe the mechanic's implementation requirements at a design level.

Consider:

- Required gameplay components.
- Relevant scenes and nodes.
- Data or resources.
- Signals and interactions with other systems.
- Required animations, audio, and visual effects.
- UI requirements.
- Persistence requirements.
- Dependencies on existing features.
- Performance considerations.
- Testing requirements.

Respect the project's feature-oriented architecture and existing technical standards.

Do not prematurely prescribe implementation details when the mechanic's behavior is not yet established.

If the mechanic introduces significant architectural complexity or technical uncertainty, recommend a separate technical design document.

The mechanic specification describes the intended gameplay behavior. It does not replace a technical design document.

## 13. Stage 9: Generate the Mechanic Specification

Use:

`docs/06_templates/MECHANIC_TEMPLATE.md`

Generate the project-specific document at:

`game_project/docs/game_design/mechanics/[mechanic_name].md`

Replace `[mechanic_name]` with an appropriate lowercase `snake_case` filename, following project naming conventions.

The generated document should include the relevant sections of the template.

Do not retain irrelevant template sections merely to fill space. Mark unresolved decisions and omit sections that genuinely do not apply.

### 13.1 Document quality requirements

The generated specification MUST:

- Describe the mechanic's purpose clearly.
- Define its core rules and behavior.
- Identify important states and transitions.
- Explain player interactions and feedback.
- Describe relevant costs and consequences.
- Identify dependencies and interactions.
- Address important edge cases.
- Define relevant balance considerations.
- Include implementation considerations.
- Identify open questions and assumptions.
- Provide validation criteria.
- Reference relevant project documents.

Use consistent terminology throughout the document.

Avoid vague descriptions such as "works normally," "behaves appropriately," or "has balanced values" when specific behavior can be described.

## 14. Stage 10: Review and Validate the Design

Review the generated specification before presenting it.

### 14.1 Design consistency

Verify that:

- The mechanic supports the game vision.
- It reinforces relevant core pillars.
- It fits the core gameplay loop.
- It is consistent with existing gameplay systems.
- It does not duplicate existing mechanics unnecessarily.
- It does not introduce unexplained contradictions.

### 14.2 Behavioral completeness

Verify that:

- Activation conditions are clear.
- Rules and constraints are understandable.
- Relevant states and transitions are defined.
- Inputs and outputs are identified.
- Success and failure conditions are described.
- Player feedback is sufficient.
- Important edge cases are addressed.

### 14.3 Feasibility

Verify that:

- The mechanic is achievable within the project's scope.
- Required dependencies are identified.
- Technical risks are documented.
- Art and audio requirements are reasonable.
- Testing can validate the intended behavior.

### 14.4 Documentation quality

Verify that:

- The correct template was used.
- The filename follows project conventions.
- Related documents are referenced accurately.
- Assumptions and unresolved decisions are visible.
- No unsupported details are presented as approved requirements.
- The document does not unnecessarily duplicate other specifications.

Resolve straightforward issues before presenting the document.

## 15. Stage 11: Human Review and Approval

Present the completed mechanic specification to the user.

The review summary should include:

- Mechanic name and purpose.
- Generated document path.
- Main gameplay rules.
- Important interactions and dependencies.
- Significant design decisions.
- Assumptions and unresolved questions.
- Potential balance or technical risks.
- Recommended next steps.

Clearly distinguish confirmed decisions from proposed design suggestions.

The agent MUST NOT:

- Approve its own design.
- Mark the document as Approved without explicit human approval.
- Treat proposed values as final.
- Implement significant unapproved design changes.
- Modify other approved design documents without authorization.

The user is responsible for accepting, rejecting, or requesting revisions.

## 16. Revision Process

When the user requests changes:

1. Re-read the current mechanic specification.
2. Identify the requested changes.
3. Check their impact on existing rules and related systems.
4. Update the specification consistently.
5. Re-evaluate affected interactions and edge cases.
6. Check whether related documents require updates.
7. Present a summary of the changes.

Preserve previously approved decisions unless the user explicitly requests a change.

If a requested change creates conflicts with other approved design decisions, explain the conflict before proceeding.

## 17. Completion Criteria

The workflow is complete when:

- The mechanic's purpose is clearly defined.
- Its rules and expected behavior are documented.
- Relevant player interactions and feedback are described.
- Important states and edge cases are addressed.
- Dependencies and system interactions are identified.
- Relevant balance and feasibility concerns are documented.
- The project-specific mechanic specification is generated.
- The document passes the design consistency and quality review.
- Unresolved questions are explicitly identified.
- The document is presented for human review.

Completion of the workflow does not imply approval of the mechanic.

## 18. AI Agent Rules

The agent MUST:

- Inspect project documentation before designing.
- Follow applicable studio and project standards.
- Reuse existing mechanics and systems where appropriate.
- Preserve approved design decisions.
- Distinguish confirmed facts, assumptions, proposals, and unresolved questions.
- Use the mechanic template.
- Follow project naming and documentation conventions.
- Keep the specification focused on the mechanic's behavior.
- Consider player experience and gameplay consequences.
- Identify relevant edge cases and dependencies.
- Avoid unnecessary complexity.
- Request clarification when critical information is missing.
- Present the result for human approval.

The agent MUST NOT:

- Invent established game lore, mechanics, or requirements.
- Silently redefine the game's vision or core pillars.
- Duplicate existing mechanics without justification.
- Introduce unnecessary systems or abstractions.
- Treat proposed balance values as approved.
- Make significant architectural decisions without authorization.
- Implement an unapproved mechanic.
- Mark its own work as Approved.

## 19. Final Report Format

After completing the workflow, provide a concise report:

### Mechanic Design Report

**Mechanic:** [Mechanic name]

**Status:** Draft / In Review / Approved

**Document:** `game_project/docs/game_design/mechanics/[mechanic_name].md`

**Purpose:** [Brief description]

**Core behavior:** [Summary of how the mechanic works]

**Related systems:** [Relevant gameplay systems and dependencies]

**Key decisions:** [Important design decisions]

**Open questions:** [Unresolved questions, or None]

**Risks:** [Relevant design, balance, or technical risks, or None identified]

**Validation:** [Checks performed and their results]

**Next step:** [Human review, revision, or another appropriate action]

Do not report approval unless the user has explicitly approved the document.