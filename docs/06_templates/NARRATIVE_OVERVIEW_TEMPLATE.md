# Narrative Overview Template

> **Purpose:** This template guides AI agents in generating the project-specific Narrative Overview document for a game.
>
> The generated Narrative Overview must provide a coherent, high-level description of the game's narrative identity, premise, world, central conflict, themes, characters, story structure, and relationship between narrative and gameplay.
>
> This template is an authoring specification, not the final narrative document. AI agents must replace the instructions and placeholders with project-specific information, following the approved source documents.
>
> Do not invent major story events, characters, relationships, world rules, endings, or narrative decisions that are not supported by approved project information. Clearly identify unresolved decisions.

---

## 1. Document Generation Instructions

### 1.1 Generation Objective

Generate a project-specific Narrative Overview that communicates the intended narrative experience and establishes a shared understanding of the game's story direction.

The generated document must:

- Explain the game's narrative premise and central conflict.
- Establish the narrative setting and its relevant context.
- Define the main themes, tone, and storytelling approach.
- Describe the protagonist and other major narrative roles.
- Summarize the intended story structure and progression.
- Explain how narrative and gameplay support each other.
- Identify major narrative constraints and unresolved decisions.
- Provide enough context for other AI agents and developers to work consistently.

### 1.2 Intended Output

