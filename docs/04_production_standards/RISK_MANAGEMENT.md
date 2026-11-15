# Risk Management

## 1. Purpose

This document defines the studio's approach to managing risks throughout game development.

It establishes guidelines for:

- Identifying potential risks.
- Evaluating likelihood and impact.
- Prioritizing risks.
- Defining mitigation and contingency strategies.
- Monitoring risk status.
- Escalating significant risks.
- Recording and communicating risk-related decisions.

The objective is to identify potential problems early, reduce uncertainty, and make informed decisions that protect project objectives, quality, and development capacity.

## 2. Scope

These guidelines apply to all game development projects and production activities.

Risk management covers, but is not limited to:

- Project scope and scheduling.
- Technical architecture and implementation.
- Gameplay design and balancing.
- Art and audio production.
- Content creation.
- Quality assurance.
- Performance and compatibility.
- External dependencies.
- Tools and development infrastructure.
- Security and data integrity.
- Licensing and intellectual property.
- Release and distribution.
- AI-assisted development.

Risk management SHOULD be proportional to the project's size, complexity, and potential impact.

Small projects MAY use a lightweight risk register, while larger or more complex projects MAY require more detailed analysis and review.

## 3. Risk Management Principles

### 3.1. Early Identification

Risks SHOULD be identified as early as practical.

Unvalidated assumptions, technical uncertainties, dependencies, and potential production bottlenecks SHOULD be investigated before they become expensive problems.

### 3.2. Proportionality

Risk management activities SHOULD reflect the likelihood and potential impact of the risk.

Low-impact risks SHOULD NOT require disproportionate documentation or review.

### 3.3. Prevention Over Reaction

Whenever practical, risks SHOULD be reduced before they become actual problems.

Prototypes, technical experiments, early testing, and incremental integration SHOULD be used to validate uncertain assumptions.

### 3.4. Transparency

Significant risks MUST be communicated clearly.

Risks MUST NOT be hidden, understated, or marked as resolved without sufficient evidence.

### 3.5. Ownership

Every significant risk SHOULD have an assigned owner responsible for monitoring it and coordinating the agreed response.

### 3.6. Continuous Monitoring

Risk management MUST be continuous throughout the project lifecycle.

Risks SHOULD be reviewed when project conditions, scope, technology, dependencies, or assumptions change.

### 3.7. Evidence-Based Decisions

Risk assessments SHOULD use available evidence, including:

- Prototype results.
- Technical experiments.
- Testing results.
- Production progress.
- Historical estimates.
- External dependency information.
- Documented assumptions.
- Actual project constraints.

Uncertainty MUST be acknowledged when reliable evidence is unavailable.

## 4. Risk Definition

A risk is an uncertain event or condition that, if it occurs, may negatively or positively affect project objectives.

This standard primarily addresses threats that could negatively affect:

- Project scope.
- Development time.
- Available resources.
- Product quality.
- Technical stability.
- Player experience.
- Release readiness.

An opportunity is an uncertain event or condition that may produce a beneficial outcome.

Opportunities MAY also be recorded when they are relevant to project decisions.

### 4.1. Risk Versus Issue

A risk is a potential future event or condition.

An issue is a problem that has already occurred and requires action.

Examples:

| Situation | Classification |
|---|---|
| A planned engine integration may not work as expected | Risk |
| The engine integration has failed | Issue |
| A feature may require more development time than estimated | Risk |
| A feature has exceeded its estimated development time | Issue |
| A save system may fail under certain conditions | Risk |
| Player saves are currently being corrupted | Issue |

When a risk materializes, it SHOULD be converted into an issue or tracked through the appropriate defect or incident process.

The original risk record MAY be retained for historical traceability.

## 5. Risk Categories

Projects SHOULD classify risks using categories that reflect their development context.

### 5.1. Scope and Design Risks

Potential problems involving project scope, gameplay design, and requirements.

Examples:

- Unclear game objectives.
- Excessive feature complexity.
- Unvalidated gameplay assumptions.
- Scope growth.
- Conflicting design requirements.
- Poorly defined acceptance criteria.
- Features that do not support the intended player experience.

### 5.2. Technical Risks

Potential problems involving architecture, implementation, technology, and infrastructure.

Examples:

- Uncertain engine capabilities.
- Architectural limitations.
- Difficult system integrations.
- Inadequate persistence design.
- Unstable dependencies.
- Technical debt accumulation.
- Incompatible plugins or tools.
- Difficult debugging or maintenance.

### 5.3. Production Risks

Potential problems affecting planning, capacity, coordination, and delivery.

Examples:

- Unrealistic estimates.
- Insufficient development capacity.
- Unclear task ownership.
- Excessive dependencies.
- Delayed deliverables.
- Poor backlog prioritization.
- Inefficient workflows.
- Uncontrolled changes.

### 5.4. Art and Audio Risks

Potential problems affecting asset production and integration.

Examples:

- Inconsistent visual direction.
- Insufficient asset production capacity.
- Missing source files.
- Incorrect asset formats.
- Licensing uncertainty.
- Audio quality problems.
- Difficult asset integration.
- Performance problems caused by assets.

### 5.5. Quality Risks

Potential problems affecting product reliability and player experience.

Examples:

- Insufficient test coverage.
- Unstable gameplay systems.
- Regression defects.
- Poor usability.
- Inconsistent game behavior.
- Inadequate accessibility.
- Save and loading failures.
- Insufficient compatibility testing.

### 5.6. Performance Risks

Potential problems involving runtime performance and resource consumption.

Examples:

- Unstable frame rates.
- Excessive memory consumption.
- Long loading times.
- Expensive physics calculations.
- Rendering bottlenecks.
- Inefficient resource loading.
- Performance degradation during extended gameplay.

### 5.7. External Dependency Risks

Potential problems caused by systems, services, people, or resources outside the project's direct control.

Examples:

- Third-party service changes.
- Plugin discontinuation.
- External API unavailability.
- Asset provider restrictions.
- Tool availability.
- Platform policy changes.
- Dependency version incompatibility.

### 5.8. Security and Data Risks

Potential problems involving unauthorized access, data integrity, privacy, or loss.

Examples:

- Save data corruption.
- Accidental exposure of credentials.
- Insecure network communication.
- Improper handling of player information.
- Data loss.
- Unsafe external integrations.

### 5.9. Legal and Licensing Risks

Potential problems involving intellectual property, licensing, and distribution requirements.

Examples:

- Unclear asset ownership.
- Incompatible open-source licenses.
- Unauthorized use of copyrighted material.
- Missing attribution.
- Unclear rights for AI-generated or externally sourced assets.
- Platform or distribution policy violations.

### 5.10. Release and Distribution Risks

Potential problems affecting publication and delivery.

Examples:

- Failed export configurations.
- Incorrect release packages.
- Platform incompatibility.
- Distribution delays.
- Unresolved critical defects.
- Incorrect release metadata.
- Inadequate post-release support capacity.

### 5.11. AI-Assisted Development Risks

Potential problems introduced or amplified by AI-assisted workflows.

Examples:

- Incorrect generated code.
- Fabricated API usage.
- Changes that violate approved architecture.
- Inconsistent documentation.
- Incorrect asset attribution.
- Unverified generated content.
- Excessive reliance on automated output.
- Accidental exposure of sensitive project information.

## 6. Risk Identification

### 6.1. Identification Activities

Risks SHOULD be identified during:

- Project initiation.
- Concept development.
- Pre-production.
- Prototyping.
- Feature planning.
- Technical design.
- Implementation.
- Integration.
- Testing.
- Milestone reviews.
- Release preparation.
- Post-release maintenance.

### 6.2. Identification Techniques

Projects MAY use the following techniques:

**Assumption review**

