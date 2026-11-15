# Create Game Vision Workflow

## 1. Purpose

This workflow defines the standard procedure for AI agents to assist in creating, refining, and documenting a project's Game Vision.

The Game Vision establishes the intended identity, direction, and player experience of the game. It communicates what the game aims to become, what makes it distinctive, who it is intended for, and which creative and design priorities should guide its development.

The objective is to produce a clear and actionable vision that aligns the project owner, designers, developers, artists, audio contributors, and AI agents around a shared understanding of the game.

The Game Vision serves as a high-level reference for subsequent design and production decisions.

## 2. Scope

This workflow covers:

- Reviewing the approved Game Concept and existing project information.
- Establishing the game's identity and creative direction.
- Defining the intended player experience.
- Identifying the target audience.
- Establishing the game's distinguishing characteristics.
- Defining high-level gameplay, narrative, world, art, and audio direction.
- Establishing design priorities and boundaries.
- Defining project success criteria.
- Identifying assumptions and unresolved decisions.
- Generating the project-specific Game Vision document.
- Reviewing consistency with other project documentation.
- Presenting the vision for project owner approval.

This workflow does not cover detailed gameplay mechanics, complete narrative development, technical architecture, production scheduling, or full feature specifications.

## 3. Output

| Property | Value |
|---|---|
| Output Document | `game_project/docs/game_design/game_vision.md` |
| Source Template | `docs/06_templates/GAME_VISION_TEMPLATE.md` |
| Document Type | Game Design |
| Primary Owner | Project Owner / Game Director |
| Approval Authority | Project Owner |
| Initial Status | Draft |

The agent MUST inspect the actual repository before creating the output.

If the Game Vision document already exists, the agent MUST review and refine it rather than creating a duplicate.

The generated document MUST follow the structure and guidance defined in the Game Vision Template.

## 4. Required Inputs

### 4.1 Primary References

Review the following documents when available:

1. Game Concept.
2. Existing Game Vision.
3. Game Design Document.
4. Core Pillars.
5. Project Concept or Pitch.
6. Target Audience Definition.
7. Existing project decisions and constraints.

The Game Concept is an important input, but it does not automatically authorize every proposal contained within it.

The agent MUST distinguish between approved decisions and unapproved ideas.

### 4.2 Supporting References

Review relevant documents when available:

- Core Game Loop.
- Narrative Overview.
- World Overview.
- Gameplay Design Guidelines.
- Player Experience Guidelines.
- Art Direction.
- Audio Direction.
- Project Roadmap.
- Technical Design Documents.
- Existing prototypes and validation results.

### 4.3 Missing Information

If important information is unavailable:

1. Identify the missing information.
2. Determine whether the vision can be drafted without it.
3. Record assumptions explicitly.
4. Ask the project owner for clarification when a missing decision materially affects the game's direction.
5. Avoid inventing approved project decisions.

The agent MAY propose alternatives when the project owner has not established a direction.

## 5. Workflow Principles

Agents MUST follow these principles:

- **Owner-driven vision:** The Game Vision must represent the project owner's intended direction.
- **Player-centered:** Define the experience the game aims to deliver.
- **Identity:** Clearly communicate what makes the game recognizable and distinctive.
- **Clarity:** Use concise language that communicates priorities without unnecessary detail.
- **Consistency:** Align gameplay, narrative, world, visual, and audio direction.
- **Actionability:** Provide guidance that can influence future design decisions.
- **Focus:** Prioritize the most important qualities of the experience.
- **Feasibility:** Respect the project's constraints and development capacity.
- **Stability:** Avoid changing the vision in response to minor implementation decisions.
- **Adaptability:** Allow refinement when meaningful evidence or approved decisions justify it.

The Game Vision MUST describe the intended destination, not every step required to reach it.

It MUST NOT become a feature inventory, technical specification, production plan, or detailed Game Design Document.

## 6. Execution Procedure

### Step 1: Inspect Project Context

1. Inspect the repository structure.
2. Read applicable agent rules and project instructions.
3. Review the Documentation Inventory when required by documentation management rules.
4. Locate the Game Concept and existing Game Vision.
5. Review the Core Pillars and other available design documents.
6. Identify approved decisions, constraints, and unresolved questions.
7. Review relevant prototypes or validation results when available.

**Expected result:** A clear understanding of the project's current direction and established decisions.

### Step 2: Understand the Game's Identity

Extract the fundamental characteristics of the game.

Identify:

- The central concept.
- The player's role or fantasy.
- The primary gameplay experience.
- The intended emotional experience.
- The setting and narrative premise.
- The game's distinguishing characteristics.
- The intended audience.
- The project's creative ambitions.
- The major constraints.

Separate essential identity characteristics from optional features.

**Expected result:** A concise summary of what the game is intended to be.

### Step 3: Define the Vision Statement

Create a concise statement describing the game's intended identity and experience.

The statement should communicate:

- What kind of game is being created.
- What the player does.
- What experience the game aims to deliver.
- What makes the game distinctive.

The vision statement should be understandable without reading the rest of the document.

Avoid generic statements that could describe almost any game.

**Expected result:** A concise and meaningful Game Vision Statement.

### Step 4: Define the Intended Player Experience

Describe the experience the game should consistently deliver.

Consider:

- What the player should feel.
- What the player should be doing most of the time.
- What motivates continued play.
- What challenges create meaningful engagement.
- What makes the experience rewarding.
- What emotions or memories the game should leave with the player.

Distinguish between:

- Core experience: the defining experience the game must deliver.
- Supporting experience: additional experiences that reinforce the core.
- Optional experience: qualities that may be included when scope allows.

**Expected result:** A clear description of the intended player experience.

### Step 5: Define the Target Audience

Describe the players the game is primarily intended for.

Consider:

- Player interests.
- Genre preferences.
- Gameplay complexity.
- Expected experience and skill level.
- Preferred platforms.
- Accessibility needs.
- Relevant comparable games.
- Potential secondary audiences.

Explain why the proposed experience is relevant to this audience.

Avoid unsupported demographic or market-size claims.

**Expected result:** A practical target audience definition.

### Step 6: Define the Game's Distinguishing Characteristics

Identify the characteristics that make the game recognizable.

Consider:

- Distinctive gameplay interactions.
- Unique combinations of mechanics.
- Player agency.
- Setting and world identity.
- Narrative perspective.
- Progression structure.
- Visual identity.
- Atmosphere.
- The relationship between systems and player experience.

Explain why each characteristic matters.

Do not claim uniqueness without supporting research.

**Expected result:** A clear description of the game's intended identity and differentiators.

### Step 7: Establish High-Level Creative Direction

Define the broad direction of the game's major creative dimensions.

#### 7.1 Gameplay Direction

Describe:

- Primary gameplay activities.
- Intended gameplay rhythm.
- Player agency.
- Core challenges.
- Intended level of complexity.
- Relationship between gameplay systems.

Do not specify detailed mechanics unless they are essential to communicating the vision.

#### 7.2 Narrative Direction

Describe:

- Narrative importance.
- Main themes.
- Intended tone.
- Player's narrative role.
- Relationship between story and gameplay.
- Desired emotional impact.

If the game is not narrative-driven, explicitly state the intended narrative scope.

#### 7.3 World Direction

Describe:

- Setting.
- World identity.
- Atmosphere.
- Important world characteristics.
- Relationship between the world and gameplay.

#### 7.4 Art Direction

Describe:

- Overall visual identity.
- Intended artistic style.
- Visual atmosphere.
- Important visual priorities.
- Relationship between visual presentation and player experience.

Detailed visual specifications belong in the project's Art Direction document.

#### 7.5 Audio Direction

Describe:

- Overall sonic identity.
- Intended musical atmosphere.
- Sound design priorities.
- Environmental audio expectations.
- Relationship between audio and gameplay feedback.

Detailed audio specifications belong in the project's Audio Direction document.

**Expected result:** A coherent high-level creative direction.

### Step 8: Establish Design Priorities

Identify the qualities that should receive the greatest attention during development.

Priorities should guide trade-offs when time, resources, technical limitations, or competing design goals create conflicts.

For each priority, document:

- Priority name.
- Why it matters.
- What it means for the player experience.
- What design decisions it should influence.
- What compromises should be avoided.

These priorities should align with the Core Pillars when that document exists.

If Core Pillars have not yet been approved, identify preliminary priorities without presenting them as approved pillars.

**Expected result:** A clear hierarchy of important design priorities.

### Step 9: Establish Design Boundaries

Identify what the game is intended to include and exclude at a high level.

Consider:

- Gameplay directions that do not support the vision.
- Features that are not central to the experience.
- Unnecessary complexity.
- Content that would dilute the game's identity.
- Platform or technical limitations.
- Scope boundaries.

Document exclusions when they prevent misunderstandings or unnecessary development.

Do not interpret exclusions as permanent prohibitions unless explicitly approved.

**Expected result:** Clear boundaries that help protect the game's identity and scope.

