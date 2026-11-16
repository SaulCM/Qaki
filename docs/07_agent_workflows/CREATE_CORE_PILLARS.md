# Create Core Pillars Workflow

## 1. Purpose

This workflow defines the standard procedure for AI agents to assist in identifying, evaluating, documenting, and refining a game's core design pillars.

Core pillars describe the fundamental qualities that define the game's identity and guide its design decisions.

They establish what makes the game distinctive, what the player experience should prioritize, and which design principles should influence gameplay, narrative, progression, art, audio, and production decisions.

The objective is to produce a concise, meaningful, and actionable Core Pillars document that can guide the entire development process.

## 2. Scope

This workflow covers:

- Reviewing existing project information.
- Understanding the game's vision and intended player experience.
- Identifying potential core pillars.
- Evaluating and prioritizing candidate pillars.
- Defining each pillar and its design implications.
- Identifying supporting mechanics and examples.
- Establishing validation criteria.
- Generating the project-specific Core Pillars document.
- Reviewing consistency with existing project documentation.

This workflow does not authorize agents to independently redefine the game's vision, change approved design decisions, or establish new project scope without approval.

## 3. Output

| Property | Value |
|---|---|
| Output Document | `game_project/docs/game_design/core_pillars.md` |
| Source Template | `docs/06_templates/CORE_PILLARS_TEMPLATE.md` |
| Document Type | Game Design |
| Primary Owner | Project Owner / Game Director |
| Approval Authority | Project Owner |
| Initial Status | Draft |

The generated document MUST follow the structure and guidance defined in the Core Pillars Template.

Agents MUST inspect the actual repository before creating the output. If the document already exists, they MUST review and update it rather than creating a duplicate.

## 4. Required Inputs

### 4.1 Primary References

Before starting, inspect the following documents when available:

1. Game Vision.
2. Game Design Document.
3. Project Concept or Pitch.
4. Target Audience Definition.
5. Existing Game Design documentation.
6. Existing Core Pillars document, if present.

### 4.2 Supporting References

Review relevant documents when available:

- Narrative Overview.
- Core Game Loop.
- Gameplay Design Guidelines.
- Player Experience Guidelines.
- Mechanic Design Guidelines.
- Progression Design Guidelines.
- Art Direction.
- Audio Direction.
- Project Roadmap.

### 4.3 Missing Information

If important information is unavailable:

1. Identify what is missing.
2. Determine whether the available information is sufficient to proceed.
3. Record assumptions explicitly.
4. Ask the project owner for clarification when a missing decision materially affects the game's identity.
5. Do not invent approved project decisions.

Agents MAY create an initial proposal from incomplete information, but MUST clearly label uncertain content.

## 5. Workflow Principles

Agents MUST follow these principles:

- **Identity first:** Pillars must communicate what makes the game distinctive.
- **Player-centered:** Pillars must describe meaningful player experiences, not merely implementation choices.
- **Specificity:** Each pillar must be understandable and distinguishable from generic game design statements.
- **Actionability:** Pillars must influence concrete design and production decisions.
- **Consistency:** Pillars must support the approved Game Vision.
- **Prioritization:** Pillars must help resolve competing design priorities.
- **Limited quantity:** Prefer approximately three to five meaningful pillars.
- **Independence:** Avoid creating multiple pillars that express essentially the same idea.
- **Validation:** Each pillar must have observable ways to evaluate whether the game supports it.
- **Practicality:** Pillars must be achievable within the project's scope and resources.

Pillars MUST NOT become a list of every feature, mechanic, genre convention, or desirable quality.

## 6. Execution Procedure

### Step 1: Inspect Project Context

1. Inspect the repository structure.
2. Read applicable agent rules and project instructions.
3. Review the Documentation Inventory when required by the documentation management rules.
4. Locate the Game Vision and other primary references.
5. Review existing game design documents.
6. Identify established decisions, constraints, and unresolved questions.
7. Check whether a Core Pillars document already exists.

**Expected result:** A clear understanding of the project's current identity, intended player experience, constraints, and existing decisions.

Do not proceed by assuming that the project is a particular genre or follows a conventional design formula.

### Step 2: Extract the Game Identity

Analyze the available project information and identify:

- The game's central concept.
- Its intended player experience.
- Its primary gameplay activities.
- Its defining mechanics.
- Its narrative identity.
- Its distinguishing characteristics.
- Its target audience.
- Its intended emotional impact.
- Its major design constraints.

Separate defining characteristics from supporting features.

A feature may contribute to a pillar without being important enough to become a pillar itself.

**Expected result:** A concise summary of the game's identity and the qualities that should define its development.

### Step 3: Identify Candidate Pillars

Generate a preliminary list of potential pillars based on the extracted game identity.

Candidate pillars may relate to:

- Core gameplay.
- Player agency.
- Exploration and discovery.
- Combat and challenge.
- Narrative and storytelling.
- World interaction.
- Progression and mastery.
- Social interaction.
- Resource management.
- Atmosphere and immersion.
- Creativity and experimentation.

These are possible categories, not mandatory pillars.

For each candidate, describe:

1. Its central idea.
2. The player experience it promises.
3. Why it matters to the game's identity.
4. Which design decisions it should influence.
5. How it differs from other candidates.

Do not promote a candidate to an approved pillar at this stage.

**Expected result:** A preliminary list of candidate pillars with supporting explanations.

### Step 4: Evaluate Candidate Pillars

Evaluate each candidate using the following criteria.

| Criterion | Evaluation Question |
|---|---|
| Identity | Does this distinguish the game from other experiences? |
| Player Experience | Does it describe something meaningful the player should experience? |
| Relevance | Does it support the central game concept? |
| Actionability | Can it guide concrete design decisions? |
| Consistency | Does it align with the Game Vision? |
| Distinctiveness | Is it meaningfully different from the other pillars? |
| Feasibility | Can the project realistically deliver it? |
| Longevity | Will it remain relevant throughout development? |

Identify candidates that:

- Are too generic.
- Overlap with other candidates.
- Describe features rather than design priorities.
- Are difficult to validate.
- Conflict with approved project constraints.
- Introduce unnecessary scope.

Revise, combine, or remove weak candidates.

**Expected result:** A prioritized set of distinct and actionable proposed pillars.

### Step 5: Define Each Pillar

For each proposed pillar, document:

1. **Name:** A concise and memorable title.
2. **Core Statement:** A clear description of the pillar.
3. **Player Promise:** What the player should experience.
4. **Design Intent:** Why this pillar matters.
5. **Supporting Elements:** Mechanics, systems, narrative elements, or content that reinforce it.
6. **Design Requirements:** What the game should do to fulfill the pillar.
7. **Anti-Patterns:** Design decisions that would undermine it.
8. **Examples:** Concrete examples of how it should appear in gameplay.
9. **Validation Criteria:** Observable conditions that demonstrate whether it is being fulfilled.
10. **Trade-offs:** Potential conflicts with other pillars or project constraints.

Each pillar MUST be specific enough to influence design decisions.

Avoid statements such as:

- "The game should be fun."
- "The game should have good graphics."
- "The game should provide an immersive experience."

These statements are too generic unless supported by a specific design interpretation.

**Expected result:** Complete definitions for every proposed pillar.

### Step 6: Evaluate Pillar Interactions

Review the proposed pillars as a coherent group.

Check:

- Whether they reinforce each other.
- Whether they create conflicting priorities.
- Whether one pillar dominates the others unintentionally.
- Whether their combined requirements are achievable.
- Whether they cover the game's defining experience without becoming an exhaustive feature list.

Document important trade-offs and explain how conflicts should be resolved.

If two pillars conflict, use the Game Vision and project priorities as the primary decision references.

Do not arbitrarily invent a hierarchy of importance without project owner agreement.

**Expected result:** A coherent set of proposed pillars with identified relationships and trade-offs.

### Step 7: Define Validation Criteria

Establish practical criteria for evaluating whether the game fulfills each pillar.

Validation may include:

- Prototype evaluation.
- Playtesting.
- Gameplay observation.
- Feature reviews.
- Design reviews.
- Player feedback.
- Technical feasibility tests.
- Content audits.

Prefer observable evidence over subjective claims.

Examples:

| Pillar | Validation Approach | Evidence |
|---|---|---|
| [Pillar] | [Playtesting / Prototype / Review] | [Observable result] |
| [Pillar] | [Gameplay evaluation] | [Observable result] |

Do not invent numerical targets or claim that validation has occurred when no evidence exists.

**Expected result:** A practical validation approach for each pillar.

### Step 8: Generate the Core Pillars Document

1. Read `docs/06_templates/CORE_PILLARS_TEMPLATE.md`.
2. Use its structure and required sections.
3. Populate the template using the evaluated pillar proposals.
4. Preserve the distinction between confirmed information and proposals.
5. Reference supporting project documents where appropriate.
6. Record unresolved questions.
7. Set the document status to `Draft`.
8. Save the document at `game_project/docs/game_design/core_pillars.md`.

The generated document MUST:

- Be concise and understandable.
- Avoid redundant explanations.
- Use consistent terminology.
- Contain actionable design guidance.
- Identify assumptions and unresolved decisions.
- Avoid duplicating entire sections of other project documents.
- Remain consistent with the approved Game Vision.

### Step 9: Review and Validate

Review the generated document against the following checklist.

**Identity and relevance**

- [ ] Pillars reflect the game's intended identity.
- [ ] Pillars support the Game Vision.
- [ ] Each pillar describes a meaningful player experience.
- [ ] Generic statements have been avoided.

**Quality and consistency**

