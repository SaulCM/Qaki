
# Development Philosophy

## 1. Purpose

This document establishes the fundamental principles that guide software development, technical decision-making, collaboration, and project evolution.

Its purpose is to provide a consistent development philosophy across the studio's projects, ensuring that technical and production decisions support long-term quality without introducing unnecessary complexity.

These principles apply to all contributors, including human developers and AI agents.

The philosophy is intended to be technology-agnostic where possible. Engine-specific and language-specific requirements belong in the appropriate technical standards.

## 2. Core Philosophy

The studio prioritizes:

- **Player experience:** Technical decisions should ultimately support the intended player experience.
- **Simplicity:** Prefer the simplest solution that adequately satisfies the requirements.
- **Maintainability:** Build systems that can be understood, modified, and extended without unnecessary effort.
- **Quality:** Treat correctness, reliability, performance, and usability as integral parts of development.
- **Pragmatism:** Apply engineering principles according to the project's actual needs and constraints.
- **Iteration:** Improve the game through small, verifiable, and deliberate increments.
- **Consistency:** Preserve coherent design, architecture, workflows, and conventions.
- **Ownership:** Every change must have a clear purpose, scope, and accountable decision-maker.

The objective is not to maximize technical sophistication. It is to create a high-quality game through a sustainable and disciplined development process.

## 3. Player Experience Comes First

Technology exists to enable the intended experience.

Development decisions should be evaluated according to their contribution to:

- Gameplay quality and responsiveness.
- Clarity of player interactions.
- Consistency of game systems.
- Immersion and presentation.
- Accessibility and usability.
- Stability and performance.
- The overall creative vision.

Technical complexity is justified when it produces a meaningful improvement to the game or enables a necessary capability.

A technically elegant solution is not automatically the best solution if it makes the game harder to develop, maintain, or understand without improving the intended experience.

## 4. Simplicity Over Unnecessary Complexity

Prefer straightforward solutions over unnecessarily elaborate designs.

The studio follows these principles:

- Solve the actual problem rather than hypothetical future problems.
- Avoid introducing abstractions without a demonstrated need.
- Avoid unnecessary frameworks, dependencies, and infrastructure.
- Prefer built-in engine capabilities when they adequately satisfy requirements.
- Keep systems focused and responsibilities understandable.
- Avoid excessive configuration and indirection.
- Introduce complexity only when its benefits justify its maintenance cost.

### 4.1 Appropriate Abstraction

Abstraction should reduce complexity for the people maintaining the project.

Create reusable components, interfaces, frameworks, or shared systems when:

- Multiple use cases demonstrate a common responsibility.
- Reuse reduces meaningful duplication.
- A stable boundary between systems is required.
- Changes can be isolated more effectively.
- The abstraction makes the implementation easier to understand.

Do not create abstractions solely because similar code appears more than once. Consider whether the implementations actually represent the same concept and are likely to evolve together.

### 4.2 Avoid Premature Optimization

Do not sacrifice readability or maintainability for speculative performance improvements.

Optimize when:

- Profiling identifies a bottleneck.
- A known engine limitation requires a specific approach.
- A feature has measurable performance requirements.
- The expected workload makes the cost reasonably predictable.

Prefer measurable improvements over assumptions.

## 5. Architecture and Modularity

The project should evolve through coherent systems with clearly defined responsibilities.

Architecture should support:

- Separation of concerns.
- High cohesion and appropriate low coupling.
- Explicit dependencies.
- Reusable components where justified.
- Clear communication between systems.
- Testability and debugging.
- Incremental development.
- Controlled architectural evolution.

### 5.1 Composition Over Unnecessary Inheritance

Prefer composition when combining independent behaviors or capabilities.

Use inheritance when there is a genuine and stable hierarchical relationship.

Avoid deep inheritance trees and rigid class structures that make behavior difficult to understand or change.

### 5.2 Clear System Boundaries

Each system should have a defined responsibility and a clear way to interact with other systems.

Avoid:

- Monolithic scripts with unrelated responsibilities.
- Excessive global state.
- Circular dependencies.
- Fragile references between unrelated components.
- Duplicated ownership of the same state.
- Hidden dependencies that make systems difficult to test.

### 5.3 Architecture Must Serve the Project

Do not adopt architectural patterns simply because they are popular or commonly used in larger studios.

Patterns such as MVC, ECS, dependency injection, event buses, service locators, and other architectural approaches should be introduced only when they solve an identifiable problem.

The selected architecture should remain proportional to the game's scale, complexity, and expected evolution.

## 6. Incremental and Iterative Development

Development should progress through small, manageable, and verifiable increments.

Prefer:

- Implementing one well-defined capability at a time.
- Validating changes before building additional functionality on top of them.
- Integrating work frequently.
- Keeping changes focused.
- Identifying technical risks early.
- Maintaining a functional project whenever practical.

Large changes should be decomposed into smaller tasks with clear dependencies and acceptance criteria.

### 6.1 Vertical Slices

When developing gameplay features, prefer vertical slices when practical.

A vertical slice implements a small but complete experience across the necessary layers, such as:

- Player interaction.
- Gameplay logic.
- State management.
- Visual and audio feedback.
- UI integration.
- Testing and validation.

This helps identify integration problems and evaluate the actual player experience earlier than developing isolated systems without a working context.

### 6.2 Early Validation

Validate important assumptions as early as possible.

Use prototypes and experiments to investigate uncertain mechanics, technical feasibility, performance constraints, and interaction designs.

Prototypes should have an explicit purpose and should not automatically become production architecture.

## 7. Quality Is a Continuous Responsibility

Quality must be considered throughout development.

It is not a final phase or a task delegated exclusively to testing.

Every implementation should consider:

- Functional correctness.
- Reliability and stability.
- Maintainability.
- Performance.
- Usability.
- Security and data integrity where applicable.
- Compatibility with the project environment.
- Regression risk.

Testing, code review, documentation, and validation should be integrated into the normal development workflow.

The project must not accumulate avoidable quality problems under the assumption that they will be fixed later.

## 8. Maintainability and Long-Term Ownership

Code and project assets should remain understandable to someone who did not originally create them.

Prefer:

- Clear naming.
- Consistent conventions.
- Focused scripts and resources.
- Explicit configuration.
- Meaningful documentation.
- Predictable project organization.
- Limited and justified dependencies.
- Small, understandable changes.

Avoid clever implementations that require disproportionate effort to understand.

Document important decisions and non-obvious constraints, especially when future development depends on them.

### 8.1 Optimize for Change

Game development involves frequent changes to mechanics, balancing, content, and presentation.

Systems should accommodate expected forms of change without requiring extensive modifications across unrelated parts of the project.

However, flexibility must be justified by realistic requirements rather than speculative possibilities.

## 9. Technical Decision-Making

Technical decisions should be deliberate, documented when significant, and consistent with the project context.

Evaluate important decisions using:

1. **Purpose:** What problem needs to be solved?
2. **Requirements:** What must the solution achieve?
3. **Alternatives:** What reasonable options exist?
4. **Trade-offs:** What are the costs, risks, and benefits?
5. **Complexity:** How much additional maintenance does the solution introduce?
6. **Compatibility:** Does it fit the current architecture and toolchain?
7. **Reversibility:** How difficult would it be to change the decision later?

### 9.1 Evidence Over Assumptions

Prefer decisions supported by:

- Official documentation.
- Reproducible experiments.
- Profiling and measurements.
- Existing project behavior.
- Established engineering practices.
- Clearly stated requirements.

Distinguish verified facts from assumptions and personal preferences.

### 9.2 Avoid Unnecessary Technology Changes

Do not introduce new tools, dependencies, frameworks, or engine upgrades without evaluating their benefits and migration costs.

Existing technologies should remain in place unless there is a concrete reason to replace them.

Significant changes must be reviewed and approved by the project owner.

### 9.3 Architectural Decision Records

Significant architectural decisions should be recorded as Architecture Decision Records (ADRs).

An ADR should capture:

- The context and problem.
- The decision.
- The alternatives considered.
- The consequences and trade-offs.
- The decision status.

ADRs provide historical context and prevent previously evaluated decisions from being repeatedly reconsidered without new evidence.

## 10. Technical Debt Management

Technical debt is an intentional or unintentional compromise that may increase future maintenance or development costs.

The studio recognizes that some compromises are reasonable, especially during prototyping and early development.

However, technical debt must remain visible and manageable.

### 10.1 Acceptable Technical Debt

A temporary compromise may be accepted when:

- It enables a necessary experiment.
- It reduces implementation time without introducing unacceptable risk.
- The affected area is isolated.
- Its limitations are understood.
- There is a reasonable path to correction when needed.

### 10.2 Unacceptable Technical Debt

Avoid compromises that:

- Hide known critical defects.
- Threaten data integrity or project stability.
- Create uncontrolled dependencies.
- Make important systems difficult to understand.
- Repeatedly introduce regressions.
- Prevent meaningful validation.
- Violate mandatory security or repository protection requirements.

### 10.3 Tracking and Resolution

Meaningful technical debt should be recorded in the project backlog.

Each item should describe:

- The affected system.
- The current limitation.
- The potential impact.
- The proposed improvement.
- Its priority or urgency.

