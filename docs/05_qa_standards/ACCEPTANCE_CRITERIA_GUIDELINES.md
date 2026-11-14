# Acceptance Criteria Guidelines

## 1. Purpose

This document defines how acceptance criteria are written, reviewed, validated, and maintained throughout game development.

Acceptance criteria establish the specific conditions that a feature, user story, task, or other deliverable must satisfy to be considered acceptable.

They provide a shared understanding between the project owner, developers, testers, and AI agents about:

- What must be delivered.
- What behavior is expected.
- What conditions must be satisfied.
- How correctness will be verified.
- What constitutes successful completion.

The objective is to make work items clear, testable, and aligned with their intended player and project outcomes.

## 2. Scope

These guidelines apply to work items that require explicit acceptance conditions, including:

- Epics.
- Features.
- User stories.
- Tasks.
- Bugs.
- Gameplay mechanics.
- UI/UX functionality.
- Technical systems.
- Art and audio deliverables.
- Performance improvements.
- Documentation.
- Integration work.

Not every minor task requires extensive acceptance criteria. The level of detail SHOULD be proportional to the complexity, risk, and importance of the work.

Acceptance criteria define what must be true for a deliverable to be accepted. They do not replace implementation specifications, test plans, or the Definition of Done.

## 3. Core Principles

### 3.1. Clear and Unambiguous

Each criterion MUST describe an understandable and specific expected outcome.

Avoid vague statements such as:

- The system should work correctly.
- The interface should look good.
- The game should perform well.
- The mechanic should feel responsive.

Replace them with observable conditions that can be evaluated.

### 3.2. Testable and Verifiable

Each criterion MUST be verifiable through an appropriate validation method.

Verification MAY involve:

- Automated tests.
- Manual testing.
- Gameplay evaluation.
- Visual inspection.
- Audio review.
- Performance measurement.
- Code or configuration inspection.
- Documentation review.

A criterion that cannot be meaningfully verified SHOULD be rewritten or supported by a defined evaluation method.

### 3.3. Focused on Outcomes

Acceptance criteria describe expected results rather than prescribing unnecessary implementation details.

They SHOULD explain what the system must do, not dictate how developers must implement it, unless a specific technical constraint is part of the requirement.

### 3.4. Independent and Understandable

Whenever practical, each criterion SHOULD describe one meaningful condition.

Avoid combining several unrelated requirements into one statement.

### 3.5. Aligned with Player Experience

Game-related acceptance criteria SHOULD consider their impact on the player.

They SHOULD describe relevant gameplay behavior, feedback, accessibility, usability, and expected player outcomes where applicable.

### 3.6. Consistent with Project Decisions

Acceptance criteria MUST respect approved project specifications, design decisions, technical standards, and constraints.

Conflicting requirements MUST be resolved before implementation or acceptance.

### 3.7. Proportional to Complexity

Simple work items MAY use a small number of direct criteria.

Complex features SHOULD have more detailed criteria covering relevant behavior, states, edge cases, integration, and failure conditions.

Avoid creating unnecessary criteria that provide no meaningful validation value.

## 4. Acceptance Criteria Structure

Acceptance criteria SHOULD be included in the relevant backlog item or project specification.

Each criterion SHOULD have:

- A unique identifier within its work item, when multiple criteria exist.
- A clear description of the expected outcome.
- A verifiable condition.
- Relevant constraints or assumptions, when necessary.
- A defined verification method when the method is not obvious.

Example:

```markdown
### Acceptance Criteria

- AC-01: The player can open the inventory using the assigned input.
- AC-02: The inventory displays all items currently owned by the player.
- AC-03: Selecting an item displays its name and description.
- AC-04: Closing the inventory returns control to the previous gameplay state.
- AC-05: The inventory cannot be opened while the player is in a state that disables inventory access.
```

Identifiers SHOULD remain stable while the criteria are being referenced by tests, defects, or reviews.

## 5. Writing Acceptance Criteria

### 5.1. Use Observable Language

Describe what a user, player, system, or reviewer can observe.

Prefer:

- The player can equip an available weapon.
- The system prevents the player from equipping an item they do not own.
- The settings menu retains the selected audio volume after reopening.
- The game displays an error message when loading a corrupted save.

Avoid:

- The equipment system is complete.
- The settings implementation is correct.
- Save loading is robust.

### 5.2. Define Expected Conditions

