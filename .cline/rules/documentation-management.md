# Documentation Management

## 1. Purpose

This rule defines how AI agents must discover, read, create, modify, organize, maintain, and verify documentation across studio and game projects.

The studio documentation located in `docs/` is the authoritative shared knowledge base for reusable standards, guidelines, templates, and agent workflows.

Agents must use this documentation when performing tasks that depend on its requirements.

The documentation inventory is the registry of existing documentation. It is not a roadmap or a list of planned documents.

## 2. Documentation Sources

The documentation system has three primary sources.

| Source | Location | Purpose |
|---|---|---|
| Studio documentation | `docs/` | Shared standards, guidelines, templates, and workflows |
| Project documentation | Project-specific documentation directory | Game-specific requirements, specifications, decisions, and records |
| Agent instructions | `.cline/rules/` and `.cline/workflows/` | Instructions governing agent behavior and execution |

Agents must distinguish these sources and respect their respective authority.

### 2.1 Studio Documentation

The studio documentation contains:

- `00_studio_standards/` — Mandatory studio-wide practices and conventions.
- `01_game_design_guidelines/` — Reusable game design principles and methods.
- `02_technical_standards/` — Engineering and technology standards.
- `03_art_audio_standards/` — Art and audio conventions.
- `04_production_standards/` — Planning and production processes.
- `05_qa_standards/` — Testing and quality assurance practices.
- `06_templates/` — Reusable documentation templates.
- `07_agent_workflows/` — Documented procedures for AI-assisted development.

The authoritative inventory is:

`docs/DOCUMENTATION_INVENTORY.md`

The authoritative documentation standard is:

`docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`

### 2.2 Project Documentation

Project documentation describes the specific game's requirements, design, architecture, implementation, and production status.

Agents must inspect the relevant project documentation before modifying existing functionality or making project-specific decisions.

Do not replace approved project-specific requirements with generic studio guidelines.

### 2.3 Agent Instructions

Agent instructions define how Cline must behave.

Agents must follow applicable instructions in `.cline/rules/` and `.cline/workflows/`.

Agent instructions should reference authoritative studio and project documentation rather than independently reproducing its requirements.

## 3. Documentation Discovery and Loading

Agents must discover and read relevant documentation before performing tasks that depend on studio or project documentation.

### 3.1 Initial Discovery

Before starting a documentation-related task or substantial game development task, agents must:

1. Identify the repository and project being worked on.
2. Inspect the relevant repository structure.
3. Locate and read `docs/DOCUMENTATION_INVENTORY.md`, when available.
4. Identify documentation relevant to the assigned task.
5. Read the applicable mandatory studio standards.
6. Read relevant guidelines, technical standards, and QA standards.
7. Read the applicable agent workflow when one exists.
8. Read relevant project-specific documentation.
9. Inspect the existing implementation when the task involves modifying project functionality.

Do not assume that documentation has been loaded automatically into the conversation.

Explicitly inspect the actual files before relying on their requirements.

### 3.2 Task-Specific Documentation Selection

Select documentation according to the task.

| Documentation type | When to consult |
|---|---|
| Studio standards | When applicable to the task or repository activity |
| Game design guidelines | When designing or modifying gameplay, mechanics, progression, narrative, or player experience |
| Technical standards | When designing or modifying architecture, scripts, scenes, resources, persistence, or other technical systems |
| Art and audio standards | When creating, importing, modifying, or integrating art and audio assets |
| Production standards | When planning, tracking, managing, or reviewing production work |
| QA standards | When creating tests, investigating bugs, validating functionality, or planning quality activities |
| Templates | When creating a document that corresponds to an existing template |
| Agent workflows | When executing a task covered by an existing workflow |
| Project documentation | When the task affects or depends on project-specific requirements, decisions, or existing systems |

Agents MUST read applicable mandatory standards.

Agents SHOULD avoid loading unrelated documents that do not contribute to the task.

Agents MUST NOT interpret this policy as requiring all studio documentation to be read for every task.

### 3.3 Workflow Discovery

When an assigned task matches an existing documented workflow:

1. Locate the corresponding workflow in `docs/07_agent_workflows/`.
2. Read its complete contents.
3. Identify its prerequisites and required references.
4. Read the referenced standards, guidelines, and templates.
5. Follow the workflow in the specified order.
6. Obtain human approval whenever required.

