# Playtesting Guidelines

## 1. Purpose

This document establishes guidelines for planning, conducting, documenting, and evaluating playtesting activities throughout game development.

Playtesting is the process of observing people playing a game to understand how they experience its mechanics, systems, content, controls, difficulty, progression, and overall design.

The objectives are to:

- Evaluate whether gameplay delivers the intended player experience.
- Identify usability problems and confusing interactions.
- Understand how players interpret game rules and feedback.
- Evaluate difficulty, pacing, and progression.
- Identify unexpected player behavior.
- Discover gameplay problems that conventional testing may not reveal.
- Gather evidence to guide design improvements.
- Validate design assumptions before committing to significant development work.

Playtesting SHOULD be integrated throughout development rather than reserved exclusively for the final stages.

## 2. Scope

These guidelines apply to playtesting activities involving:

- Gameplay mechanics.
- Core gameplay loops.
- Controls and input.
- Combat and interaction systems.
- Level and environment design.
- Difficulty and challenge.
- Progression and rewards.
- Game economy.
- User interface and usability.
- Narrative and dialogue.
- Tutorials and onboarding.
- Accessibility.
- Audio and visual feedback.
- Overall player experience.

Playtesting MAY involve:

- The project owner.
- Internal testers.
- External playtesters.
- Target audience representatives.
- Friends or community members.
- Specialized usability testers.

These guidelines apply to prototypes, vertical slices, production builds, alpha versions, beta versions, and post-release updates.

## 3. Playtesting Principles

### 3.1. Player-Centered Evaluation

Playtesting MUST focus on the actual player experience rather than only the developer's intended experience.

A feature that works technically may still be confusing, frustrating, uninteresting, or difficult to understand.

### 3.2. Observe Before Explaining

During evaluation sessions, testers SHOULD be allowed to interact with the game without unnecessary instructions or intervention.

Observe what players naturally understand, attempt, avoid, and struggle with.

Do not immediately explain intended mechanics when the objective is to evaluate whether those mechanics communicate themselves effectively.

### 3.3. Evidence Over Assumptions

Design decisions SHOULD be informed by observed behavior, player feedback, and relevant measurements.

Individual opinions are useful, but they SHOULD NOT automatically be treated as representative of the entire target audience.

### 3.4. Iterative Improvement

Playtesting SHOULD be conducted repeatedly as the game evolves.

Findings SHOULD lead to specific design questions, experiments, improvements, or documented decisions.

### 3.5. Appropriate Testing Context

The testing environment SHOULD resemble the intended player experience as closely as practical.

Unnecessary interruptions, unclear instructions, unsuitable hardware, or artificial testing conditions can distort results.

### 3.6. Proportionality

The complexity of a playtesting activity SHOULD match the importance and uncertainty of the design decision being evaluated.

A small mechanic prototype may require only a few focused sessions. A major gameplay redesign may justify more structured testing.

### 3.7. Respect for Participants

Participants MUST be treated respectfully.

Their feedback SHOULD be collected without pressure, manipulation, or judgment.

## 4. Playtesting Objectives

Every structured playtesting activity SHOULD have a clear objective.

Possible objectives include:

### 4.1. Gameplay Validation

Determine whether a gameplay mechanic or system behaves as intended from the player's perspective.

Examples:

- Can players understand how to perform the mechanic?
- Does the mechanic produce meaningful decisions?
- Does it provide appropriate feedback?
- Does it interact correctly with other gameplay systems?
- Does it remain interesting after repeated use?

### 4.2. Usability Evaluation

Identify difficulties interacting with the game.

Examples:

- Can players navigate the menus?
- Are controls discoverable?
- Is important information easy to understand?
- Can players identify available actions?
- Are interaction prompts clear?

### 4.3. Difficulty Evaluation

Understand whether gameplay challenge is appropriate.

Examples:

- Can players recognize why they failed?
- Does difficulty increase at a reasonable pace?
- Are encounters perceived as fair?
- Do players have enough information and resources?
- Are challenge spikes intentional?