Include the conditions under which the expected behavior must occur.

For example:

Weak:

"The player can interact with objects."

Better:

"When the player is within interaction range of an interactable object, pressing the interaction input triggers that object's interaction behavior."

### 5.3. Include Relevant Constraints

Specify important restrictions or limits.

Examples:

- Maximum inventory capacity.
- Minimum interaction distance.
- Required player state.
- Resource availability.
- Supported input methods.
- Platform limitations.
- Performance budgets.

Avoid repeating constraints already defined clearly in an authoritative specification. Reference the relevant document instead.

### 5.4. Include Failure and Boundary Conditions

Consider what happens when:

- Required data is missing.
- An operation is interrupted.
- The player performs an invalid action.
- A resource is unavailable.
- A system reaches its limit.
- An operation fails.
- The player changes state during an interaction.

Include these conditions when they are relevant to the work item.

### 5.5. Avoid Implementation Assumptions

Acceptance criteria SHOULD NOT unnecessarily prescribe:

- Script names.
- Internal class structures.
- Node hierarchy.
- Variable names.
- Specific algorithms.
- Internal architectural details.

These belong in technical specifications or implementation decisions unless they are explicit acceptance requirements.

## 6. Recommended Writing Formats

Acceptance criteria MAY use different formats depending on the type of work.

### 6.1. Direct Condition Format

Use direct statements for simple and technical requirements.

Format:

"The system [expected behavior] when [condition]."

Example:

"The game pauses when the player opens the pause menu during active gameplay."

### 6.2. Given-When-Then Format

Use Given-When-Then when the behavior depends on a specific initial state, action, and expected result.

Format:

```gherkin
Given [initial context]
When [action or event]
Then [expected result]
```

Example:

```gherkin
Given the player has a health value of 50
When the player receives 20 points of damage
Then the player's health becomes 30
```

This format is particularly useful for:

- Gameplay interactions.
- State transitions.
- Conditional behavior.
- User interface interactions.
- Inventory and equipment systems.
- Save and loading behavior.
- Automated acceptance tests.

### 6.3. Rule-Based Format

Use explicit rules when a feature has multiple conditions or restrictions.

Example:

```markdown
- The player can equip only items available in their inventory.
- Equipping an item replaces the currently equipped item in the same equipment slot.
- Items that do not match the selected equipment slot cannot be equipped.
- An equipment change updates the player character's visible equipment.
```

### 6.4. Visual and Audio Acceptance Format

For visual and audio deliverables, criteria MAY describe observable quality requirements and reference approved art or audio direction.

Example:

- The character animation uses the approved movement style.
- The animation communicates the start and completion of the attack.
- The attack animation does not visibly detach the character's weapon from the hand.
- The sound effect plays when the attack successfully connects.
- The sound effect does not play when the attack is interrupted before execution.

Visual and audio criteria SHOULD reference approved references or specifications when subjective qualities are involved.

## 7. Acceptance Criteria by Work Type

### 7.1. Gameplay Features

Gameplay acceptance criteria SHOULD cover relevant aspects such as:

- Player inputs and actions.
- Gameplay rules.
- Expected outcomes.
- State transitions.
- Resource consumption.
- Feedback.
- Interactions with other mechanics.
- Failure conditions.
- Edge cases.
- Multiplayer behavior, if applicable.

Example:

**Feature:** Health and damage system.

```markdown
- AC-01: The player starts with the configured maximum health value.
- AC-02: Receiving damage decreases the player's current health by the damage amount after applicable reductions.
- AC-03: Current health cannot exceed maximum health.
- AC-04: Current health cannot fall below zero.
- AC-05: Reaching zero health triggers the configured death behavior.
- AC-06: The player receives appropriate feedback when taking damage.
```

### 7.2. User Interface and UX

UI/UX criteria SHOULD cover:

- Visibility and availability.
- Navigation.
- Input behavior.
- Interaction states.
- Feedback.
- Readability.
- Accessibility.
- Persistence of relevant settings.
- Expected behavior across supported resolutions and platforms.

Example:

**Feature:** Audio settings.

```markdown
- AC-01: The player can access audio settings from the settings menu.
- AC-02: The player can adjust the master volume.
- AC-03: Changing the master volume updates audio output.
- AC-04: The selected volume is retained after closing and reopening the menu.
- AC-05: The selected volume persists after restarting the game.
```

