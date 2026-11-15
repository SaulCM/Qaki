# Postmortem Guidelines

## 1. Purpose

This document defines the studio-wide guidelines for conducting project and milestone postmortems.

A postmortem is a structured review of completed work intended to understand what happened, identify lessons, and improve future development practices.

Its purpose is to:

- Identify what worked well and why.
- Understand problems, failures, and unexpected outcomes.
- Evaluate planning and execution.
- Identify technical and production risks.
- Capture lessons that can improve future work.
- Define practical improvement actions.
- Preserve useful project knowledge.
- Prevent recurring problems.

Postmortems MUST focus on learning and continuous improvement rather than assigning blame.

These guidelines are reusable across studio projects. Individual game projects SHOULD maintain their own postmortem records.

## 2. Scope

These guidelines apply to postmortems conducted after:

- Major development milestones.
- Completed production phases.
- Vertical slices.
- Alpha and beta stages.
- Game releases.
- Significant features or technical initiatives.
- Major incidents or unexpected failures.
- Development experiments.
- Other substantial bodies of work.

A postmortem MAY also be conducted when a project, feature, or initiative is cancelled.

Not every small task requires a formal postmortem. The depth of the review SHOULD be proportional to the importance, complexity, and learning value of the work.

## 3. Postmortem Principles

### 3.1. Learning Over Blame

Postmortems MUST focus on understanding processes, decisions, conditions, and outcomes.

Avoid assigning personal blame for mistakes or unexpected results.

When problems occur, investigate contributing factors rather than stopping at identifying who performed the work.

### 3.2. Evidence-Based Analysis

Conclusions SHOULD be supported by available evidence.

Useful sources include:

- Backlog history.
- Milestone plans.
- Sprint records.
- Git history.
- Pull requests.
- Issue reports.
- Test results.
- Performance measurements.
- Build history.
- Development notes.
- Playtest feedback.
- Project owner observations.

Distinguish verified facts from interpretations and assumptions.

### 3.3. Balanced Evaluation

Postmortems MUST consider both successes and problems.

Understanding why an approach worked is as valuable as understanding why another failed.

### 3.4. Actionable Improvements

A postmortem SHOULD produce practical improvements.

Avoid recommendations that are vague, unrealistic, or disconnected from the identified problems.

### 3.5. Proportional Effort

Postmortem effort SHOULD reflect the value of the review.

A short milestone may require only a concise written reflection. A major release may justify a more comprehensive analysis.

### 3.6. Continuous Improvement

Lessons SHOULD influence future planning, design, engineering, QA, and production decisions.

Recording lessons without considering their application provides limited value.

## 4. When to Conduct a Postmortem

Postmortems SHOULD be conducted when meaningful learning opportunities exist.

Recommended occasions include:

### 4.1. Milestone Completion

Conduct a postmortem after major milestones when the work provides useful insight into planning, implementation, integration, or validation.

Examples:

- Core gameplay prototype.
- Vertical slice.
- Feature-complete milestone.
- Alpha.
- Beta.
- Release candidate.

### 4.2. Major Feature Completion

A feature postmortem MAY be appropriate when:

- The feature was technically complex.
- Significant assumptions were validated.
- Unexpected problems occurred.
- The implementation introduced important architectural lessons.
- The feature required substantial iteration.

### 4.3. Release Completion

A release postmortem SHOULD review the overall development and delivery process.

Consider:

- Scope and schedule.
- Product quality.
- Technical stability.
- Release preparation.
- Player feedback, when available.
- Team and production effectiveness.
- Remaining risks.

### 4.4. Major Problems or Incidents

A focused postmortem SHOULD be considered after significant incidents, such as:

- Data loss.
- Critical save system failures.
- Major regressions.
- Failed builds or deployments.
- Severe performance problems.
- Unexpected integration failures.
- Serious security or reliability issues.

The review SHOULD focus on causes, impact, recovery, and prevention.

### 4.5. Cancelled Work

Cancelled features or projects MAY receive a postmortem when the decision provides useful lessons.

Consider why the work was cancelled, what was learned, and whether any work or knowledge can be reused.

## 5. Postmortem Preparation

A postmortem SHOULD be prepared before conducting the review.

### 5.1. Define the Review Scope

Identify:

- Project or feature being reviewed.
- Relevant development period.
- Milestone or release.
- Intended review objectives.
- Participants, when applicable.