### 4.4. Progression Evaluation

Determine whether players understand and value progression.

Examples:

- Are rewards meaningful?
- Do players understand progression requirements?
- Does the game provide a sense of advancement?
- Are upgrades understandable?
- Does progression encourage continued engagement?

### 4.5. Player Experience Evaluation

Understand the emotions and experiences produced by the game.

Examples:

- Does the intended atmosphere come across?
- Are players engaged?
- Do important moments feel satisfying?
- Does pacing support the intended experience?
- Are players motivated to continue?

### 4.6. Design Assumption Validation

Test assumptions before investing significant development effort.

Examples:

- Players understand the intended core loop.
- A particular mechanic is enjoyable.
- A level communicates its objective.
- A reward motivates the intended behavior.
- A tutorial teaches a mechanic effectively.

## 5. Types of Playtesting

Different playtesting approaches serve different purposes.

### 5.1. Informal Playtesting

Informal playtesting involves observing gameplay without a highly structured test plan.

It is useful for:

- Early prototypes.
- Experimental mechanics.
- Frequent design iterations.
- Identifying obvious usability issues.
- Gathering initial reactions.

Informal testing MAY be conducted by the project owner or a small number of participants.

Observations SHOULD still be documented when they influence design decisions.

### 5.2. Structured Playtesting

Structured playtesting uses predefined objectives, scenarios, tasks, and evaluation questions.

It is useful for:

- Evaluating important gameplay features.
- Comparing design alternatives.
- Validating progression.
- Evaluating difficulty.
- Measuring usability.
- Preparing for milestone reviews.

Structured sessions SHOULD include a playtesting plan and a documented summary.

### 5.3. Exploratory Playtesting

Exploratory playtesting allows participants to interact with the game freely.

It is useful for discovering:

- Unexpected player strategies.
- Unintended interactions.
- Hidden usability problems.
- Emergent gameplay.
- Exploits.
- Unanticipated interpretations of game mechanics.

Exploratory sessions SHOULD avoid excessive instructions that restrict natural player behavior.

### 5.4. Comparative Playtesting

Comparative playtesting evaluates different implementations or design alternatives.

Examples:

- Comparing two control schemes.
- Comparing alternative level layouts.
- Comparing different difficulty settings.
- Comparing reward structures.
- Comparing tutorial approaches.

Comparisons SHOULD use sufficiently similar conditions to make the results meaningful.

### 5.5. Remote Playtesting

Remote playtesting allows participants to test the game independently or through a remote observation session.

It is useful when participants cannot attend in person.

Remote sessions SHOULD account for:

- Different hardware configurations.
- Input devices.
- Screen resolutions.
- Network conditions, when relevant.
- Recording and communication limitations.
- Participant instructions and support.

### 5.6. Internal and External Playtesting

Internal playtesting is conducted by the project owner, developers, or collaborators.

External playtesting involves participants who are not directly responsible for developing the game.

External playtesting is particularly valuable because external participants are less likely to understand undocumented design assumptions or automatically interpret unclear mechanics correctly.

Internal testing MUST NOT be treated as a complete substitute for external player feedback when external evaluation is feasible.

## 6. Playtesting Planning

### 6.1. Define the Objective

Before a structured session, identify the question the session should answer.

Good objectives are specific.

Examples:

- Determine whether new players can complete the first combat encounter without assistance.
- Evaluate whether players understand how inventory capacity works.
- Determine whether the current boss encounter is perceived as fair.
- Identify where players become confused during the tutorial.

Avoid objectives that are too broad, such as "find out whether the game is fun."

Broad objectives SHOULD be divided into more specific evaluation questions.

### 6.2. Define the Scope

Specify what will be tested.

The scope MAY include:

- A particular feature.
- A gameplay sequence.
- A level.
- A progression segment.
- A prototype.
- A complete play session.

Clearly identify what is outside the evaluation scope.

### 6.3. Identify the Target Participants