- [ ] Each pillar is distinct.
- [ ] Pillars do not unnecessarily overlap.
- [ ] Each pillar contains actionable design implications.
- [ ] Supporting mechanics and examples are relevant.
- [ ] Conflicts and trade-offs are documented.
- [ ] Validation criteria are understandable.

**Documentation**

- [ ] The correct template was used.
- [ ] The correct output location was used.
- [ ] Related documents are referenced accurately.
- [ ] Assumptions and unresolved questions are identified.
- [ ] The document status is `Draft`.
- [ ] No duplicate document was created.

If problems are found, correct them before presenting the result.

### Step 10: Present for Project Owner Review

Provide the project owner with:

1. The generated document path.
2. A short summary of the proposed pillars.
3. The reasoning behind their selection.
4. Important trade-offs or conflicts.
5. Missing information and unresolved questions.
6. Any assumptions requiring confirmation.
7. The validation checklist results.

The project owner MUST review and approve the proposed pillars.

AI agents MUST NOT:

- Approve their own proposals.
- Change the document status to `Approved` without explicit authorization.
- Treat suggestions as confirmed design decisions.
- Modify the approved Game Vision to accommodate proposed pillars.
- Introduce new project commitments without approval.

## 7. Decision and Revision Handling

### 7.1 Project Owner Feedback

When feedback is received:

1. Identify requested changes.
2. Determine whether they affect individual pillars or the overall game identity.
3. Check for conflicts with existing approved documents.
4. Revise the proposal.
5. Revalidate the complete pillar set.
6. Present significant changes for review.

### 7.2 Changes to Approved Pillars

Changes to approved pillars may affect:

- Game Vision.
- Gameplay systems.
- Core Game Loop.
- Narrative direction.
- Art and audio direction.
- Progression.
- Production priorities.
- Existing features and milestones.

Before implementing a significant change, identify affected documents and request project owner approval.

### 7.3 Superseded Pillars

When a pillar is removed or replaced:

- Preserve relevant historical decisions.
- Explain why the change was made.
- Identify affected project documents.
- Update references where authorized.
- Do not silently delete important approved design history.

## 8. Completion Criteria

The workflow is complete when:

- [ ] Project context has been reviewed.
- [ ] Game identity has been extracted.
- [ ] Candidate pillars have been evaluated.
- [ ] Proposed pillars are distinct and actionable.
- [ ] Each pillar has a clear player promise.
- [ ] Supporting elements and design implications are documented.
- [ ] Conflicts and trade-offs have been considered.
- [ ] Validation criteria are defined.
- [ ] The Core Pillars document has been generated.
- [ ] Documentation consistency has been checked.
- [ ] The document has been presented for project owner review.

Completion of this workflow does not imply approval of the Core Pillars document.

## 9. Expected Agent Report

After execution, provide a report using the following structure:

### Core Pillars Creation Report

**Status:** [Completed / Partially Completed / Blocked]

**Output Document:** `game_project/docs/game_design/core_pillars.md`

**Project Context Reviewed:**
- [Document]
- [Document]

**Proposed Pillars:**
1. [Pillar name] — [One-sentence description]
2. [Pillar name] — [One-sentence description]
3. [Pillar name] — [One-sentence description]

**Validation Results:**
- Identity alignment: [Passed / Failed / Not Verified]
- Pillar distinctiveness: [Passed / Failed / Not Verified]
- Design actionability: [Passed / Failed / Not Verified]
- Documentation consistency: [Passed / Failed / Not Verified]

**Assumptions:**
- [Assumption or None]

**Unresolved Questions:**
- [Question or None]

**Conflicts or Risks:**
- [Issue or None]

**Project Owner Review:** Pending

**Next Action:** [Required action]

## 10. Related References

### Studio Documentation

- Core Pillars Template: `docs/06_templates/CORE_PILLARS_TEMPLATE.md`
- Game Design Principles: `docs/01_game_design_guidelines/DESIGN_PRINCIPLES.md`
- Player Experience Guidelines: `docs/01_game_design_guidelines/PLAYER_EXPERIENCE_GUIDELINES.md`
- Core Loop Design Guidelines: `docs/01_game_design_guidelines/CORE_LOOP_DESIGN_GUIDELINES.md`
- Gameplay Design Guidelines: `docs/01_game_design_guidelines/GAMEPLAY_DESIGN_GUIDELINES.md`
- Documentation Standards: `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- Definition of Done: `docs/00_studio_standards/DEFINITION_OF_DONE.md`

### Project Documentation

- Game Vision: `game_project/docs/game_design/game_vision.md`
- Game Design Document: `game_project/docs/game_design/game_design_document.md`
- Core Game Loop: `game_project/docs/game_design/core_game_loop.md`
- Narrative Overview: `game_project/docs/game_design/narrative/narrative_overview.md`

Only use references that exist in the applicable repository.

---

**End of Workflow**
