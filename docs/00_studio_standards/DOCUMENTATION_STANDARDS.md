# Documentation Standards

## 1. Purpose

This document defines the standards and conventions for creating, organizing, maintaining, and managing documentation across studio projects.

Its objectives are to:

- Establish a consistent documentation structure.
- Ensure information is accurate, understandable, and actionable.
- Define clear ownership and sources of truth.
- Prevent duplication and contradictory documentation.
- Support collaboration between human developers and AI agents.
- Preserve important design and technical decisions.
- Keep documentation maintainable as projects evolve.

These standards apply to all studio documentation, including shared standards, game design documents, technical specifications, production records, QA documentation, and AI-agent instructions.

## 2. Documentation Principles

All documentation must follow these principles.

### 2.1 Purpose-Driven Documentation

Every document must have a clearly identifiable purpose.

Create documentation when it helps to:

- Communicate requirements or decisions.
- Explain systems, processes, or constraints.
- Establish standards or conventions.
- Coordinate development work.
- Preserve important project knowledge.
- Support implementation, testing, or maintenance.

Avoid creating documents that provide no meaningful value or duplicate existing information.

### 2.2 Single Source of Truth

Every important piece of information must have an identifiable authoritative location.

- Maintain each rule or decision in its designated source document.
- Reference authoritative documents instead of copying their contents.
- Avoid maintaining competing versions of the same specification.
- Update the authoritative source when a decision changes.
- Identify derived documents and keep them consistent with their sources.

For example, Git conventions belong in `GIT_CONVENTIONS.md`. Agent-specific Git behavior belongs in `.cline/rules/git-workflow.md`, which should reference the studio standard rather than reproduce it.

### 2.3 Accuracy and Consistency

Documentation must accurately represent approved decisions and current project behavior.

- Do not present assumptions as established facts.
- Do not present proposals as approved requirements.
- Use consistent terminology across documents.
- Resolve contradictions between related documents.
- Update affected documentation when implementation changes invalidate existing information.

### 2.4 Actionability

Documentation should help its intended audience perform a task, understand a system, or make a decision.

Prefer concrete instructions, examples, diagrams, tables, and acceptance criteria over vague statements.

### 2.5 Maintainability

Documents should be easy to locate, understand, review, and update.

Avoid unnecessary length, excessive cross-references, duplicated explanations, and overly complex structures.

### 2.6 Appropriate Detail

Documentation depth must be proportional to the complexity, importance, and expected lifespan of the information.

Not every feature requires a comprehensive specification. Significant systems and decisions deserve more detailed documentation than temporary experiments.

## 3. Documentation Hierarchy

Documentation is organized according to its scope and authority.

### 3.1 Repository Root and Project Root

Documentation is organized around two distinct roots.

| Root | Location | Responsibility |
|---|---|---|
| Repository root | Repository top-level directory | Studio infrastructure, reusable studio documentation, references, and repository configuration. |
| Godot project root | `game_project/` | The Godot project, game implementation, and game-specific documentation. |

The repository root is not the Godot project root.

`game_project/` contains `project.godot` and is the only directory treated as a Godot project.

### 3.2 Studio-Level Documentation

Studio-level documentation defines reusable principles, standards, guidelines, templates, and workflows shared across projects.

Location:

`docs/` at the repository root.

The shared documentation structure is:

```text
docs/
├── DOCUMENTATION_INVENTORY.md
├── 00_studio_standards/
├── 01_game_design_guidelines/
├── 02_technical_standards/
├── 03_art_audio_standards/
├── 04_production_standards/
├── 05_qa_standards/
├── 06_templates/
└── 07_agent_workflows/
```

Responsibilities:

| Directory | Purpose |
|---|---|
| `00_studio_standards/` | Mandatory studio-wide practices and conventions |
| `01_game_design_guidelines/` | Reusable game design principles and methods |
| `02_technical_standards/` | Reusable engineering and technology requirements |
| `03_art_audio_standards/` | Art, audio, and content production conventions |
| `04_production_standards/` | Planning, tracking, and production processes |
| `05_qa_standards/` | Testing and quality assurance practices |
| `06_templates/` | Reusable document templates |
| `07_agent_workflows/` | Procedures for AI-assisted development |