Select participants according to the objective.

Relevant characteristics MAY include:

- Familiarity with the game genre.
- Previous gaming experience.
- Familiarity with similar mechanics.
- Experience with the intended platform.
- Familiarity with the control scheme.
- Accessibility requirements relevant to the evaluation.

Participants SHOULD represent the intended audience when practical.

Do not assume that a single participant's experience represents all players.

### 6.4. Prepare the Build

Before a session:

- Verify that the build launches correctly.
- Confirm that the intended content is available.
- Check required controls and input devices.
- Confirm that the test scenario can be reached.
- Prepare suitable save data or starting conditions.
- Check that known technical issues will not invalidate the session.
- Record the tested game version and build.

Known issues that could influence observations SHOULD be documented before testing.

When the project has no exportable build yet, the game MAY be run from the editor for a playtesting session. The session record MUST state that it was run from the editor rather than from a build (section 15.1).

### 6.5. Prepare Materials

Depending on the session, prepare:

- Playtesting plan.
- Participant instructions.
- Gameplay scenarios.
- Observation checklist.
- Feedback questions.
- Note-taking template.
- Recording equipment.
- Relevant test data.
- Consent information when recording or collecting personal information.

Preparation SHOULD be proportional to the session's complexity.

## 7. Participant Selection

### 7.1. Participant Suitability

Participants SHOULD be selected according to the testing objective rather than convenience alone.

Examples:

- Beginner players for onboarding evaluation.
- Experienced players for advanced combat evaluation.
- Genre enthusiasts for mechanics familiar to the target audience.
- Players unfamiliar with the genre for discoverability evaluation.

### 7.2. Participant Diversity

When practical, include participants with different levels of experience and different approaches to gameplay.

Different participants may reveal different problems.

Consider relevant differences in:

- Gaming experience.
- Genre familiarity.
- Input preferences.
- Accessibility needs.
- Play styles.
- Platform familiarity.

### 7.3. Sample Size

The number of participants SHOULD reflect the purpose of the evaluation.

Small sessions can reveal significant usability and gameplay problems, especially during iterative development.

However, a small sample MUST NOT be presented as statistically representative of a larger population.

Use additional participants when:

- Comparing alternatives.
- Investigating inconsistent observations.
- Evaluating audience preferences.
- Supporting decisions that require stronger evidence.

There is no universal participant count suitable for every playtesting activity.

### 7.4. Reduced-Participant and Self-Playtesting

External participants are not always available, and early work may not yet produce a playable build for them. In that situation, the project owner MAY evaluate the game as the sole player (self-playtesting) or with a very small number of internal participants (reduced-participant playtesting).

These modes are legitimate sources of evidence, but they are weaker than external playtesting:

- The developer knows the intended design and is likely to underestimate unclear mechanics, hidden assumptions, and difficulty.
- One participant cannot reveal disagreement between different play styles or experience levels.

Self-playtesting SHOULD therefore be structured to reduce that bias where practical:

- State the objective and the intended behavior before playing, and record them before the outcome is known.
- Follow the scenario without using developer knowledge or debug tooling that a player would not have.
- Record observable evidence — what was attempted, what happened, and how long or how many attempts it took — rather than impressions alone.
- Identify observations that depend on knowledge a player would not have.

Findings MUST be disclosed as self-playtesting or reduced-participant testing. They MUST NOT be presented as external player feedback, as representative of the target audience, or as validation of player comprehension, difficulty, pacing, or enjoyment.

The playtesting record MUST identify the session as self-playtesting or reduced-participant testing and state how many participants took part (section 15.1).

When external evaluation becomes feasible, findings that depend on player comprehension, difficulty, pacing, or enjoyment SHOULD be re-examined before they are treated as established.

## 8. Conducting a Playtesting Session

### 8.1. Introduction

At the beginning of a session:

- Explain the purpose of the session.
- Explain the expected duration.
- Describe any relevant controls or starting conditions.
- Clarify whether participants should think aloud.
- Explain how feedback and observations will be collected.
- Confirm that participation is voluntary.

