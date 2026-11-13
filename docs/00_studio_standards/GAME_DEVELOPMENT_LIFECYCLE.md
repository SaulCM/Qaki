
# Game Development Lifecycle

## 1. Purpose

This document defines the standard lifecycle used to develop, validate, produce, release, and maintain games within the studio.

Its objectives are to:

- Establish a consistent development framework.
- Define the major phases of game development.
- Identify the objectives and expected outcomes of each phase.
- Establish decision gates for progressing between phases.
- Support realistic planning and resource allocation.
- Reduce production risks through early validation.
- Maintain alignment between creative vision, technical implementation, and production goals.

The lifecycle is a reusable framework. Individual projects may adapt its phases, deliverables, and decision gates according to their scope, genre, complexity, risks, and available resources.

## 2. Lifecycle Principles

The studio follows these principles throughout game development.

### 2.1 Iterative Development

Game development is an iterative process.

Phases provide structure, but they do not imply that all activities must occur in a strictly linear sequence.

Design, implementation, testing, and refinement may overlap or repeat as new information becomes available.

### 2.2 Validate Risk Early

Identify and investigate the assumptions most likely to threaten project success.

Prioritize early validation of:

- Core gameplay mechanics.
- Technical feasibility.
- Performance constraints.
- Content production requirements.
- Player experience assumptions.
- Development scope and resource constraints.

Do not invest heavily in production before critical uncertainties have been sufficiently investigated.

### 2.3 Deliver Incrementally

Prefer small, verifiable increments over large, unvalidated development efforts.

Each significant increment should produce a demonstrable improvement to the game or reduce a meaningful project risk.

### 2.4 Evidence-Based Decisions

Progression decisions should consider:

- Playable results.
- Technical validation.
- Testing feedback.
- Production progress.
- Resource availability.
- Remaining risks.
- Alignment with the approved game vision.

Do not advance a project phase merely because a planned date has arrived.

### 2.5 Proportional Process

The amount of planning, documentation, testing, and review must be appropriate to the project's complexity.

A small prototype should not require the same production infrastructure as a large commercial release.

## 3. Lifecycle Overview

The standard game development lifecycle consists of the following phases:

<escape>
```text
CONCEPT
   |
   v
PRE-PRODUCTION
   |
   v
PROTOTYPING
   |
   v
PRODUCTION
   |
   v
ALPHA
   |
   v
BETA
   |
   v
RELEASE CANDIDATE
   |
   v
RELEASE
   |
   v
POST-RELEASE
```
</escape>

These phases represent development maturity and decision points, not necessarily isolated periods.

Depending on project needs:

- Prototyping may occur during concept development or pre-production.
- Production may begin incrementally as individual systems are validated.
- Alpha and beta activities may overlap with ongoing content production.
- Some projects may use a smaller number of formal milestones.
- Some projects may never proceed to public release.

## 4. Phase 1 — Concept

### 4.1 Objective

Establish the initial creative direction and determine whether the game concept is worth investigating further.

The concept phase defines the fundamental idea without requiring a complete design or technical specification.

### 4.2 Key Activities

- Identify the core game idea.
- Define the intended player experience.
- Explore genre, setting, themes, and creative direction.
- Identify potential audiences.
- Establish initial gameplay hypotheses.
- Identify major creative and technical risks.
- Evaluate the concept's feasibility at a high level.
- Define preliminary project constraints.

### 4.3 Expected Deliverables

Depending on project scope:

- Initial game concept.
- Preliminary game vision.
- Core gameplay hypothesis.
- Initial reference collection.
- High-level feasibility assessment.
- Preliminary risk list.

### 4.4 Exit Criteria

The project may proceed to pre-production when:

- [ ] The core concept can be clearly communicated.
- [ ] The intended player experience is sufficiently understood.
- [ ] The main gameplay proposition is identifiable.
- [ ] The concept is compatible with the studio's resources and objectives.
- [ ] Major uncertainties have been identified.
- [ ] The project owner decides that further investigation is justified.

