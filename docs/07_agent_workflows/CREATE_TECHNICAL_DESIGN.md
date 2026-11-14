# Create Technical Design Workflow

## 1. Purpose

This workflow defines the standard procedure for AI agents to assist in creating, reviewing, and maintaining Technical Design Documents (TDDs).

A Technical Design Document describes how a feature, system, integration, or significant technical change should be implemented.

It translates approved requirements and design intentions into a technical solution that developers can implement, test, maintain, and extend.

The objective is to establish a clear technical implementation plan before development begins, reducing architectural uncertainty, implementation rework, integration problems, and unnecessary complexity.

## 2. Scope

This workflow applies to:

- New gameplay system implementations.
- Significant feature implementations.
- Architectural changes.
- Cross-feature integrations.
- Data management and persistence systems.
- Complex UI architecture.
- Save and load systems.
- AI and simulation systems.
- Performance-critical implementations.
- External service integrations.
- Technical refactoring with significant structural impact.
- Changes involving important dependencies or shared infrastructure.

A separate Technical Design Document is generally unnecessary for:

- Small isolated bug fixes.
- Simple UI adjustments.
- Minor script modifications.
- Straightforward content additions.
- Changes that follow an already approved technical design.
- Routine implementation tasks with no meaningful architectural uncertainty.

The agent MUST use judgment and avoid creating documentation overhead for trivial work.

## 3. Output

| Property | Value |
|---|---|
| Output Document | `game_project/docs/technical/designs/[system_name]_technical_design.md` |
| Source Template | `docs/06_templates/technical_design_template.md` |
| Document Type | Technical Design |
| Primary Owner | Project Owner / Technical Lead |
| Approval Authority | Project Owner |
| Initial Status | Draft |

The agent MUST inspect the actual repository before creating the output.

If an appropriate Technical Design Document already exists, the agent MUST review and update it rather than creating a duplicate.

If the proposed change is already covered by an approved design, the agent SHOULD reference that document instead of creating redundant documentation.

## 4. Required Inputs

### 4.1 Functional Requirements

Review the available information describing what the system or feature must accomplish.

Sources may include:

- Game Design Document.
- Gameplay System Specification.
- Mechanic Specification.
- User Stories.
- Backlog Items.
- Acceptance Criteria.
- Core Game Loop.
- UI/UX Specifications.
- Existing technical documentation.

The agent MUST identify the expected behavior and constraints before designing the implementation.

### 4.2 Existing Technical Context

Inspect the existing project and relevant technical documentation.

Review:

- Project Structure Standards.
- Architecture Guidelines.
- Engine Standards.
- GDScript Standards.
- Scene and Node Conventions.
- Resource Management Guidelines.
- Event and Signal Guidelines.
- Data Persistence Guidelines.
- Performance Guidelines.
- Testing Strategy.
- Existing Architecture Decision Records.
- Relevant source code, scenes, resources, and tests.

The agent MUST inspect actual implementation details rather than relying exclusively on documentation.

### 4.3 Supporting Information

When relevant, identify:

- Target Godot version.
- Existing dependencies and plugins.
- Target platforms.
- Performance constraints.
- Memory constraints.
- Save compatibility requirements.
- Multiplayer or networking requirements.
- Security and privacy requirements.
- Integration dependencies.
- Known technical limitations.

### 4.4 Missing Information

If required information is unavailable:

1. Identify the missing information.
2. Determine whether it prevents a reliable technical design.
3. Record assumptions explicitly.
4. Ask focused clarification questions when necessary.
5. Present alternatives when multiple solutions are viable.
6. Do not invent approved requirements or technical decisions.

## 5. Workflow Principles

Agents MUST follow these principles:

- **Requirements first:** Understand what must be implemented before deciding how.
- **Inspect before designing:** Review the existing project architecture and implementation.
- **Consistency:** Follow approved studio standards and project conventions.
- **Simplicity:** Prefer the simplest solution that satisfies the requirements.
- **Modularity:** Maintain clear responsibilities and appropriate feature boundaries.
- **Low coupling:** Minimize unnecessary dependencies between systems.
- **Explicit dependencies:** Avoid hidden dependencies and implicit global state.
- **Godot-native design:** Use Godot's existing capabilities appropriately.
- **Testability:** Design systems so their behavior can be validated.
- **Maintainability:** Consider readability, extension, debugging, and future changes.
- **Evidence-based decisions:** Support important technical choices with reasoning.
- **Controlled scope:** Do not introduce unrelated systems or unnecessary abstractions.
- **Human approval:** Significant architectural decisions require project owner approval.