Do not reveal solutions or intended behavior when doing so would invalidate the evaluation.

### 8.2. Establish the Starting Conditions

Ensure participants begin from the intended state.

Record relevant conditions, including:

- Game version.
- Starting level or scene.
- Character state.
- Available resources.
- Difficulty setting.
- Control configuration.
- Relevant progression state.

### 8.3. Observe Player Behavior

During gameplay, observe:

- Actions and decisions.
- Interaction patterns.
- Hesitation.
- Repeated failed attempts.
- Unexpected strategies.
- Confusion.
- Navigation choices.
- Responses to feedback.
- Reactions to success and failure.
- Attempts to use unsupported interactions.

Record what participants actually do rather than assuming what they are thinking.

### 8.4. Avoid Unnecessary Intervention

The observer SHOULD avoid guiding participants unless assistance is necessary.

If assistance is provided, document:

- What assistance was given.
- Why it was necessary.
- Whether it influenced subsequent behavior.

Intervention MAY be appropriate when:

- A technical problem prevents further testing.
- The participant becomes unable to continue.
- The session requires clarification of a non-evaluated instruction.
- Safety or accessibility considerations require assistance.

### 8.5. Encourage Natural Feedback

Participants MAY be encouraged to explain their thoughts while playing.

Useful prompts include:

- What do you think this interaction does?
- What are you trying to accomplish?
- What do you expect to happen?
- What information are you looking for?
- What made this action difficult?
- What would you try next?

Questions SHOULD be neutral and MUST NOT lead participants toward a preferred answer.

### 8.6. Avoid Leading Questions

Avoid questions that suggest a desired response.

Weak:

"Wasn't that boss fight too difficult?"

Better:

"How would you describe the difficulty of that encounter?"

Weak:

"Did you like the new inventory system?"

Better:

"How did you find using the inventory system?"

### 8.7. End the Session

At the end:

- Ask for general impressions.
- Collect unresolved feedback.
- Ask about particularly confusing or enjoyable moments.
- Record any final observations.
- Thank the participant.
- Explain any relevant next steps.

Do not argue with participants about their feedback or attempt to justify every design decision.

## 9. Observation and Data Collection

Playtesting SHOULD collect evidence appropriate to its objective.

### 9.1. Qualitative Data

Qualitative data describes player experiences, reactions, and behavior.

Examples:

- Player comments.
- Observed confusion.
- Reactions to difficulty.
- Perceived clarity.
- Unexpected strategies.
- Frustration or satisfaction.
- Suggestions for improvement.

Qualitative observations SHOULD distinguish direct observations from interpretations.

### 9.2. Quantitative Data

Quantitative data provides measurable information about gameplay.

Examples:

- Time required to complete a level.
- Number of failed attempts.
- Number of deaths.
- Number of incorrect interactions.
- Percentage of participants completing a task.
- Time spent in menus.
- Frequency of specific actions.
- Number of hints requested.
- Resources consumed during an encounter.

Metrics SHOULD be selected according to the testing objective.

Do not collect metrics merely because they are easy to measure.

### 9.3. Behavioral Evidence

Behavioral evidence is particularly useful because player actions may differ from what participants report afterward.

Examples:

- Repeatedly attempting an incorrect interaction.
- Ignoring an important interface element.
- Moving toward an unintended location.
- Avoiding a mechanic.
- Repeating an ineffective strategy.
- Failing to recognize available resources.

### 9.4. Player Feedback

Feedback SHOULD be recorded as accurately as practical.

When summarizing comments:

- Preserve the intended meaning.
- Avoid removing important context.
- Distinguish direct quotations from paraphrases.
- Do not interpret an opinion as an objective fact.

### 9.5. Privacy and Recording

Before recording sessions or collecting personal information:

- Explain what information will be collected.
- Obtain appropriate consent.
- Collect only information necessary for the evaluation.
- Restrict access to recordings and participant information.
- Define an appropriate retention period.
- Avoid including sensitive personal information in project documentation.

Recording SHOULD NOT be required when it is unnecessary for the evaluation.

## 10. Evaluating Playtesting Results

### 10.1. Organize Findings

After a session, group observations into meaningful categories.

Suggested categories:

- Usability.
- Controls and input.
- Gameplay mechanics.
- Difficulty.
- Progression.
- Level design.
- UI/UX.
- Narrative.
- Performance.
- Bugs.
- Player enjoyment.
- Accessibility.

A single observation MAY belong to multiple categories.

### 10.2. Identify Patterns

Look for recurring problems and consistent player behavior.

Examples:

- Multiple participants misunderstand the same interaction.
- Players consistently miss an important objective.
- Several participants stop progressing at the same encounter.
- Players repeatedly ignore a particular upgrade.
- A control causes difficulty across multiple sessions.

Repeated observations SHOULD receive greater attention, but a single observation may still reveal a serious defect.

### 10.3. Distinguish Symptoms from Causes

A player struggling with an encounter is an observation, not necessarily an explanation.

Possible causes include:

- Unclear enemy telegraphs.
- Poor camera positioning.
- Unresponsive controls.
- Insufficient player resources.
- Inadequate onboarding.
- Unexpected difficulty scaling.

Investigate the underlying cause before choosing a solution.

### 10.4. Evaluate Against Objectives

Compare the findings with the original playtesting objectives.

Determine:

- Which questions were answered?
- Which assumptions were supported?
- Which assumptions were challenged?
- Which problems were discovered?
- Which questions remain unresolved?
- What additional testing is necessary?

### 10.5. Avoid Overgeneralization

A participant's preference SHOULD NOT automatically become a universal design requirement.

Consider:

- Participant background.
- Testing conditions.
- Number of observations.
- Consistency of feedback.
- Intended target audience.
- The game's design goals.

Conflicting feedback is valuable and SHOULD be investigated rather than ignored.

## 11. Finding Classification and Prioritization

Playtesting findings SHOULD be classified according to their nature.

| Classification | Description |
|---|---|
| Bug | Unexpected behavior that violates expected or approved functionality. |
| Usability Issue | Players struggle to understand or interact with the game. |
| Design Issue | A mechanic or design decision does not produce the intended experience. |
| Balance Issue | Difficulty, resources, or rewards are incorrectly tuned. |
| Content Issue | Art, audio, narrative, or gameplay content needs correction. |
| Performance Issue | The game does not meet relevant performance expectations. |
| Feature Suggestion | A participant proposes additional functionality. |
| Positive Finding | A successful design element or behavior worth preserving. |

### 11.1. Prioritization Factors

Evaluate findings based on:

- Impact on player experience.
- Frequency of occurrence.
- Number of affected players.
- Severity of the problem.
- Importance of the affected feature.
- Effect on progression.
- Availability of workarounds.
- Cost and risk of correction.
- Relevance to the current milestone or release.

### 11.2. Positive Findings

Playtesting SHOULD also identify what works well.

Examples:

- A mechanic is immediately understood.
- Players enjoy a particular encounter.
- A reward creates meaningful motivation.
- A level encourages exploration.
- A tutorial successfully teaches a mechanic.

Positive findings help prevent unnecessary changes to successful design elements.

## 12. From Findings to Actionable Work

Playtesting findings SHOULD be translated into actionable decisions when appropriate.

Possible outcomes include:

- Create a bug report.
- Create a backlog item.
- Update acceptance criteria.
- Revise a design specification.
- Adjust gameplay balancing.
- Improve onboarding.
- Conduct additional research.
- Run another playtesting session.
- Accept the current behavior.
- Defer the proposed change.
- Make no change.

### 12.1. Defect Reports

Technical defects discovered during playtesting MUST be documented according to the bug reporting guidelines.

A subjective complaint SHOULD NOT automatically be classified as a software defect.