### Step 10: Define High-Level Success Criteria

Describe what would make the project successful from a creative and player-experience perspective.

Consider:

- Whether the core experience is recognizable.
- Whether gameplay supports the intended player fantasy.
- Whether the game's identity is communicated clearly.
- Whether the target audience responds positively.
- Whether the major design priorities are fulfilled.
- Whether the project delivers a coherent experience.

Define measurable criteria only when meaningful metrics are available.

Do not invent performance, commercial, or player engagement targets.

**Expected result:** A set of high-level success criteria.

### Step 11: Review Feasibility and Constraints

Evaluate whether the proposed vision is achievable within the project's circumstances.

Consider:

| Dimension | Evaluation Focus |
|---|---|
| Development Capacity | Available time, skills, and team resources |
| Technical Feasibility | Engine and implementation constraints |
| Content Scope | Number and complexity of systems and assets |
| Art Production | Visual production requirements |
| Audio Production | Music, sound, and voice requirements |
| Narrative Scope | Writing and content requirements |
| Platform | Hardware and platform limitations |
| Production Risk | Major dependencies and uncertainties |

Identify any conflict between the intended vision and known constraints.

The agent MAY recommend scope adjustments but MUST NOT silently weaken or redefine the vision to make it appear feasible.

**Expected result:** A documented assessment of feasibility and constraints.

### Step 12: Generate the Game Vision Document

1. Read `docs/06_templates/GAME_VISION_TEMPLATE.md`.
2. Follow its structure and required sections.
3. Populate the template using confirmed project information.
4. Incorporate approved decisions from supporting documents.
5. Identify proposals and assumptions.
6. Document unresolved questions.
7. Reference relevant project documents.
8. Set the document status to `Draft`.
9. Save the document at `game_project/docs/game_design/game_vision.md`.

The generated document MUST:

- Clearly communicate the game's identity.
- Describe the intended player experience.
- Establish coherent creative direction.
- Identify the target audience.
- Communicate meaningful design priorities.
- Establish relevant boundaries and success criteria.
- Avoid duplicating detailed design specifications.
- Remain consistent with approved project decisions.

### Step 13: Validate the Game Vision

Review the document against the following checklist.

**Vision clarity**

- [ ] The vision statement clearly describes the game.
- [ ] The intended player experience is understandable.
- [ ] The target audience is identified.
- [ ] The game's distinguishing characteristics are explained.
- [ ] The creative direction is coherent.

**Design direction**

- [ ] Gameplay direction supports the vision.
- [ ] Narrative direction is appropriate.
- [ ] World direction supports the intended experience.
- [ ] Art and audio direction reinforce the identity.
- [ ] Design priorities are clearly established.
- [ ] Design boundaries are understandable.

**Feasibility and consistency**

- [ ] Known constraints are documented.
- [ ] Major feasibility concerns are identified.
- [ ] Success criteria are meaningful.
- [ ] The document is consistent with approved project decisions.
- [ ] Assumptions and unresolved questions are identified.

**Documentation quality**

- [ ] The correct template was used.
- [ ] The correct output location was used.
- [ ] Related references are accurate.
- [ ] No unnecessary duplication exists.
- [ ] The document status is `Draft`.
- [ ] No duplicate document was created.

Correct identified issues before presenting the document.

### Step 14: Present for Project Owner Approval

Present the proposed Game Vision to the project owner.

Include:

1. The vision statement.
2. A summary of the intended player experience.
3. The target audience.
4. The game's distinguishing characteristics.
5. The high-level creative direction.
6. The most important design priorities.
7. The design boundaries.
8. The proposed success criteria.
9. Feasibility concerns.
10. Assumptions and unresolved questions.

The project owner MUST explicitly review and approve the vision.

Agents MUST NOT:

- Approve their own work.
- Change the status to `Approved` without authorization.
- Treat unapproved proposals as established direction.
- Modify the approved concept without permission.
- Introduce new project commitments without approval.

## 7. Vision Maintenance and Change Management

### 7.1 Maintaining the Vision

The Game Vision should remain relatively stable throughout development.

Minor implementation changes do not necessarily require changes to the vision.

Review it when:

- The core player experience changes.
- The game's intended audience changes.
- The project's identity or differentiators change.
- Major scope changes are proposed.
- Validation reveals that the original vision is not achievable.
- The project owner requests a revision.

### 7.2 Evaluating Proposed Changes

Before changing an approved vision:

1. Identify the proposed change.
2. Explain why it is necessary.
3. Identify the affected vision elements.
4. Review the impact on Core Pillars.
5. Identify affected design and production documents.
6. Evaluate scope, technical, and creative implications.
7. Present the change to the project owner.

Do not modify the approved vision simply to justify an isolated feature or implementation decision.

### 7.3 Updating Related Documents

When an approved vision change affects other project documents:

- Identify affected documents.
- Explain the required updates.
- Update only documents authorized by the project owner or applicable workflow.
- Preserve consistency across the project.
- Record significant changes where appropriate.

### 7.4 Historical Integrity

When the vision changes significantly:

- Preserve relevant historical context.
- Record the reason for the change.
- Identify the affected decisions.
- Do not silently erase important approved direction.

## 8. Relationship with Other Design Documents

The Game Vision is a high-level creative reference. It should not duplicate the responsibilities of other design documents.

| Document | Responsibility |
|---|---|
| Game Concept | Explores and evaluates the proposed game idea |
| Game Vision | Defines the approved creative direction and intended experience |
| Core Pillars | Establishes fundamental design priorities |
| Core Game Loop | Defines the central recurring gameplay structure |
| Game Design Document | Describes the broader game design |
| Narrative Overview | Defines the high-level narrative direction |
| World Overview | Establishes the setting and worldbuilding foundation |
| Art Direction | Defines detailed visual identity and production guidance |
| Audio Direction | Defines detailed sonic identity and production guidance |
| Project Roadmap | Defines planned development direction and priorities |

The Game Vision should guide these documents without replacing them.

## 9. Completion Criteria

This workflow is complete when:

- [ ] Project context has been reviewed.
- [ ] The game's identity has been established.
- [ ] The vision statement has been defined.
- [ ] The intended player experience has been described.
- [ ] The target audience has been identified.
- [ ] Distinguishing characteristics have been documented.
- [ ] High-level creative direction has been established.
- [ ] Design priorities and boundaries have been identified.
- [ ] Success criteria have been defined.
- [ ] Feasibility and constraints have been considered.
- [ ] The Game Vision document has been generated.
- [ ] Documentation consistency has been validated.
- [ ] The document has been presented for project owner approval.

Completion of this workflow does not imply approval of the Game Vision.

## 10. Expected Agent Report

After execution, provide a report using the following structure:

### Game Vision Creation Report

**Status:** [Completed / Partially Completed / Blocked]

**Output Document:** `game_project/docs/game_design/game_vision.md`

**Vision Statement:**

[Concise vision statement.]

**Intended Player Experience:**

[Summary.]

**Target Audience:**

[Summary.]

**Distinguishing Characteristics:**

1. [Characteristic]
2. [Characteristic]
3. [Characteristic]

**Creative Direction:**

- Gameplay: [Summary]
- Narrative: [Summary]
- World: [Summary]
- Art: [Summary]
- Audio: [Summary]

**Design Priorities:**

1. [Priority]
2. [Priority]
3. [Priority]

**Design Boundaries:**

- [Boundary or None]

**Feasibility Concerns:**

- [Concern or None]

**Assumptions:**

- [Assumption or None]

**Unresolved Questions:**

- [Question or None]

**Validation Results:**

- Vision clarity: [Passed / Failed / Not Verified]
- Design coherence: [Passed / Failed / Not Verified]
- Feasibility review: [Passed / Failed / Not Verified]
- Documentation consistency: [Passed / Failed / Not Verified]

**Project Owner Approval:** Pending

**Next Action:** [Required action.]

## 11. Related References

### Studio Documentation

- Development Philosophy: `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- Game Development Lifecycle: `docs/00_studio_standards/GAME_DEVELOPMENT_LIFECYCLE.md`
- Design Principles: `docs/01_game_design_guidelines/DESIGN_PRINCIPLES.md`
- Player Experience Guidelines: `docs/01_game_design_guidelines/PLAYER_EXPERIENCE_GUIDELINES.md`
- Core Pillars Template: `docs/06_templates/CORE_PILLARS_TEMPLATE.md`
- Game Vision Template: `docs/06_templates/GAME_VISION_TEMPLATE.md`
- Game Design Document Template: `docs/06_templates/GAME_DESIGN_DOCUMENT_TEMPLATE.md`

### Related Agent Workflows

- Create Game Concept: `docs/07_agent_workflows/CREATE_GAME_CONCEPT.md`
- Create Core Pillars: `docs/07_agent_workflows/CREATE_CORE_PILLARS.md`

Only use references that exist in the applicable repository.

---

**End of Workflow**