Agents MUST NOT implement a significant technical design decision merely because it appears convenient without first evaluating its implications.

## 6. Execution Procedure

### Step 1: Determine Whether a Technical Design Is Necessary

Evaluate the complexity and impact of the requested work.

Consider:

- Number of affected features.
- Number of affected scripts, scenes, and resources.
- Architectural impact.
- New dependencies.
- Data ownership and persistence.
- Integration complexity.
- Performance implications.
- Testing requirements.
- Risk of breaking existing functionality.

Use the following guidance:

| Change Type | Technical Design |
|---|---|
| Minor isolated change | Usually unnecessary |
| Small feature using established architecture | Usually unnecessary |
| New self-contained system | Recommended |
| Cross-feature integration | Recommended |
| Significant architecture change | Required |
| New persistence or save architecture | Required |
| Complex external integration | Required |
| High-risk technical implementation | Required |

If a Technical Design Document is unnecessary, briefly explain why and follow the existing approved implementation standards.

**Expected result:** A decision about whether a TDD is required.

### Step 2: Inspect Project Context

1. Inspect the repository structure.
2. Read applicable agent rules and project instructions.
3. Review the Documentation Inventory when required.
4. Locate relevant design and requirements documents.
5. Review existing technical standards.
6. Inspect relevant scripts, scenes, resources, and tests.
7. Identify existing systems that provide similar functionality.
8. Review relevant ADRs.
9. Identify existing architectural constraints and conventions.

For Godot projects, inspect relevant elements such as:

- `project.godot`.
- Scene hierarchy and ownership.
- Autoloads.
- Input Map configuration.
- Resources and custom resource classes.
- Signals and event communication.
- Feature dependencies.
- Existing GDScript implementations.
- Relevant test scripts and fixtures.

Do not assume the project follows the intended architecture merely because the documentation describes it. Identify discrepancies between standards and actual implementation.

**Expected result:** A reliable understanding of the existing technical environment.

### Step 3: Understand the Requirements

Identify the functional and non-functional requirements.

#### 3.1 Functional Requirements

Describe what the system must do.

Examples:

- Accept player input.
- Manage game state.
- Process gameplay events.
- Store and retrieve data.
- Communicate with other systems.
- Provide feedback to the player.

Requirements should be traceable to relevant game design documents or backlog items.

#### 3.2 Non-Functional Requirements

Identify relevant quality requirements:

- Performance.
- Memory usage.
- Reliability.
- Maintainability.
- Scalability.
- Testability.
- Security.
- Accessibility.
- Compatibility.
- Persistence and data integrity.

Do not include irrelevant quality attributes merely to fill out a document.

#### 3.3 Constraints

Identify limitations that affect implementation.

Examples:

- Godot version.
- GDScript language requirements.
- Target platforms.
- Existing architecture.
- Approved plugins.
- Available resources.
- Performance budgets.
- Save compatibility.

#### 3.4 Acceptance Criteria

Identify how successful implementation will be evaluated.

Use existing acceptance criteria when available.

If technical acceptance criteria are missing, propose measurable conditions and identify those requiring approval.

**Expected result:** A clear and traceable set of implementation requirements.

### Step 4: Define Technical Goals and Non-Goals

Establish what the technical solution is expected to achieve.

#### Technical Goals

Examples:

- Provide a modular implementation.
- Integrate with existing gameplay systems.
- Support deterministic behavior.
- Allow isolated testing.
- Preserve existing save data.
- Maintain acceptable performance.

#### Non-Goals

Explicitly identify concerns outside the scope of the design.

Examples:

- Replacing unrelated systems.
- Introducing multiplayer support.
- Supporting unplanned platforms.
- Implementing optional features.
- Redesigning the entire project architecture.

