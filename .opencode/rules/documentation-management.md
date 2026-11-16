# Documentation Management

## 1. Purpose

This rule defines how OpenCode discovers, reads, creates, modifies, organizes, maintains, and verifies documentation across the studio and game project.

The studio documentation in `docs/` is the authoritative shared knowledge base for reusable standards, guidelines, templates, and agent workflows. The documentation inventory is the registry of existing documentation; it is not a roadmap or a list of planned documents.

## 2. Documentation sources

| Source | Location | Purpose |
|---|---|---|
| Studio documentation | `docs/` | Shared standards, guidelines, templates, and workflows |
| Project documentation | `game_project/docs/` | Game-specific requirements, specifications, decisions, and records |
| Agent instructions | `AGENTS.md`, `opencode.json`, `.opencode/rules/`, `.opencode/command/`, `.opencode/agent/` | OpenCode behavior, workflow adapters, and read-only specialist agents |

Agents must distinguish these sources and respect their respective authority.

### 2.1 Studio documentation

- `docs/00_studio_standards/` — mandatory studio-wide practices and conventions.
- `docs/01_game_design_guidelines/` — reusable game design principles and methods.
- `docs/02_technical_standards/` — engineering and technology standards.
- `docs/03_art_audio_standards/` — art and audio conventions.
- `docs/04_production_standards/` — planning and production processes.
- `docs/05_qa_standards/` — testing and quality assurance practices.
- `docs/06_templates/` — reusable documentation templates.
- `docs/07_agent_workflows/` — authoritative procedures for AI-assisted development.

The authoritative inventory is `docs/DOCUMENTATION_INVENTORY.md`. The authoritative documentation standard is `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`.

### 2.2 Project documentation

Project documentation describes the specific game's requirements, design, architecture, implementation, and production status. In this repository it belongs under `game_project/docs/`.

Inspect relevant project documentation before modifying existing functionality or making project-specific decisions. Do not replace approved project-specific requirements with generic studio guidelines.

### 2.3 Agent instructions

OpenCode agent instructions define how the agent must behave. `AGENTS.md` routes tasks; `.opencode/rules/` contains operating rules; `.opencode/command/` contains thin adapters; `.opencode/agent/` contains read-only specialist agents.

Agent instructions must reference authoritative studio and project documentation rather than reproducing their requirements.

## 3. Documentation discovery and loading

Before a documentation-related task or substantial game-development task:

1. Identify the repository and project being worked on.
2. Inspect the relevant repository structure.
3. Read `docs/DOCUMENTATION_INVENTORY.md`.
4. Identify documentation relevant to the assigned task.
5. Read the applicable mandatory studio standards.
6. Read relevant guidelines, technical standards, and QA standards.
7. Read the applicable `docs/07_agent_workflows/` procedure.
8. Read relevant project-specific documentation.
9. Inspect the existing implementation when modifying project functionality.

Do not assume documentation has been loaded automatically. Explicitly inspect the actual files before relying on their requirements.

### 3.1 Task-specific selection

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

Read applicable mandatory standards. Avoid loading unrelated documents that do not contribute to the task. Do not interpret this policy as requiring all studio documentation to be read for every task.

### 3.2 Workflow discovery

When an assigned task matches an existing documented workflow:

1. Locate the corresponding workflow in `docs/07_agent_workflows/`.
2. Read its complete contents.
3. Identify its prerequisites and required references.
4. Read the referenced standards, guidelines, and templates.
5. Follow the workflow in the specified order.
6. Obtain human approval whenever required.

Do not assume that reading a workflow means it has been executed. Do not skip workflow requirements without a justified reason. If no applicable workflow exists, follow the relevant studio standards and established project procedures.

### 3.3 Reference resolution

When a document references another document:

- Follow the reference when its contents are relevant to the task.
- Prefer descriptive Markdown links with valid relative paths.
- Resolve relative paths from the directory containing the referencing document.
- Preserve exact repository-relative paths and filenames.
- Treat paths and filenames as case-sensitive.
- Verify that referenced documents physically exist before relying on them.
- Follow relevant references recursively when additional authoritative context is necessary.

Do not silently substitute a similarly named document when a reference is broken or ambiguous. If a referenced document cannot be located, verify the path against the repository, check the inventory, identify whether it was renamed or moved, report the unresolved reference, and request clarification if the missing information affects the task.

### 3.4 Documentation authority

Follow `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md` for authority and conflict resolution.

- Distinguish mandatory standards from recommendations.
- Distinguish approved documentation from drafts and proposals.
- Respect approved project-specific requirements.
- Follow applicable studio-wide standards.
- Identify contradictions rather than silently resolving significant conflicts.
- Request clarification when conflicting requirements cannot be resolved confidently.

## 4. Documentation inventory management

Whenever creating, modifying, renaming, moving, deprecating, or deleting documentation, follow `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`.

### 4.1 Inventory rules

1. Read `docs/DOCUMENTATION_INVENTORY.md` before making documentation changes.
2. Inspect the actual documentation directory structure before creating, moving, or renaming documents.
3. Update the inventory whenever a document is created, renamed, moved, deprecated, or deleted.
4. Register only documents that physically exist in the repository.
5. Use exact repository-relative paths and filenames.
6. Assign the correct document category and current status.
7. Keep descriptions concise and accurate.
8. Include related documents only when a meaningful relationship exists.
9. Never change a document's status to `Approved` without explicit project owner approval.
10. Never remove an inventory entry merely because a document is incomplete.
11. Do not create placeholder entries for planned documents.
12. Modifying a document does not automatically change its status. Update its status only when its review state genuinely changes.
13. When deprecating or superseding a document, identify its replacement when one exists.
14. When deleting a document, remove its inventory entry and verify that no active documents depend on it.
15. Verify that every inventory entry resolves to an existing file before completing the task.