Keep the scope focused enough to support meaningful analysis.

### 5.2. Gather Evidence

Collect relevant project records before drawing conclusions.

Possible evidence includes:

- Original objectives and scope.
- Initial estimates and target dates.
- Actual completion dates.
- Backlog changes.
- Completed and incomplete work.
- Defect reports.
- Testing results.
- Technical decisions.
- Build and integration problems.
- Performance measurements.
- Player or reviewer feedback.

Use available evidence rather than reconstructing every historical detail.

### 5.3. Identify Relevant Changes

Review important differences between the original plan and actual outcome.

Examples include:

- Scope changes.
- Delayed dependencies.
- Unexpected technical complexity.
- Repeated rework.
- Unplanned features.
- Quality issues.
- Changes in priorities.

### 5.4. Prepare Questions

Define questions relevant to the work being reviewed.

Avoid conducting a generic review that ignores the project's actual challenges.

## 6. Postmortem Structure

A postmortem SHOULD include the following sections.

### 6.1. Overview

Record:

- Project or feature name.
- Review subject.
- Relevant milestone or release.
- Review period.
- Review date.
- Participants, when applicable.
- Responsible reviewer.

### 6.2. Original Objectives

Describe what the work was intended to achieve.

Include:

- Initial scope.
- Expected deliverables.
- Quality expectations.
- Target dates, when relevant.
- Important assumptions.

### 6.3. Actual Outcomes

Describe what was achieved.

Include:

- Completed deliverables.
- Incomplete objectives.
- Important scope changes.
- Final quality condition.
- Significant deviations from the original plan.

### 6.4. What Went Well

Identify successful practices, decisions, and outcomes.

Examples:

- Effective task decomposition.
- Useful technical prototypes.
- Reliable automated tests.
- Clear feature boundaries.
- Successful early integration.
- Effective AI-assisted workflows.
- Good documentation.
- Successful risk mitigation.

Explain why these practices worked and whether they should be repeated.

### 6.5. What Did Not Go Well

Identify problems and undesirable outcomes.

Examples:

- Unclear requirements.
- Inaccurate estimates.
- Excessive scope changes.
- Architectural rework.
- Unstable tests.
- Integration problems.
- Missing assets.
- Performance issues.
- Incomplete validation.
- Poor communication.
- Unreliable AI-generated changes.

Describe their actual impact without exaggerating their importance.

### 6.6. Unexpected Discoveries

Record important findings that were not anticipated during planning.

Examples:

- Engine limitations.
- Better implementation approaches.
- Unexpected gameplay behavior.
- Hidden dependencies.
- Performance bottlenecks.
- Tooling limitations.
- Player behavior that differed from expectations.

### 6.7. Root Cause and Contributing Factors

Analyze why significant problems occurred.

Consider:

- Requirements.
- Planning.
- Architecture.
- Implementation.
- Testing.
- Tooling.
- Dependencies.
- Documentation.
- Communication.
- Uncertainty.
- External constraints.

Distinguish the immediate cause from underlying contributing factors.

### 6.8. Lessons Learned

Summarize the knowledge gained.

Lessons SHOULD be specific enough to influence future decisions.

For example:

**Weak lesson:** Improve testing.

**Useful lesson:** Integrate automated scene tests earlier because testing only after feature integration caused defects to be discovered too late.

### 6.9. Improvement Actions

Define practical actions based on the most important findings.

Each action SHOULD identify:

- Description.
- Expected benefit.
- Priority.
- Responsible owner, when applicable.
- Related backlog item, when applicable.
- Target milestone or review point.

### 6.10. Final Assessment

Summarize the overall outcome.

Consider:

- Whether objectives were achieved.
- Whether the work met expected quality.
- Whether the original approach was effective.
- What should change in future work.
- Whether additional follow-up is required.

## 7. Analysis Guidelines

Postmortem analysis SHOULD go beyond describing symptoms.

### 7.1. Separate Facts from Interpretations

Clearly distinguish:

- Verified events.
- Measured results.
- Observations.
- Hypotheses.
- Opinions.

For example:

**Fact:** The feature was integrated two weeks after its original target.

**Interpretation:** The original estimate did not account for the complexity of integrating its dependencies.

**Hypothesis:** Earlier integration testing may have reduced the delay.

Do not present an unverified hypothesis as an established root cause.