### 7.3. Technical Features

Technical criteria SHOULD focus on externally observable behavior, integration requirements, reliability, and measurable technical constraints.

Examples:

- The system exposes the required public interface.
- Invalid input is rejected without corrupting existing data.
- The system handles missing resources without crashing.
- The feature integrates with the existing save system.
- The implementation remains within the approved performance budget.

Internal implementation requirements MAY be included when they are necessary to enforce an architectural or technical decision.

### 7.4. Bug Fixes

Bug-related acceptance criteria SHOULD describe:

- The incorrect behavior.
- The expected corrected behavior.
- The conditions under which the defect occurred.
- Relevant regression scenarios.

Example:

**Bug:** Player can move while the inventory is open.

```markdown
- AC-01: Opening the inventory prevents gameplay movement.
- AC-02: Closing the inventory restores normal movement behavior.
- AC-03: Inventory navigation remains functional while gameplay movement is disabled.
- AC-04: Other gameplay states that disable movement remain unaffected by the fix.
```

### 7.5. Art and Animation

Art and animation criteria SHOULD cover:

- Compliance with the approved art direction.
- Required dimensions and formats.
- Visual consistency.
- Animation behavior.
- Engine compatibility.
- Transparency or layering requirements.
- Performance constraints.
- Licensing and source requirements.

Example:

**Asset:** Player idle animation.

```markdown
- AC-01: The animation uses the approved character design.
- AC-02: The animation loops without visible discontinuities.
- AC-03: The animation is compatible with the character's movement state machine.
- AC-04: The exported animation uses the required project asset format.
- AC-05: The asset is stored in the appropriate feature directory.
```

### 7.6. Audio

Audio criteria SHOULD cover:

- Intended playback conditions.
- Audio category and purpose.
- Format and technical requirements.
- Perceived quality.
- Volume and clipping.
- Looping behavior, when applicable.
- Integration with gameplay events.
- Accessibility requirements where relevant.

Example:

**Asset:** Player footsteps.

```markdown
- AC-01: Footstep sounds play while the player is moving on supported surfaces.
- AC-02: Footstep sounds stop when the player stops moving.
- AC-03: The appropriate sound variation is selected for the current surface.
- AC-04: Footstep playback does not continue after the player enters a state that disables normal movement audio.
- AC-05: Audio playback does not produce audible clipping.
```

### 7.7. Performance Improvements

Performance criteria MUST define measurable conditions whenever practical.

Examples:

- The feature remains within its allocated memory budget.
- The scene maintains the project's target frame rate under the defined test conditions.
- Resource loading completes within the specified time budget.
- The system does not introduce a measurable regression in the agreed performance scenario.

Performance criteria SHOULD identify the relevant hardware, scene, workload, or test conditions when those factors materially affect the result.

Avoid statements such as "the game must be optimized" without a measurable target.

### 7.8. Documentation

Documentation criteria SHOULD cover:

- Required content.
- Accuracy.
- Correct location.
- Relevant references.
- Consistency with current implementation.
- Required examples or diagrams.
- Review and approval requirements.

Example:

```markdown
- AC-01: The document explains the feature's purpose and scope.
- AC-02: The document describes the expected behavior and relevant limitations.
- AC-03: All referenced repository paths exist.
- AC-04: Examples are consistent with the current implementation.
- AC-05: The document follows the studio documentation standards.
```

## 8. Acceptance Criteria and Test Design

Acceptance criteria SHOULD provide a foundation for validation and test design.

Each criterion SHOULD be covered by one or more appropriate validation activities.

### 8.1. Test Coverage

For every criterion, determine:

- What must be verified?
- Under what conditions?
- What result is expected?
- What validation method is appropriate?
- What evidence demonstrates success?

Complex criteria MAY require multiple test cases.

A single test case MAY verify multiple related criteria when doing so does not reduce clarity or traceability.

### 8.2. Positive Testing

Verify that the feature works under expected valid conditions.

Examples:

- Valid player actions.
- Correct resource availability.
- Supported inputs.
- Expected gameplay states.

### 8.3. Negative Testing

Verify that invalid or unsupported conditions are handled correctly.

Examples:

- Invalid inputs.
- Missing resources.
- Insufficient inventory space.
- Unauthorized actions.
- Corrupted data.
- Unsupported state transitions.

### 8.4. Boundary Testing