Identify assumptions that have not been validated.

**Technical investigation**

Explore uncertain technical capabilities through experiments and prototypes.

**Dependency analysis**

Identify external services, plugins, assets, systems, and tasks that could block progress.

**Historical analysis**

Review previous project problems, defects, delays, and postmortems.

**Design review**

Identify unclear requirements, complex interactions, and unvalidated gameplay decisions.

**Production review**

Identify capacity limitations, unrealistic estimates, bottlenecks, and scope concerns.

**Testing and feedback**

Use test results and player feedback to identify emerging risks.

### 6.3. Risk Statement

A risk SHOULD be described in a way that makes its cause, uncertain event, and potential consequence understandable.

Recommended structure:

"If [cause or condition], then [uncertain event] may occur, resulting in [potential impact]."

Example:

"If the selected pathfinding approach cannot handle the expected number of dynamic obstacles, navigation performance may degrade, resulting in unstable gameplay frame rates."

Risk statements SHOULD describe potential outcomes rather than vague concerns.

## 7. Risk Assessment

Each significant risk SHOULD be evaluated according to its likelihood and impact.

### 7.1. Likelihood

Likelihood represents the estimated probability that a risk will occur.

Use the following qualitative scale:

| Level | Classification | Description |
|---|---|---|
| 1 | Rare | Unlikely to occur under current conditions |
| 2 | Unlikely | Possible, but not expected |
| 3 | Possible | Could reasonably occur |
| 4 | Likely | Expected to occur unless addressed |
| 5 | Almost Certain | Very likely or already emerging |

These classifications are qualitative estimates, not precise statistical probabilities.

### 7.2. Impact

Impact represents the potential consequences if the risk occurs.

Use the following scale:

| Level | Classification | Description |
|---|---|---|
| 1 | Negligible | Minimal effect; easily handled |
| 2 | Minor | Limited disruption with manageable consequences |
| 3 | Moderate | Meaningful impact on a feature, milestone, or quality target |
| 4 | Major | Significant impact on project objectives, quality, or delivery |
| 5 | Critical | Threatens project viability, release readiness, data integrity, or other essential objectives |

Impact SHOULD consider relevant dimensions, including:

- Player experience.
- Technical stability.
- Project schedule.
- Development effort.
- Product quality.
- Financial or resource constraints.
- Legal or licensing exposure.
- Data integrity.
- Release viability.

The highest relevant impact SHOULD be used when a risk affects multiple dimensions.

### 7.3. Risk Score

A simple risk score MAY be calculated as:

`Risk Score = Likelihood × Impact`

The resulting score ranges from 1 to 25.

### 7.4. Risk Priority

Use the following default priority ranges:

| Score | Priority | Recommended Response |
|---|---|---|
| 1–4 | Low | Monitor or accept |
| 5–9 | Medium | Define an appropriate response |
| 10–16 | High | Prioritize mitigation and regular review |
| 17–25 | Critical | Immediate attention and owner review |

These ranges are a prioritization aid, not an automatic decision mechanism.

A risk with a low numerical score MAY still require immediate action when it involves severe legal, security, privacy, or data integrity consequences.

### 7.5. Assessment Confidence

Risk assessments SHOULD distinguish between the estimated risk level and confidence in that estimate.

Confidence MAY be recorded as:

- **High:** Supported by reliable evidence.
- **Medium:** Supported by partial evidence or reasonable assumptions.
- **Low:** Based on limited information or significant uncertainty.

Low-confidence assessments SHOULD trigger investigation when the potential impact is significant.

## 8. Risk Response Strategies

Each significant risk SHOULD have an appropriate response strategy.

### 8.1. Avoid

Change the plan or approach to eliminate the risk.

Examples:

- Remove an unnecessary feature with unacceptable technical complexity.
- Replace an unreliable dependency.
- Avoid an unsupported platform.
- Select a simpler architecture.

### 8.2. Mitigate