### 12.2. Backlog Items

Design improvements and feature requests SHOULD be added to the project backlog when they require planned work.

Each actionable item SHOULD have:

- A clear objective.
- A description of the finding.
- Relevant evidence.
- Expected outcome.
- Appropriate priority.
- Related playtesting session or observation.

### 12.3. Design Changes

Significant changes to approved gameplay or product design MUST follow the project's decision-making and documentation processes.

Playtesting feedback provides evidence for design decisions; it does not automatically authorize changes to approved scope.

### 12.4. Re-testing

When a change is made in response to playtesting, consider whether another session is necessary.

Re-testing is particularly important when:

- The change affects core gameplay.
- The original problem was observed repeatedly.
- The change introduces new interactions.
- The result depends on player perception.
- The original design assumption remains uncertain.

## 13. Playtesting Across Development Stages

Playtesting activities SHOULD evolve with the project.

### 13.1. Concept Development

Objectives:

- Evaluate the clarity of the game concept.
- Validate core gameplay assumptions.
- Identify potential audience interest.
- Explore alternative mechanics.
- Identify major design risks.

Testing MAY use paper prototypes, mockups, videos, or simple interactive demonstrations.

### 13.2. Prototyping

Objectives:

- Evaluate basic mechanic interactions.
- Test the core gameplay loop.
- Identify control problems.
- Evaluate initial feedback and responsiveness.
- Discover unexpected behavior.
- Determine whether a concept is worth further development.

Focus on validating the experience rather than visual polish.

### 13.3. Pre-production

Objectives:

- Validate the proposed core experience.
- Evaluate representative gameplay systems.
- Test important design decisions.
- Identify scope and usability risks.
- Validate the intended player experience.

Vertical slices and representative prototypes are useful at this stage.

### 13.4. Production

Objectives:

- Evaluate newly implemented features.
- Validate interactions between systems.
- Identify gameplay and usability problems.
- Review difficulty and progression.
- Confirm that content supports the intended experience.

Playtesting SHOULD occur incrementally as meaningful features become available.

### 13.5. Alpha

Objectives:

- Evaluate the completeness of the gameplay experience.
- Identify major usability problems.
- Evaluate progression and difficulty.
- Identify missing or confusing content.
- Discover significant integration problems.

Testing SHOULD cover the main gameplay loops and important progression paths.

### 13.6. Beta

Objectives:

- Evaluate overall player experience.
- Identify remaining gameplay and usability problems.
- Validate difficulty and balance.
- Test a broader range of player behavior.
- Evaluate accessibility and onboarding.
- Identify problems that could affect release readiness.

Testing SHOULD involve participants who represent the intended audience when practical.

### 13.7. Release Candidate

Objectives:

- Confirm that the release candidate provides the intended experience.
- Evaluate known issues and remaining risks.
- Verify important player journeys.
- Identify release-blocking usability or gameplay problems.

Only changes justified by release readiness SHOULD be introduced at this stage.

### 13.8. Post-release

Objectives:

- Evaluate player feedback from the released game.
- Identify recurring problems.
- Understand unexpected player behavior.
- Evaluate new content and updates.
- Identify opportunities for improvements.

Post-release feedback SHOULD be evaluated alongside available support reports, telemetry, and defect information.

## 14. Playtesting Metrics

Metrics SHOULD be selected according to the feature and evaluation objective.

Examples include:

| Area | Possible Metrics |
|---|---|
| Onboarding | Tutorial completion rate, hints requested, time to complete |
| Level Design | Completion time, navigation errors, deaths |
| Combat | Encounter completion rate, failed attempts, damage received |
| Progression | Upgrade selection, progression time, resource usage |
| Economy | Resource acquisition, resource spending, shortages |
| UI/UX | Task completion time, incorrect interactions, navigation errors |
| Difficulty | Death frequency, retry count, encounter success rate |
| Engagement | Session duration, voluntary continuation, content exploration |

### 14.1. Metric Interpretation