Verify behavior at relevant limits.

Examples:

- Minimum and maximum values.
- Empty inventories.
- Full inventories.
- Zero health.
- Maximum resource capacity.
- Minimum and maximum supported resolution.

### 8.5. Regression Testing

When modifying existing functionality, identify related behavior that could be affected.

Acceptance criteria SHOULD include regression expectations when a change introduces meaningful risk to existing functionality.

### 8.6. Traceability

When practical, acceptance criteria SHOULD be traceable to:

- Backlog items.
- Design specifications.
- Technical specifications.
- Test cases.
- Defects.
- Pull requests.
- Release records.

Use stable work item and criterion identifiers when the project requires explicit traceability.

## 9. Quality of Acceptance Criteria

Acceptance criteria SHOULD satisfy the following quality characteristics:

| Characteristic | Description |
|---|---|
| Clear | The expected outcome is understandable. |
| Specific | The requirement avoids vague language. |
| Testable | A suitable validation method exists. |
| Relevant | The criterion supports the work item's objective. |
| Feasible | The requirement can reasonably be implemented. |
| Consistent | It does not conflict with approved decisions. |
| Complete | Important conditions and constraints are covered. |
| Independent | It avoids unnecessary coupling with unrelated criteria. |

### 9.1. Common Problems

Avoid the following:

**Vague requirements**

Weak: "The inventory should be user-friendly."

Improved: "The inventory displays item names, icons, and quantities for all items currently owned by the player."

**Implementation disguised as acceptance**

Weak: "Create an InventoryManager singleton with five functions."

Improved: "The inventory provides a consistent interface for adding, removing, and retrieving player items."

**Multiple unrelated requirements**

Weak: "The player can open the inventory, equip weapons, use potions, and save the game."

Improved: Separate each behavior into its own criterion or work item.

**Unverifiable subjective statements**

Weak: "The animation must look amazing."

Improved: "The animation follows the approved character animation reference and communicates the intended attack action."

**Missing conditions**

Weak: "The player can interact with doors."

Improved: "When the player is within the door's interaction range and the door is interactable, using the interaction input opens or closes it according to its current state."

## 10. Definition of Ready

Before a work item enters implementation, its acceptance criteria SHOULD be sufficiently clear to guide development and validation.

A work item is considered ready for implementation when:

- Its objective and expected outcome are understood.
- Relevant acceptance criteria are documented.
- Criteria are sufficiently specific and testable.
- Important constraints and dependencies are identified.
- Relevant design or technical references are available.
- Unresolved questions that could materially change implementation are addressed.

Not every minor task requires formal review, but ambiguous requirements MUST be clarified before they create significant implementation risk.

## 11. Acceptance and Completion

Acceptance criteria and the Definition of Done serve different purposes.

**Acceptance criteria** define the expected outcomes of a particular work item.

**Definition of Done** defines the general quality and completion requirements that apply to completed work.

A work item is acceptable when:

1. All mandatory acceptance criteria have been verified.
2. Relevant defects have been resolved or explicitly accepted by the project owner.
3. Required evidence or validation results are available.
4. The deliverable satisfies the applicable Definition of Done.
5. Any exceptions have been documented and approved.

Passing acceptance criteria does not automatically mean that the work is ready to merge or release. Repository, review, integration, and release requirements still apply.

### 11.1. Acceptance Status

Projects MAY use the following statuses for tracking acceptance:

| Status | Meaning |
|---|---|
| Not Evaluated | Acceptance has not been assessed. |
| In Progress | Implementation or validation is ongoing. |
| Accepted | All required acceptance conditions are satisfied. |
| Rejected | One or more mandatory conditions are not satisfied. |
| Blocked | Acceptance cannot proceed because of an unresolved dependency or issue. |
| Accepted with Exceptions | The project owner has explicitly approved documented deviations. |

Acceptance status MUST reflect actual validation results.

AI agents and developers MUST NOT mark work as accepted merely because implementation is complete.

### 11.2. Acceptance with Exceptions

Exceptions MAY be accepted when:

- The deviation is understood.
- Its impact is evaluated.
- The remaining risk is acceptable.
- The project owner explicitly approves it.
- The exception is documented.

An exception MUST NOT silently redefine an existing acceptance criterion.

If requirements change, update the relevant work item or specification.

## 12. Managing Changes to Acceptance Criteria