The inventory also registers repository governance files, including `AGENTS.md`, `opencode.json`, `.opencode/`, `.github/`, and `references/`, because those files govern repository behavior. Keep those registrations consistent with the actual repository.

### 4.2 Inventory audits

When auditing documentation:

- Identify existing documents missing from the inventory.
- Identify inventory entries pointing to nonexistent files.
- Identify incorrect paths, categories, and statuses.
- Identify deprecated documents without replacement references, where applicable.
- Identify duplicate entries and inconsistent document references.
- Identify documents whose status cannot be reasonably verified.
- Report inconsistencies before making potentially destructive changes.

Do not silently remove or rewrite questionable entries to make an audit appear successful.

### 4.3 Completion requirements

After documentation changes:

- Ensure the inventory reflects the actual repository state.
- Verify all affected paths and references.
- Report inventory changes in the completion summary.
- Explicitly report unresolved inconsistencies rather than assuming they are correct.

## 5. Documentation creation and modification

### 5.1 Before creating a document

1. Inspect the documentation inventory.
2. Inspect the relevant directory.
3. Search for existing documents covering the same subject.
4. Identify the appropriate document category and location.
5. Check whether an existing template should be used.
6. Identify relevant authoritative references.
7. Confirm that the proposed document provides meaningful value and does not duplicate existing content.

Do not create a new document when an existing document can be appropriately extended. Do not create placeholder documents unless explicitly requested.

### 5.2 When modifying a document

1. Read the complete document when practical.
2. Identify its purpose, scope, and authority.
3. Inspect relevant referenced documents.
4. Preserve valid existing requirements and decisions.
5. Avoid unrelated changes.
6. Verify that modifications do not introduce contradictions.
7. Update related references when necessary.

Do not silently remove approved requirements or change their meaning.

### 5.3 When renaming or moving documents

- Verify the intended destination.
- Preserve content unless changes are explicitly required.
- Update incoming Markdown links.
- Update agent instructions and workflow references.
- Update the documentation inventory.
- Verify all affected paths and check for broken references.

Do not leave references pointing to the old location.

### 5.4 When deprecating or deleting documents

Before deprecating or deleting a document:

- Identify documents that depend on it.
- Identify whether an authoritative replacement exists.
- Update affected references.
- Preserve historical information when appropriate.
- Obtain authorization when the operation is destructive or affects approved documentation.
- Update the inventory.

Do not delete documentation merely because it is outdated or incomplete.

## 6. Documentation quality and consistency

When creating or modifying documentation:

- Follow `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`.
- Use established terminology and naming conventions.
- Use exact paths and filenames.
- Prefer relative Markdown links within the repository.
- Reference authoritative documents instead of duplicating their contents.
- Clearly distinguish requirements, recommendations, assumptions, and proposals.
- Avoid introducing contradictory instructions.
- Use existing templates when appropriate.
- Keep documentation concise, relevant, and maintainable.

Do not invent project decisions, technical requirements, or approvals.

## 7. Documentation verification

Before completing documentation work, verify:

### 7.1 File verification

- [ ] All modified files exist in their intended locations.
- [ ] Filenames follow repository conventions.
- [ ] No unintended duplicate documents were created.
- [ ] No unintended files were removed or renamed.

### 7.2 Reference verification

- [ ] Internal Markdown links resolve correctly.
- [ ] Referenced documents exist.
- [ ] Relative paths resolve from the correct directories.
- [ ] Path capitalization matches actual filenames.
- [ ] Incoming references were updated after moves or renames.
- [ ] No unintended broken references remain.

### 7.3 Inventory verification

- [ ] Every new document is registered.
- [ ] Renamed or moved documents have updated paths.
- [ ] Deleted documents are no longer registered.
- [ ] Deprecated documents have accurate statuses.
- [ ] Existing incomplete documents remain registered.
- [ ] Every inventory entry resolves to an existing file.

### 7.4 Content verification

- [ ] No approved requirements were silently removed.
- [ ] No contradictory instructions were introduced.
- [ ] Related documents remain consistent.
- [ ] Assumptions and unresolved questions are identified.
- [ ] Approval status has not been changed without authorization.

## 8. Reporting requirements

When completing a task involving documentation, provide a concise summary containing:

### Documents consulted

List the important standards, guidelines, templates, workflows, and project-specific documents actually inspected. Do not claim to have consulted documents that were not read.

### Documents changed

List documents created, modified, renamed, moved, deprecated, or deleted.

### Inventory changes

Explain how the inventory was updated, or state that no inventory changes were necessary.

### Verification results

Report reference verification, inventory verification, broken or missing references, unresolved inconsistencies, and outstanding approval requirements. Do not claim successful verification when it was not performed.

## 9. Human approval and agent restrictions

The agent may inspect, create, modify, organize, and audit documentation within its authorized permissions. However, the agent MUST NOT:

- Approve its own documentation changes.
- Change document statuses to `Approved` without project owner approval.
- Invent missing requirements or decisions.
- Silently resolve significant documentation conflicts.
- Delete or deprecate approved documentation without authorization.
- Claim that documentation was inspected when it was not.
- Claim that a task complies with standards that were not consulted.
- Modify unrelated documentation without justification.

When an action requires human approval, stop before performing it and request approval.

## 10. Core principle

Documentation is an active part of the development process, not an optional reference. Agents must discover, inspect, understand, and follow applicable documentation before performing work that depends on it. Agents must also maintain documentation and its inventory whenever their actions change the repository.

The inventory must represent the actual repository state, references must resolve to real files, and all completion claims must be supported by work that was actually performed.