Metrics MUST be interpreted in context.

For example:

- A high death count does not automatically indicate poor difficulty balance.
- A long session does not automatically indicate strong engagement.
- A low feature usage rate does not automatically mean the feature is unnecessary.
- A high completion rate does not automatically mean a mechanic is understandable.

Combine quantitative results with observed behavior and participant feedback.

### 14.2. Targets and Baselines

Projects MAY define measurable targets for important gameplay experiences.

Targets SHOULD be based on design objectives and relevant testing evidence.

Avoid arbitrary numerical targets that are not connected to player experience or project requirements.

## 15. Playtesting Documentation

Structured playtesting sessions SHOULD produce a record that preserves the objectives, conditions, observations, findings, and decisions.

Recommended storage location within an individual game repository:

`game_project/docs/qa/playtesting/`

Recommended filename format:

`playtest-YYYY-MM-DD-topic.md`

Example:

`playtest-2026-11-14-inventory-usability.md`

### 15.1. Playtesting Record Template

```markdown
# Playtesting Session: [Topic]

## 1. Session Information

- **Session ID:** PLAYTEST-XXX
- **Date:** YYYY-MM-DD
- **Game Version:** X.Y.Z
- **Build:** BUILD-XXXXX
- **Platform:** Windows / Linux / macOS / Other
- **Session Type:** Informal / Structured / Exploratory / Comparative / Remote
- **Session Mode:** Self-playtest / Reduced-participant / External (state the participant count)
- **Facilitator:**
- **Participants:**
- **Duration:**

## 2. Objectives

Describe what the session is intended to evaluate.

## 3. Scope

Describe the features, mechanics, levels, or gameplay scenarios being tested.

## 4. Participant Profile

Describe relevant participant characteristics without including unnecessary personal information.

## 5. Test Environment

- Hardware:
- Input Device:
- Resolution:
- Difficulty:
- Starting State:
- Additional Conditions:

## 6. Scenarios and Tasks

Describe the scenarios or tasks given to participants.

## 7. Observations

| ID | Observation | Evidence | Impact |
|---|---|---|---|
| OBS-01 | Description | Reference | Description |
| OBS-02 | Description | Reference | Description |

## 8. Participant Feedback

Summarize relevant comments and feedback.

Distinguish direct quotations from paraphrased comments.

## 9. Metrics

| Metric | Result | Context |
|---|---|---|
| Metric 1 | Value | Explanation |
| Metric 2 | Value | Explanation |

## 10. Findings

Summarize the most important findings.

## 11. Positive Findings

Describe mechanics, interactions, or experiences that worked well.

## 12. Problems and Recommendations

| Finding ID | Classification | Description | Priority | Recommended Action |
|---|---|---|---|---|
| FIND-01 | Usability Issue | Description | High | Action |

## 13. Related Work Items

- Bug reports:
- Backlog items:
- Design documents:
- Related test cases:

## 14. Conclusions

Summarize what was learned and whether the original objectives were achieved.

## 15. Follow-up Actions

List additional testing, design changes, or investigations required.

## 16. Attachments

List relevant screenshots, recordings, logs, and other evidence.
```

### 15.2. Observation Identifiers

Projects MAY use identifiers such as:

- `PLAYTEST-001` for sessions.
- `OBS-001` for individual observations.
- `FIND-001` for evaluated findings.

Identifiers SHOULD remain traceable to the session in which they were recorded.

## 16. AI-Assisted Playtesting

AI agents MAY assist with:

- Preparing playtesting plans.
- Suggesting evaluation scenarios.
- Reviewing playtesting objectives.
- Organizing observations.
- Summarizing participant feedback.
- Identifying recurring patterns.
- Suggesting additional evaluation questions.
- Classifying findings.
- Drafting bug reports and backlog items.
- Comparing findings across documented sessions.
- Identifying gaps in evaluation coverage.

AI agents MUST:

1. Use actual playtesting observations and evidence.
2. Distinguish participant feedback from observer interpretation.
3. Distinguish individual opinions from recurring patterns.
4. Preserve important context when summarizing findings.
5. Identify uncertainty and limitations.
6. Avoid inventing participant responses or metrics.
7. Avoid treating subjective feedback as objective fact.
8. Reference relevant sessions and findings when available.
9. Request human review before significant design changes.
10. Report conclusions proportionally to the available evidence.

AI agents MUST NOT:

- Claim to have conducted human playtesting when they have not.
- Fabricate participant behavior or feedback.
- Present simulated player behavior as real participant evidence.
- Modify approved game design decisions without authorization.
- Treat automated gameplay validation as a complete replacement for human playtesting.
- Publish participant information without appropriate authorization.

AI-generated analysis SHOULD be treated as supporting evidence rather than a substitute for human interpretation.

The project owner retains final authority over design decisions and acceptance of playtesting findings.

## 17. Playtesting Checklist

### Preparation

- [ ] Playtesting objectives are defined.
- [ ] Scope and evaluation questions are clear.
- [ ] Participants are appropriate for the objective.
- [ ] The game build is prepared and identified.
- [ ] Starting conditions are established.
- [ ] Relevant materials and equipment are ready.
- [ ] Recording and privacy requirements are addressed.

### Execution

- [ ] Participants understand the session.
- [ ] Instructions do not unnecessarily influence behavior.
- [ ] Player behavior is observed.
- [ ] Relevant feedback is collected.
- [ ] Important events and difficulties are recorded.
- [ ] Interventions are documented.
- [ ] Session conditions are recorded.

### Evaluation

- [ ] Findings are organized.
- [ ] Observations are distinguished from interpretations.
- [ ] Recurring patterns are identified.
- [ ] Positive findings are preserved.
- [ ] Important problems are classified.
- [ ] Findings are evaluated against the original objectives.
- [ ] Limitations and uncertainties are documented.

### Follow-up

- [ ] Relevant defects are reported.
- [ ] Actionable improvements are added to the backlog.
- [ ] Design changes follow the appropriate approval process.
- [ ] Additional testing needs are identified.
- [ ] The session record is complete.
- [ ] Evidence is stored appropriately.

## 18. Exceptions

Projects MAY adapt these guidelines according to their development stage, available resources, and testing objectives.

Early prototypes MAY use informal observation and lightweight feedback rather than structured sessions.

Small teams MAY combine the roles of facilitator, observer, and note-taker.

However, significant design decisions SHOULD be supported by documented evidence when practical.

Exceptions MUST NOT justify fabricating results, misrepresenting participant feedback, or treating unverified assumptions as established findings.

## 19. Related Documents

- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/01_game_design_guidelines/PLAYER_EXPERIENCE_GUIDELINES.md`
- `docs/01_game_design_guidelines/DIFFICULTY_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/BALANCING_GUIDELINES.md`
- `docs/01_game_design_guidelines/CORE_LOOP_DESIGN_GUIDELINES.md`
- `docs/01_game_design_guidelines/UI_UX_DESIGN_GUIDELINES.md`
- `docs/04_production_standards/BACKLOG_MANAGEMENT.md`
- `docs/04_production_standards/MILESTONE_GUIDELINES.md`
- `docs/04_production_standards/POSTMORTEM_GUIDELINES.md`
- `docs/05_qa_standards/ACCEPTANCE_CRITERIA_GUIDELINES.md`
- `docs/05_qa_standards/BUG_REPORTING.md`
- `docs/02_technical_standards/TESTING_STRATEGY.md`

## 20. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- Playtesting practices evolve.
- New testing methods or tools are introduced.
- Recurring evaluation problems are identified.
- The target audience or project objectives change.
- AI-assisted analysis introduces new requirements.
- Lessons from previous sessions reveal opportunities for improvement.

Changes MUST preserve the distinction between playtesting, automated testing, defect reporting, and design approval.

The project owner is responsible for approving changes to these guidelines.