Acceptance criteria MAY change as project understanding improves.

Changes SHOULD be controlled and traceable.

When modifying criteria:

1. Identify why the change is necessary.
2. Evaluate its effect on scope and implementation.
3. Identify affected tests and documentation.
4. Update the work item or authoritative specification.
5. Communicate relevant changes to affected contributors.
6. Reassess estimates, dependencies, and risks when necessary.

Significant changes to approved requirements require project owner approval.

Previously accepted work MUST NOT be retroactively marked as incomplete without a documented reason and an explicit decision.

## 13. AI-Assisted Acceptance Criteria

AI agents MAY assist with:

- Drafting acceptance criteria from requirements.
- Identifying ambiguous or incomplete conditions.
- Suggesting edge cases.
- Converting criteria into Given-When-Then scenarios.
- Identifying test coverage gaps.
- Mapping criteria to test cases.
- Reviewing consistency with existing specifications.
- Identifying conflicting requirements.

AI agents MUST:

1. Read the relevant backlog item and authoritative project documentation.
2. Preserve the intended outcome.
3. Use observable and verifiable language.
4. Identify assumptions instead of presenting them as approved requirements.
5. Avoid introducing unrequested functionality.
6. Distinguish mandatory criteria from optional suggestions.
7. Identify unresolved questions that affect implementation.
8. Report criteria that cannot be verified objectively.
9. Request human clarification or approval when requirements are ambiguous or materially change scope.

AI agents MUST NOT:

- Invent product requirements.
- Change approved acceptance criteria without authorization.
- Mark criteria as satisfied without validation evidence.
- Claim automated test coverage without actual tests.
- Treat successful code generation as proof of acceptance.
- Approve their own work as the final project authority.

The project owner retains final authority over requirement interpretation and acceptance decisions.

## 14. Acceptance Criteria Review Checklist

Use this checklist when reviewing acceptance criteria.

### Clarity and Scope

- [ ] The expected outcome is clear.
- [ ] Each criterion is understandable without unnecessary interpretation.
- [ ] Criteria are relevant to the work item's objective.
- [ ] The criteria do not introduce unapproved scope.

### Testability

- [ ] Each criterion can be verified.
- [ ] Expected conditions and outcomes are defined.
- [ ] Relevant boundary conditions are covered.
- [ ] Relevant failure conditions are covered.
- [ ] Appropriate validation methods can be identified.

### Consistency

- [ ] Criteria align with approved design decisions.
- [ ] Criteria respect technical constraints.
- [ ] Related requirements are not contradictory.
- [ ] Relevant documentation is referenced.

### Completeness

- [ ] Important gameplay or system behavior is covered.
- [ ] Relevant integration behavior is considered.
- [ ] Regression risks are considered.
- [ ] Accessibility, performance, or compatibility requirements are included when applicable.

### Acceptance

- [ ] Acceptance conditions are distinguishable from Definition of Done requirements.
- [ ] Required validation evidence is understood.
- [ ] Exceptions require explicit approval.
- [ ] Acceptance responsibility is clear.

## 15. Exceptions

Projects MAY simplify acceptance criteria for small tasks, low-risk changes, or exploratory work.

However, requirements MUST remain sufficiently clear to prevent avoidable misunderstandings.

For prototypes and experiments, acceptance criteria MAY focus on learning objectives, validation questions, and measurable evidence rather than production-ready behavior.

Exceptions to these guidelines SHOULD be proportional to the work and documented when they materially affect quality or project scope.

## 16. Related Documents

- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/quality_standards.md`
- `docs/00_studio_standards/code_review_guidelines.md`
- `docs/01_game_design_guidelines/gameplay_design_guidelines.md`
- `docs/01_game_design_guidelines/mechanic_design_guidelines.md`
- `docs/04_production_standards/backlog_management.md`
- `docs/04_production_standards/sprint_workflow.md`
- `docs/05_qa_standards/testing_strategy.md`

## 17. Maintenance

These guidelines SHOULD be reviewed periodically and updated when:

- Recurring requirement ambiguities are identified.
- Testing practices evolve.
- New development workflows are introduced.
- Changes to project complexity require different levels of acceptance detail.
- AI-assisted development reveals new requirement-management challenges.

Changes MUST preserve the distinction between acceptance criteria, test cases, implementation specifications, and general completion requirements.

The project owner is responsible for approving changes to these guidelines.