### 4.5 Decision Gate

**Decision:** Continue, revise, postpone, or abandon the concept.

The concept phase is exploratory. Approval does not imply that the game design or technical implementation has been finalized.

## 5. Phase 2 — Pre-Production

### 5.1 Objective

Transform the initial concept into a sufficiently defined and actionable project direction.

Pre-production reduces uncertainty by establishing the game's vision, design foundations, technical approach, production strategy, and initial scope.

### 5.2 Key Activities

- Refine the game vision.
- Define the target audience and intended experience.
- Establish design pillars.
- Define the core gameplay loop.
- Identify major gameplay systems.
- Establish initial mechanics and progression concepts.
- Define visual and audio direction.
- Evaluate technical requirements.
- Establish the initial architecture direction.
- Identify development tools and pipelines.
- Estimate project complexity and major production needs.
- Identify critical dependencies and risks.
- Define the initial backlog and milestone structure.

### 5.3 Expected Deliverables

As applicable:

- Approved Game Vision Document.
- Initial Game Design Document.
- Core gameplay loop definition.
- Preliminary system specifications.
- Initial technical design.
- Art and audio direction.
- Technical feasibility assessment.
- Initial risk register.
- Initial project roadmap.
- Prioritized development backlog.

### 5.4 Exit Criteria

The project may proceed to structured prototyping when:

- [ ] The game vision is sufficiently clear.
- [ ] Core design pillars are established.
- [ ] The intended gameplay experience is understood.
- [ ] Major systems and dependencies are identified.
- [ ] Critical technical questions have investigation plans.
- [ ] The initial scope is realistic.
- [ ] Development priorities are established.
- [ ] The project owner approves the direction.

### 5.5 Decision Gate

**Decision:** Proceed to prototyping, revise the project direction, or stop development.

Pre-production does not require every gameplay detail to be finalized. It must provide enough clarity to investigate the most important uncertainties.

## 6. Phase 3 — Prototyping

### 6.1 Objective

Validate the most important gameplay and technical assumptions through focused experiments and playable implementations.

Prototypes should answer specific questions rather than attempt to represent the complete game.

### 6.2 Key Activities

- Implement the core gameplay loop.
- Experiment with movement and interaction.
- Test important mechanics.
- Evaluate game feel and responsiveness.
- Investigate technical feasibility.
- Test uncertain architectural approaches.
- Evaluate performance risks.
- Explore visual and audio prototypes.
- Gather feedback where appropriate.
- Refine or reject design assumptions.

### 6.3 Prototype Types

Common prototype categories include:

| Type | Purpose |
|---|---|
| Paper prototype | Explore rules, systems, and interactions without software implementation |
| Gameplay prototype | Test mechanics and player interactions |
| Technical prototype | Validate feasibility, performance, or engine capabilities |
| Visual prototype | Explore art direction, composition, and presentation |
| Vertical slice | Validate a representative, integrated portion of the intended experience |

### 6.4 Expected Deliverables

- Playable prototype or technical experiment.
- Validated or rejected design hypotheses.
- Technical findings.
- Updated risk register.
- Refined gameplay specifications.
- Documented architectural findings where relevant.
- Updated scope and production estimates.

### 6.5 Exit Criteria

The project may proceed to full production when:

- [ ] The core gameplay concept has been demonstrated.
- [ ] The most important design assumptions have been investigated.
- [ ] Critical technical risks have been sufficiently reduced.
- [ ] The intended experience remains aligned with the game vision.
- [ ] Major gameplay systems have an implementation direction.
- [ ] The production scope is sufficiently understood.
- [ ] The project owner approves proceeding.

### 6.6 Decision Gate

**Decision:** Proceed to production, iterate on prototypes, revise the design, or abandon the project.

A prototype is successful when it provides sufficient evidence to make a decision. It does not need to become production code.