Studio documentation MUST NOT contain game-specific specifications, production records, or implementation details for a particular game.

### 3.3 Project-Level Documentation

Project-level documentation describes a specific game's vision, requirements, systems, implementation, and production status.

Location:

`game_project/docs/`

Recommended structure:

```text
game_project/
└── docs/
    ├── game_design/
    ├── technical/
    ├── production/
    ├── qa/
    ├── art/
    └── audio/
```

Typical categories include:

- Game vision and creative direction.
- Game design documentation.
- Technical design and architecture.
- Gameplay systems and mechanics.
- Art and audio specifications.
- Production planning and backlog.
- QA plans and test cases.
- Release and project status records.

Requirements:

- Game-specific documentation MUST be created under `game_project/docs/`.
- Documents instantiated from templates in `docs/06_templates/` MUST be stored under `game_project/docs/`.
- Reusable studio standards MUST NOT be copied into `game_project/docs/`.
- Subdirectories SHOULD be created only when an actual document requires them.

Project-specific requirements must not be placed in shared studio standards unless they are intentionally generalized and reusable.

### 3.4 Templates and Their Instantiated Documents

- Reusable studio templates are stored in repository-root `docs/06_templates/`.
- A template is not a project document. Instantiating a template produces a game-specific document under `game_project/docs/`.
- Templates SHOULD state their recommended destination using the full repository-relative path (`game_project/docs/...`).
- Studio agent workflows are stored in repository-root `docs/07_agent_workflows/`.
- Cline execution workflows are stored in `.clinerules/workflows/` and act as execution adapters to the authoritative studio workflows (Section 3.8).

### 3.5 Documentation Path Resolution

- Repository-relative documentation paths resolve from the repository root, for example `docs/06_templates/`.
- Project-relative documentation paths resolve from the Godot project root (`game_project/`); for example, a project-relative game design path resolves to `game_project/docs/game_design/`.
- Because both roots contain a `docs/` directory, documentation MUST use full repository-relative paths when identifying a document: repository-root `docs/...` for studio documentation and `game_project/docs/...` for game-specific documentation.
- Relative Markdown links resolve from the directory containing the referencing document.
- When a path is ambiguous, do not guess. Qualify the path or report the ambiguity.

### 3.6 Authority Across Documentation Roots

- Studio documentation establishes reusable standards and processes.
- Game-specific documentation establishes approved requirements for the current game.
- Approved project-specific requirements take precedence over studio guidelines for that project.
- Mandatory studio standards that govern repository-wide practice, such as documentation management and project structure, continue to apply to the game project.
- Conflicts are resolved using the authority order in Section 4.7.
- A conflict MUST NOT be resolved by copying documents between the two roots or by creating a second authoritative copy.

### 3.7 Agent Configuration and Instructions

Agent-specific instructions belong in the appropriate agent configuration directories, such as:

- `.cline/rules/`
- `.clinerules/workflows/`
- `.github/`

These files govern agent behavior and repository-specific automation.

They should reference authoritative studio and project documentation instead of duplicating entire standards.

Agent configuration is not a replacement for formal project documentation.

### 3.8 Workflow Layers and Precedence

Workflow knowledge is divided between two layers with different responsibilities.

| Layer | Location | Responsibility |
|---|---|---|
| Studio workflow layer | `docs/07_agent_workflows/` | Authoritative procedures. Defines how a task is performed. |
| Execution workflow layer | `.clinerules/workflows/` | Thin adapters. Select a task type, bind agent rules, and delegate to the authoritative studio workflow. |

Requirements:

- Studio workflows are the single source of procedural truth. A procedure MUST be defined once, in `docs/07_agent_workflows/`.
- Execution workflows are adapters, not independent procedures. Each adapter MUST identify its authoritative studio workflow by full repository-relative path and MUST instruct the reader to read and follow it.
- An adapter MUST NOT restate, reorder, extend, or replace the studio procedure, and MUST NOT introduce a procedure of its own.
- Adapters MAY carry execution-specific routing that is not part of the procedure: when the workflow applies, which agent rules bind the task, which standards govern repository operations, and where related tasks belong.
- Where an adapter and its authoritative studio workflow conflict, the studio workflow governs. The conflict MUST be reported and corrected in the adapter, not resolved by preferring the adapter.
- A new workflow MUST follow this architecture: the procedure is added to `docs/07_agent_workflows/` first, and an adapter is added only if the execution layer needs one.
- When an execution workflow has no authoritative studio workflow, the gap MUST be reported and resolved through owner-approved documentation work. The gap MUST NOT be closed by writing an independent procedure in the execution layer.
- A change that alters a procedure MUST update the authoritative studio workflow and leave the adapter consistent with it.

A workflow is therefore documented completely only when its procedure exists once in the studio layer and every execution adapter points to it.

## 4. Document Classification and Authority

Every document must have an identifiable classification.

### 4.1 Standards

Standards define mandatory practices or constraints.

They use normative language:

- **MUST:** Mandatory requirement.
- **MUST NOT:** Prohibited behavior.
- **SHOULD:** Recommended practice that may be deviated from with a justified reason.
- **SHOULD NOT:** Practice that should generally be avoided unless justified.
- **MAY:** Optional practice.

These terms should be used consistently and only when their normative meaning is intended.

### 4.2 Guidelines

Guidelines provide recommended approaches and principles.

They allow flexibility according to project context and should not be interpreted as mandatory requirements unless explicitly stated.

### 4.3 Specifications

Specifications describe approved requirements, expected behavior, constraints, and acceptance criteria.

They should be sufficiently precise to support implementation and validation.

### 4.4 Plans

Plans describe intended activities, milestones, schedules, dependencies, and expected outcomes.

A plan represents an intended course of action, not proof that the work has been completed.

### 4.5 Records

Records preserve information about completed activities, decisions, results, and historical states.

Examples include:

- Architecture Decision Records.
- Meeting or decision records.
- Test reports.
- Release notes.
- Retrospectives.

Records should not be silently rewritten to make historical decisions appear different from what actually occurred.

### 4.6 Templates

Templates define reusable structures for creating consistent documents.

They should contain instructions and placeholders that are replaced when a template is instantiated.

### 4.7 Authority and Conflict Resolution

When documentation conflicts, use the following authority principles:

1. Explicit, current project owner decisions.
2. Approved project-specific requirements and specifications.
3. Approved architectural decisions and applicable studio standards.
4. Applicable studio guidelines.
5. Draft documents and proposals.
6. General industry practices and assumptions.

The authority order must be interpreted according to the scope of each document. A project-specific gameplay specification, for example, governs that game's approved gameplay behavior, while studio-wide Git standards govern repository practices.

A Cline execution workflow in `.clinerules/workflows/` is never an independent authority. When it and its authoritative studio workflow in `docs/07_agent_workflows/` conflict, the studio workflow governs (Section 3.8).

When a conflict cannot be resolved confidently, identify it and request clarification rather than silently choosing an interpretation.

## 5. File Naming and Organization

### 5.1 File Naming

Use descriptive, consistent filenames.

Recommended conventions:

- Use uppercase `SNAKE_CASE.md` for formal shared standards and reusable templates.
- Use uppercase `SNAKE_CASE.md` for major project specifications and formal technical documents.
- Use descriptive lowercase `kebab-case.md` for agent-specific configuration and workflow files when required by the tool.
- Use stable, meaningful names rather than temporary or ambiguous labels.

Examples:

```text
DEVELOPMENT_PHILOSOPHY.md
GIT_CONVENTIONS.md
GAME_VISION.md
TECHNICAL_DESIGN.md
.cline/rules/git-workflow.md
```

Do not use filenames such as:

```text
final.md
final_v2.md
new_document.md
notes2.md
```

### 5.2 Directory Organization

- Group documents by purpose and domain.
- Keep related information together.
- Avoid excessively deep directory structures.
- Avoid placing unrelated content in generic folders.
- Preserve established directory conventions.
- Do not create new directories without a clear organizational purpose.