| Property | Requirement |
|---|---|
| Output Filename | `narrative_overview.md` |
| Recommended Location | `docs/game_design/narrative/narrative_overview.md` |
| Document Type | Project-specific narrative specification |
| Primary Audience | Project owner, narrative designers, game designers, developers, AI agents |
| Source of Truth | Approved project documents |
| Document Status | Draft until reviewed and approved |
| Language | [Use the project's designated documentation language] |

### 1.3 Source Documents

Before generating the Narrative Overview, inspect the available project documents.

**Primary sources:**

1. Game Vision.
2. Game Design Document.
3. Core Pillars.
4. Narrative direction or narrative design documents, if available.
5. Worldbuilding and setting documents, if available.
6. Character specifications, if available.

**Supporting sources:**

- Core Game Loop.
- Gameplay System Specifications.
- Level Design Documents.
- Art Direction.
- Audio Direction.
- Progression Design.
- Approved Architecture Decision Records, when they contain relevant narrative constraints.
- Existing narrative dialogue, scripts, quests, or other story material.

Use only documents that actually exist in the project. Do not assume that every listed document is available.

### 1.4 Source Authority and Conflict Resolution

When information conflicts, use this precedence:

1. Explicitly approved project owner decisions.
2. Approved project-specific specifications.
3. Approved Game Design Document and Game Vision.
4. Approved supporting design documents.
5. Draft documents and unapproved proposals.
6. Previous brainstorming, AI suggestions, and informal notes.

If two authoritative sources conflict:

- Do not silently choose one.
- Identify the conflicting statements.
- Explain their impact on the narrative.
- Record the issue as an open question.
- Request project owner clarification when the conflict affects major narrative decisions.

### 1.5 Information Classification

The generated document must distinguish between:

| Classification | Meaning |
|---|---|
| Confirmed | Explicitly established by an approved source or project owner decision. |
| Derived | A reasonable conclusion supported by existing approved information. |
| Proposed | An AI-generated or designer-suggested idea that has not been approved. |
| Undecided | An important narrative element that has not been established. |
| Not Applicable | A section that does not apply to the project's narrative approach. |

Do not present proposed, derived, or undecided information as confirmed canon.

### 1.6 Generation Rules

AI agents MUST:

1. Read the relevant project documents before writing.
2. Preserve the project's established identity, themes, and creative direction.
3. Avoid contradicting approved narrative information.
4. Avoid introducing major characters, factions, locations, historical events, or plot twists without supporting sources.
5. Avoid expanding the narrative beyond the approved project scope.
6. Distinguish established facts from interpretation and proposals.
7. Keep the overview focused on narrative direction rather than detailed implementation.
8. Avoid duplicating detailed character, quest, dialogue, and worldbuilding specifications.
9. Reference existing project documents where additional detail is required.
10. Preserve unresolved questions rather than filling gaps with invented information.
11. Use consistent names, terminology, dates, relationships, and world rules.
12. Never change approved narrative decisions without explicit project owner authorization.

---

# Generated Project Document Structure

The AI agent must use the following structure when generating the project-specific `narrative_overview.md`.

## 2. Document Information

| Field | Value |
|---|---|
| Document Title | Narrative Overview |
| Project | [Project name] |
| Document ID | [Document identifier, if used] |
| Version | 1.0 |
| Status | Draft |
| Author | [Author or AI-assisted] |
| Narrative Owner | [Responsible person] |
| Created Date | [YYYY-MM-DD] |
| Last Updated | [YYYY-MM-DD] |
| Related Documents | [Links to relevant project documents] |

### 2.1 Document Purpose

Explain that this document establishes the high-level narrative direction of the game.

Describe its role as a shared reference for:

- Narrative design.
- Game design.
- Character development.
- Worldbuilding.
- Quest and mission design.
- Dialogue and environmental storytelling.
- Level design.
- Art and audio direction.
- AI-assisted content generation.

### 2.2 Scope

Define what this document covers and what it intentionally leaves to other specifications.

**Included:**
- Narrative premise and identity.
- Setting and world context.
- Themes and tone.
- Main characters and narrative roles.
- Central conflict.
- High-level story structure.
- Narrative and gameplay integration.
- Narrative constraints and unresolved questions.

**Excluded:**
- Complete dialogue scripts.
- Detailed character biographies.
- Individual quest and mission specifications.
- Detailed location descriptions.
- Full historical timelines.
- Cinematic scripts and storyboards.
- Technical narrative implementation.

Reference dedicated documents when these details exist.

---

## 3. Narrative Identity

### 3.1 Narrative Summary

Provide a concise overview of the game's narrative.

Explain:

- What the story is about.
- Who or what the story follows.
- Where the story takes place.
- What central situation drives the narrative.
- What makes the narrative distinctive.
- What the player should understand about the experience.

This section should communicate the narrative identity without revealing every major plot event.

### 3.2 Narrative Premise

Describe the fundamental situation from which the story emerges.

Include:

- Initial world condition.
- Protagonist's situation.
- Inciting circumstances, if established.
- Central problem or opportunity.
- Main source of tension.
- Why the situation matters.

### 3.3 High Concept

Summarize the narrative in one or two sentences.

The high concept should communicate the protagonist, setting, and central narrative conflict.

### 3.4 Narrative Hooks

Identify the elements that make the story interesting and distinguishable.

| Hook | Description | Narrative Purpose |
|---|---|---|
| [Hook] | [Description] | [Purpose] |

### 3.5 Narrative Identity and Game Pillars

Explain how the narrative supports the game's core pillars.

| Core Pillar | Narrative Contribution | Design Implication |
|---|---|---|
| [Pillar] | [Contribution] | [Implication] |

---

## 4. Themes and Tone

### 4.1 Central Themes

Identify the primary themes explored by the narrative.

| Theme | Description | Narrative Expression |
|---|---|---|
| [Theme] | [Meaning] | [How it appears in the story] |

### 4.2 Supporting Themes

Describe secondary themes that complement the central narrative.

### 4.3 Narrative Questions

Identify the important questions the story explores.

Examples:

- What does the story ask the player to consider?
- What moral or philosophical conflicts emerge?
- What contradictions exist between characters, institutions, or beliefs?
- What tensions drive the narrative?

Do not impose interpretations that contradict the established creative direction.

### 4.4 Narrative Tone

Describe the intended emotional and stylistic tone.

| Aspect | Description |
|---|---|
| Primary Tone | [Primary tone] |
| Secondary Tones | [Additional tones] |
| Emotional Intensity | [Description] |
| Humor | [Role and frequency, if applicable] |
| Seriousness | [Description] |
| Violence / Mature Content | [Relevant direction] |
| Emotional Boundaries | [Content the narrative should avoid or handle carefully] |

### 4.5 Tone Consistency

Explain how the narrative maintains a coherent tone across:

- Main story.
- Character interactions.
- Dialogue.
- Environmental storytelling.
- Gameplay events.
- Optional content.
- Endings.

### 4.6 Themes and Tone Boundaries

Define what the narrative should and should not communicate.

**Should emphasize:**
- [Element]
- [Element]

**Should avoid:**
- [Element]
- [Element]

---

## 5. World and Setting Overview

### 5.1 Setting Summary

Describe the world in which the game takes place.

Include only information relevant to understanding the narrative.

- Geographic or physical setting.
- Historical or chronological context.
- Social and cultural context.
- Political or institutional context.
- Technological or supernatural context, if applicable.
- Environmental conditions.
- Relevant historical events.

### 5.2 World State

Describe the world's condition at the beginning of the story.

Explain:

- What is considered normal.
- What is unstable or changing.
- What major problems exist.
- What forces influence the world.
- What circumstances affect the protagonist.

### 5.3 Important Locations

| Location | Description | Narrative Significance |
|---|---|---|
| [Location] | [Description] | [Significance] |

Detailed location specifications should remain in dedicated worldbuilding or level design documents.

### 5.4 Factions and Organizations

| Faction | Description | Goals | Relationship to the Story |
|---|---|---|---|
| [Faction] | [Description] | [Goals] | [Role] |

Include only established or approved factions.

### 5.5 World Rules

Document the rules that directly influence the narrative.

Examples:

- Historical constraints.
- Social structures.
- Political relationships.
- Cultural practices.
- Technological limitations.
- Supernatural rules.
- Environmental conditions.

These rules must remain consistent across narrative content.

### 5.6 Historical Context

Summarize the historical events necessary to understand the current narrative situation.

| Event / Period | Description | Narrative Relevance |
|---|---|---|
| [Event] | [Description] | [Relevance] |

Link to a dedicated timeline or history document if one exists.

---

## 6. Main Characters and Narrative Roles

### 6.1 Protagonist

Provide a high-level description of the main playable character or central narrative perspective.

| Property | Description |
|---|---|
| Name | [Name or TBD] |
| Narrative Role | [Protagonist, ensemble member, etc.] |
| Background | [Summary] |
| Initial Situation | [Situation] |
| Motivation | [Motivation] |
| Primary Goal | [Goal] |
| Main Conflict | [Conflict] |
| Character Development | [Expected direction] |

Explain the protagonist's relationship with the world and central narrative conflict.

### 6.2 Supporting Characters

| Character | Narrative Role | Relationship to Protagonist | Main Contribution |
|---|---|---|---|
| [Character] | [Role] | [Relationship] | [Contribution] |

### 6.3 Antagonistic Forces

Describe the primary opposition to the protagonist.

This does not necessarily need to be an individual villain. It may be an institution, environment, social structure, ideology, natural force, or internal conflict.

| Antagonistic Force | Motivation / Cause | Conflict with Protagonist |
|---|---|---|
| [Force] | [Description] | [Conflict] |

### 6.4 Character Relationships

Summarize important relationships and their narrative significance.

### 6.5 Character Development

Describe the high-level direction of important character changes.

Avoid inventing detailed character arcs when they have not been established.

Reference individual character documents for detailed personalities, histories, dialogue, and progression.

---

## 7. Central Conflict and Narrative Stakes

### 7.1 Central Conflict

Explain the main conflict that drives the story.

Include:

- What is in conflict.
- Who or what is involved.
- Why the conflict exists.
- What prevents an easy resolution.
- What makes the conflict meaningful.

### 7.2 Conflict Dimensions

| Conflict Type | Description | Narrative Role |
|---|---|---|
| External | [External opposition] | [Role] |
| Internal | [Personal struggle] | [Role] |
| Social / Political | [Broader conflict] | [Role] |
| Environmental | [Environmental conflict] | [Role] |
| Ideological | [Competing beliefs] | [Role] |

Include only applicable categories.

### 7.3 Stakes

Explain what can be gained, lost, changed, or protected.

- Personal stakes.
- Interpersonal stakes.
- Community or social stakes.
- World-level stakes, if applicable.

### 7.4 Sources of Narrative Tension

Describe what creates uncertainty, conflict, suspense, or emotional investment.

---

## 8. Story Structure and Progression

### 8.1 Narrative Structure Overview

Describe the intended high-level structure.

Identify the major narrative stages and how they relate to one another.

The structure may be linear, branching, episodic, emergent, environmental, or a combination.

### 8.2 Major Story Phases

| Phase | Narrative Purpose | Main Events | Player Context |
|---|---|---|---|
| Beginning | [Purpose] | [Established events] | [Context] |
| Development | [Purpose] | [Established events] | [Context] |
| Escalation | [Purpose] | [Established events] | [Context] |
| Climax | [Purpose] | [Established events] | [Context] |
| Resolution | [Purpose] | [Established events] | [Context] |

If specific events are not established, describe the intended narrative function rather than inventing events.

### 8.3 Inciting Incident

Describe the event or circumstance that initiates the central narrative, if applicable.

### 8.4 Major Turning Points

Identify established turning points and explain their consequences.

| Turning Point | Narrative Change | Consequence |
|---|---|---|
| [Event] | [Change] | [Consequence] |

### 8.5 Climax and Resolution

Describe the intended narrative function of the climax and resolution.

If the actual events or ending are undecided, identify them as unresolved rather than inventing a definitive outcome.

### 8.6 Narrative Pacing

Describe how narrative intensity and information are distributed throughout the experience.

Consider:

- Story progression.
- Character development.
- Discovery and revelation.
- Dialogue frequency.
- Gameplay and narrative balance.
- Quiet and intense moments.
- Optional narrative content.

### 8.7 Branching and Player Choice

If applicable, explain:

- Which decisions the player can make.
- What types of consequences are possible.
- Whether choices affect characters, relationships, world state, or endings.
- Whether choices are reversible.
- How the game communicates consequences.

Detailed branching logic should be documented separately.

---

## 9. Narrative and Gameplay Integration

### 9.1 Narrative Role in Gameplay

Explain how the narrative supports and is supported by the game's core gameplay loop.

Describe:

- How gameplay advances the story.
- How narrative context gives meaning to player actions.
- How mechanics reinforce narrative themes.
- How player progression relates to narrative progression.
- How the world communicates story information during gameplay.

### 9.2 Narrative Delivery Methods

| Delivery Method | Purpose | Intended Use |
|---|---|---|
| Environmental storytelling | [Purpose] | [Use] |
| Dialogue | [Purpose] | [Use] |
| Gameplay events | [Purpose] | [Use] |
| Cinematics | [Purpose] | [Use] |
| Documents / Collectibles | [Purpose] | [Use] |
| Character interactions | [Purpose] | [Use] |

Include only methods appropriate to the game.

### 9.3 Player Agency

Explain the player's influence on the narrative.

Distinguish between:

- Direct narrative choices.
- Gameplay-driven consequences.
- Exploration-based discoveries.
- Character relationship changes.
- Fixed narrative events.

### 9.4 Narrative and Mechanical Consistency

Explain how the narrative remains consistent with what the player can actually do.

Avoid narrative promises that gameplay systems cannot support.

### 9.5 Optional Narrative Content

Describe how optional content contributes to the world, characters, themes, and player understanding.

### 9.6 Narrative Restrictions

Identify actions, mechanics, or gameplay outcomes that could contradict established narrative rules.

---

## 10. Story Information and Revelation

### 10.1 Information the Player Should Know

Identify the information necessary for understanding the main narrative.

### 10.2 Information the Player Discovers

Describe important information revealed through progression and exploration.

| Information | Discovery Method | Intended Timing | Narrative Importance |
|---|---|---|---|
| [Information] | [Method] | [Stage / condition] | [Importance] |

### 10.3 Mysteries and Unanswered Questions

Identify intentional mysteries and unresolved narrative questions.

Distinguish between:
- Questions intentionally left unanswered.
- Questions answered later.
- Questions left to player interpretation.
- Questions not yet decided by the design team.

### 10.4 Spoiler Management

When the project requires spoiler-sensitive documentation, classify major narrative information:

- **Public:** Information the player can know early.
- **Progressive:** Information revealed through normal progression.
- **Restricted:** Major revelations, twists, or endings.

Use appropriate spoiler warnings when documenting restricted information.

---

## 11. Narrative Content and Scope

### 11.1 Required Narrative Content

| Content | Purpose | Status | Related Document |
|---|---|---|---|
| [Content] | [Purpose] | [Confirmed / Proposed / Undecided] | [Reference] |

### 11.2 Optional Narrative Content

Identify narrative content that enriches the experience but is not required for understanding the main story.

### 11.3 Narrative Scope Boundaries

Define what is included in the current game's narrative scope and what is intentionally excluded.

### 11.4 Narrative Production Dependencies

Identify dependencies such as:

- Character designs.
- Environment and location designs.
- Quest and mission specifications.
- Dialogue production.
- Cinematics.
- Voice acting.
- Audio direction.
- Gameplay mechanics.
- Localization.

---

## 12. Narrative Consistency and Continuity

### 12.1 Canonical Facts

Summarize the important established facts that other documents and AI agents must preserve.

| ID | Canonical Fact | Source | Notes |
|---|---|---|---|
| CANON-01 | [Fact] | [Approved document] | [Notes] |
| CANON-02 | [Fact] | [Approved document] | [Notes] |

### 12.2 Continuity Rules

Define important consistency requirements.

Examples:

- Character relationships must remain consistent.
- Historical events must not contradict the established timeline.
- Locations must follow established world rules.
- Character motivations must remain coherent.
- Narrative consequences must reflect previously established events.

### 12.3 Terminology

| Term | Definition | Usage Notes |
|---|---|---|
| [Term] | [Definition] | [Notes] |

### 12.4 Known Continuity Risks

Identify contradictions, incomplete information, or narrative dependencies that may cause future inconsistencies.

---

## 13. Narrative Experience and Evaluation

### 13.1 Intended Player Experience

Describe the desired emotional and intellectual experience.

### 13.2 Narrative Success Criteria

| ID | Criterion | Expected Evidence |
|---|---|---|
| NARR-01 | [Criterion] | [Evidence] |
| NARR-02 | [Criterion] | [Evidence] |

### 13.3 Evaluation Questions

- Is the central premise understandable?
- Are character motivations coherent?
- Does the central conflict provide sufficient narrative interest?
- Are themes reflected in story and gameplay?
- Is narrative information delivered at appropriate times?
- Does the narrative respect the game's core pillars?
- Are important events consistent with established world rules?
- Does the narrative scope match the production capacity?

### 13.4 Narrative Validation

Describe how the narrative will be evaluated through:

- Design reviews.
- Story walkthroughs.
- Prototype testing.
- Playtesting.
- Dialogue and character reviews.
- Continuity reviews.
- Player feedback.

Do not treat subjective narrative preferences as objective facts. Record feedback and the reasoning behind approved changes.

---

## 14. Open Questions and Unresolved Decisions

Record narrative decisions that still require clarification.

| ID | Question / Decision | Impact | Current Understanding | Owner / Next Action |
|---|---|---|---|---|
| OPEN-01 | [Question] | [Impact] | [Known information] | [Action] |
| OPEN-02 | [Question] | [Impact] | [Known information] | [Action] |

For each unresolved issue:

- Explain why it matters.
- Identify affected documents or systems.
- Distinguish required decisions from optional improvements.
- Avoid inventing an answer to make the document appear complete.

---

## 15. Narrative Document References

List the project documents that provide additional narrative detail.

| Document | Purpose | Relationship |
|---|---|---|
| [Game Vision] | Establishes creative direction | Primary reference |
| [Game Design Document] | Defines overall game design | Supporting reference |
| [Core Pillars] | Defines design commitments | Supporting reference |
| [Character Documents] | Defines individual characters | Detailed reference |
| [Worldbuilding Documents] | Defines setting and history | Detailed reference |
| [Quest Documents] | Defines individual quests | Detailed reference |
| [Dialogue Documents] | Defines dialogue content | Detailed reference |

Only include documents that exist in the project.

---

## 16. AI Usage and Narrative Generation Constraints

### 16.1 Narrative Source of Truth

This document and its approved source documents define the established narrative direction.

AI agents must consult these sources before generating:

- Character descriptions.
- Dialogue.
- Quest narratives.
- Mission descriptions.
- Environmental storytelling.
- Historical events.
- Locations and factions.
- Narrative collectibles.
- Cinematic scripts.
- Narrative branches and endings.

### 16.2 Generation Constraints

AI agents MUST:

1. Preserve established canon.
2. Maintain character motivation and personality consistency.
3. Respect established historical, cultural, geographical, and world rules.
4. Preserve the intended tone and themes.
5. Avoid introducing unsupported narrative facts.
6. Avoid creating contradictions with existing documents.
7. Identify assumptions and proposed ideas.
8. Avoid treating generated content as approved canon.
9. Reference the source of important narrative facts when practical.
10. Request clarification when missing information materially affects the generated content.

### 16.3 Narrative Expansion

When asked to expand the narrative:

- Prefer developing established ideas over introducing unrelated concepts.
- Preserve the intended narrative identity.
- Explain significant additions and their implications.
- Identify affected documents.
- Keep proposed additions separate from confirmed information.
- Obtain project owner approval before treating major additions as canon.

### 16.4 Document Maintenance

When approved narrative decisions change:

- Update this overview where necessary.
- Update affected detailed specifications.
- Identify outdated or contradictory references.
- Preserve historical decisions where appropriate.
- Do not overwrite approved narrative decisions without authorization.

---

## 17. Approval and Change History

### 17.1 Review Status

| Review Area | Reviewer | Status | Date |
|---|---|---|---|
| Narrative Consistency | [Name] | [Pending / Approved] | [Date] |
| Game Design Consistency | [Name] | [Pending / Approved] | [Date] |
| Project Owner Approval | [Name] | [Pending / Approved] | [Date] |

### 17.2 Change History

| Version | Date | Author | Description |
|---|---|---|---|
| 1.0 | [YYYY-MM-DD] | [Author] | Initial narrative overview |

### 17.3 Final Approval

**Approval Status:** [Draft / In Review / Approved]

**Approved By:** [Project owner]

**Approval Date:** [YYYY-MM-DD]

**Notes:** [Relevant approval comments]

---

**End of Narrative Overview**