### 7.2. Identify Contributing Factors

Problems often result from multiple contributing factors.

Avoid assuming that a single decision or action explains every failure.

Consider how planning, technical constraints, missing information, and validation practices interacted.

### 7.3. Use Root Cause Techniques When Appropriate

For significant problems, use a structured investigation technique.

Possible approaches include:

- Five Whys.
- Cause-and-effect analysis.
- Timeline reconstruction.
- Fault tree analysis.
- Dependency analysis.

Use the simplest technique that provides sufficient understanding.

Do not apply formal analysis techniques to minor issues that do not justify the effort.

### 7.4. Evaluate Decisions in Context

Evaluate decisions based on the information available when they were made.

Avoid judging historical decisions solely using information discovered later.

Consider whether the decision was reasonable given its original constraints and assumptions.

## 8. Production and Planning Review

Postmortems SHOULD evaluate the effectiveness of the production process.

Consider:

### 8.1. Scope Management

- Was the scope clearly defined?
- Were priorities appropriate?
- Were scope changes justified?
- Was unnecessary work introduced?
- Were important requirements missed?

### 8.2. Estimation

- Were estimates realistic?
- Which tasks took longer than expected?
- Were dependencies considered?
- Was uncertainty identified?
- Did estimates improve as more information became available?

### 8.3. Backlog Management

- Were work items sufficiently clear?
- Was task decomposition effective?
- Were priorities maintained?
- Were blockers visible?
- Was the backlog kept relevant?

### 8.4. Milestone Management

- Were milestone objectives meaningful?
- Were acceptance criteria clear?
- Were deliverables achieved?
- Were risks identified early?
- Were milestone changes managed appropriately?

### 8.5. Development Workflow

- Was branching effective?
- Were code reviews useful?
- Were integrations performed regularly?
- Did automation support development?
- Were development standards followed?

### 8.6. Capacity and Workload

- Was the planned workload realistic?
- Were interruptions or context switching significant?
- Was too much work started simultaneously?
- Were dependencies or external constraints underestimated?

Production improvements SHOULD address the underlying process rather than simply demanding more effort.

## 9. Technical and Quality Review

Postmortems SHOULD evaluate technical outcomes when relevant.

Consider:

### 9.1. Architecture

- Were architectural decisions appropriate?
- Were feature boundaries clear?
- Did systems become unnecessarily coupled?
- Were abstractions justified?
- Was technical debt introduced?
- Were important decisions documented?

### 9.2. Implementation

- Was code maintainable?
- Were studio coding standards followed?
- Were repeated implementation problems identified?
- Was refactoring performed at appropriate times?
- Were technical limitations discovered too late?

### 9.3. Testing and QA

- Were tests introduced early enough?
- Did automated tests provide useful coverage?
- Were manual validation activities effective?
- Were regressions detected promptly?
- Were flaky tests or missing test infrastructure significant problems?

### 9.4. Performance

- Were performance targets established?
- Were bottlenecks identified early?
- Was optimization evidence-based?
- Were target platforms validated?
- Were performance regressions introduced?

### 9.5. Documentation

- Was documentation sufficient?
- Were important decisions recorded?
- Did contributors follow authoritative documents?
- Was documentation updated when implementation changed?
- Were there duplicated or conflicting sources of truth?

### 9.6. Integration and Reliability

- Were feature integrations predictable?
- Were dependencies managed effectively?
- Were builds reliable?
- Were save data, resources, and runtime state handled correctly?
- Were failures detected and reported appropriately?

## 10. Art, Audio, and Content Review

When relevant, postmortems SHOULD evaluate the content production process.

Consider:

- Was the visual direction sufficiently clear?
- Were asset requirements understood?
- Were references available?
- Were asset pipelines effective?
- Was visual consistency maintained?
- Were audio requirements defined early?
- Were asset dependencies identified?
- Were assets integrated and validated in context?
- Was rework caused by unclear specifications?
- Did production estimates reflect actual complexity?

Identify improvements that can make future content production more predictable and consistent.

## 11. AI-Assisted Development Review

Projects using AI agents SHOULD evaluate whether AI-assisted workflows contributed positively to development.

Consider:

### 11.1. Context and Instructions

- Did agents receive sufficient project context?
- Were authoritative documents followed?
- Were instructions clear?
- Were relevant constraints preserved?
- Did agents misunderstand project requirements?