Reduce the likelihood or impact of the risk.

Examples:

- Build a technical prototype.
- Introduce automated testing.
- Add data validation.
- Reduce feature scope.
- Improve asset optimization.
- Establish backups.
- Validate integrations earlier.

### 8.3. Transfer

Move some responsibility or exposure to another party when appropriate.

Examples:

- Use a supported third-party service with defined responsibilities.
- Obtain professional legal review.
- Use a contractual service agreement.

Transferring responsibility does not eliminate the need to monitor the remaining risk.

### 8.4. Accept

Acknowledge the risk and decide not to take additional mitigation action.

Acceptance MAY be appropriate when:

- The potential impact is low.
- Mitigation would cost more than the expected benefit.
- The risk is unavoidable.
- The project owner explicitly accepts the consequences.

Significant accepted risks MUST be documented.

### 8.5. Contingency Planning

A contingency plan defines what the project will do if a risk occurs.

Examples:

- Use an alternative technical implementation.
- Reduce the feature scope.
- Replace an unavailable asset.
- Revert a problematic release.
- Restore a known-good save backup.
- Delay a milestone until a critical dependency is resolved.

Mitigation reduces the chance or impact of a risk. Contingency planning prepares the project to respond if it materializes.

## 9. Risk Ownership

### 9.1. Risk Owner

Every High or Critical risk MUST have an assigned owner.

Medium risks SHOULD have an owner when they require active mitigation.

The risk owner is responsible for:

- Monitoring the risk.
- Reviewing its assessment.
- Coordinating mitigation activities.
- Reporting changes.
- Identifying when escalation is necessary.
- Confirming when the risk can be closed.

### 9.2. Project Owner

The project owner is responsible for:

- Reviewing significant risks.
- Approving major risk responses.
- Accepting significant residual risks.
- Resolving conflicting priorities.
- Authorizing major scope or direction changes.
- Deciding whether project work should continue, pause, or be cancelled.

### 9.3. Contributors and AI Agents

Contributors and AI agents SHOULD report newly identified risks when they discover them.

They MAY propose assessments and mitigation strategies.

They MUST NOT silently accept significant risks or change approved project direction without authorization.

## 10. Risk Register

### 10.1. Purpose

The risk register is the project's primary record of identified and actively managed risks.

Each project SHOULD maintain a risk register appropriate to its complexity.

Recommended location:

`game_project/docs/production/risk_register.md`

The project MAY use a project management tool or another structured format when it provides a reliable source of truth.

### 10.2. Required Information

Each risk SHOULD contain:

| Field | Description |
|---|---|
| Risk ID | Unique identifier |
| Title | Concise risk description |
| Category | Relevant risk category |
| Description | Cause, uncertain event, and potential impact |
| Likelihood | Estimated likelihood from 1 to 5 |
| Impact | Estimated impact from 1 to 5 |
| Score | Likelihood multiplied by impact |
| Priority | Low, Medium, High, or Critical |
| Status | Current risk status |
| Owner | Person responsible for monitoring the risk |
| Response Strategy | Avoid, Mitigate, Transfer, or Accept |
| Mitigation | Planned actions to reduce the risk |
| Contingency | Planned response if the risk occurs |
| Review Date | Date of the latest assessment |

Additional information MAY include:

- Assessment confidence.
- Affected features or milestones.
- Dependencies.
- Evidence and references.
- Target mitigation date.
- Residual risk.
- Related issues.
- Decision history.

### 10.3. Risk Identification

Risk IDs SHOULD be unique within the project.

Recommended format:

`RISK-001`

Examples:

- `RISK-001`
- `RISK-002`
- `RISK-003`

IDs MUST NOT be reused after a risk is closed.

### 10.4. Risk Status

Use the following statuses:

| Status | Description |
|---|---|
| Identified | Risk has been recorded but not fully assessed |
| Assessing | Risk is being investigated or evaluated |
| Open | Risk is active and requires monitoring |
| Mitigating | Mitigation actions are in progress |
| Accepted | Risk has been explicitly accepted |
| Materialized | Risk has occurred and requires issue or incident handling |
| Closed | Risk is no longer relevant or has been sufficiently resolved |

A risk marked as Accepted MUST still be monitored when its consequences remain relevant.

A risk MUST NOT be marked Closed merely because mitigation work was completed. Its remaining exposure must be evaluated first.

## 11. Risk Monitoring and Review

### 11.1. Continuous Monitoring

Risks SHOULD be monitored throughout development.

Review frequency SHOULD reflect their priority and volatility.

Recommended minimum review frequency:

| Priority | Suggested Review Frequency |
|---|---|
| Critical | Immediate attention and frequent follow-up |
| High | At least once per development iteration |
| Medium | During relevant milestone or periodic reviews |
| Low | During normal project reviews or when conditions change |

Projects MAY adjust these frequencies.

### 11.2. Review Triggers

A risk SHOULD be reassessed when:

- New evidence becomes available.
- A mitigation action is completed.
- A dependency changes.
- Project scope changes.
- A milestone is delayed.
- A prototype invalidates an assumption.
- A defect reveals a previously unknown weakness.
- A new platform or technology is introduced.
- An external service or policy changes.
- The risk materializes.

### 11.3. Reassessment

During reassessment:

- Verify whether the original cause still exists.
- Review the likelihood.
- Review the potential impact.
- Recalculate the risk score.
- Evaluate mitigation effectiveness.
- Identify remaining exposure.
- Update the response strategy.
- Record significant changes.

### 11.4. Residual Risk

Residual risk is the remaining exposure after mitigation actions have been applied.

Residual risk SHOULD be reassessed rather than automatically assumed to be Low.

Significant residual risks MUST be communicated to the project owner.

## 12. Risk Escalation

Risks MUST be escalated when their potential impact exceeds the authority or capacity of the assigned owner.

Immediate escalation SHOULD occur when:

- A Critical risk is identified.
- Project viability is threatened.
- A critical milestone is likely to fail.
- Significant data loss or corruption is possible.
- A serious security or privacy concern is discovered.
- Legal or licensing violations are suspected.
- A release may be unsafe or unacceptable.
- An approved mitigation strategy is no longer viable.

Escalation SHOULD include:

- Risk description.
- Potential impact.
- Current assessment.
- Available evidence.
- Actions already taken.
- Recommended response.
- Decision or support required.

## 13. Risk Management Across the Project Lifecycle

Risk management SHOULD evolve as the project progresses.

### 13.1. Project Initiation

Focus on:

- Project feasibility.
- Resource constraints.
- Unclear objectives.
- Initial technical assumptions.
- External dependencies.

### 13.2. Concept Development

Focus on:

- Unvalidated gameplay concepts.
- Unclear audience expectations.
- Design complexity.
- Scope uncertainty.
- Uncertain production requirements.

### 13.3. Pre-production

Focus on:

- Architecture decisions.
- Technical feasibility.
- Asset requirements.
- Tooling dependencies.
- Production estimates.
- Major design assumptions.

### 13.4. Prototyping

Focus on:

- Technical limitations.
- Gameplay feasibility.
- Performance constraints.
- Unsuccessful design experiments.
- Uncertain integration approaches.

### 13.5. Production

Focus on:

- Development bottlenecks.
- Feature dependencies.
- Scope growth.
- Technical debt.
- Asset production delays.
- Integration problems.
- Quality and regression risks.

### 13.6. Alpha

Focus on:

- Incomplete gameplay systems.
- Progression problems.
- Critical defects.
- Missing content.
- Save and loading reliability.
- End-to-end stability.

### 13.7. Beta

Focus on:

- Remaining defects.
- Performance.
- Compatibility.
- Balance.
- Usability.
- Content completeness.
- Regression risks.

