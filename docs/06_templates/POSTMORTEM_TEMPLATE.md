# Postmortem Template

> **Purpose:** This template guides AI agents in generating project-specific postmortem documents.
>
> A postmortem is a structured review of completed work or a significant event. Its purpose is to understand what happened, evaluate outcomes, identify lessons, and define actionable improvements.
>
> This template is an authoring specification, not the final postmortem. AI agents must use available project records and supporting evidence to generate the corresponding project-specific document.
>
> Postmortems are intended for learning and improvement, not assigning blame. Do not invent events, causes, metrics, decisions, or outcomes that cannot be supported by available evidence.

---

## 1. Document Generation Instructions

### 1.1 Generation Objective

Generate a factual, balanced, and actionable postmortem that evaluates the selected work or event.

The generated document must:

- Explain what was planned and what actually happened.
- Evaluate the objectives and expected outcomes.
- Identify what went well and what did not.
- Analyze significant deviations, problems, and unexpected results.
- Distinguish observed facts from interpretations and hypotheses.
- Identify contributing factors and root causes where evidence permits.
- Capture lessons that can improve future work.
- Define actionable improvement recommendations.
- Connect approved improvement actions to the project backlog when appropriate.

### 1.2 Intended Output

| Property | Requirement |
|---|---|
| Output Filename | `[YYYY-MM-DD]-[subject].md` |
| Recommended Location | `game_project/docs/production/postmortems/` |
| Document Type | Project-specific postmortem record |
| Primary Audience | Project owner, developers, designers, AI agents |
| Source of Truth | Actual project records and verified evidence |
| Document Status | Draft until reviewed |
| Language | [Use the project's designated documentation language] |

### 1.3 Postmortem Subject

Identify the work or event being reviewed.

Possible subjects include:

- Project milestone.
- Sprint or development iteration.
- Feature or gameplay system.
- Technical implementation.
- Release or deployment.
- Production incident.
- Failed or cancelled initiative.
- Significant design or production decision.

The postmortem must have a clearly defined scope. Do not combine unrelated events into one report unless they are directly connected.

### 1.4 Source Documents and Evidence

Before generating the postmortem, inspect relevant project records.

**Potential sources include:**

- Milestone records.
- Sprint records.
- Backlog items.
- Project plans and schedules.
- Definition of Done.
- Acceptance criteria.
- Pull requests and code review discussions.
- Git history and commit records.
- CI/CD results and test reports.
- Bug reports and issue records.
- Playtesting reports.
- Performance measurements.
- Risk registers.
- Architecture Decision Records.
- Release records and changelogs.
- Previous postmortems.
- Relevant project discussions and approved decisions.

Only use sources that actually exist and are accessible.

### 1.5 Evidence and Information Classification

Every important conclusion must be appropriately supported and classified.

| Classification | Meaning |
|---|---|
| Verified Fact | Directly supported by a reliable project record, measurement, or confirmed observation. |
| Reported Observation | Described by a participant but not independently verified. |
| Interpretation | An explanation or evaluation based on available facts. |
| Hypothesis | A possible explanation that requires further validation. |
| Recommendation | A proposed action intended to improve future work. |
| Unknown | Information that cannot be established from available evidence. |

Do not present interpretations or hypotheses as verified facts.

### 1.6 Source Authority

When sources disagree, prefer:

1. Verified project records and direct measurements.
2. Approved project decisions and official records.
3. Version-controlled documentation and implementation history.
4. Test reports, bug reports, and production records.
5. Participant observations and feedback.
6. Informal discussions and retrospective recollections.
7. AI-generated summaries or assumptions.

If conflicting evidence cannot be reconciled, document the discrepancy rather than silently choosing one version.

### 1.7 Generation Rules

AI agents MUST:

1. Inspect the relevant project records before generating the report.
2. Establish the postmortem's scope and review period.
3. Use evidence to support important factual claims.
4. Distinguish planned outcomes from actual outcomes.
5. Avoid assigning blame to individuals.
6. Avoid treating correlation as proof of causation.
7. Identify uncertainty and missing information.
8. Consider both successful and unsuccessful aspects of the work.
9. Propose practical improvements proportional to the problem.
10. Avoid creating duplicate backlog items for existing improvement work.
11. Preserve historical accuracy when describing decisions and events.
12. Never modify historical records to make the project appear more successful.
13. Never claim that an improvement action has been completed without evidence.
14. Keep the report concise enough to be useful while preserving important findings.

If evidence is insufficient, explicitly state what could not be verified.

---

# Generated Project Document Structure

The AI agent must use the following structure when generating the project-specific postmortem.

## 2. Document Information

| Field | Value |
|---|---|
| Document Title | [Postmortem title] |
| Postmortem ID | `PM-XXX` |
| Project | [Project name] |
| Subject | [Milestone, sprint, feature, release, incident, etc.] |
| Related ID | [Milestone ID, sprint ID, backlog ID, release version, etc.] |
| Review Period | [Start date – End date] |
| Review Date | [YYYY-MM-DD] |
| Author | [Author or AI-assisted] |
| Reviewer | [Project owner or reviewer] |
| Status | Draft |
| Version | 1.0 |

### 2.1 Purpose

Explain why this postmortem is being conducted and what it intends to evaluate.

### 2.2 Scope

Define what is included in the review.

**Included:**
- [Work or event being reviewed]
- [Relevant decisions and outcomes]
- [Relevant production and quality aspects]

**Excluded:**
- [Unrelated work]
- [Areas not covered due to insufficient evidence]
- [Other exclusions]

### 2.3 Review Context

Provide a brief explanation of the circumstances surrounding the work or event.

Include relevant project phase, objectives, constraints, and conditions.

### 2.4 Evidence Sources

| Source | Description | Reference | Reliability |
|---|---|---|---|
| [Source] | [What it contains] | [Path or link] | [High / Medium / Low] |

Only include sources actually inspected.

---

## 3. Executive Summary

Provide a concise overview of the postmortem.

Include:

- What was planned.
- What actually happened.
- Whether the objectives were achieved.
- The most important successes.
- The most significant problems.
- The most important lessons.
- The recommended improvements.

The executive summary should allow someone unfamiliar with the work to understand its outcome quickly.

### 3.1 Overall Assessment

**Outcome:** [Successful / Partially Successful / Unsuccessful / Inconclusive]

**Summary:**

[Explain the overall result and the most important reasons behind it.]

Do not equate successful completion with perfect execution. A completed milestone can still reveal significant problems worth addressing.

---

## 4. Objectives and Expected Outcomes

### 4.1 Original Objectives

Document the objectives established before the work began.

| Objective ID | Original Objective | Expected Result | Source |
|---|---|---|---|
| [OBJ-01] | [Objective] | [Expected result] | [Reference] |

### 4.2 Success Criteria

| Criterion ID | Original Success Criterion | Expected Target | Source |
|---|---|---|---|
| [SC-01] | [Criterion] | [Target] | [Reference] |

### 4.3 Original Assumptions and Constraints

Summarize the assumptions, dependencies, and constraints that influenced planning.

### 4.4 Changes During Execution

Document significant changes to objectives, scope, priorities, or constraints.

| Change | Original State | Updated State | Reason | Approval |
|---|---|---|---|---|
| [Change] | [Original] | [Updated] | [Reason] | [Reference] |

Distinguish approved changes from informal or unapproved deviations.

---

## 5. Actual Results

### 5.1 Outcome Summary

Describe what was actually completed or what happened during the review period.

### 5.2 Objective Evaluation

| Objective ID | Expected Result | Actual Result | Evaluation | Evidence |
|---|---|---|---|---|
| [OBJ-01] | [Expected] | [Actual] | [Achieved / Partially Achieved / Not Achieved] | [Reference] |

### 5.3 Deliverable Evaluation

| Deliverable | Expected State | Actual State | Evaluation | Evidence |
|---|---|---|---|---|
| [Deliverable] | [Expected] | [Actual] | [Accepted / Partial / Rejected / Unknown] | [Reference] |

### 5.4 Schedule and Effort

Compare planned and actual execution where reliable information exists.

| Measurement | Planned | Actual | Variance |
|---|---:|---:|---:|
| Start Date | [Date] | [Date] | [Difference] |
| Completion Date | [Date] | [Date] | [Difference] |
| Estimated Effort | [Estimate] | [Actual] | [Difference] |

Explain important deviations and identify whether the comparison is based on complete records or estimates.

### 5.5 Quality Results

Summarize relevant quality outcomes.

Consider:

- Functional correctness.
- Defects discovered.
- Test execution results.
- Regression issues.
- Performance.
- Stability.
- Usability and player experience.
- Art and audio quality.
- Documentation completeness.

Use actual measurements and test results when available.

### 5.6 Unexpected Outcomes

Document results that were not anticipated during planning.

Include positive and negative surprises.

---

## 6. What Went Well

Identify practices, decisions, tools, processes, or circumstances that contributed positively.

| Observation | Supporting Evidence | Positive Impact | Should Be Repeated? |
|---|---|---|---|
| [Observation] | [Evidence] | [Impact] | [Yes / No / Depends] |

Consider:

- Effective planning.
- Clear requirements and acceptance criteria.
- Successful technical decisions.
- Efficient implementation.
- Useful automation.
- Good testing practices.
- Effective collaboration.
- Appropriate use of AI agents.
- Successful art and audio workflows.
- Good risk management.
- Positive player feedback.

Explain why the identified practices worked, not merely that they were successful.

---

## 7. What Did Not Go Well

Identify problems, inefficiencies, unexpected difficulties, and shortcomings.

| Observation | Supporting Evidence | Impact | Contributing Factors |
|---|---|---|---|
| [Observation] | [Evidence] | [Impact] | [Factors] |

Consider:

- Unclear requirements.
- Unrealistic estimates.
- Scope expansion.
- Technical difficulties.
- Architectural problems.
- Inadequate testing.
- Integration issues.
- Poor documentation.
- Asset production delays.
- Performance problems.
- Communication or coordination issues.
- Ineffective AI-generated work.
- Repeated rework.
- Unresolved dependencies.

Describe problems objectively. Focus on conditions and processes rather than blaming individuals.

---

## 8. Root Cause and Contributing Factor Analysis

### 8.1 Significant Problems

Select the most important problems that require deeper analysis.

| Problem ID | Problem | Impact | Priority |
|---|---|---|---|
| PROB-01 | [Problem] | [Impact] | [Critical / High / Medium / Low] |

### 8.2 Root Cause Analysis

For each significant problem, use an appropriate analysis method.

**Problem ID:** [PROB-XXX]

- **Observed problem:** [What happened]
- **Evidence:** [Supporting records]
- **Immediate cause:** [Direct cause, if established]
- **Contributing factors:** [Factors that increased the likelihood or impact]
- **Underlying cause:** [Root cause, if supported]
- **Confidence:** [High / Medium / Low]
- **Remaining uncertainty:** [What is not known]

### 8.3 Optional Analysis Techniques

Use only when appropriate:

- Five Whys.
- Cause-and-effect analysis.
- Timeline analysis.
- Dependency analysis.
- Failure Mode and Effects Analysis (FMEA).
- Assumption analysis.
- Technical investigation.

Do not force a root cause when the available evidence does not support one.

### 8.4 Distinguishing Symptoms from Causes

Explain whether the identified problem is:

- An isolated failure.
- A recurring symptom.
- A process weakness.
- A technical limitation.
- A planning assumption that proved incorrect.
- An external dependency.
- An unresolved issue requiring further investigation.

### 8.5 Confidence and Evidence Limitations

Identify conclusions that require additional investigation.

Do not overstate certainty.

---

## 9. Production and Workflow Evaluation

### 9.1 Planning and Estimation

Evaluate whether the work was appropriately scoped and estimated.

Consider:

- Clarity of objectives.
- Backlog readiness.
- Work breakdown.
- Complexity estimation.
- Capacity assumptions.
- Dependency identification.
- Scope management.

### 9.2 Execution and Workflow

Evaluate the effectiveness of the production workflow.

Consider:

- Work prioritization.
- Task organization.
- Branching and integration.
- Review practices.
- Work in progress.
- Blocker resolution.
- Iteration and feedback cycles.

### 9.3 Decision-Making

Review important decisions.

| Decision | Context | Outcome | Assessment | Future Implication |
|---|---|---|---|---|
| [Decision] | [Context] | [Outcome] | [Assessment] | [Implication] |

### 9.4 Resource and Capacity Management

Evaluate whether available resources, tools, and capacity were appropriate.

### 9.5 Production Improvement Opportunities

Identify specific ways to improve future planning and execution.

---

## 10. Technical and Quality Evaluation

### 10.1 Architecture and Implementation

Evaluate relevant technical decisions and implementation quality.

Consider:

- Architecture suitability.
- Maintainability.
- Modularity.
- Reusability.
- Technical debt.
- Error handling.
- Integration complexity.
- Godot and GDScript practices.

### 10.2 Testing and Quality Assurance

Evaluate:

- Testing strategy suitability.
- Automated test effectiveness.
- Manual testing.
- Regression prevention.
- Test coverage limitations.
- Defect detection timing.
- CI/CD reliability.
- Quality gate effectiveness.

### 10.3 Performance and Stability

Review relevant performance and stability results.

Use measured evidence when available. Do not infer performance problems from subjective impressions alone.

### 10.4 Documentation

Evaluate whether documentation was accurate, accessible, sufficient, and maintained.

### 10.5 Technical Improvement Opportunities

Identify improvements that could prevent recurrence or improve maintainability.

---

## 11. Art, Audio, and Content Evaluation

Complete this section when relevant to the postmortem.

### 11.1 Art Production

Evaluate:

- Art direction consistency.
- Asset quality.
- Production efficiency.
- Import and integration workflow.
- Asset reuse.
- Technical limitations.
- Review and approval.

### 11.2 Audio Production

Evaluate:

- Audio direction consistency.
- Sound design quality.
- Music integration.
- Dialogue and voice production.
- Mixing and mastering.
- Engine integration.
- Audio performance.

### 11.3 Game Content

Evaluate:

- Gameplay content quality.
- Level and encounter design.
- Narrative consistency.
- Player experience.
- Difficulty and balancing.
- Content production efficiency.

### 11.4 Improvement Opportunities

Document concrete improvements for future art, audio, and content production.

---

## 12. AI-Assisted Development Evaluation

Complete this section when AI tools or agents contributed to the reviewed work.

### 12.1 AI Usage Summary

| Tool / Agent | Purpose | Work Performed | Outcome |
|---|---|---|---|
| [Tool / Agent] | [Purpose] | [Work] | [Result] |

### 12.2 Effectiveness

Evaluate:

- Quality of generated output.
- Accuracy of context understanding.
- Adherence to project documentation.
- Code and design consistency.
- Reliability of generated tests.
- Amount of human correction required.
- Time saved or additional effort introduced.

Use actual evidence where possible.

### 12.3 Problems and Limitations

Identify issues such as:

- Missing context.
- Hallucinated requirements.
- Inconsistent implementation.
- Duplicate documentation.
- Unverified code.
- Poor architectural suggestions.
- Incomplete testing.
- Incorrect assumptions.
- Excessive human review or rework.

### 12.4 AI Workflow Improvements

Document practical changes to improve future AI-assisted work.

Examples:

- Improve agent instructions.
- Improve source document organization.
- Add validation requirements.
- Refine task breakdown.
- Introduce clearer approval boundaries.
- Improve automated verification.
- Provide better implementation examples.

### 12.5 Human Oversight

Evaluate whether human review and approval were appropriate for the decisions and work performed.

---

## 13. Lessons Learned

Summarize the most important knowledge gained.

| Lesson ID | Lesson | Supporting Observation | Future Application |
|---|---|---|---|
| LESSON-01 | [Lesson] | [Evidence] | [How it should be applied] |
| LESSON-02 | [Lesson] | [Evidence] | [How it should be applied] |

Lessons should be specific and reusable.

Avoid vague conclusions such as "communicate better" or "test more." Explain what should change and under what circumstances.

---

## 14. Improvement Actions

Convert important lessons into actionable improvements.

### 14.1 Improvement Action Register

| Action ID | Improvement Action | Related Finding | Priority | Owner | Status |
|---|---|---|---|---|---|
| IMP-01 | [Action] | [Finding ID] | [Critical / High / Medium / Low] | [Owner] | Proposed |
| IMP-02 | [Action] | [Finding ID] | [Priority] | [Owner] | Proposed |

### 14.2 Action Details

For each significant action, document:

**Action ID:** [IMP-XXX]

- **Problem addressed:** [Description]
- **Proposed improvement:** [Action]
- **Expected benefit:** [Benefit]
- **Implementation requirements:** [Requirements]
- **Dependencies:** [Dependencies]
- **Success measurement:** [How effectiveness will be evaluated]
- **Target date:** [Date or TBD]
- **Related backlog item:** [ID or TBD]

### 14.3 Prioritization

Prioritize improvement actions based on:

- Impact of the original problem.
- Likelihood of recurrence.
- Expected improvement.
- Implementation effort.
- Dependencies.
- Project priorities.

Avoid creating too many improvement actions. Focus on changes that are likely to produce meaningful benefits.

### 14.4 Backlog Integration

Identify whether each action should become a project backlog item.

| Action ID | Backlog Item | Existing / New | Reference |
|---|---|---|---|
| IMP-01 | [Title] | [Existing / New / Not Required] | [Backlog ID] |

Do not create duplicate backlog items. The project owner must approve new work and its prioritization.

### 14.5 Follow-up Evaluation

Explain when and how the effectiveness of significant improvements should be evaluated.

---

## 15. Final Assessment and Conclusion

### 15.1 Overall Evaluation

Summarize the outcome of the reviewed work or event.

Evaluate:

- Whether the intended objectives were achieved.
- Whether the quality expectations were met.
- Whether the execution process was effective.
- What contributed most to success or failure.
- What should change in future work.

### 15.2 Most Important Findings

List the most important findings from the postmortem.

1. [Finding]
2. [Finding]
3. [Finding]

### 15.3 Key Recommendations

List the most important recommendations for future project work.

1. [Recommendation]
2. [Recommendation]
3. [Recommendation]

### 15.4 Final Conclusion

Provide a concise conclusion explaining what the project should carry forward from this experience.

---

## 16. Evidence and References

List the records used to support the postmortem.

| Reference ID | Source | Description | Location |
|---|---|---|---|
| REF-01 | [Source type] | [Description] | [Path or link] |
| REF-02 | [Source type] | [Description] | [Path or link] |

Ensure references point to actual project records.

Do not invent paths, links, or document identifiers.

---

## 17. AI-Assisted Postmortem Generation Guidelines

AI agents generating or updating postmortems MUST:

1. Inspect relevant project records before writing.
2. Identify the reviewed period and scope.
3. Use actual evidence to establish what happened.
4. Distinguish facts, observations, interpretations, hypotheses, and recommendations.
5. Never fabricate metrics, dates, events, decisions, or participant statements.
6. Never assign blame or infer personal motivations without reliable evidence.
7. Avoid presenting assumptions as root causes.
8. Include uncertainty when evidence is incomplete.
9. Evaluate successes as well as problems.
10. Propose improvements that are specific and actionable.
11. Link improvement actions to existing backlog items when applicable.
12. Preserve the historical accuracy of the reviewed work.
13. Avoid modifying historical records while preparing the postmortem.
14. Keep the report proportional to the importance of the reviewed work.
15. Never mark improvement actions as completed without evidence.
16. Never mark the postmortem as approved without explicit project owner authorization.

### 17.1 Missing Information

If relevant information is unavailable:

- Identify what is missing.
- Explain which conclusions are affected.
- Avoid filling gaps with invented information.
- Mark affected findings as uncertain or inconclusive.
- Record additional investigation as a possible improvement action when appropriate.

### 17.2 Human Review

The project owner must review:

- Accuracy of factual statements.
- Interpretation of significant events.
- Root cause conclusions.
- Improvement recommendations.
- Proposed backlog changes.
- Final assessment.

The AI agent may prepare and organize the analysis but cannot independently approve the postmortem.

---

## 18. Review and Approval

### 18.1 Review Checklist

- [ ] The review scope is clearly defined.
- [ ] Relevant project evidence was inspected.
- [ ] Planned and actual outcomes are compared.
- [ ] Successes and problems are both documented.
- [ ] Important conclusions have supporting evidence.
- [ ] Facts are distinguished from interpretations and hypotheses.
- [ ] Root cause claims are appropriately qualified.
- [ ] Lessons are specific and actionable.
- [ ] Improvement actions are prioritized.
- [ ] Backlog references are accurate.
- [ ] Missing information and uncertainties are documented.
- [ ] The report does not assign blame.
- [ ] The project owner has reviewed the report.

### 18.2 Approval

| Role | Name | Status | Date |
|---|---|---|---|
| Postmortem Author | [Name] | [Pending / Reviewed] | [Date] |
| Project Owner | [Name] | [Pending / Approved] | [Date] |

### 18.3 Change History

| Version | Date | Author | Description |
|---|---|---|---|
| 1.0 | [YYYY-MM-DD] | [Author] | Initial postmortem |

### 18.4 Related Documents

- Postmortem Guidelines: `docs/04_production_standards/POSTMORTEM_GUIDELINES.md`
- Milestone Guidelines: `docs/04_production_standards/MILESTONE_GUIDELINES.md`
- Backlog Management: `docs/04_production_standards/BACKLOG_MANAGEMENT.md`
- Sprint Workflow: `docs/04_production_standards/SPRINT_WORKFLOW.md`
- Risk Management: `docs/04_production_standards/RISK_MANAGEMENT.md`
- Definition of Done: `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- QA Strategy: `docs/05_qa_standards/QA_STRATEGY.md`
- Bug Reporting: `docs/05_qa_standards/BUG_REPORTING.md`

---

**End of Postmortem**
