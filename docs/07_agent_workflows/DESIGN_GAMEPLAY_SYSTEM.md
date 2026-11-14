# Design Gameplay System

## 1. Purpose

This workflow defines how an AI agent should design, evaluate, document, and validate a gameplay system.

The objective is to transform a gameplay requirement or concept into a structured system specification that describes its purpose, components, rules, interactions, dependencies, and expected player experience.

The resulting document should provide a shared reference for game designers, developers, artists, audio designers, and QA.

## 2. Scope

Use this workflow when:

- Creating a new gameplay system.
- Significantly redesigning an existing gameplay system.
- Defining a group of interconnected gameplay mechanics.
- Establishing the rules and behavior of a major gameplay feature.
- Documenting interactions between multiple mechanics.
- Evaluating the feasibility and consistency of a gameplay system.

Examples of gameplay systems include:

- Combat systems.
- Inventory systems.
- Crafting systems.
- Character progression systems.
- Dialogue systems.
- Quest systems.
- Stealth systems.
- Survival systems.
- Resource management systems.
- Interaction systems.

Do not use this workflow for:

- Designing the entire game.
- Defining the game's core vision or pillars.
- Documenting a single isolated mechanic when a mechanic specification is sufficient.
- Describing technical implementation in detail.
- Planning production tasks or sprint activities.

A gameplay system may contain multiple mechanics. Use the `design_game_mechanic.md` workflow when an individual mechanic requires its own detailed specification.

## 3. Authoritative References

Before designing a gameplay system, inspect the applicable studio standards and existing project documentation.

### 3.1 Studio references

Relevant references may include:

- `docs/01_game_design_guidelines/gameplay_design_guidelines.md`
- `docs/01_game_design_guidelines/mechanic_design_guidelines.md`
- `docs/01_game_design_guidelines/core_loop_design_guidelines.md`
- `docs/01_game_design_guidelines/design_principles.md`
- `docs/01_game_design_guidelines/player_experience_guidelines.md`
- `docs/01_game_design_guidelines/balancing_guidelines.md`
- `docs/01_game_design_guidelines/progression_design_guidelines.md`
- `docs/01_game_design_guidelines/economy_design_guidelines.md`
- `docs/06_templates/gameplay_system_template.md`

Read only the references relevant to the system being designed.

### 3.2 Project references

Inspect available project documentation, prioritizing:

- `game_project/docs/game_design/game_concept.md`
- `game_project/docs/game_design/game_vision.md`
- `game_project/docs/game_design/core_pillars.md`
- `game_project/docs/game_design/game_design_document.md`
- `game_project/docs/game_design/core_game_loop.md`
- Existing gameplay system specifications.
- Relevant mechanic specifications.
- Relevant character, quest, world, progression, economy, and UI/UX documents.
- Relevant technical design documents.

These are possible reference locations, not assumptions that every document already exists.

The agent MUST inspect the actual project structure and available documentation before proceeding.

## 4. Workflow Overview

Follow these stages:

1. Understand the system request.
2. Inspect project context.
3. Define the system's purpose and boundaries.
4. Identify system components and responsibilities.
5. Define system behavior and rules.
6. Define interactions and dependencies.
7. Define player experience and feedback.
8. Evaluate balance, progression, and edge cases.
9. Define implementation considerations.
10. Generate the gameplay system specification.
11. Review and validate the design.
12. Present the document for human approval.

The level of detail should be proportional to the system's complexity.

## 5. Stage 1: Understand the Request

Identify what the user wants to design.

Extract the available information:

- System concept or initial idea.
- Gameplay problem or opportunity.
- Intended player experience.
- Expected system responsibilities.
- Related mechanics and features.
- Known requirements and constraints.
- Expected level of detail.
- Existing decisions or design references.

Determine whether the request describes:

- A new gameplay system.
- An extension of an existing system.
- A redesign or replacement.
- A collection of related mechanics.
- A system-level specification for an already approved concept.

If critical information is missing, ask focused clarification questions.

Do not invent requirements or present assumptions as confirmed decisions.

## 6. Stage 2: Inspect Project Context

Examine the existing game design before proposing the system.

Determine:

- How the system supports the game vision.
- Which core pillars it reinforces.
- Where it fits within the core gameplay loop.
- Which gameplay systems it interacts with.
- Which mechanics it contains or depends on.
- Which player actions and decisions it enables.
- Whether similar functionality already exists.
- Whether the proposed system conflicts with established rules.
- Whether technical or production constraints affect its design.

### 6.1 Existing systems

When an existing system is involved:

- Understand its current responsibilities.
- Identify its documented behavior.
- Determine which components are reusable.
- Identify limitations and known problems.
- Avoid duplicating existing functionality.
- Preserve approved behavior unless the user requests changes.