Non-goals prevent unnecessary scope expansion.

**Expected result:** A defined technical scope.

### Step 5: Identify System Boundaries and Responsibilities

Define the responsibilities of the system.

Identify:

- What the system owns.
- What the system controls.
- What the system receives.
- What the system produces.
- Which features depend on it.
- Which systems it depends on.
- Which responsibilities belong elsewhere.

For feature-oriented projects, place implementation within the owning feature.

Use `shared/` only for functionality genuinely required by multiple features.

Use `infrastructure/` for project-wide technical infrastructure.

Do not introduce shared systems simply to avoid small amounts of duplicated code.

**Expected result:** Clear system boundaries and ownership.

### Step 6: Design the Architecture

Describe the proposed technical structure.

Consider:

- Main components.
- Component responsibilities.
- Relationships between components.
- Data ownership.
- Dependency direction.
- Communication mechanisms.
- Lifecycle management.
- Error handling.
- Resource management.

For Godot projects, consider appropriate use of:

- Nodes and Scenes.
- GDScript classes.
- Custom Resources.
- Signals.
- Direct method calls.
- Autoloads.
- ResourceLoader.
- Scene instantiation.
- Composition.
- Interfaces or clearly defined public APIs.

Prefer composition and explicit dependencies over unnecessary inheritance or global access.

Do not create an elaborate architecture when a small number of well-defined components is sufficient.

**Expected result:** A coherent architecture that satisfies the requirements and respects project standards.

### Step 7: Define Components and Responsibilities

For each significant component, document:

| Component | Responsibility | Inputs | Outputs | Dependencies |
|---|---|---|---|---|
| [Component] | [Responsibility] | [Inputs] | [Outputs] | [Dependencies] |

Describe:

- Main classes or scripts.
- Relevant scenes.
- Custom Resources.
- Important methods.
- Signals.
- State ownership.
- Initialization and cleanup.
- Error handling.

Use conceptual component names when implementation names have not yet been approved.

Avoid prescribing unnecessary classes or methods prematurely.

**Expected result:** A clear component breakdown.

### Step 8: Define Interfaces and Communication

Describe how components communicate.

For each important interface, document:

- Purpose.
- Owner.
- Inputs and parameters.
- Outputs or return values.
- Signals and events.
- Expected behavior.
- Error conditions.
- Dependencies.

Follow the studio's Event and Signal Guidelines.

Prefer direct method calls when requesting an operation from a known owner.

Use signals when communicating that an event or state change has occurred.

Avoid unnecessary event buses, global managers, and tightly coupled feature dependencies.

**Expected result:** Explicit communication contracts.

### Step 9: Define Data Structures and State Management

Identify the data required by the system.

Consider:

- Runtime state.
- Configuration data.
- Persistent data.
- Derived data.
- Temporary data.
- Shared data.
- Data ownership.
- Initialization and reset behavior.

For each important data structure, document:

- Purpose.
- Fields or properties.
- Data types.
- Defaults.
- Validation requirements.
- Ownership.
- Lifecycle.
- Persistence requirements.

Use custom Godot Resources when appropriate for reusable configuration or structured data.

Avoid storing mutable runtime state in shared Resource instances unless the sharing behavior is intentional.

If persistence is involved, follow the Data Persistence Guidelines and document:

- Serialization approach.
- Save format.
- Versioning.
- Loading behavior.
- Failure recovery.
- Migration requirements.
- Data integrity considerations.

**Expected result:** A clear data model and state ownership strategy.

### Step 10: Define Processing and System Behavior

Describe how the system operates.

Depending on the feature, document:

- Execution flow.
- State transitions.
- Input processing.
- Validation.
- Business or gameplay rules.
- Event handling.
- Asynchronous operations.
- Error conditions.
- Recovery behavior.
- Cleanup.

Use diagrams or pseudocode when they clarify complex behavior.

For stateful systems, define relevant states and transitions.

For example:

```text
INACTIVE -> INITIALIZING -> ACTIVE -> SHUTTING_DOWN
```

The example is illustrative. Use states that reflect the actual system.

**Expected result:** A clear understanding of system behavior and execution flow.