### 13.8. Release Preparation

Focus on:

- Build integrity.
- Platform requirements.
- Release-blocking defects.
- Licensing and attribution.
- Save compatibility.
- Distribution dependencies.
- Release readiness.

### 13.9. Post-release

Focus on:

- Critical player-impacting defects.
- Data integrity.
- Platform compatibility.
- External service changes.
- Maintenance capacity.
- Long-term dependency risks.

## 14. Risk Management and Production Planning

Risk management MUST be connected to project planning.

### 14.1. Backlog Integration

Mitigation activities SHOULD be represented as backlog items when they require meaningful work.

Examples:

- Investigate an engine limitation.
- Build a prototype.
- Replace a dependency.
- Add automated validation.
- Optimize a performance bottleneck.
- Improve save recovery.

Backlog items SHOULD reference the relevant risk ID when practical.

### 14.2. Milestone Integration

Significant risks SHOULD be considered during milestone planning.

Milestones MAY include risk reduction or validation as explicit objectives.

### 14.3. Schedule and Scope

Risk assessments SHOULD inform:

- Estimates.
- Priorities.
- Dependencies.
- Milestone targets.
- Feature scope.
- Release planning.

High uncertainty SHOULD be reflected in project plans rather than hidden behind overly precise estimates.

### 14.4. Risk-Driven Development

When uncertainty is high, prioritize work that reduces important risks.

A small prototype or technical investigation MAY provide more value than immediately implementing the complete feature.

## 15. Risk Analysis Techniques

Projects MAY use additional analysis techniques when they provide meaningful value.

### 15.1. Assumption Mapping

Identify assumptions and classify them by importance and uncertainty.

High-impact, low-confidence assumptions SHOULD be validated early.

### 15.2. Dependency Analysis

Review dependencies between features, systems, assets, tools, and external services.

Identify dependencies that could block multiple parts of the project.

### 15.3. Root Cause Analysis

When a risk materializes, investigate contributing factors to understand why it occurred.

Avoid treating symptoms as the only cause.

### 15.4. Failure Mode and Effects Analysis

For critical systems, projects MAY use Failure Mode and Effects Analysis (FMEA) to identify:

- Potential failure modes.
- Their causes.
- Their effects.
- Existing controls.
- Recommended actions.

This technique is particularly useful for persistence, networking, critical gameplay systems, and complex integrations.

### 15.5. Scenario Analysis

Evaluate plausible scenarios to understand how different conditions could affect the project.

Examples:

- A critical plugin becomes unavailable.
- A feature takes twice as long as estimated.
- A target platform introduces new requirements.
- A save migration fails.
- A key gameplay mechanic does not pass playtesting.

Formal quantitative analysis is optional unless the project requires it.

## 16. AI-Assisted Risk Management

AI agents MAY assist with:

- Identifying potential risks in design documents.
- Reviewing architecture proposals.
- Analyzing feature dependencies.
- Evaluating technical assumptions.
- Suggesting mitigation strategies.
- Preparing risk assessments.
- Identifying inconsistencies in risk records.
- Reviewing milestone and release risks.
- Summarizing changes in risk exposure.

AI agents MUST:

1. Base assessments on available project evidence.
2. Distinguish facts from assumptions.
3. Explain uncertainty.
4. Avoid presenting speculative risks as confirmed problems.
5. Identify potential impacts and affected systems.
6. Reference related project documentation when applicable.
7. Report significant newly identified risks.
8. Preserve the existing risk register structure.
9. Request approval for significant risk acceptance or project changes.

AI agents MUST NOT:

- Invent project incidents or evidence.
- Mark risks as resolved without verification.
- Silently change risk priorities.
- Accept Critical or High risks on behalf of the project owner.
- Hide uncertainty behind unsupported numerical precision.
- Independently change project scope to avoid reporting a risk.

The project owner retains responsibility for significant risk decisions.

## 17. Risk Register Template