### 5.3 Document Location

Each document must have one primary location.

Do not create multiple independent copies of the same document in different directories.

When another location needs the information, use a relative link to the authoritative document.

## 6. Document Structure

Documents should use a consistent structure appropriate to their purpose.

### 6.1 General Document Structure

Where applicable, use the following organization:

```markdown
# Document Title

## 1. Purpose

Explain why the document exists.

## 2. Scope

Define what the document covers and excludes.

## 3. Main Content

Organize the information into meaningful sections.

## 4. Related Documentation

Reference relevant authoritative documents.

## 5. Maintenance

Describe ownership or review expectations when necessary.
```

Not every document needs every section. Templates, short references, and records may require different structures.

### 6.2 Headings

- Use a single level-one heading for the document title.
- Organize major sections using level-two headings.
- Use deeper heading levels only when needed.
- Keep heading names descriptive and consistent.
- Do not skip heading levels without a clear reason.
- Avoid excessive nesting.

### 6.3 Purpose and Scope

Formal standards, specifications, and major guidelines should define their purpose and scope.

Readers must be able to understand:

- Why the document exists.
- What it governs.
- Who or what it applies to.
- What is outside its scope.

### 6.4 Related Documentation

Include references to documents that provide necessary context or define related requirements.

References should point to authoritative sources and should not become a substitute for explaining the document's own purpose.

## 7. Writing and Formatting Standards

### 7.1 Language

- Use clear, professional, direct language.
- Prefer concise sentences.
- Avoid unnecessary jargon and marketing language.
- Define specialized terminology when necessary.
- Use consistent terms for the same concepts.
- Avoid ambiguous expressions such as "soon", "somehow", or "as needed" when precise requirements are necessary.

English is the default language for shared studio standards and technical documentation unless a project explicitly establishes another language.

### 7.2 Markdown

Use standard Markdown for documentation.

Recommended conventions:

- Use headings to establish hierarchy.
- Use bullet lists for related items without a required sequence.
- Use numbered lists for ordered procedures.
- Use tables for compact comparisons and structured information.
- Use fenced code blocks for commands, examples, and configuration.
- Use inline code for filenames, paths, commands, identifiers, and code symbols.
- Use checkboxes for actionable checklists.

### 7.3 Code and Commands

Examples must be:

- Syntactically valid where practical.
- Consistent with the project's actual toolchain.
- Clearly labeled with the appropriate language.
- Safe to execute within their documented context.

Explain potentially destructive commands and identify their prerequisites.

Do not include fabricated commands, unsupported APIs, or unverified configuration options as established instructions.

### 7.4 Tables and Diagrams

Use tables when they improve comparison or readability.

Use diagrams when they communicate relationships, workflows, dependencies, or architecture more effectively than prose.

Every diagram should have a clear purpose and remain consistent with the described system.

### 7.5 Links and References

- Prefer relative links for documents within the same repository.
- Use descriptive link text.
- Avoid unnecessary external references.
- Verify internal paths when creating or modifying links.
- Prefer official documentation for technical references.
- Include access dates for external references when their content is likely to change.

Do not invent references, citations, or external standards.

## 8. Document Status and Approval

Documents must distinguish between proposed content and approved information.

### 8.1 Recommended Status Values

Use the following statuses in the documentation inventory:

| Status | Meaning |
|---|---|
| Not Started | Document has not been created. |
| Draft | Document exists but has not been reviewed or approved. |
| In Review | Document is undergoing review. |
| Approved | Document has been reviewed and accepted as authoritative. |
| Deprecated | Document is retained for historical or migration purposes but should no longer be followed. |

A document should not be treated as approved merely because it exists in the repository.

### 8.2 Approval

The project owner is responsible for approving shared studio standards and significant project-level specifications.

AI agents and contributors may prepare or revise documentation, but must not independently declare significant standards or requirements approved.

### 8.3 Drafts and Proposals

Draft documents must clearly communicate their status.

Do not allow agents or contributors to interpret draft content as an approved decision when that distinction affects implementation.