### Step 11: Evaluate Technical Alternatives

When meaningful alternatives exist, compare them before selecting an implementation.

Consider:

- Simplicity.
- Performance.
- Maintainability.
- Testability.
- Compatibility.
- Dependency impact.
- Development effort.
- Future extensibility.
- Godot-native support.

Use a comparison table:

| Option | Advantages | Disadvantages | Risks |
|---|---|---|---|
| Option A | [Advantages] | [Disadvantages] | [Risks] |
| Option B | [Advantages] | [Disadvantages] | [Risks] |

Select a recommended approach and explain the reasoning.

Do not introduce alternatives when the appropriate solution is already established by approved architecture or standards.

**Expected result:** A justified technical solution.

### Step 12: Evaluate Performance and Resource Requirements

Identify potential performance concerns.

Consider:

- CPU processing.
- Rendering.
- Memory allocation.
- Object creation and destruction.
- Physics processing.
- Resource loading.
- Scene transitions.
- Signal and event frequency.
- Large data collections.
- Background processing.

For relevant systems, define measurable performance targets or budgets.

Do not optimize prematurely or claim performance improvements without profiling evidence.

Follow the Performance Guidelines and Resource Management standards.

**Expected result:** A performance-aware design with appropriate validation requirements.

### Step 13: Evaluate Reliability and Security

Identify relevant failure conditions and protections.

Consider:

- Invalid input.
- Missing resources.
- Unexpected state transitions.
- Corrupted data.
- Failed dependencies.
- Resource loading errors.
- Network failures, if applicable.
- Unauthorized access to sensitive operations.
- Save data integrity.
- Unsafe file operations.

Define expected error handling and recovery behavior.

Do not expose secrets, credentials, or sensitive information in source code or project documentation.

**Expected result:** Documented reliability and security considerations.

### Step 14: Define the Testing Approach

Identify how the technical implementation will be validated.

Consider:

- Unit tests.
- Integration tests.
- Scene tests.
- End-to-end tests.
- Regression tests.
- Performance tests.
- Manual verification.

Define important test scenarios, including:

- Normal behavior.
- Boundary conditions.
- Invalid input.
- Failure handling.
- State transitions.
- Integration behavior.
- Persistence behavior, when applicable.

Tests MUST validate observable behavior rather than merely confirming implementation details.

Follow the Testing Strategy and relevant QA standards.

Do not claim that tests have passed before they have actually been executed.

**Expected result:** A testable design with defined validation scenarios.

### Step 15: Identify Dependencies, Risks, and Implementation Constraints

Document:

- Required existing systems.
- New dependencies.
- Plugin requirements.
- External services.
- Cross-feature dependencies.
- Migration requirements.
- Implementation risks.
- Technical uncertainties.
- Potential blockers.

For significant risks, identify mitigation or validation approaches.

Do not add dependencies without evaluating whether they are necessary and compatible with the project.

**Expected result:** A documented dependency and risk assessment.

### Step 16: Determine Whether an ADR Is Required

A Technical Design Document describes a proposed implementation.

An Architecture Decision Record captures a significant architectural decision and its reasoning.

Consider creating or updating an ADR when the design involves:

- A major architectural direction.
- A new architectural pattern.
- A significant technology or dependency choice.
- A project-wide communication or state-management approach.
- A significant persistence or data architecture decision.
- A decision with long-term consequences or difficult reversibility.

If an ADR is required:

1. Follow `docs/02_technical_standards/adr/README.md`.
2. Use the ADR Template.
3. Create the project-specific ADR in `game_project/docs/technical/adr/`.
4. Reference the ADR from the Technical Design Document.
5. Keep the ADR status `Proposed` until approved.

Not every technical implementation requires an ADR.

**Expected result:** A determination of whether an architectural decision requires separate documentation.

### Step 17: Generate the Technical Design Document

1. Read `docs/06_templates/technical_design_template.md`.
2. Follow its structure and required sections.
3. Populate the template using inspected project information.
4. Reference the relevant requirements and design specifications.
5. Document the architecture and component responsibilities.
6. Include interfaces, data structures, and execution flows where appropriate.
7. Document alternatives and technical decisions.
8. Identify risks and unresolved questions.
9. Define testing and validation requirements.
10. Set the document status to `Draft`.
11. Save the document at `game_project/docs/technical/designs/[system_name]_technical_design.md`.

