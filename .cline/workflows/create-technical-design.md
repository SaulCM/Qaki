# Create Technical Design Workflow

## Purpose

Create a technical design document that explains how a proposed feature, system, or significant technical change should be implemented.

The design must translate approved requirements and specifications into a practical technical solution that fits the existing project architecture, Godot engine, and studio standards.

This workflow produces a design document only. It does not authorize implementation.

## When to Use

Use this workflow when:

- Designing a new gameplay or technical system.
- Planning a significant feature implementation.
- Introducing a new architectural component or integration.
- Changing existing system architecture.
- Evaluating multiple technical implementation approaches.
- Planning a technically complex change that requires design decisions before implementation.

Do not use this workflow for trivial changes, isolated bug fixes, or straightforward implementation tasks that do not require a separate technical design.

## Inputs

Identify the available inputs from the user's request and repository.

Potential inputs include:

- Game concept or vision.
- Game Design Document.
- Core game pillars.
- Gameplay system specifications.
- Mechanic specifications.
- World or level design documents.
- Existing technical overview.
- Existing architecture documentation.
- Relevant Architecture Decision Records (ADRs).
- Existing source code, scenes, resources, and tests.
- Technical constraints and requirements.

Do not invent missing requirements or assume that proposed features have already been approved.

If essential information is missing or contradictory, identify the gap and ask the user for clarification when it prevents a reliable design.

---

## Workflow

### Step 1: Establish Project Context

Before creating the design:

1. Inspect the repository structure.
2. Identify the Godot version and project configuration.
3. Inspect the existing architecture and feature organization.
4. Identify relevant scenes, scripts, resources, autoloads, and integrations.
5. Identify existing conventions and implementation patterns.
6. Check the current Git working-tree status.
7. Identify existing documentation related to the proposed change.

Do not assume that a proposed system is entirely new. Determine whether existing functionality can be extended or reused.

Do not modify project files during this step.

### Step 2: Load Applicable Documentation

Read `docs/DOCUMENTATION_INVENTORY.md` and inspect the actual documentation structure.

Consult the applicable studio standards:

- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`

Load additional documentation based on the proposed system.

Examples:

| Design area | Relevant documentation |
|---|---|
| General architecture | `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md` |
| Godot engine practices | `docs/02_technical_standards/ENGINE_STANDARDS.md` |
| GDScript implementation | `docs/02_technical_standards/GDSCRIPT_STANDARDS.md` |
| Scene and node structure | `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md` |
| Events and signals | `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md` |
| Data persistence | `docs/02_technical_standards/DATA_PERSISTENCE_GUIDELINES.md` |
| Resource management | `docs/02_technical_standards/RESOURCE_MANAGEMENT.md` |
| Performance requirements | `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md` |
| Asset integration | `docs/02_technical_standards/ASSET_PIPELINE.md` |
| Testing approach | `docs/02_technical_standards/TESTING_STRATEGY.md` |

Also consult relevant game design, art/audio, production, and QA guidelines when they affect the proposed technical solution.

Read `docs/07_agent_workflows/CREATE_TECHNICAL_DESIGN.md` when it exists and is applicable.

Inspect relevant project-specific specifications and existing ADRs.

Follow relevant documentation references and resolve relative paths from the document containing the reference.

Verify that referenced documents exist before relying on them. Do not assume that every document listed in the inventory is relevant to the current design.

### Step 3: Understand the Requirements

Establish what the proposed system must accomplish before selecting an implementation.

Identify:

- The problem being addressed.
- The intended system behavior.
- Functional requirements.
- Non-functional requirements.
- Dependencies on other systems.
- User or player-facing behavior.
- Technical constraints.
- Performance expectations.
- Persistence requirements, if applicable.
- Testing and validation expectations.
- Explicit exclusions and out-of-scope behavior.

Distinguish between:

- **Confirmed:** Explicitly established by the user or authoritative project documentation.
- **Derived:** A reasonable implication of confirmed requirements.
- **Proposed:** A recommendation introduced by the technical design.
- **Undecided:** A question requiring a decision.
- **Not Applicable:** A requirement that does not apply to the proposed system.

Do not convert proposals or assumptions into confirmed requirements.

### Step 4: Inspect Existing Implementation

Inspect relevant existing code and project resources.

Evaluate:

- Existing systems that provide related functionality.
- Existing interfaces and dependencies.
- Current scene and node organization.
- Existing data structures and resources.
- Autoload responsibilities.
- Signal and event communication.
- Resource loading and lifecycle management.
- Existing error-handling patterns.
- Testing infrastructure.

Identify what should be:

- Reused.
- Extended.
- Introduced.
- Replaced.
- Deprecated.

Avoid proposing duplicate systems when existing functionality can be extended safely.

Do not recommend large-scale refactoring unless it is necessary to satisfy the requirements or resolve an identified architectural limitation.

### Step 5: Define the Technical Approach

Develop an implementation approach consistent with the existing project architecture.

Describe the following as applicable:

#### 5.1 System Overview

Explain:

- The system's purpose.
- Its main responsibilities.
- Its boundaries.
- How it fits into the overall project architecture.

#### 5.2 Architecture and Components

Identify the proposed components and their responsibilities.

For each significant component, specify:

- Name.
- Responsibility.
- Type (Node, Resource, RefCounted, RefCounted-derived class, Node-derived class, autoload, or other appropriate construct).
- Dependencies.
- Public interfaces.
- Ownership and lifecycle considerations.

Use actual Godot and GDScript terminology.

Do not prescribe a class or node type without a reason.

#### 5.3 Data Design

Describe:

- Data structures.
- Resources and custom resource types.
- State ownership.
- Data flow.
- Serialization requirements.
- Persistence requirements.
- Validation rules.

Avoid duplicating data unnecessarily.

#### 5.4 Communication and Interactions

Explain how components communicate.

Consider:

- Direct method calls.
- Signals.
- Events.
- Shared resources.
- Dependency injection or explicit references.
- Autoload access, when justified.

Prefer clear ownership and explicit dependencies over unnecessary global state.

#### 5.5 Execution Flow

Describe important execution sequences.

Use numbered steps or sequence diagrams when they clarify interactions.

Include:

- Initialization.
- Normal operation.
- State transitions.
- Error handling.
- Cleanup and shutdown.

#### 5.6 Scene and Node Design

When applicable, propose the scene hierarchy and explain the responsibilities of important nodes.

Use a text tree when useful.

Do not invent scene hierarchies for systems that do not require scenes.

#### 5.7 Integration

Explain how the proposed system interacts with existing systems.

Identify:

- Integration points.
- Required interface changes.
- Dependencies.
- Potential compatibility issues.
- Required configuration changes.

#### 5.8 Performance and Scalability

Identify meaningful performance considerations.

Consider:

- Processing frequency.
- Memory allocation.
- Resource loading.
- Scene-tree operations.
- Object lifecycle.
- Data volume.
- Expected runtime workload.

Do not introduce optimization complexity without a justified requirement.

#### 5.9 Error Handling and Reliability

Describe how the system handles:

- Invalid inputs.
- Missing dependencies.
- Missing resources.
- Unexpected states.
- Failed operations.
- Invalid or unavailable references.

#### 5.10 Testing Strategy

Define how the implementation will be validated.

Identify:

- Unit tests, where applicable.
- Integration tests.
- Scene-level tests.
- Gameplay tests.
- Regression tests.
- Manual validation.
- Important edge cases.

Testing details should be specific enough to guide implementation and QA.

### Step 6: Evaluate Alternatives and Trade-offs

When meaningful architectural decisions exist:

1. Identify viable alternatives.
2. Compare their advantages and disadvantages.
3. Evaluate complexity, maintainability, performance, and compatibility.
4. Explain why the recommended approach is preferable.
5. Identify important trade-offs.

Do not manufacture alternatives for straightforward decisions.

If a significant architectural decision is unresolved, document the options and ask the user to decide rather than silently selecting one.

### Step 7: Identify Risks and Open Questions

Identify relevant risks, such as:

- Architectural complexity.
- Performance bottlenecks.
- Tight coupling.
- Resource lifecycle problems.
- Save compatibility.
- Integration difficulties.
- Unclear requirements.
- Testing limitations.

For each meaningful risk, describe its potential impact and mitigation.

List unresolved questions separately.

Do not hide uncertainty behind confident technical language.

### Step 8: Identify Required Project Changes

Provide a proposed list of files and resources that the implementation may introduce or modify.

For each entry, include:

- Proposed path.
- File or resource purpose.
- Whether it is new or existing.
- Main responsibility.

Example:

```text
features/
└── inventory/
    ├── scenes/
    │   └── inventory_panel.tscn
    ├── scripts/
    │   ├── inventory_controller.gd
    │   └── inventory_item.gd
    ├── resources/
    │   └── inventory_item_data.gd
    └── tests/
        └── test_inventory_controller.gd