## 9. Document Maintenance

Documentation must evolve alongside the project.

### 9.1 Update Requirements

Update documentation when changes affect:

- Approved requirements.
- System behavior.
- Architecture or dependencies.
- Development workflows.
- Technical constraints.
- Testing procedures.
- Production processes.
- Repository conventions.

Do not update unrelated documents merely to create the appearance of activity.

### 9.2 Avoid Stale Documentation

When a document becomes inaccurate:

1. Identify the outdated information.
2. Determine the authoritative source.
3. Update the affected content.
4. Verify related references and documents.
5. Record important changes where appropriate.

Do not leave known incorrect instructions in active documentation.

### 9.3 Deprecation

When a document is superseded:

- Mark it as deprecated.
- Identify its replacement.
- Explain the reason when useful.
- Update incoming references.
- Preserve historical records when they provide meaningful context.

Delete obsolete documents only when their removal is safe and authorized.

### 9.4 Documentation Inventory

Maintain a documentation inventory at:

`docs/DOCUMENTATION_INVENTORY.md`

The inventory should identify:

- Document path.
- Category.
- Purpose.
- Status.
- Dependencies or related documents.
- Last review date, when maintained.

The inventory should reflect the actual repository. Do not list planned documents as existing documents.

## 10. Documentation Quality Review

Before approving a document, verify the following.

### 10.1 Content

- [ ] The document has a clear purpose.
- [ ] Its scope is defined where necessary.
- [ ] Content is accurate and relevant.
- [ ] Requirements and recommendations are distinguishable.
- [ ] Terminology is consistent.
- [ ] Assumptions are identified.
- [ ] No known contradictions remain.

### 10.2 Structure and Readability

- [ ] The document is stored in the correct directory.
- [ ] The filename follows naming conventions.
- [ ] Headings establish a clear hierarchy.
- [ ] Sections follow a logical order.
- [ ] Formatting is consistent.
- [ ] Examples are understandable and relevant.
- [ ] Content is not unnecessarily duplicated.

### 10.3 References and Maintenance

- [ ] Internal links resolve correctly.
- [ ] External references are relevant and trustworthy.
- [ ] Referenced documents exist.
- [ ] Related documentation is consistent.
- [ ] The document's status is accurate.
- [ ] The documentation inventory is updated when necessary.

## 11. AI-Assisted Documentation

AI agents must follow these additional requirements when creating or modifying documentation and when executing tasks that depend on studio or project documentation.

### 11.1 Inspect Before Writing

Before creating a document, agents must inspect:

- Existing documentation.
- The documentation directory structure.
- Related standards and specifications.
- Relevant project implementation.
- Existing templates.
- The documentation inventory, if available.

The purpose is to prevent duplicate documents, conflicting requirements, and unnecessary structural changes.

### 11.2 Respect Document Authority

Agents must:

- Distinguish approved documents from drafts.
- Follow established sources of truth.
- Avoid inventing project decisions.
- Identify contradictions rather than silently resolving significant conflicts.
- Preserve approved requirements unless explicitly instructed otherwise.

### 11.3 Generate Consistent Documentation

Generated documents must:

- Follow this standard.
- Use consistent terminology and formatting.
- Reference authoritative documents.
- Avoid duplicating existing rules.
- Use accurate paths and filenames.
- Include only content supported by requirements, established decisions, or clearly labeled recommendations.

### 11.4 Verify Before Completion

Before reporting a documentation task as complete, agents must:

- Inspect the generated or modified files.
- Verify internal references.
- Check for duplicated or contradictory content.
- Confirm that the documents are in the intended locations.
- Update the documentation inventory when required.
- Report assumptions, unresolved questions, and incomplete work.

Agents must not claim that documentation has been approved unless the project owner has approved it.

### 11.5 Documentation Loading and Discovery

AI agents must discover and read the documentation relevant to their assigned task before taking action.

#### Documentation Discovery

Agents must:

- Read `docs/DOCUMENTATION_INVENTORY.md` when it is available to understand the documentation structure and locate relevant documents.
- Inspect the actual repository structure before accessing referenced documents.
- Use the inventory as a discovery aid, not as proof that a listed file currently exists.
- Verify that a document exists before relying on its contents.
- Follow references to authoritative documents when additional context is required.