The generated document MUST:

- Follow the approved project architecture.
- Use correct Godot and GDScript terminology.
- Respect feature-oriented organization.
- Avoid unnecessary abstraction.
- Define ownership and dependencies.
- Provide sufficient detail for implementation.
- Avoid duplicating unrelated documentation.
- Clearly identify assumptions and proposals.
- Reference ADRs when applicable.

### Step 18: Review and Validate the Technical Design

Review the generated document against the following checklist.

**Requirements**

- [ ] Functional requirements are understood.
- [ ] Non-functional requirements are considered.
- [ ] Technical goals and non-goals are defined.
- [ ] Acceptance criteria are traceable.

**Architecture**

- [ ] System boundaries are clear.
- [ ] Component responsibilities are defined.
- [ ] Dependencies are explicit.
- [ ] Communication contracts are documented.
- [ ] Data ownership is clear.
- [ ] The design follows feature-oriented organization.
- [ ] The design respects approved architecture.

**Implementation**

- [ ] The proposed approach is compatible with the selected Godot version.
- [ ] GDScript conventions are respected.
- [ ] Relevant scenes, nodes, scripts, and resources are identified.
- [ ] Lifecycle and state management are considered.
- [ ] Error handling is defined.
- [ ] Resource management is considered.

**Quality**

- [ ] Performance risks are evaluated.
- [ ] Security and reliability are considered where relevant.
- [ ] Testing requirements are defined.
- [ ] Dependencies and risks are documented.
- [ ] Relevant architectural decisions have been identified.

**Documentation**

- [ ] The correct template was used.
- [ ] The output location is correct.
- [ ] Related documents are referenced accurately.
- [ ] Assumptions and open questions are identified.
- [ ] The document status is `Draft`.
- [ ] No duplicate document was created.

Correct identified problems before presenting the document.

### Step 19: Present for Technical Review and Approval

Present the Technical Design Document to the project owner or designated technical reviewer.

Include:

1. The technical problem being addressed.
2. The requirements and constraints.
3. The proposed architecture.
4. The main components and responsibilities.
5. Important interfaces and data structures.
6. The selected implementation approach.
7. Alternatives considered.
8. Performance and reliability considerations.
9. Testing strategy.
10. Risks and unresolved questions.
11. Relevant ADR requirements.
12. Recommended implementation sequence.

The project owner MUST approve significant technical decisions before implementation begins.

Agents MUST NOT:

- Approve their own technical designs.
- Mark the document as `Approved` without authorization.
- Implement unapproved architectural changes.
- Introduce dependencies without appropriate evaluation.
- Bypass established project standards.
- Modify unrelated architecture as part of the task without authorization.

## 7. Implementation Handoff

Once the technical design has been approved, it may be used as the implementation reference.

### 7.1 Implementation Preparation

Before implementation:

1. Verify that the approved design is available.
2. Confirm that its requirements remain valid.
3. Identify implementation tasks.
4. Identify dependencies and execution order.
5. Identify required tests.
6. Confirm relevant acceptance criteria.
7. Create or update backlog items as appropriate.

### 7.2 Implementation Responsibilities

During implementation, agents MUST:

- Follow the approved technical design.
- Respect existing project conventions.
- Avoid unrelated refactoring.
- Maintain feature boundaries.
- Implement the defined interfaces and data ownership.
- Add or update tests.
- Update documentation when behavior or architecture changes.
- Report discrepancies between the design and actual implementation.

### 7.3 Design Deviations

If implementation reveals that the approved design is incorrect, incomplete, or impractical:

1. Stop before making a significant architectural deviation.
2. Describe the problem.
3. Explain why the approved approach is insufficient.
4. Propose alternatives.
5. Evaluate the impact on requirements and architecture.
6. Request approval for significant changes.
7. Update the Technical Design Document after the decision.

Minor implementation details that do not change the approved architecture may be adjusted without a separate approval, provided they remain within the agent's authorized scope.