## 7. Phase 4 — Production

### 7.1 Objective

Build the complete game through incremental implementation, content creation, integration, and validation.

Production is the main development phase, during which approved gameplay systems, content, infrastructure, and supporting features are implemented.

### 7.2 Key Activities

- Implement gameplay systems.
- Develop and integrate game content.
- Build levels and environments.
- Implement UI and user interactions.
- Integrate art, animation, and audio.
- Develop progression and balancing systems.
- Implement persistence and save functionality where required.
- Develop supporting technical infrastructure.
- Maintain automated testing.
- Perform continuous integration and regression validation.
- Monitor technical debt and production risks.
- Refine design based on validated feedback.

### 7.3 Development Approach

Production should use incremental development.

Recommended practices:

- Break large features into manageable tasks.
- Prioritize work according to dependencies, risk, and player impact.
- Use vertical slices for complex gameplay features where practical.
- Integrate completed work frequently.
- Maintain a playable project whenever practical.
- Validate systems as they are implemented.
- Keep documentation synchronized with approved changes.
- Review progress against the actual scope rather than task counts alone.

### 7.4 Expected Deliverables

- Implemented gameplay systems.
- Integrated game content.
- Functional UI and interaction flows.
- Implemented progression and supporting systems.
- Automated and manual test coverage.
- Updated technical and design documentation.
- Regular playable builds.
- Updated production backlog.
- Recorded technical debt and known limitations.

### 7.5 Exit Criteria

The project may enter formal alpha validation when:

- [ ] All essential gameplay systems are implemented or sufficiently integrated for evaluation.
- [ ] The primary gameplay loop is functional.
- [ ] A representative amount of core content exists.
- [ ] Major gameplay flows can be completed.
- [ ] The project can be built and executed reliably enough for systematic testing.
- [ ] Major technical risks are understood.
- [ ] Known limitations and remaining work are documented.

### 7.6 Decision Gate

**Decision:** Begin alpha validation, continue production, or revise scope.

Production is not considered complete merely because the planned task backlog has been exhausted.

## 8. Phase 5 — Alpha

### 8.1 Objective

Validate that the game is functionally complete enough to support systematic testing and refinement.

Alpha focuses on identifying missing functionality, major defects, incomplete content, and fundamental gameplay problems.

The exact meaning of alpha may vary by project, but the project must define its own entry criteria.

### 8.2 Key Activities

- Test complete gameplay flows.
- Identify missing or incomplete features.
- Validate system integration.
- Perform functional and regression testing.
- Evaluate progression and game balance.
- Investigate major usability problems.
- Identify stability and performance issues.
- Review save and loading behavior where applicable.
- Evaluate content completeness.
- Prioritize defects and remaining work.

### 8.3 Expected Deliverables

- Alpha build.
- Functional test results.
- Defect and issue backlog.
- Updated feature completion status.
- Updated risk register.
- Initial balance findings.
- Known limitations.
- Prioritized stabilization plan.

### 8.4 Exit Criteria

The project may proceed to beta when:

- [ ] All planned critical gameplay functionality is implemented.
- [ ] The primary game experience can be completed.
- [ ] No known critical defects prevent meaningful gameplay.
- [ ] Major systems are integrated.
- [ ] Essential content is present.
- [ ] Save and loading functionality works when required.
- [ ] The remaining work is primarily refinement, balancing, optimization, and defect resolution.
- [ ] The project owner approves the transition.

### 8.5 Decision Gate

**Decision:** Proceed to beta, continue alpha stabilization, or revise the remaining scope.

## 9. Phase 6 — Beta

### 9.1 Objective

Refine the game into a stable and release-ready experience.

Beta emphasizes quality, balancing, compatibility, performance, usability, and the resolution of remaining defects.

The introduction of new major features should generally be avoided unless explicitly approved.

### 9.2 Key Activities