### 11.2. Output Quality

- Was generated code correct and maintainable?
- Were architectural conventions followed?
- Were changes appropriately scoped?
- Did agents introduce unnecessary complexity?
- Were generated assets consistent with the visual direction?

### 11.3. Validation

- Were generated changes properly tested?
- Were validation claims accurate?
- Were defects introduced by generated work?
- Was human review effective?
- Were important assumptions identified?

### 11.4. Workflow Effectiveness

- Did agents reduce development effort?
- Did they create additional review or correction work?
- Were tasks sufficiently well-defined?
- Were tool limitations significant?
- Were agent workflows repeatable?

### 11.5. Improvement Opportunities

Identify opportunities to improve:

- Agent instructions.
- Project documentation.
- Task decomposition.
- Context preparation.
- Tool configuration.
- Validation procedures.
- Human approval boundaries.

AI-assisted development SHOULD be evaluated based on actual results, not assumptions that automation necessarily improves productivity.

## 12. Improvement Action Management

Postmortems SHOULD produce a manageable set of improvement actions.

### 12.1. Action Quality

Actions SHOULD be:

- Specific.
- Achievable.
- Relevant to identified findings.
- Proportional to the problem.
- Verifiable.

Avoid vague actions such as:

- Improve communication.
- Write better code.
- Test more.
- Be more careful.

Prefer:

- Add automated validation for resource identifiers before integration.
- Introduce an early playable integration checkpoint for new gameplay features.
- Add dependency identification to feature refinement.
- Establish a documented approval process for changes to shared architecture.

### 12.2. Action Prioritization

Prioritize actions according to:

- Potential impact.
- Likelihood of recurrence.
- Cost of implementation.
- Risk reduction.
- Relevance to upcoming work.

Not every observation requires a backlog item.

### 12.3. Action Ownership

Each significant improvement action SHOULD have an owner.

For a solo project, the project owner may be responsible for all actions.

AI agents MAY assist with implementation but MUST NOT assume ownership or approve process changes independently.

### 12.4. Backlog Integration

Actions requiring implementation SHOULD be added to the authoritative project backlog.

They SHOULD reference the postmortem that generated them.

### 12.5. Follow-Up

Review significant actions during relevant future milestones or production reviews.

An action SHOULD be considered complete only when its expected result has been achieved.

## 13. Postmortem Records

Postmortems SHOULD be stored in the corresponding game repository.

A recommended location is:

`game_project/docs/production/postmortems/`

Each postmortem SHOULD use a descriptive filename.

Example:

`2026-11-14-core_gameplay_prototype.md`

### 13.1. Record Requirements

A postmortem record SHOULD include:

- Review subject.
- Review date.
- Relevant project period.
- Findings.
- Lessons learned.
- Improvement actions.
- Relevant references.

### 13.2. Historical Preservation

Completed postmortem records SHOULD be preserved as historical project knowledge.

Do not rewrite historical conclusions merely because later project decisions change.

Additional context or follow-up findings MAY be added when necessary.

### 13.3. Confidentiality

Postmortem records SHOULD avoid unnecessary sensitive information.

Do not include:

- Credentials.
- Access tokens.
- Private personal information.
- Sensitive customer or player data.
- Unnecessary personal criticism.

## 14. Postmortem Frequency and Effort

Postmortem frequency SHOULD reflect project scope and development activity.

Recommended practices:

- Conduct a focused review after major milestones.
- Conduct a broader review after major releases.
- Review significant incidents when their causes and consequences are understood sufficiently.
- Avoid formal postmortems for routine tasks with limited learning value.

For solo development, a concise written review may be sufficient.

The purpose is to preserve useful knowledge, not to create recurring administrative work.

## 15. Postmortem Documentation Template

Projects SHOULD use a consistent template for recording postmortems.

The following template MAY be copied into project-specific documentation:

```markdown
# Postmortem: [Review Subject]

## 1. Overview

- **Project:** [Project Name]
- **Review Subject:** [Milestone / Feature / Release / Incident]
- **Review Period:** [Start Date - End Date]
- **Review Date:** [Date]
- **Participants:** [Names or roles, if applicable]

## 2. Original Objectives

[Describe the original goals, scope, and expected outcomes.]

## 3. Actual Outcomes

[Describe what was achieved and identify relevant differences from the original plan.]

## 4. What Went Well

- [Successful practice or decision]
- [Why it worked]
- [Whether it should be repeated]

## 5. What Did Not Go Well

- [Problem or unexpected outcome]
- [Its impact]
- [Relevant contributing factors]

## 6. Unexpected Discoveries

- [Important discovery]
- [New technical or production knowledge]

## 7. Root Cause Analysis

### Problem

[Describe the problem.]

### Immediate Cause

[Identify the direct cause, if known.]

### Contributing Factors

- [Factor]
- [Factor]

### Evidence and Confidence

[Record supporting evidence and distinguish verified findings from hypotheses.]

## 8. Lessons Learned

- [Specific lesson]
- [How it should influence future work]

## 9. Improvement Actions

| Action | Priority | Owner | Backlog Reference | Status |
|---|---|---|---|---|
| [Action] | [Priority] | [Owner] | [ID] | [Status] |

## 10. Final Assessment

[Summarize the overall outcome and most important findings.]

## 11. Follow-Up

- [Future milestone or review point]
- [Outstanding action]

## 12. References

- [Relevant backlog items]
- [Milestone documentation]
- [Technical documents]
- [Test results]
- [Other evidence]
```

The template MAY be simplified for small reviews.

## 16. AI-Assisted Postmortems

AI agents MAY assist with preparing and analyzing postmortems.

They MAY:

- Gather relevant project records.
- Summarize development history.
- Compare planned and actual outcomes.
- Identify recurring problems.
- Suggest contributing factors.
- Organize lessons learned.
- Propose improvement actions.
- Draft postmortem documentation.
- Identify related backlog items.

AI agents MUST:

1. Use available project evidence.
2. Distinguish facts from interpretations.
3. Identify uncertainty and missing information.
4. Avoid inventing events, metrics, or conclusions.
5. Consider both successes and failures.
6. Preserve relevant historical context.
7. Propose actionable improvements.
8. Respect project documentation standards.
9. Request approval before changing established studio or project processes.

AI agents MUST NOT:

- Assign personal blame.
- Present assumptions as verified root causes.
- Invent development metrics.
- Rewrite historical records without authorization.
- Mark improvement actions complete without validation.
- Treat their own generated output as independent evidence of successful work.

The project owner is responsible for reviewing and approving postmortem conclusions and significant improvement actions.

## 17. Postmortem Review Checklist

Before completing a postmortem, verify the applicable requirements:

- [ ] The review scope is clear.
- [ ] Original objectives are documented.
- [ ] Actual outcomes are described.
- [ ] Successful practices are identified.
- [ ] Problems and unexpected outcomes are identified.
- [ ] Significant problems have been analyzed.
- [ ] Facts are distinguished from assumptions.
- [ ] Lessons learned are actionable.
- [ ] Improvement actions are prioritized.
- [ ] Relevant actions are added to the backlog.
- [ ] Important findings are preserved.
- [ ] Follow-up responsibilities are identified.
- [ ] The review avoids unnecessary personal blame.
- [ ] The postmortem record is stored in the project repository.

## 18. Exceptions

Projects MAY adapt these guidelines according to their size, development model, and available resources.

Exceptions SHOULD be justified when they:

- Reduce unnecessary administrative overhead.
- Support experimental or research-driven development.
- Address limited historical evidence.
- Better reflect the scale of the work.
- Improve the usefulness of the review.

Exceptions MUST NOT compromise the core purpose of learning, preserving relevant findings, and improving future work.

Significant changes to the studio postmortem process require project owner approval.

## 19. Related Documents

- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/00_studio_standards/GAME_DEVELOPMENT_LIFECYCLE.md`
- `docs/04_production_standards/BACKLOG_MANAGEMENT.md`
- `docs/04_production_standards/MILESTONE_GUIDELINES.md`

Project-specific postmortems SHOULD reference relevant backlog items, milestone plans, sprint records, technical documentation, QA reports, and release records.

## 20. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- Studio production practices change.
- Recurring development problems are identified.
- Postmortems consistently fail to produce useful improvements.
- New development or collaboration workflows are adopted.
- AI-assisted development practices evolve.
- Improvements to knowledge capture and continuous improvement are identified.

Changes MUST preserve the distinction between reusable studio guidelines and project-specific postmortem findings.

The project owner is responsible for approving changes to these guidelines.