# Review Design

## 1. Purpose

This workflow defines how an AI agent should review game design documents, specifications, and proposed design changes.

The objective is to evaluate whether a design is clear, coherent, feasible, consistent with the game's identity, aligned with its intended player experience, and sufficiently detailed to guide implementation.

The review should identify design weaknesses, contradictions, missing information, unnecessary complexity, and potential risks before the design is approved or implemented.

## 2. Scope

Use this workflow when reviewing:

- Game concepts.
- Game vision documents.
- Core game pillars.
- Game design documents.
- Core gameplay loops.
- Gameplay mechanics.
- Gameplay systems.
- Character designs.
- Quest designs.
- Level designs.
- Narrative and worldbuilding documents.
- Progression systems.
- Difficulty and balancing proposals.
- Economy and reward systems.
- UI/UX designs.
- Proposed changes to existing game design.

Do not use this workflow for:

- Implementing gameplay systems.
- Reviewing source code.
- Performing technical architecture reviews.
- Replacing player playtesting.
- Making final creative decisions on behalf of the user.
- Approving designs without human authorization.

For technical implementation reviews, use `review_code.md`.

## 3. Authoritative References

Before reviewing a design, inspect the relevant studio standards and project documentation.

### 3.1 Studio references

Use the references applicable to the design under review:

- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/01_game_design_guidelines/DESIGN_PRINCIPLES.md`
- `docs/01_game_design_guidelines/PLAYER_EXPERIENCE_GUIDELINES.md`
- `docs/01_game_design_guidelines/CORE_LOOP_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/GAMEPLAY_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/MECHANIC_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/PROGRESSION_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/DIFFICULTY_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/BALANCING_GUIDELINES.md`
- `docs/01_game_design_guidelines/ECONOMY_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/REWARD_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/NARRATIVE_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/LEVEL_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/UI_UX_DESIGN_GUIDELINES.md`

Read only the references relevant to the design being reviewed.

If a referenced document is not present in the repository, do not assume its contents. Use the available authoritative documents and report relevant missing guidance when necessary.

### 3.2 Project references

Inspect available project-specific documents, prioritizing:

- Game concept.
- Game vision.
- Core pillars.
- Game design document.
- Core gameplay loop.
- Relevant gameplay specifications.
- Relevant mechanic specifications.
- Narrative and world overview.
- Character, quest, and level specifications.
- Progression and balancing documentation.
- Approved technical constraints.
- Previous design decisions.
- Related playtesting findings.

Project documents take precedence over assumptions about the intended game, provided they have the appropriate approval status.

## 4. Workflow Overview

Follow these stages:

1. Understand the review request.
2. Inspect project context and authoritative documents.
3. Identify the design's purpose and scope.
4. Evaluate alignment with game identity and core pillars.
5. Evaluate player experience and gameplay value.
6. Evaluate design clarity and completeness.
7. Evaluate system interactions and consistency.
8. Evaluate feasibility and production risks.
9. Evaluate balance, progression, and edge cases where relevant.
10. Evaluate narrative, presentation, and accessibility where relevant.
11. Evaluate validation requirements.
12. Classify and report findings.
13. Provide an overall review assessment.

Adapt the depth of the review to the design's importance, complexity, and risk.

## 5. Stage 1: Understand the Review Request

Determine what design material needs to be reviewed.

Identify:

- Review target.
- Design document or proposal.
- Related feature, system, or milestone.
- Intended audience.
- Design objectives.
- Expected player experience.
- Relevant requirements.
- Requested review depth.
- Known constraints.
- Specific concerns raised by the user.

Determine whether the review concerns:

- A new design proposal.
- An existing approved design.
- A revision to an existing design.
- A specific mechanic or system.
- A complete game design document.
- Consistency between multiple design documents.

If the request is ambiguous, identify the missing information rather than making unsupported assumptions.

## 6. Stage 2: Inspect Project Context and Authoritative Documents

Understand the game before judging individual design decisions.

Inspect:

- Current game concept and vision.
- Core pillars.
- Target audience.
- Genre and intended experience.
- Core gameplay loop.
- Established mechanics and systems.
- Narrative and worldbuilding direction.
- Technical and production constraints.
- Approved design decisions.
- Relevant playtesting feedback.

### 6.1 Establish document authority

Distinguish between:

- **Approved:** Explicitly accepted by the authorized project owner.
- **Draft:** Work in progress that has not been approved.
- **Proposed:** A candidate design or recommendation awaiting a decision.
- **Deprecated:** Superseded or no longer applicable.
- **Unknown:** Approval status cannot be established.

Do not treat a draft or proposal as approved project canon.

When documents conflict:

1. Identify the conflicting statements.
2. Check their approval status and revision history.
3. Determine whether one document explicitly supersedes another.
4. Report unresolved conflicts.
5. Request human clarification when the conflict affects the review.

Do not silently resolve significant design conflicts.

## 7. Stage 3: Identify the Design's Purpose and Scope

Establish what the design is intended to accomplish.

Identify:

- Design problem or opportunity.
- Intended player experience.
- Design goals.
- Non-goals.
- Intended gameplay role.
- Expected player actions.
- Relevant systems and dependencies.
- Scope boundaries.
- Assumptions.
- Constraints.
- Success criteria.

### 7.1 Scope consistency

Evaluate whether the proposal stays within its intended scope.

Look for:

- Unnecessary features.
- Unrelated mechanics.
- Unjustified complexity.
- Missing essential elements.
- Overlapping responsibilities.
- Requirements that contradict the stated objectives.

A design may contain optional extensions, but they should be distinguished from the minimum required design.

## 8. Stage 4: Evaluate Alignment with Game Identity and Core Pillars

Determine whether the design supports the game's identity.

Evaluate:

- Alignment with the game vision.
- Contribution to core pillars.
- Consistency with the intended genre.
- Relevance to the target audience.
- Contribution to the game's distinctive experience.
- Compatibility with established design priorities.
- Consistency with the game's tone and identity.

### 8.1 Core pillar alignment

For each relevant pillar, determine:

- Whether the design supports it.
- How it supports it.
- Whether it introduces conflicts.
- Whether the conflict is intentional.
- Whether the design weakens the game's identity.

Not every feature must directly reinforce every pillar.

A design should not be rejected simply because it does not contribute equally to all pillars.

### 8.2 Design identity

Identify whether the design:

- Adds meaningful value to the game.
- Reinforces the intended experience.
- Introduces unnecessary genre conventions.
- Feels disconnected from other systems.
- Creates an identity or tone inconsistency.

Avoid recommending features merely because they are common in other games.

## 9. Stage 5: Evaluate Player Experience and Gameplay Value

Assess the design from the player's perspective.

### 9.1 Player motivation

Evaluate:

- Why the player would engage with the design.
- What the player wants to accomplish.
- What motivates continued interaction.
- Whether the design creates meaningful decisions.
- Whether the intended experience is understandable.

### 9.2 Player agency

Consider:

- Available choices.
- Consequences of decisions.
- Meaningful alternatives.
- Player control.
- Opportunities for experimentation.
- Whether outcomes feel predictable or understandable.

### 9.3 Feedback and readability

Check whether the design explains:

- What the player can do.
- What happens after an action.
- Whether an action succeeded or failed.
- Why a particular outcome occurred.
- What changed in the game state.
- What the player can do next.

### 9.4 Engagement and pacing

Evaluate:

- Challenge and reward balance.
- Repetition.
- Variety.
- Downtime.
- Cognitive load.
- Progression of complexity.
- Potential frustration.
- Opportunities for mastery.

Do not assume that every mechanic needs to be continuously exciting. Quiet, reflective, or deliberately repetitive experiences may be valid when they support the intended design.

## 10. Stage 6: Evaluate Design Clarity and Completeness

Determine whether the document communicates the design sufficiently for its intended purpose.

### 10.1 Clarity

Check whether:

- Terminology is consistent.
- Rules are understandable.
- Player actions are explicit.
- Outcomes are described.
- Constraints are identifiable.
- Important assumptions are stated.
- Ambiguous statements are minimized.

### 10.2 Completeness

Evaluate whether the document contains the information necessary for its type.

For a gameplay mechanic, relevant information may include:

- Purpose.
- Activation conditions.
- Inputs.
- Rules.
- States and transitions.
- Outputs.
- Feedback.
- Costs and consequences.
- Failure conditions.
- Edge cases.

For a gameplay system, relevant information may include:

- System purpose.
- Scope and boundaries.
- Components.
- Responsibilities.
- Rules.
- Interactions.
- Dependencies.
- Player experience.
- State management.
- Failure and recovery behavior.

For a quest, relevant information may include:

- Narrative purpose.
- Prerequisites.
- Objectives.
- Stages.
- Choices.
- Outcomes.
- Rewards.
- Completion and failure conditions.

For a level, relevant information may include:

- Intended experience.
- Layout and progression.
- Player navigation.
- Challenges.
- Encounters.
- Landmarks.
- Environmental storytelling.
- Pacing.
- Completion conditions.

Do not require every document to contain every possible section.

Evaluate completeness according to the document's purpose and level of detail.

### 10.3 Actionability

Determine whether the design provides enough information for the next production step.

Identify missing information that would prevent:

- Implementation.
- Content creation.
- Balancing.
- Narrative production.
- Level construction.
- Testing.
- Acceptance.

Distinguish essential missing information from details that can reasonably be decided during implementation.

## 11. Stage 7: Evaluate System Interactions and Consistency

Review how the design interacts with the rest of the game.

Consider relevant relationships with:

- Core gameplay loop.
- Combat.
- Exploration.
- Movement.
- Inventory.
- Crafting.
- Economy.
- Progression.
- Rewards.
- Difficulty.
- Narrative.
- Quests.
- Characters.
- Level design.
- UI/UX.
- Save/load behavior.

### 11.1 Interaction analysis

Evaluate:

- Inputs and outputs between systems.
- Dependencies.
- Shared resources.
- State ownership.
- Player-facing consequences.
- Potential conflicts.
- Unintended feedback loops.
- Exploitable interactions.

### 11.2 Consistency

Look for:

- Contradictory rules.
- Inconsistent terminology.
- Conflicting player capabilities.
- Incompatible progression assumptions.
- Contradictory reward structures.
- Narrative inconsistencies.
- Repeated functionality with different rules.
- Unclear ownership between systems.

### 11.3 Emergent behavior

When multiple mechanics interact, consider whether their combination creates:

- Unexpected advantages.
- Degenerate strategies.
- Unintended difficulty spikes.
- Resource exploits.
- Progression shortcuts.
- Unavoidable failure states.
- Unintended repetitive behavior.

Do not assume that emergent behavior is undesirable. Evaluate whether it supports or damages the intended player experience.

## 12. Stage 8: Evaluate Feasibility and Production Risks

Determine whether the design can reasonably be produced within the project's constraints.

Evaluate:

- Implementation complexity.
- Content production requirements.
- Art and animation requirements.
- Audio requirements.
- UI requirements.
- Technical dependencies.
- Required tools or plugins.
- Testing complexity.
- Performance implications.
- Maintenance cost.
- Production effort.
- Scope impact.

### 12.1 Scope and complexity

Identify:

- Features that can be simplified.
- Unnecessary dependencies.
- Excessive content requirements.
- Systems that could be combined.
- Features that should be prototyped first.
- High-risk assumptions.

Do not remove important creative elements solely to minimize implementation effort.

Recommend alternatives that preserve the intended player experience while reducing unnecessary complexity.

### 12.2 Technical feasibility

When relevant, inspect existing technical documentation and constraints.

Determine whether the design appears compatible with:

- The selected Godot version.
- Existing project architecture.
- Current project capabilities.
- Resource and asset requirements.
- Performance expectations.
- Save and persistence requirements.
- Platform constraints.

A design review evaluates feasibility at the design level. Detailed implementation decisions belong in technical design and architecture reviews.

## 13. Stage 9: Evaluate Balance, Progression, and Edge Cases

Apply this stage when the design affects game balance, player progression, resources, difficulty, or rewards.

### 13.1 Balance

Evaluate:

- Relative effectiveness.
- Costs and benefits.
- Risk and reward.
- Player choices.
- Dominant strategies.
- Viable alternatives.
- Difficulty implications.
- Long-term consequences.

Check whether design targets are explicit enough to be evaluated.

Do not invent numerical balance targets when the project has not established them.

### 13.2 Progression

Evaluate:

- Progression purpose.
- Unlock conditions.
- Pacing.
- Player power growth.
- Reward frequency.
- Dependencies.
- Long-term goals.
- Potential progression bottlenecks.

### 13.3 Economy and rewards

When applicable, inspect:

- Resource acquisition.
- Resource consumption.
- Resource scarcity.
- Reward value.
- Reward frequency.
- Economic sinks.
- Exploitable loops.
- Inflation or resource accumulation.
- Relationship with player progression.

### 13.4 Difficulty

Evaluate:

- Challenge expectations.
- Learning curve.
- Fairness.
- Failure consequences.
- Recovery opportunities.
- Difficulty progression.
- Accessibility.
- Potential frustration.

### 13.5 Edge cases

Consider:

- Repeated interactions.
- Interrupted actions.
- Missing prerequisites.
- Resource shortages.
- Maximum and minimum values.
- Conflicting player states.
- Optional content interactions.
- Sequence-breaking possibilities.
- Save/load during important transitions.
- Player actions outside the intended sequence.

Identify which edge cases require explicit design decisions and which can be handled by implementation details.

## 14. Stage 10: Evaluate Narrative, Presentation, and Accessibility

Apply these checks when relevant to the design.

### 14.1 Narrative consistency

Evaluate:

- Character motivations.
- World rules.
- Narrative tone.
- Story continuity.
- Faction relationships.
- Player choices and consequences.
- Gameplay and narrative integration.
- Consistency with established worldbuilding.

Distinguish confirmed narrative facts from proposed ideas and unresolved questions.

Do not invent canon to fill gaps.

### 14.2 Presentation

Consider:

- Visual communication.
- Animation requirements.
- Audio feedback.
- UI presentation.
- Readability.
- Consistency with art and audio direction.
- Whether presentation communicates gameplay meaning.

### 14.3 Accessibility

Evaluate relevant considerations such as:

- Readability.
- Color dependency.
- Input flexibility.
- Timing requirements.
- Audio and visual alternatives.
- Difficulty options.
- Information clarity.
- Cognitive load.

Not every accessibility consideration applies to every design. Identify meaningful barriers rather than applying a mechanical checklist.

## 15. Stage 11: Evaluate Validation Requirements

Determine how the design should be validated before full implementation or approval.

Consider:

- Paper design evaluation.
- Prototypes.
- Graybox levels.
- Gameplay experiments.
- Numerical simulations.
- Balance spreadsheets.
- Internal playtesting.
- External playtesting.
- Usability testing.
- Narrative reviews.
- Technical feasibility tests.

### 15.1 Validation objectives

For each important design assumption, identify:

- What needs to be validated.
- Why it matters.
- How it can be tested.
- What evidence should be collected.
- What outcome would support the design.
- What outcome would require revision.

### 15.2 Playtesting evidence

When playtesting findings exist, evaluate:

- Observed player behavior.
- Player feedback.
- Repeated usability problems.
- Difficulty patterns.
- Unexpected strategies.
- Confusion or frustration.
- Differences between intended and actual experiences.

Distinguish observed evidence from interpretations and recommendations.

Do not present an untested design assumption as a proven player experience.

## 16. Stage 12: Classify and Report Findings

Classify findings according to their importance.

### 16.1 Finding categories

Use the following categories:

- **Critical:** A fundamental design problem that undermines the game's identity, makes the intended experience unworkable, or creates a serious contradiction that prevents meaningful progression or implementation.
- **High:** A significant design weakness that substantially affects player experience, system coherence, feasibility, or implementation readiness.
- **Medium:** A meaningful issue that should be addressed but does not invalidate the overall design.
- **Low:** A minor clarity, consistency, or completeness issue.
- **Suggestion:** An optional improvement or alternative worth considering.

Severity should reflect the impact of the issue, not the agent's personal preference.

### 16.2 Finding requirements

Each finding should include:

- Severity.
- Category.
- Short descriptive title.
- Relevant document and section.
- Description of the issue.
- Why it matters.
- Supporting evidence or reasoning.
- Recommended correction or alternative.

### 16.3 Finding quality

A useful finding must:

- Identify a specific design issue.
- Explain its impact.
- Relate to an established design objective or requirement.
- Offer an actionable recommendation.
- Distinguish facts from assumptions.
- Avoid subjective statements presented as objective defects.

When proposing an alternative, explain the tradeoffs rather than presenting it as automatically superior.

### 16.4 Positive observations

Include important design strengths when they are relevant to the review.

Examples:

- Strong alignment with a core pillar.
- Clear player motivation.
- Meaningful player choices.
- Good integration between systems.
- Effective scope boundaries.
- Well-defined validation criteria.

Positive observations should be specific and useful, not generic praise.

## 17. Stage 13: Provide an Overall Review Assessment

After reviewing the design, provide one of the following outcomes:

- **Changes Required:** Significant design issues must be addressed before approval.
- **Review Passed:** No blocking design issues were identified within the reviewed scope.
- **Review Incomplete:** Important areas could not be evaluated because of missing information or insufficient context.
- **Needs Clarification:** Requirements, project decisions, or intended player experience are ambiguous.

A review passing does not mean that the design is guaranteed to succeed with players.

### 17.1 Approval boundaries

The agent may:

- Identify design problems.
- Recommend improvements.
- Propose alternative approaches.
- Highlight tradeoffs.
- Suggest prototypes and experiments.
- Prepare revised design drafts when requested.

The agent MUST NOT:

- Approve its own design.
- Mark a document as Approved without human authorization.
- Change established game canon without approval.
- Make significant creative decisions on behalf of the user.
- Treat suggestions as approved requirements.
- Replace human playtesting with assumptions.
- Rewrite approved design documents without authorization.

The user or authorized project owner remains responsible for final design approval.

## 18. Revision and Re-review Process

When the design author submits revisions:

1. Inspect the updated document.
2. Compare the changes with the previous version.
3. Identify which findings were addressed.
4. Verify that corrections resolve the original issues.
5. Check whether the changes introduce new inconsistencies.
6. Re-evaluate affected systems and documents.
7. Update unresolved findings.
8. Provide a revised assessment.

Do not assume a finding is resolved simply because the author states that it was addressed.

When a revision changes the design's scope or intended experience, review the affected sections and dependencies again.

## 19. Completion Criteria

The design review is complete when:

- The review request is understood.
- Relevant project context has been inspected.
- Document authority and approval status have been considered.
- Design purpose and scope are clear.
- Alignment with the game vision and core pillars has been evaluated.
- Player experience and gameplay value have been assessed.
- Clarity and completeness have been reviewed.
- Relevant system interactions and dependencies have been evaluated.
- Feasibility and production risks have been considered.
- Relevant balance, progression, and edge cases have been reviewed.
- Narrative, presentation, and accessibility have been considered where applicable.
- Validation requirements have been identified.
- Findings have been classified and documented.
- An overall review assessment has been provided.

Completion of this workflow does not imply human approval.

## 20. AI Agent Rules

The agent MUST:

- Understand the game's identity before reviewing individual design decisions.
- Inspect relevant approved project documentation.
- Respect established design decisions and project constraints.
- Evaluate designs from the player's perspective.
- Identify contradictions and missing information.
- Consider interactions with existing systems.
- Distinguish design problems from personal preferences.
- Support findings with clear reasoning.
- Distinguish confirmed facts, assumptions, and proposals.
- Recommend validation for uncertain design assumptions.
- Preserve approved narrative and worldbuilding facts.
- Respect human creative authority.
- Report limitations and unresolved questions.

The agent MUST NOT:

- Invent project requirements.
- Invent established game canon.
- Treat unapproved proposals as confirmed decisions.
- Reject a design solely because it differs from common genre conventions.
- Add unnecessary features to make a design appear more complete.
- Force complexity or abstractions without justification.
- Replace missing evidence with confident assumptions.
- Claim that an untested design has been validated.
- Approve its own design.
- Change approved documents without authorization.

## 21. Final Report Format

After completing the review, provide the following report:

### Design Review Report

**Review target:** [Document, feature, mechanic, system, or proposal]

**Related project area:** [Relevant game system or None]

**Review scope:** [Sections and design aspects inspected]

**Overall assessment:** Changes Required / Review Passed / Review Incomplete / Needs Clarification

**Design alignment:**
- Game vision: [Aligned / Partially Aligned / Misaligned / Not Evaluated]
- Core pillars: [Aligned / Partially Aligned / Misaligned / Not Evaluated]
- Player experience: [Strong / Needs Improvement / Unclear / Not Evaluated]

**Strengths:**
- [Important design strengths or None]

**Findings:**

#### Critical
- [Finding or None]

#### High
- [Finding or None]

#### Medium
- [Finding or None]

#### Low
- [Finding or None]

#### Suggestions
- [Suggestion or None]

**System interactions:** [Relevant observations or None]

**Feasibility and production risks:** [Risks or None]

**Validation recommendations:** [Required prototypes, experiments, or playtests]

**Unresolved questions:** [Questions or None]

**Recommended next steps:** [Actions required]

**Human approval:** Required / Pending / Not Applicable

Do not report a design review as passed when significant areas remain uninspected or important requirements remain unresolved.