- Perform extensive regression testing.
- Validate complete gameplay sessions.
- Refine gameplay balance.
- Improve usability and accessibility.
- Optimize performance.
- Validate platform and hardware compatibility.
- Test save data integrity.
- Test installation and startup workflows.
- Verify audio and visual consistency.
- Validate localization where applicable.
- Address prioritized defects.
- Evaluate feedback from external testers when available.

### 9.3 Expected Deliverables

- Beta build.
- Updated test reports.
- Updated defect backlog.
- Performance and compatibility findings.
- Balance adjustments.
- Updated release requirements.
- Release preparation checklist.

### 9.4 Exit Criteria

The project may proceed to release candidate preparation when:

- [ ] Core gameplay and content are complete.
- [ ] No known critical defects remain.
- [ ] High-priority defects are resolved or explicitly accepted.
- [ ] Relevant regression tests pass.
- [ ] Performance meets the project's established targets.
- [ ] Required platforms and configurations have been validated.
- [ ] Save and loading behavior is reliable.
- [ ] Release requirements are understood.
- [ ] The project owner approves release candidate preparation.

### 9.5 Decision Gate

**Decision:** Proceed to release candidate preparation or continue beta stabilization.

## 10. Phase 7 — Release Candidate

### 10.1 Objective

Validate a specific build as a potential final release.

A release candidate should contain no planned feature additions and should undergo focused final verification.

### 10.2 Key Activities

- Freeze the release scope.
- Prepare a release candidate build.
- Perform final regression testing.
- Verify build configuration.
- Validate installation and startup.
- Verify required metadata and version information.
- Check distribution packages.
- Review release notes.
- Verify legal, licensing, and attribution requirements.
- Confirm that known issues are documented.
- Validate release and rollback procedures where applicable.

### 10.3 Expected Deliverables

- Release candidate build.
- Final validation results.
- Release notes.
- Version and build information.
- Distribution package.
- Known issues list.
- Release approval record.

### 10.4 Exit Criteria

A release candidate may be approved when:

- [ ] All release-blocking checks pass.
- [ ] No known critical or high-severity defects remain.
- [ ] Required functionality has been validated.
- [ ] The build is reproducible using the documented process.
- [ ] Distribution packages are verified.
- [ ] Required documentation and metadata are complete.
- [ ] Remaining issues are understood and accepted.
- [ ] The project owner explicitly approves the release.

### 10.5 Decision Gate

**Decision:** Approve the release, reject the candidate, or prepare another candidate.

If a release-blocking issue is discovered, correct it and repeat the relevant validation. A new release candidate may be required.

## 11. Phase 8 — Release

### 11.1 Objective

Deliver the approved game to its intended audience through the selected distribution channels.

### 11.2 Key Activities

- Publish or distribute the approved build.
- Verify the published package.
- Confirm installation and startup.
- Monitor release issues where possible.
- Communicate release information.
- Track reported defects.
- Preserve the released build and associated records.

### 11.3 Expected Deliverables

- Published or distributed game.
- Release notes.
- Version information.
- Archived release build.
- Release record.
- Initial post-release issue list.

### 11.4 Exit Criteria

Release is considered complete when:

- [ ] The approved build has been distributed.
- [ ] Distribution has been verified.
- [ ] Release information is available.
- [ ] The released version is identifiable and preserved.
- [ ] Critical release problems have been assessed.

## 12. Phase 9 — Post-Release

### 12.1 Objective

Maintain the released game, resolve issues, and evaluate opportunities for improvement.

Post-release activities depend on the project's distribution model, support commitments, and long-term objectives.

### 12.2 Key Activities

- Monitor reported defects.
- Investigate stability and compatibility problems.
- Prepare bug fixes and patches.
- Maintain supported versions.
- Evaluate player feedback.
- Improve performance where justified.
- Develop approved content updates.
- Maintain platform compatibility.
- Review technical debt.
- Record lessons learned.