### 6.2 Resolve conflicts

When project documents contain conflicting information:

1. Identify the conflicting decisions.
2. Determine which source is authoritative.
3. Preserve explicitly approved requirements.
4. Document unresolved conflicts.
5. Ask the user to resolve conflicts that materially affect the design.

The agent MUST NOT silently redefine approved game vision, core pillars, or other high-level design decisions.

## 7. Stage 3: Define the System's Purpose and Boundaries

Establish the system's identity and intended contribution to gameplay.

Define:

- **System name:** A clear, descriptive name.
- **Overview:** A concise explanation of the system.
- **Design intent:** Why the system exists.
- **Player experience:** What the player should experience.
- **Gameplay purpose:** What problem or opportunity it addresses.
- **Design goals:** What the system must accomplish.
- **Non-goals:** What the system is not responsible for.
- **Related pillars:** Which core pillars it supports.
- **Core loop integration:** How it participates in gameplay.
- **Dependencies:** Which other systems or features it requires.
- **Constraints:** Relevant design, technical, and production limitations.

### 7.1 Define system boundaries

Clearly establish what belongs to the system and what belongs elsewhere.

For example, an inventory system may be responsible for:

- Storing and organizing items.
- Managing item quantities.
- Validating inventory operations.
- Providing inventory information to the UI.

It may interact with, but not own:

- Item acquisition.
- Crafting recipes.
- Equipment behavior.
- Quest rewards.
- Shop transactions.

Avoid assigning unrelated responsibilities to a single system.

## 8. Stage 4: Identify System Components and Responsibilities

Break the system into logical components.

For each component, define:

- Name.
- Purpose.
- Responsibilities.
- Inputs.
- Outputs.
- Rules.
- State or data it owns.
- Dependencies.
- Interactions with other components.

Use components only when they represent meaningful responsibilities.

Do not create unnecessary subsystems or abstractions merely to make the design appear more sophisticated.

### 8.1 Component relationships

Describe how components cooperate.

Identify:

- Which component initiates an operation.
- Which component validates it.
- Which component owns relevant state.
- Which component applies the result.
- Which components receive notifications.
- Which component handles failure.

Use a diagram when it makes complex relationships easier to understand.

## 9. Stage 5: Define System Behavior and Rules

Describe how the system behaves during normal gameplay.

### 9.1 Main gameplay flow

Document the primary interaction sequence:

1. Initial conditions.
2. Player action or triggering event.
3. System validation.
4. Processing or state transition.
5. Result or consequence.
6. Feedback to the player.
7. Final system state.

Include alternative flows when they are important to understanding the system.

### 9.2 Rules and constraints

Specify relevant:

- Activation conditions.
- Requirements and prerequisites.
- Restrictions.
- Costs and resource consumption.
- Limits and capacities.
- Durations and cooldowns.
- Success and failure conditions.
- State transitions.
- Cancellation and interruption behavior.
- Priority rules.
- Recovery behavior.

Use measurable values when they are established.

Mark undecided values as proposed or unresolved rather than presenting them as final.

### 9.3 System states

Identify important system states.

For each state, describe:

- What it represents.
- How the system enters it.
- What actions are allowed.
- What actions are prohibited.
- What causes transitions.
- What happens when the state ends.

For complex systems, use a state diagram or flowchart.

### 9.4 System data

Identify the data required by the system.

Consider:

- Configuration data.
- Runtime state.
- Player-owned data.
- World state.
- Temporary data.
- Derived values.
- Persistent data.

Clarify data ownership and avoid unnecessary duplication of authoritative state.

## 10. Stage 6: Define Interactions and Dependencies

Describe how the system interacts with other gameplay systems.

For each important interaction, document:

- Participating systems.
- Trigger or initiating action.
- Information exchanged.
- Expected behavior.
- Resulting state changes.
- Failure behavior.
- Relevant dependencies.

Consider interactions with:

- Player controls and character abilities.
- Combat and AI.
- Inventory and equipment.
- Economy and resources.
- Progression.
- Quests and narrative.
- World and environment.
- UI and feedback.
- Audio and animation.
- Save and persistence.

### 10.1 Dependency direction

Avoid circular dependencies and unnecessary coupling.

Prefer clear ownership and well-defined interfaces.

Use direct interactions when one system needs to request an operation from another system. Use events or signals when a system needs to communicate that something happened without requiring unrelated systems to own its behavior.

Follow the project's architecture and event/signal standards.

### 10.2 Cross-system consistency

Verify that the system does not introduce contradictory rules.

For example:

- An item consumed by one system should not remain available in another.
- A completed quest objective should not be reset by unrelated system updates.
- A character state should be interpreted consistently by combat, animation, and interaction systems.

Document important consistency requirements.