Technical debt should be reviewed during planning and addressed according to risk and development priorities.

## 11. Documentation Philosophy

Documentation should help people make decisions, understand systems, and perform work consistently.

The studio favors documentation that is:

- Accurate.
- Actionable.
- Concise but sufficiently complete.
- Consistent with the implementation.
- Organized by purpose.
- Maintained as the project evolves.

Avoid documenting obvious implementation details that are already clear from the code.

Prioritize documenting:

- Requirements and design intent.
- System responsibilities and boundaries.
- Important technical decisions.
- Non-obvious behavior and constraints.
- Development and production workflows.
- Testing and validation procedures.

Documentation must not become an independent source of truth that contradicts the actual project.

## 12. AI-Assisted Development Philosophy

AI tools are treated as development assistants, not autonomous project owners.

They may support:

- Research and technical investigation.
- Requirements analysis.
- Architecture proposals.
- Implementation.
- Testing and debugging.
- Documentation.
- Code review.
- Refactoring and maintenance.

AI-generated output must be evaluated according to the same quality expectations as human-generated work.

### 12.1 Human Direction and Accountability

The project owner retains authority over:

- Creative direction and game vision.
- Requirements and priorities.
- Architectural decisions.
- Technical standards and exceptions.
- Security and repository permissions.
- Pull request approval and merging.
- Releases and production decisions.

Agents must not silently redefine requirements or introduce significant architectural changes.

### 12.2 Context Before Implementation

Before making substantial changes, AI agents should inspect:

- Relevant project documentation.
- Existing implementation.
- Applicable studio standards.
- Approved architectural decisions.
- Current task requirements.
- Existing tests and validation procedures.

Agents should reuse established project conventions rather than inventing new ones.

### 12.3 Controlled Autonomy

AI agents should be allowed to perform clearly scoped tasks independently within their authorized permissions.

They should request clarification or approval when:

- Requirements are ambiguous.
- A significant architectural decision is necessary.
- The task requires changes outside its authorized scope.
- A destructive operation is proposed.
- Security or repository permissions are affected.
- Existing project decisions conflict.

The goal is to maximize useful automation while preserving project control and accountability.

## 13. Pragmatic Engineering for a Small Studio

The studio operates with limited development resources and must prioritize effort carefully.

Engineering processes should improve productivity and quality without becoming an unnecessary burden.

Prefer:

- Lightweight processes with clear responsibilities.
- Automation for repetitive and error-prone work.
- Reusable documentation and templates.
- Small and focused pull requests.
- Practical testing strategies.
- Simple tools that integrate well with the existing workflow.
- Processes proportional to project risk.

Avoid:

- Enterprise-level bureaucracy without a corresponding need.
- Excessive documentation maintenance.
- Unnecessary meetings and approval layers.
- Complex infrastructure that provides little practical value.
- Applying every industry pattern or methodology indiscriminately.

Professional standards should improve the development process, not obstruct it.

## 14. Continuous Improvement

The development philosophy should evolve as the studio gains experience.

Improve processes and standards based on:

- Recurring defects.
- Development bottlenecks.
- Review feedback.
- Testing results.
- Technical limitations.
- Tooling improvements.
- Lessons learned from completed work.

Changes should be deliberate and documented when they affect established practices.

Avoid changing standards merely for novelty or personal preference.

## 15. Relationship with Other Studio Standards

This document establishes guiding principles. Specific operational requirements are defined by the corresponding studio standards.

| Document | Responsibility |
|---|---|
| `GIT_CONVENTIONS.md` | Git usage and repository conventions |
| `BRANCHING_STRATEGY.md` | Branch lifecycle and integration workflow |
| `CODE_REVIEW_GUIDELINES.md` | Code review and approval practices |
| `DEFINITION_OF_DONE.md` | Completion and acceptance criteria |
| `docs/01_game_design_guidelines/` | Game design principles and practices |
| `docs/02_technical_standards/` | Technical implementation requirements |
| `docs/03_art_audio_standards/` | Art and audio production standards |
| `docs/04_production_standards/` | Planning and production practices |
| `docs/05_qa_standards/` | Quality assurance and testing standards |
| `docs/07_agent_workflows/` | AI-assisted development procedures |

In case of conflict, explicit project owner decisions and approved project-specific requirements take precedence over general recommendations in this philosophy.

Mandatory studio standards remain applicable unless an exception is explicitly authorized.

## 16. Maintenance

This document should be reviewed when:

- The studio's development approach changes significantly.
- New technologies or development practices are adopted.
- Repeated project issues reveal gaps in existing principles.
- The balance between process, quality, and productivity needs adjustment.

The project owner is responsible for maintaining and approving changes to this document.