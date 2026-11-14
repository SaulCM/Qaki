# Create Game Concept Workflow

## 1. Purpose

This workflow defines the standard procedure for AI agents to assist in creating, evaluating, refining, and documenting a game's initial concept.

A Game Concept establishes the fundamental idea behind a game. It communicates what the game is about, what the player does, what makes the experience interesting, and why the concept is worth developing.

The objective is to transform an initial idea into a coherent concept that can be evaluated before committing significant development resources.

The resulting document provides the foundation for subsequent activities such as defining the Game Vision, identifying Core Pillars, developing the Core Game Loop, and planning pre-production.

## 2. Scope

This workflow covers:

- Collecting and understanding the initial game idea.
- Identifying the game's central premise.
- Defining the intended player experience.
- Establishing the genre and gameplay direction.
- Identifying the target audience.
- Exploring potential differentiators.
- Establishing the preliminary gameplay direction.
- Evaluating concept feasibility and risks.
- Identifying assumptions and unresolved questions.
- Generating the project-specific Game Concept document.
- Presenting the concept for project owner review.

This workflow does not cover detailed gameplay specifications, complete narrative development, technical architecture, production planning, or full Game Design Document creation.

## 3. Output

| Property | Value |
|---|---|
| Output Document | `game_project/docs/game_design/game_concept.md` |
| Document Type | Game Design |
| Primary Owner | Project Owner / Game Director |
| Approval Authority | Project Owner |
| Initial Status | Draft |

The agent MUST inspect the actual repository before creating the output.

If the document already exists, the agent MUST review and refine the existing document instead of creating a duplicate.

If a dedicated Game Concept Template exists in the repository, use it. Otherwise, use the structure defined in this workflow and follow the studio documentation standards.

## 4. Required Inputs

### 4.1 Initial Concept Information

The agent should obtain as much of the following information as is available:

- Initial game idea.
- Genre or possible genres.
- Intended platform.
- Intended audience.
- Main player role or fantasy.
- Primary gameplay activities.
- Setting or world concept.
- Narrative premise, if relevant.
- Visual direction or references.
- Inspiration from existing games or other media.
- Known constraints.
- Project goals.

The user does not need to provide every item before the workflow begins.

### 4.2 Existing Project References

If available, inspect:

- Game Vision.
- Game Design Document.
- Core Pillars.
- Core Game Loop.
- Narrative Overview.
- World Overview.
- Art Direction.
- Audio Direction.
- Project Roadmap.
- Existing concept notes or prototypes.

For a new project, many of these documents may not exist yet. Their absence MUST NOT be treated as a reason to invent information or block concept exploration.

### 4.3 Clarification Requirements

If the initial idea is ambiguous, ask focused questions to understand its defining characteristics.

Prioritize questions that materially affect:

1. What the player does.
2. What experience the game aims to provide.
3. What makes the concept distinctive.
4. What kind of game is being proposed.
5. What constraints significantly influence feasibility.

Ask one focused question at a time when clarification is needed.

Do not overwhelm the project owner with an extensive questionnaire before providing useful concept development.

## 5. Workflow Principles

Agents MUST follow these principles:

- **Preserve the original idea:** Understand the project owner's intent before proposing modifications.
- **Explore before committing:** Consider alternatives when important design decisions are unresolved.
- **Player experience first:** Define the experience rather than starting with a list of features.
- **Clarity:** Explain the concept in language that can be understood without extensive design knowledge.
- **Distinctiveness:** Identify what makes the concept interesting or different.
- **Coherence:** Ensure the gameplay, setting, narrative, and intended experience support each other.
- **Feasibility:** Consider development scope, technical constraints, resources, and production risks.
- **Honest evaluation:** Identify weaknesses and uncertainties instead of presenting every idea as equally viable.
- **Controlled scope:** Avoid introducing unnecessary systems and features during concept development.
- **Owner authority:** The project owner makes final decisions about the concept.

Agents MUST distinguish between the original concept, their suggestions, and approved project decisions.

## 6. Execution Procedure

### Step 1: Understand the Initial Idea

Analyze the information provided by the project owner.

Identify:

- The central idea.
- The intended player role.
- The primary activity.
- The setting.
- The intended experience.
- The most important design characteristics.
- The owner's expectations.
- Known constraints.

Summarize the idea in a short paragraph before expanding it.

If the summary does not accurately represent the owner's intention, request clarification.