## 11. Stage 7: Define Player Experience and Feedback

Describe how the system appears and behaves from the player's perspective.

Consider:

- Available player actions.
- Player decisions and agency.
- Interaction sequence.
- Controls and input methods.
- Visual feedback.
- Audio feedback.
- Animations.
- UI information.
- Success and failure communication.
- Waiting and response times.
- Accessibility.
- Learning and discoverability.

The system should communicate important information clearly and consistently.

Avoid exposing unnecessary internal complexity to the player.

### 11.1 Feedback requirements

For important system events, define the feedback the player should receive.

Examples include:

- Action accepted.
- Action rejected.
- Resource consumed.
- Resource insufficient.
- State changed.
- Objective completed.
- Operation interrupted.
- System unavailable.

Specify feedback requirements without unnecessarily prescribing final art or audio assets.

## 12. Stage 8: Evaluate Balance, Progression, and Edge Cases

Evaluate the system's effect on gameplay over time.

### 12.1 Balance

Consider:

- Resource generation and consumption.
- System efficiency.
- Frequency of use.
- Player power.
- Difficulty.
- Risk and reward.
- Exploitable behavior.
- Interaction with other systems.
- Long-term gameplay consequences.

Identify tunable parameters and describe their intended effects.

Document formulas and proposed values when relevant.

### 12.2 Progression

If the system evolves with player progress, define:

- Unlock conditions.
- Upgrade paths.
- Progression requirements.
- Available improvements.
- Restrictions.
- Effects on system behavior.
- Relationship with other progression systems.

Avoid progression that introduces complexity without a meaningful player benefit.

### 12.3 Edge cases

Consider relevant exceptional situations:

- Missing prerequisites.
- Insufficient resources.
- Invalid inputs.
- Invalid targets.
- Repeated requests.
- Simultaneous events.
- Interrupted operations.
- Player death or incapacitation.
- Scene transitions.
- System initialization failure.
- Loading and unloading.
- Save and load.
- Unexpected or invalid state combinations.

Define expected behavior for important cases.

### 12.4 Exploit analysis

Identify possible exploits, including:

- Repeated resource generation.
- Duplicate rewards.
- Bypassing restrictions.
- Unexpected state transitions.
- Unintended combinations with other systems.
- Save/load manipulation.
- Repeated activation or cancellation.

Not every theoretical exploit requires a complex solution. Prioritize those that materially affect gameplay integrity.

## 13. Stage 9: Define Implementation Considerations

Describe implementation requirements at a design level.

Consider:

- Main system components.
- Feature boundaries.
- Required scenes and nodes.
- Scripts and responsibilities.
- Resources and configuration data.
- Signals and system communication.
- Input requirements.
- UI integration.
- Animation and audio requirements.
- Persistence requirements.
- Dependencies on existing features.
- Performance considerations.
- Testing requirements.

Respect the project's feature-oriented architecture and Godot technical standards.

Do not prescribe unnecessary implementation details before the system's behavior and responsibilities are clear.

If implementation introduces significant technical complexity, architectural uncertainty, or cross-feature dependencies, recommend a separate technical design document.

The gameplay system specification describes what the system does and how it behaves. A technical design document describes how the system should be implemented.

## 14. Stage 10: Generate the Gameplay System Specification

Use:

`docs/06_templates/gameplay_system_template.md`

Generate the project-specific document at:

`game_project/docs/game_design/systems/[system_name]_system.md`

Replace `[system_name]` with an appropriate lowercase `snake_case` filename.

Include the relevant sections from the template.

Do not retain irrelevant template sections merely to fill space. Mark unresolved decisions and omit sections that genuinely do not apply.

### 14.1 Document quality requirements

The generated specification MUST:

- Clearly explain the system's purpose.
- Define its boundaries and responsibilities.
- Identify its major components.
- Describe core behavior and rules.
- Define important states and transitions.
- Explain player interactions and feedback.
- Document relevant system interactions and dependencies.
- Address important edge cases.
- Include balance and progression considerations where applicable.
- Identify implementation considerations.
- Define validation criteria.
- Identify assumptions and unresolved questions.
- Reference relevant project documentation.

Use consistent terminology and avoid duplicating information unnecessarily.

## 15. Stage 11: Review and Validate the Design

Review the generated specification before presenting it.

### 15.1 Design consistency

Verify that:

- The system supports the game vision.
- It reinforces relevant core pillars.
- It fits the core gameplay loop.
- It has a clear purpose.
- Its responsibilities are well-defined.
- Its components have coherent responsibilities.
- It is consistent with existing systems.
- It does not unnecessarily duplicate existing functionality.

### 15.2 Behavioral completeness

Verify that:

- Main gameplay flows are understandable.
- Rules and constraints are explicit.
- Important states and transitions are defined.
- Inputs and outputs are identified.
- Failure behavior is described.
- Player feedback is sufficient.
- Important edge cases are addressed.

### 15.3 Interaction consistency

Verify that:

- Dependencies are identified.
- Data ownership is clear.
- Interactions have defined outcomes.
- No unnecessary circular dependencies are introduced.
- Cross-system behavior is consistent.
- Relevant persistence requirements are considered.

### 15.4 Feasibility

Verify that:

- The system is achievable within project scope.
- Its complexity is justified.
- Required dependencies are available or identified.
- Technical risks are documented.
- Art and audio requirements are reasonable.
- Testing can validate its expected behavior.

### 15.5 Documentation quality

Verify that:

- The correct template was used.
- The filename follows project conventions.
- Related documents are referenced accurately.
- Assumptions and unresolved decisions are visible.
- No unsupported details are presented as approved requirements.
- The document does not unnecessarily duplicate other specifications.

Resolve straightforward issues before presenting the document.

## 16. Stage 12: Human Review and Approval

Present the completed gameplay system specification to the user.

The review summary should include:

- System name and purpose.
- Generated document path.
- System boundaries and responsibilities.
- Main components.
- Core gameplay behavior.
- Important interactions and dependencies.
- Significant design decisions.
- Open questions and assumptions.
- Potential design, balance, and technical risks.
- Recommended next steps.

Clearly distinguish confirmed decisions from proposed suggestions.

The agent MUST NOT:

- Approve its own design.
- Mark the document as Approved without explicit human approval.
- Treat proposed values as final.
- Implement significant unapproved design decisions.
- Modify other approved design documents without authorization.

The user is responsible for accepting, rejecting, or requesting revisions.

## 17. Revision Process

When the user requests changes:

1. Re-read the current gameplay system specification.
2. Identify the requested changes.
3. Evaluate their impact on components, rules, and system interactions.
4. Check for conflicts with existing approved designs.
5. Update the specification consistently.
6. Re-evaluate affected edge cases and dependencies.
7. Check whether related documents require updates.
8. Present a summary of the changes.

Preserve previously approved decisions unless the user explicitly requests a change.

If a requested change affects the game vision, core pillars, or other approved high-level decisions, explain the implications and request authorization where necessary.

## 18. Completion Criteria

The workflow is complete when:

- The system's purpose and boundaries are clearly defined.
- Its responsibilities and major components are documented.
- Core behavior and rules are specified.
- Important states and transitions are defined.
- Player interactions and feedback are described.
- System interactions and dependencies are identified.
- Relevant balance and progression considerations are addressed.
- Important edge cases are documented.
- Implementation considerations are identified.
- The project-specific specification is generated.
- The document passes the design consistency and quality review.
- Open questions and assumptions are explicitly identified.
- The document is presented for human review.

Completion of this workflow does not imply approval of the system.

## 19. AI Agent Rules

The agent MUST:

- Inspect project documentation before designing.
- Follow applicable studio and project standards.
- Reuse existing systems and mechanics where appropriate.
- Preserve approved design decisions.
- Distinguish confirmed facts, assumptions, proposals, and unresolved questions.
- Define clear system boundaries and responsibilities.
- Consider interactions with other gameplay systems.
- Follow the project's feature-oriented architecture.
- Use the gameplay system template.
- Follow project naming and documentation conventions.
- Consider player experience, balance, and long-term consequences.
- Identify important edge cases and dependencies.
- Avoid unnecessary complexity.
- Request clarification when critical information is missing.
- Present the result for human approval.

The agent MUST NOT:

- Invent established game lore, mechanics, or requirements.
- Silently redefine the game's vision or core pillars.
- Duplicate existing systems without justification.
- Introduce unnecessary subsystems or abstractions.
- Treat proposed values as approved.
- Make significant architectural decisions without authorization.
- Implement an unapproved system.
- Mark its own work as Approved.

## 20. Final Report Format

After completing the workflow, provide a concise report:

### Gameplay System Design Report

**System:** [System name]

**Status:** Draft / In Review / Approved

**Document:** `game_project/docs/game_design/systems/[system_name]_system.md`

**Purpose:** [Brief description]

**System boundaries:** [Main responsibilities and exclusions]

**Core components:** [Main components and their responsibilities]

**Core behavior:** [Summary of the gameplay flow and rules]

**Related systems:** [Relevant interactions and dependencies]

**Key decisions:** [Important design decisions]

**Open questions:** [Unresolved questions, or None]

**Risks:** [Relevant design, balance, or technical risks, or None identified]

**Validation:** [Checks performed and their results]

**Next step:** [Human review, revision, or another appropriate action]

Do not report approval unless the user has explicitly approved the document.