### 12.3 Expected Deliverables

As applicable:

- Bug fixes and patches.
- Updated builds.
- Release notes.
- Support documentation.
- Maintenance backlog.
- Postmortem or retrospective.
- Lessons learned.
- Project archival records.

### 12.4 Exit Criteria

Post-release maintenance may conclude when:

- [ ] Planned support obligations are fulfilled.
- [ ] Remaining known issues are documented.
- [ ] Required project records are preserved.
- [ ] The project owner approves the maintenance closure or transition to archival status.

## 13. Lifecycle Decision Gates

Each phase transition should be treated as a decision rather than an automatic progression.

| Gate | Decision | Primary question |
|---|---|---|
| Concept approval | Continue to pre-production | Is the concept worth investigating? |
| Pre-production approval | Continue to prototyping | Is the direction sufficiently defined? |
| Prototype validation | Continue to production | Have critical assumptions been validated? |
| Production completion | Enter alpha | Is the game sufficiently implemented for systematic testing? |
| Alpha exit | Enter beta | Is core functionality complete and integrated? |
| Beta exit | Enter release candidate | Is the game sufficiently stable and refined? |
| Release approval | Publish | Is the specific build ready for distribution? |
| Maintenance closure | Archive or transition | Have support obligations been addressed? |

A decision gate may result in:

- **Proceed:** Required conditions are sufficiently satisfied.
- **Iterate:** More work or validation is required.
- **Revise:** The direction or scope must change.
- **Pause:** Development is temporarily suspended.
- **Stop:** The project or current approach is abandoned.

Decisions should be based on evidence, risks, and project objectives.

## 14. Project Tailoring

Not every project requires the same lifecycle structure.

The project owner may adapt the lifecycle according to:

- Project size and complexity.
- Genre and gameplay requirements.
- Technical uncertainty.
- Content production needs.
- Available resources.
- Target platforms.
- Distribution model.
- Commercial or personal objectives.

For example:

### 14.1 Small Experimental Project

May combine:

- Concept and pre-production.
- Prototyping and limited production.
- A simplified testing and release process.

### 14.2 Larger or Content-Heavy Project

May require:

- More extensive pre-production.
- Multiple prototypes.
- Dedicated vertical slices.
- Incremental production milestones.
- Formal alpha and beta milestones.
- More extensive compatibility and regression testing.

### 14.3 Ongoing or Early Access Project

May use repeated production, testing, and release cycles rather than a single final release transition.

Tailoring must not eliminate necessary validation or obscure project risks.

## 15. Lifecycle Governance

The project owner is responsible for:

- Approving major lifecycle transitions.
- Defining project-specific milestones.
- Accepting changes to scope.
- Reviewing major risks.
- Approving significant architectural decisions.
- Determining release readiness.
- Authorizing project suspension, cancellation, or closure.

Contributors and AI agents may recommend decisions and prepare evidence, but they must not independently approve major project transitions.

## 16. Related Documentation

This document should be used together with:

- `DEVELOPMENT_PHILOSOPHY.md` — Guiding principles for development.
- `DEFINITION_OF_DONE.md` — Completion and acceptance criteria.
- `BRANCHING_STRATEGY.md` — Branch lifecycle and integration workflow.
- `CODE_REVIEW_GUIDELINES.md` — Code review and approval requirements.
- `docs/01_game_design_guidelines/` — Game design principles.
- `docs/02_technical_standards/` — Technical implementation requirements.
- `docs/04_production_standards/` — Detailed production planning and execution.
- `docs/05_qa_standards/` — Testing and quality assurance practices.
- `docs/07_agent_workflows/` — AI-assisted development procedures.

## 17. Maintenance

This document should be reviewed when:

- The studio's development process changes.
- New production practices are adopted.
- Repeated project experiences reveal lifecycle improvements.
- The scale or complexity of studio projects changes.

The project owner is responsible for maintaining and approving updates to this document.