Do not assume that reading a workflow means it has been executed.

Do not skip workflow requirements without a justified reason.

If no applicable workflow exists, follow the relevant studio standards and established project procedures.

### 3.4 Reference Resolution

When a document references another document, agents must:

- Follow the reference when its contents are relevant to the task.
- Prefer descriptive Markdown links with valid relative paths.
- Resolve relative paths from the directory containing the referencing document.
- Preserve exact repository-relative paths and filenames.
- Treat paths and filenames as case-sensitive.
- Verify that referenced documents physically exist before relying on them.
- Follow relevant references recursively when additional authoritative context is necessary.

Agents must not silently substitute a similarly named document when a reference is broken or ambiguous.

If a referenced document cannot be located:

1. Verify the path against the actual repository structure.
2. Check the documentation inventory when available.
3. Identify whether the document was renamed, moved, or deprecated.
4. Report the unresolved reference.
5. Request clarification if the missing information affects the task.

Do not invent missing documents or assume their contents.

### 3.5 Documentation Authority

Agents must follow the authority and conflict-resolution principles defined in:

`docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`

Agents must:

- Distinguish mandatory standards from recommendations.
- Distinguish approved documentation from drafts and proposals.
- Respect approved project-specific requirements.
- Follow applicable studio-wide standards.
- Identify contradictions rather than silently resolving significant conflicts.
- Request clarification when conflicting requirements cannot be resolved confidently.

## 4. Documentation Inventory Management

Whenever creating, modifying, renaming, moving, deprecating, or deleting documentation, follow the documentation standards defined in:

`docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`

### 4.1 Documentation Management Rules

1. Read `docs/DOCUMENTATION_INVENTORY.md` before making documentation changes.
2. Inspect the actual documentation directory structure before creating, moving, or renaming documents.
3. Update the inventory whenever a document is created, renamed, moved, deprecated, or deleted.
4. Register only documents that physically exist in the repository.
5. Use exact repository-relative paths and filenames.
6. Assign the correct document category and current document status.
7. Keep document descriptions concise and accurate.
8. Include related documents only when a meaningful relationship exists.
9. Never change a document's status to `Approved` without explicit project owner approval.
10. Never remove an inventory entry merely because a document is incomplete.
11. Do not create placeholder entries for planned documents.
12. Modifying a document does not automatically change its status. Update its status only when its review state genuinely changes.
13. When deprecating or superseding a document, identify its replacement when one exists.
14. When deleting a document, remove its inventory entry and verify that no active documents depend on it.
15. Verify that every inventory entry resolves to an existing file before completing the task.

### 4.2 Documentation Inventory Audits

When auditing documentation:

- Identify existing documents missing from the inventory.
- Identify inventory entries pointing to nonexistent files.
- Identify incorrect paths, categories, and statuses.
- Identify deprecated documents without replacement references, where applicable.
- Identify duplicate entries and inconsistent document references.
- Identify documents whose status cannot be reasonably verified.
- Report inconsistencies before making potentially destructive changes.

Do not silently remove or rewrite questionable entries to make an audit appear successful.

### 4.3 Completion Requirements

After documentation changes:

- Ensure the inventory reflects the actual repository state.
- Verify all affected paths and references.
- Report inventory changes in the task completion summary.
- Explicitly report unresolved inconsistencies rather than silently assuming they are correct.

The documentation inventory must always reflect the actual repository state. It is a record of existing documentation, not a documentation roadmap or a list of planned work.

## 5. Documentation Creation and Modification

### 5.1 Before Creating a Document

Before creating a new document:

1. Inspect the documentation inventory.
2. Inspect the relevant directory.
3. Search for existing documents covering the same subject.
4. Identify the appropriate document category and location.
5. Check whether an existing template should be used.
6. Identify relevant authoritative references.
7. Confirm that the proposed document provides meaningful value and does not duplicate existing content.

Do not create a new document when an existing document can be appropriately extended.

Do not create placeholder documents unless explicitly requested.

### 5.2 When Modifying a Document

Before modifying an existing document:

1. Read the complete document when practical.
2. Identify its purpose, scope, and authority.
3. Inspect relevant referenced documents.
4. Preserve valid existing requirements and decisions.
5. Avoid unrelated changes.
6. Verify that modifications do not introduce contradictions.
7. Update related references when necessary.