```

This is a proposed structure, not permission to create the files.

Follow the actual project structure standards. Do not impose this example structure if the existing project uses a different valid organization.

### Step 9: Define Implementation and Validation Criteria

Translate the technical design into implementation-ready criteria.

Include:

- Expected system behavior.
- Required components and interfaces.
- Integration requirements.
- Relevant edge cases.
- Testing expectations.
- Performance constraints, if applicable.
- Documentation requirements.

Criteria must be verifiable.

Where useful, identify implementation tasks or milestones, but do not automatically create backlog items unless requested.

### Step 10: Create the Technical Design Document

Use the template:

`docs/06_templates/TECHNICAL_DESIGN_TEMPLATE.md`

Read the template before creating the document.

Create the resulting technical design in the game's project-specific documentation directory, following the project's documentation organization and naming conventions.

Do not modify the shared template to store project-specific design information.

If the project does not have an established location for technical design documents, propose an appropriate location and obtain approval before introducing a new documentation convention.

Use a descriptive filename in `snake_case.md` when consistent with the project's naming conventions.

The document should be complete enough to guide implementation without unnecessarily duplicating existing specifications.

### Step 11: Review the Design

Before presenting the document:

1. Verify that all confirmed requirements are addressed.
2. Check consistency with existing architecture.
3. Check compliance with applicable studio standards.
4. Verify that proposed paths and components are reasonable.
5. Review dependencies and integration points.
6. Check that risks and unresolved questions are visible.
7. Confirm that implementation and testing criteria are verifiable.
8. Ensure that proposals are not presented as approved decisions.
9. Verify references to existing documentation.
10. Check the document for contradictions and unnecessary duplication.

If the design conflicts with an existing ADR or authoritative project decision, identify the conflict and request a decision.

Do not silently override established decisions.

### Step 12: Present the Result for Approval

Present the completed technical design to the user.

Summarize:

- The proposed technical approach.
- Important architectural decisions.
- Main components and their responsibilities.
- Important dependencies.
- Key risks and trade-offs.
- Open questions.
- Proposed implementation scope.

Clearly distinguish confirmed requirements from proposed design decisions.

Ask for approval before implementation begins.

Do not treat document creation as authorization to implement the design.

---

## Output Requirements

The technical design document should follow the structure defined by `docs/06_templates/TECHNICAL_DESIGN_TEMPLATE.md`.

At minimum, it should communicate:

1. Purpose and scope.
2. Requirements and constraints.
3. Existing architecture and context.
4. Proposed architecture.
5. Components and responsibilities.
6. Data design.
7. Communication and execution flow.
8. Integration points.
9. Performance and reliability considerations.
10. Testing strategy.
11. Alternatives and trade-offs, when applicable.
12. Risks and open questions.
13. Proposed file and resource changes.
14. Implementation and validation criteria.
15. Related documentation.

Sections that are genuinely not applicable may be marked accordingly. Do not add filler content merely to complete a section.

## Constraints

### Documentation Only

This workflow authorizes creation of a technical design document.

The agent MUST NOT:

- Implement the proposed system.
- Modify source code.
- Create scenes or resources.
- Change project configuration.
- Install dependencies.
- Modify existing architecture.
- Create commits or merge branches.
- Treat proposed design decisions as approved.

Only create or modify the requested design document, and only after verifying the appropriate destination and following applicable documentation-management rules.

### Design Quality

The agent MUST:

- Base the design on confirmed requirements and actual project context.
- Prefer the simplest solution that satisfies the requirements.
- Reuse existing systems when appropriate.
- Follow established architecture and naming conventions.
- Use Godot and GDScript appropriately.
- Make dependencies and responsibilities explicit.
- Document meaningful trade-offs.
- Identify uncertainty and unresolved decisions.
- Avoid unnecessary abstractions and speculative infrastructure.
- Keep the design implementation-ready.

### Human Approval

The user retains authority over significant technical decisions.

The agent MUST NOT:

- Approve its own proposed architecture.
- Mark the design as approved without explicit user approval.
- Override existing ADRs or project decisions without authorization.
- Begin implementation without a separate explicit request.

---

## Completion Checklist

Before completing the workflow, verify that:

- [ ] The project structure and relevant implementation were inspected.
- [ ] The documentation inventory was consulted.
- [ ] Applicable studio and project standards were read.
- [ ] The technical design template was read.
- [ ] Requirements and constraints were identified.
- [ ] Confirmed requirements are distinguished from proposals.
- [ ] Existing systems and dependencies were considered.
- [ ] The proposed architecture is explained.
- [ ] Components and responsibilities are defined.
- [ ] Data flow and communication are documented.
- [ ] Integration and lifecycle concerns are addressed.
- [ ] Performance and reliability considerations are included where relevant.
- [ ] Testing and validation criteria are defined.
- [ ] Meaningful risks and open questions are documented.
- [ ] Proposed file changes are identified.
- [ ] Documentation references were verified.
- [ ] The resulting document was reviewed for consistency.
- [ ] No implementation changes were made.
- [ ] The design was presented for user approval.

## Final Principle

A technical design is a bridge between what the game must accomplish and how the software should accomplish it.

It should reduce implementation uncertainty, make important decisions explicit, and provide a practical direction for development.

Design only what the requirements justify. Preserve the flexibility to evolve the implementation when new evidence or approved requirements demand it.