## 8. Design Maintenance

Technical Design Documents should remain accurate enough to guide implementation and future maintenance.

Update the document when:

- The approved architecture changes.
- Important interfaces change.
- Data ownership changes.
- Significant implementation assumptions are invalidated.
- New technical constraints are discovered.
- Important decisions are superseded.

Do not update a Technical Design Document for every minor code change.

If implementation differs materially from the approved design, document the actual decision and implementation rather than leaving misleading instructions.

## 9. Completion Criteria

This workflow is complete when:

- [ ] The need for a Technical Design Document has been evaluated.
- [ ] Existing project architecture has been inspected.
- [ ] Requirements and constraints have been identified.
- [ ] Technical goals and non-goals have been defined.
- [ ] System boundaries and responsibilities have been established.
- [ ] Architecture and components have been documented.
- [ ] Interfaces and communication are defined.
- [ ] Data structures and state management are addressed.
- [ ] System behavior is described.
- [ ] Alternatives have been evaluated where appropriate.
- [ ] Performance and reliability have been considered.
- [ ] Testing requirements have been defined.
- [ ] Dependencies and risks have been documented.
- [ ] ADR requirements have been evaluated.
- [ ] The Technical Design Document has been generated.
- [ ] The document has passed technical review.
- [ ] The design has been presented for approval.

Completion of this workflow does not imply approval of the Technical Design Document.

Implementation may proceed only after the required approval has been obtained.

## 10. Expected Agent Report

After execution, provide a report using the following structure:

### Technical Design Creation Report

**Status:** [Completed / Partially Completed / Blocked]

**Output Document:** `game_project/docs/technical/designs/[system_name]_technical_design.md`

**System or Feature:** [Name]

**Technical Problem:**

[Short description.]

**Requirements Reviewed:**

- [Requirement source]
- [Requirement source]

**Proposed Architecture:**

[Summary.]

**Main Components:**

1. [Component] — [Responsibility]
2. [Component] — [Responsibility]

**Key Technical Decisions:**

- [Decision and reasoning]

**Alternatives Considered:**

- [Alternative and evaluation]

**Dependencies:**

- [Dependency or None]

**Performance and Reliability Considerations:**

[Summary.]

**Testing Requirements:**

[Summary.]

**ADRs Required:** [Yes / No]

**Risks and Open Questions:**

- [Risk or question]

**Validation Results:**

- Requirements coverage: [Passed / Failed / Not Verified]
- Architecture consistency: [Passed / Failed / Not Verified]
- Implementation feasibility: [Passed / Failed / Not Verified]
- Documentation quality: [Passed / Failed / Not Verified]

**Approval Status:** Pending

**Recommended Next Action:** [Required action.]

## 11. Related References

### Studio Documentation

- Architecture Guidelines: `docs/02_technical_standards/architecture_guidelines.md`
- GDScript Standards: `docs/02_technical_standards/gdscript_standards.md`
- Engine Standards: `docs/02_technical_standards/engine_standards.md`
- Scene and Node Convention: `docs/02_technical_standards/scene_and_node_convention.md`
- Resource Management: `docs/02_technical_standards/resource_management.md`
- Event and Signal Guidelines: `docs/02_technical_standards/event_and_signal_guidelines.md`
- Data Persistence Guidelines: `docs/02_technical_standards/data_persistence_guidelines.md`
- Performance Guidelines: `docs/02_technical_standards/performance_guidelines.md`
- Testing Strategy: `docs/02_technical_standards/testing_strategy.md`
- ADR Guidelines: `docs/02_technical_standards/adr/README.md`
- Technical Design Template: `docs/06_templates/technical_design_template.md`
- ADR Template: `docs/06_templates/adr_template.md`

### Project Documentation

- Game Design Document: `game_project/docs/game_design/game_design_document.md`
- Gameplay System Specifications: `game_project/docs/game_design/systems/`
- Technical Design Documents: `game_project/docs/technical/designs/`
- Architecture Decision Records: `game_project/docs/technical/adr/`
- Test Plans: `game_project/docs/qa/test_plans/`

Only use references that exist in the applicable repository.

---

**End of Workflow**