**Expected result:** A shared understanding of the initial concept.

### Step 2: Define the Core Premise

Develop a concise description of what the game is about.

The premise should communicate:

- Who the player is or what role they assume.
- Where or in what context the game takes place.
- What the player primarily does.
- What central challenge, opportunity, or conflict drives the experience.

Avoid introducing unnecessary narrative details or mechanics.

Produce a short concept statement that can communicate the idea to someone unfamiliar with the project.

**Expected result:** A clear and concise game premise.

### Step 3: Identify the Player Experience

Define the experience the game intends to deliver.

Consider:

- What the player should feel.
- What the player should do repeatedly.
- What motivates the player.
- What challenges the player faces.
- What makes the experience rewarding.
- What distinguishes the experience from similar games.

Describe the intended experience in terms of player actions and outcomes rather than vague adjectives.

For example, instead of stating "the game is immersive," explain what interactions, environmental details, and gameplay systems are expected to create immersion.

**Expected result:** A clear description of the intended player experience.

### Step 4: Establish Genre and Gameplay Direction

Identify the proposed genre and gameplay structure.

Consider:

- Primary genre.
- Secondary genres or influences.
- Single-player or multiplayer.
- Perspective and camera.
- Real-time or turn-based gameplay.
- Action-oriented or strategy-oriented gameplay.
- Linear, open, or semi-open structure.
- Session-based or continuous progression.
- Exploration, combat, simulation, management, puzzle-solving, or other primary activities.

Not every category requires a decision during concept development.

When multiple directions remain viable, present alternatives and explain their implications.

Do not select technical or design conventions simply because they are common within a genre.

**Expected result:** A preliminary gameplay direction.

### Step 5: Define the Setting and Narrative Premise

When relevant, describe:

- The setting.
- The time period.
- The world concept.
- The player's role in the setting.
- The central conflict or situation.
- The narrative themes.
- The relationship between gameplay and narrative.

The concept does not require a complete story or detailed worldbuilding.

If the game is primarily systems-driven or does not require a narrative, explicitly state that narrative is not a primary focus.

**Expected result:** A preliminary setting and narrative direction.

### Step 6: Identify the Target Audience

Describe the intended audience based on the proposed experience.

Consider:

- Relevant player interests.
- Genre familiarity.
- Expected gameplay complexity.
- Expected session length.
- Preferred platform.
- Accessibility considerations.
- Similar games that may attract comparable audiences.

Distinguish between:

- Primary audience.
- Secondary audience.
- Potential audience outside the initial target.

Avoid inventing demographic statistics or making unsupported claims about market size.

**Expected result:** A preliminary target audience definition.

### Step 7: Identify Differentiators

Evaluate what makes the concept worth exploring.

Potential differentiators include:

- Distinctive gameplay interactions.
- An unusual combination of mechanics.
- A compelling player fantasy.
- A distinctive setting.
- A specific narrative perspective.
- A novel progression structure.
- A particular atmosphere.
- An interesting relationship between gameplay systems.

For each proposed differentiator, explain:

1. What it is.
2. Why it matters.
3. How it affects the player experience.
4. Whether it is central to the concept or merely a supporting feature.

Do not claim that a concept is unique without sufficient research.

If the concept is inspired by existing games, identify those influences and explain the intended differences.

**Expected result:** A preliminary list of meaningful differentiators.

### Step 8: Establish Preliminary Gameplay Activities

Identify the main activities the player is expected to perform.

Examples:

- Explore environments.
- Fight enemies.
- Gather resources.
- Build or manage facilities.
- Solve puzzles.
- Interact with characters.
- Craft equipment.
- Complete objectives.
- Make consequential decisions.
- Discover narrative information.

Group activities into:

- Primary activities: central to the experience.
- Supporting activities: reinforce primary activities.
- Optional activities: provide additional variety or depth.

Do not expand these activities into complete mechanics or technical specifications.

Detailed mechanics should be developed through the appropriate design workflow.

**Expected result:** A preliminary gameplay activity structure.

### Step 9: Evaluate Scope and Feasibility

Assess whether the concept is realistically achievable within the project's constraints.

Evaluate the following dimensions:

| Dimension | Evaluation Focus |
|---|---|
| Development Scope | Number and complexity of major systems |
| Technical Feasibility | Engine capabilities and implementation challenges |
| Content Requirements | Environments, characters, assets, and gameplay content |
| Art Requirements | Visual complexity and production effort |
| Audio Requirements | Music, sound effects, dialogue, and implementation |
| Narrative Requirements | Story complexity and writing requirements |
| Team Capacity | Available skills and development resources |
| Production Risk | Uncertain or expensive development areas |
| Platform Constraints | Performance, input, and platform limitations |

Classify findings as:

- Low Risk.
- Medium Risk.
- High Risk.
- Unknown.

Do not fabricate development estimates or claim that technical feasibility has been proven without evidence.

Identify the assumptions that should be validated through prototyping or research.

**Expected result:** A preliminary feasibility assessment.

### Step 10: Explore Alternatives

When important design decisions are uncertain, generate a limited number of meaningful alternatives.

Examples:

- Different gameplay structures.
- Different player perspectives.
- Different progression models.
- Different narrative approaches.
- Different levels of world openness.
- Different approaches to multiplayer or single-player design.

For each alternative, explain:

- Advantages.
- Disadvantages.
- Development implications.
- Player experience implications.
- Major risks.

Avoid producing alternatives merely to increase document length.

Present recommendations with reasoning, but leave unresolved decisions to the project owner.

**Expected result:** A set of evaluated alternatives for important concept decisions.

### Step 11: Identify the Concept's Main Risks and Unknowns

Document uncertainties that could significantly affect the viability or identity of the concept.

Consider:

- Unproven gameplay assumptions.
- Unclear player motivation.
- Uncertain technical feasibility.
- Excessive content requirements.
- Difficult asset production.
- Unclear target audience.
- Weak differentiation.
- Dependencies on external tools or services.
- Potential scope expansion.

For each important risk, identify a possible validation approach.

**Expected result:** A preliminary list of risks, assumptions, and validation needs.

### Step 12: Generate the Game Concept Document

Create or update:

`game_project/docs/game_design/game_concept.md`

The document SHOULD contain:

1. Document Information.
2. Concept Summary.
3. Core Premise.
4. Intended Player Experience.
5. Genre and Gameplay Direction.
6. Setting and Narrative Premise.
7. Target Audience.
8. Gameplay Activities.
9. Key Differentiators.
10. Preliminary Scope.
11. Feasibility Assessment.
12. Risks and Assumptions.
13. Alternatives and Open Questions.
14. Recommended Next Steps.
15. Related Documents.
16. Review and Approval.

The agent MUST:

- Follow studio documentation standards.
- Use consistent terminology.
- Avoid redundant information.
- Distinguish confirmed decisions from proposals.
- Preserve the project owner's original intent.
- Reference relevant existing documents.
- Avoid creating detailed specifications prematurely.
- Set the document status to `Draft`.

### Step 13: Review the Concept

Evaluate the completed document against the following checklist.

**Concept clarity**

- [ ] The central idea is understandable.
- [ ] The premise clearly communicates what the game is about.
- [ ] The player's role is defined.
- [ ] The intended experience is explained.
- [ ] Primary gameplay activities are identified.

**Design coherence**

- [ ] Genre and gameplay direction are consistent.
- [ ] Setting supports the intended experience.
- [ ] Narrative and gameplay are compatible where applicable.
- [ ] Differentiators are meaningful.
- [ ] The target audience is reasonably defined.

**Feasibility**

- [ ] Major development constraints are identified.
- [ ] Significant risks are documented.
- [ ] Unproven assumptions are visible.
- [ ] Potential scope problems are identified.
- [ ] Important technical uncertainties are acknowledged.

**Documentation**

- [ ] The correct output location is used.
- [ ] Existing project decisions are respected.
- [ ] Proposals are distinguished from confirmed information.
- [ ] Related documents are referenced accurately.
- [ ] The document status is `Draft`.
- [ ] No duplicate document was created.

Correct identified issues before presenting the concept.

### Step 14: Present for Project Owner Review

Present the Game Concept to the project owner.

Include:

1. A concise concept summary.
2. The central player experience.
3. The proposed genre and gameplay direction.
4. The strongest differentiators.
5. The target audience.
6. The preliminary scope and feasibility assessment.
7. The most important risks and unknowns.
8. Alternative directions considered.
9. Recommendations and unresolved decisions.

The project owner MUST review the concept before it is treated as an approved project direction.

Agents MUST NOT:

- Approve their own concept.
- Mark the document as `Approved` without explicit authorization.
- Treat generated suggestions as confirmed decisions.
- Modify the original project idea without authorization.
- Commit the project to features or production scope without approval.