Agents must not assume that a document exists merely because it is listed in the inventory or referenced by another document.

#### Documentation Selection

Agents must load documentation according to the task's scope and requirements.

The following rules apply:

| Documentation type | Expected agent behavior |
|---|---|
| Studio standards | Read all applicable mandatory standards. |
| Game design guidelines | Read guidelines relevant to the design task. |
| Technical standards | Read standards relevant to the proposed or existing implementation. |
| Art and audio standards | Read standards relevant to affected art, audio, or content assets. |
| Production standards | Read standards relevant to planning, scheduling, tracking, or production activities. |
| QA standards | Read standards relevant to testing, validation, and quality assurance. |
| Templates | Read the applicable template when creating a document based on it. |
| Agent workflows | Read and follow the applicable workflow when executing it. |
| Project documentation | Read approved specifications and existing project records relevant to the task. |

Agents SHOULD avoid loading unrelated documents that do not contribute to the task.

Agents MUST NOT skip applicable mandatory standards merely to reduce the amount of documentation they inspect.

#### Reference Resolution

When a document references another document, agents must:

- Follow the reference when its contents are relevant to the task.
- Prefer Markdown links with descriptive link text and valid relative paths.
- Resolve relative links from the directory containing the document with the reference.
- Preserve exact repository-relative paths and filenames.
- Treat paths and filenames as case-sensitive.
- Verify that referenced files exist before reading or relying on them.
- Follow relevant references recursively when additional authoritative context is necessary.

Agents must not silently substitute a similarly named document when a reference is broken or ambiguous.

If a reference cannot be resolved, agents must report the issue and continue only when doing so does not require an unsupported assumption or compromise an important requirement.

#### Authority and Conflict Handling

When loading multiple documents, agents must:

- Apply the authority and conflict-resolution principles defined in Section 4.7.
- Distinguish mandatory standards from recommendations and optional guidance.
- Give approved project-specific requirements authority over general guidelines for project-specific behavior.
- Preserve the authority of applicable studio-wide standards.
- Identify missing, outdated, contradictory, or ambiguous requirements.
- Request clarification when a conflict cannot be resolved confidently.

Agents must not silently ignore a relevant requirement because another document is easier to access or more convenient to follow.

#### Before Execution

Before performing substantial work, agents must identify the documentation relevant to the task and inspect the applicable sources.

When appropriate, agents should report:

- The key documents consulted.
- Important requirements or constraints identified.
- Missing or inaccessible documents.
- Unresolved conflicts or ambiguities.

Agents must not claim to have read, consulted, or followed documents that they did not actually inspect.

## 12. Documentation Security

Documentation must not expose sensitive information.

Never include:

- Passwords.
- Access tokens.
- Private SSH keys.
- API secrets.
- Authentication credentials.
- Personal information that is unnecessary for the project.

Use placeholders and references to approved secret-management mechanisms instead.

Review generated logs, screenshots, and configuration examples for accidentally exposed credentials before committing them.

## 13. Related Documentation

This document should be used together with:

- `DEVELOPMENT_PHILOSOPHY.md` — Guiding principles for development.
- `GIT_CONVENTIONS.md` — Repository and version-control conventions.
- `BRANCHING_STRATEGY.md` — Branch lifecycle and integration practices.
- `CODE_REVIEW_GUIDELINES.md` — Review and approval practices.
- `DEFINITION_OF_DONE.md` — Completion and acceptance criteria.
- `docs/06_templates/` — Reusable documentation templates.
- `docs/07_agent_workflows/` — Authoritative AI-assisted development procedures; `.clinerules/workflows/` holds their execution adapters (Section 3.8).

## 14. Maintenance

These standards should be reviewed when:

- The documentation hierarchy changes.
- New documentation categories or tools are introduced.
- Repeated documentation problems reveal gaps.
- The studio's development or collaboration processes evolve.

The project owner is responsible for maintaining and approving changes to this document.