Do not silently remove approved requirements or change their meaning.

### 5.3 When Renaming or Moving Documents

When renaming or moving a document:

- Verify the intended destination.
- Preserve the document's content unless changes are explicitly required.
- Update incoming Markdown links.
- Update agent instructions and workflow references.
- Update the documentation inventory.
- Verify all affected paths.
- Check for broken references.

Do not leave references pointing to the old location.

### 5.4 When Deprecating or Deleting Documents

Before deprecating or deleting a document:

- Identify documents that depend on it.
- Identify whether an authoritative replacement exists.
- Update affected references.
- Preserve historical information when appropriate.
- Obtain authorization when the operation is destructive or affects approved documentation.
- Update the inventory.

Do not delete documentation merely because it is outdated or incomplete.

## 6. Documentation Quality and Consistency

When creating or modifying documentation, agents must:

- Follow `DOCUMENTATION_STANDARDS.md`.
- Use established terminology and naming conventions.
- Use exact paths and filenames.
- Prefer relative Markdown links within the repository.
- Reference authoritative documents instead of duplicating their contents.
- Clearly distinguish requirements, recommendations, assumptions, and proposals.
- Avoid introducing contradictory instructions.
- Use existing templates when appropriate.
- Keep documentation concise, relevant, and maintainable.

Do not invent project decisions, technical requirements, or approvals.

## 7. Documentation Verification

Before completing documentation work, agents must verify:

### 7.1 File Verification

- [ ] All modified files exist in their intended locations.
- [ ] Filenames follow repository conventions.
- [ ] No unintended duplicate documents were created.
- [ ] No unintended files were removed or renamed.

### 7.2 Reference Verification

- [ ] Internal Markdown links resolve correctly.
- [ ] Referenced documents exist.
- [ ] Relative paths resolve from the correct directories.
- [ ] Path capitalization matches actual filenames.
- [ ] Incoming references were updated after moves or renames.
- [ ] No unintended broken references remain.

### 7.3 Inventory Verification

- [ ] Every new document is registered.
- [ ] Renamed or moved documents have updated paths.
- [ ] Deleted documents are no longer registered.
- [ ] Deprecated documents have accurate statuses.
- [ ] Existing incomplete documents remain registered.
- [ ] Every inventory entry resolves to an existing file.

### 7.4 Content Verification

- [ ] No approved requirements were silently removed.
- [ ] No contradictory instructions were introduced.
- [ ] Related documents remain consistent.
- [ ] Assumptions and unresolved questions are identified.
- [ ] Approval status has not been changed without authorization.

## 8. Reporting Requirements

When completing a task involving documentation, provide a concise summary containing:

### Documents Consulted

List the important standards, guidelines, templates, workflows, and project-specific documents actually inspected.

Do not claim to have consulted documents that were not read.

### Documents Changed

List documents created, modified, renamed, moved, deprecated, or deleted.

### Inventory Changes

Explain how the documentation inventory was updated, or state that no inventory changes were necessary.

### Verification Results

Report:

- Reference verification results.
- Inventory verification results.
- Any broken or missing references.
- Any unresolved inconsistencies.
- Any assumptions or outstanding approval requirements.

Do not claim successful verification when it was not performed.

## 9. Human Approval and Agent Restrictions

AI agents may inspect, create, modify, organize, and audit documentation within their authorized permissions.

However, agents MUST NOT:

- Approve their own documentation changes.
- Change document statuses to `Approved` without project owner approval.
- Invent missing requirements or decisions.
- Silently resolve significant documentation conflicts.
- Delete or deprecate approved documentation without appropriate authorization.
- Claim that documentation was inspected when it was not.
- Claim that a task complies with standards that were not consulted.
- Modify unrelated documentation without justification.

When an action requires human approval, stop before performing that action and request approval.

## 10. Core Principle

Documentation is an active part of the development process, not an optional reference.

Agents must discover, inspect, understand, and follow applicable documentation before performing work that depends on it.

Agents must also maintain documentation and its inventory whenever their actions change the repository.

The inventory must represent the actual repository state, references must resolve to real files, and all completion claims must be supported by work that was actually performed.