## 7. Concept Validation and Iteration

### 7.1 Concept Validation

A concept may require validation before moving into pre-production.

Depending on the project, validation may include:

- Research into comparable games.
- Prototype development.
- Gameplay experiments.
- Player interviews.
- Playtesting.
- Technical feasibility tests.
- Art or visual experiments.
- Narrative experiments.

The validation method should target the most important uncertainties.

Do not build a complete game to validate a concept that could be tested with a small prototype.

### 7.2 Concept Revision

When feedback or validation results are received:

1. Identify the original assumption or decision being evaluated.
2. Review the available evidence.
3. Determine whether the concept remains viable.
4. Identify the required changes.
5. Assess their impact on other project documents.
6. Revise the Game Concept.
7. Present significant changes for owner review.

Preserve the reasoning behind major changes when it is relevant to future decisions.

### 7.3 Concept Outcomes

The concept review may result in one of the following decisions:

| Outcome | Description |
|---|---|
| Proceed | The concept is sufficiently clear and viable to continue development. |
| Revise | The concept has potential but requires significant refinement. |
| Validate | Important assumptions require research or prototyping before proceeding. |
| Hold | Development is temporarily postponed. |
| Reject | The concept will not proceed in its current form. |

The project owner makes the final decision.

## 8. Transition to Subsequent Workflows

Once the Game Concept has been reviewed and accepted, the project may proceed to additional design activities.

Recommended sequence:

1. Create or refine the Game Vision.
2. Create the Core Pillars.
3. Define the Core Game Loop.
4. Develop the preliminary Game Design Document.
5. Establish the initial world and narrative direction.
6. Identify major gameplay systems.
7. Plan concept validation and pre-production activities.

These activities do not need to follow a rigid sequence. Some may be performed iteratively as the concept becomes clearer.

The Game Concept remains a high-level reference. It should not become a substitute for detailed design documentation.

## 9. Completion Criteria

This workflow is complete when:

- [ ] The initial idea has been understood.
- [ ] The core premise has been defined.
- [ ] The intended player experience has been described.
- [ ] Genre and gameplay direction have been explored.
- [ ] Setting and narrative direction have been considered.
- [ ] Target audience has been identified.
- [ ] Key differentiators have been evaluated.
- [ ] Primary gameplay activities have been identified.
- [ ] Scope and feasibility have been assessed.
- [ ] Important risks and assumptions have been documented.
- [ ] Significant alternatives have been considered where appropriate.
- [ ] The Game Concept document has been generated.
- [ ] Documentation consistency has been checked.
- [ ] The concept has been presented for project owner review.

Completion of this workflow does not imply approval of the Game Concept.

## 10. Expected Agent Report

After execution, provide a report using the following structure:

### Game Concept Creation Report

**Status:** [Completed / Partially Completed / Blocked]

**Output Document:** `game_project/docs/game_design/game_concept.md`

**Concept Summary:**

[Short description of the proposed game.]

**Genre and Gameplay Direction:**

[Summary.]

**Intended Player Experience:**

[Summary.]

**Key Differentiators:**

1. [Differentiator]
2. [Differentiator]
3. [Differentiator]

**Target Audience:**

[Summary.]

**Feasibility Assessment:**

[Summary.]

**Major Risks:**

- [Risk or None.]

**Unresolved Questions:**

- [Question or None.]

**Assumptions:**

- [Assumption or None.]

**Recommendations:**

- [Recommended next step.]

**Project Owner Review:** Pending

**Next Action:** [Required action.]

## 11. Related References

### Studio Documentation

- Game Development Lifecycle: `docs/00_studio_standards/game_development_lifecycle.md`
- Development Philosophy: `docs/00_studio_standards/development_philosophy.md`
- Design Principles: `docs/01_game_design_guidelines/design_principles.md`
- Player Experience Guidelines: `docs/01_game_design_guidelines/player_experience_guidelines.md`
- Core Pillars Template: `docs/06_templates/core_pillars_template.md`
- Game Vision Template: `docs/06_templates/game_vision_template.md`
- Game Design Document Template: `docs/06_templates/game_design_document_template.md`

### Related Agent Workflows

- Create Core Pillars: `docs/07_agent_workflows/create_core_pillars.md`

Only use references that exist in the applicable repository.

---

**End of Workflow**