Use the following template when creating a project risk register.

### Risk Register

| ID | Title | Category | Likelihood | Impact | Score | Priority | Status | Owner |
|---|---|---|---:|---:|---:|---|---|---|
| RISK-001 | Example risk | Technical | 3 | 4 | 12 | High | Open | Project Owner |

### Risk Details

#### RISK-001: Example Risk Title

**Category:** Technical

**Status:** Open

**Priority:** High

**Owner:** Project Owner

**Description:**

If [cause or condition], then [uncertain event] may occur, resulting in [potential impact].

**Assessment:**

- Likelihood: 3 - Possible
- Impact: 4 - Major
- Risk Score: 12
- Assessment Confidence: Medium

**Affected Areas:**

- Relevant feature or system.
- Related milestone.
- External dependency, when applicable.

**Response Strategy:** Mitigate

**Mitigation Actions:**

- Action 1.
- Action 2.
- Action 3.

**Contingency Plan:**

Describe the response if the risk materializes.

**Residual Risk:**

Describe the remaining exposure after mitigation.

**Evidence and References:**

- Relevant documents.
- Prototype results.
- Test results.
- Related issues.

**Review History:**

| Date | Assessment Change | Decision or Action |
|---|---|---|
| YYYY-MM-DD | Initial assessment | Risk identified |

## 18. Risk Review Checklist

Use this checklist during project, milestone, or release reviews.

### Identification

- [ ] Relevant risks have been identified.
- [ ] Important assumptions have been reviewed.
- [ ] Dependencies have been evaluated.
- [ ] New technical and production uncertainties have been considered.
- [ ] Existing issues have been distinguished from potential risks.

### Assessment

- [ ] Significant risks have likelihood assessments.
- [ ] Potential impacts have been evaluated.
- [ ] Priorities reflect actual project exposure.
- [ ] Assessment confidence is understood.
- [ ] Critical risks have been escalated.

### Response

- [ ] Significant risks have owners.
- [ ] Appropriate response strategies are defined.
- [ ] Mitigation actions are actionable.
- [ ] Contingency plans exist where necessary.
- [ ] Accepted risks have appropriate approval.

### Monitoring

- [ ] Risk statuses are current.
- [ ] Mitigation progress is reviewed.
- [ ] Residual risks are evaluated.
- [ ] Materialized risks are handled as issues.
- [ ] Risk records reflect current project conditions.

### Documentation

- [ ] The risk register is updated.
- [ ] Important decisions are recorded.
- [ ] Relevant backlog items reference risks.
- [ ] Significant milestone and release risks are documented.

## 19. Exceptions

Projects MAY simplify risk management activities according to:

- Project size.
- Development complexity.
- Available resources.
- Experimental objectives.
- Technical constraints.
- Risk exposure.

Simplification MUST NOT result in ignoring significant risks.

Critical risks involving data integrity, security, privacy, legal compliance, or release safety MUST receive appropriate attention regardless of project size.

Significant deviations SHOULD be documented and approved by the project owner.

## 20. Related Documents

- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/GAME_DEVELOPMENT_LIFECYCLE.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md`
- `docs/02_technical_standards/TESTING_STRATEGY.md`
- `docs/04_production_standards/BACKLOG_MANAGEMENT.md`
- `docs/04_production_standards/MILESTONE_GUIDELINES.md`
- `docs/04_production_standards/PROJECT_LIFECYCLE.md`
- `docs/04_production_standards/RELEASE_PROCESS.md`
- `docs/04_production_standards/POSTMORTEM_GUIDELINES.md`

## 21. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- Studio risk management practices change.
- New categories of project risk emerge.
- Development tools or workflows introduce new risks.
- Recurring project problems reveal weaknesses in existing practices.
- Postmortems identify opportunities for improvement.

Changes MUST preserve the distinction between reusable studio risk management practices and project-specific risk assessments.

The project owner is responsible for approving changes to these guidelines.