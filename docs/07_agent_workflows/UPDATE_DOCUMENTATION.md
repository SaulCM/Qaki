# Update Documentation

## 1. Purpose

This workflow defines how an AI agent should update and maintain documentation in a game project.

The objective is to ensure that documentation accurately reflects approved requirements, design decisions, technical implementation, and production status.

The workflow establishes a controlled process for creating, modifying, reviewing, and synchronizing documentation without introducing unsupported information, duplicate sources of truth, or undocumented assumptions.

## 2. Scope

Use this workflow when:

- Creating a new project document.
- Updating an existing document.
- Correcting outdated information.
- Documenting approved design changes.
- Documenting technical implementation changes.
- Updating production and QA records.
- Synchronizing related documents.
- Updating documentation references.
- Updating the documentation inventory.
- Deprecating or replacing documents.
- Reviewing documentation consistency.

Do not use this workflow for:

- Making unapproved design decisions.
- Changing technical architecture without authorization.
- Implementing features.
- Replacing the code review process.
- Rewriting entire documents when a focused update is sufficient.
- Creating documentation that duplicates an existing authoritative source.

## 3. Authoritative References

Before modifying documentation, inspect the applicable studio standards and project rules.

### 3.1 Studio references

Relevant references include:

- `docs/00_studio_standards/documentation_standards.md`
- `docs/00_studio_standards/definition_of_done.md`
- `docs/00_studio_standards/project_structure_standards.md`
- `docs/00_studio_standards/naming_conventions.md`
- `docs/00_studio_standards/quality_standards.md`

Read additional standards when they are relevant to the document being updated.

### 3.2 Project references

Inspect available project documentation, prioritizing:

- `docs/DOCUMENTATION_INVENTORY.md`
- Game vision and core pillars.
- Game design documents.
- Gameplay specifications.
- Technical design documents.
- Architecture decision records.
- QA documentation.
- Production plans and records.
- Relevant implementation and configuration files.
- Approved decisions and previous revisions.

The actual repository structure is authoritative for file existence and location.

Do not assume that a document exists merely because another document references it.

## 4. Workflow Overview

Follow these stages:

1. Understand the documentation request.
2. Inspect documentation standards and repository structure.
3. Identify the correct document and source of truth.
4. Establish the accuracy and authority of the information.
5. Determine the required documentation changes.
6. Update the document.
7. Synchronize related documentation.
8. Validate content, structure, and references.
9. Update the documentation inventory.
10. Review the final changes.
11. Report the documentation update.

Adapt the workflow to the scope of the change. Small corrections should not require an unnecessarily extensive process.

## 5. Stage 1: Understand the Documentation Request

Determine what documentation work is required.

Identify:

- Target document.
- Requested change.
- Reason for the update.
- Related feature, system, or task.
- Expected document status.
- Relevant source information.
- Required approval.
- Potentially affected documents.

Classify the requested operation:

- **Create:** Add a new document.
- **Update:** Modify an existing document.
- **Correct:** Fix inaccurate or inconsistent information.
- **Synchronize:** Align multiple related documents.
- **Deprecate:** Mark a document as no longer authoritative.
- **Replace:** Introduce a successor document.
- **Review:** Evaluate documentation without modifying it.

If the requested document or change is ambiguous, inspect the repository and existing references before asking for clarification.

## 6. Stage 2: Inspect Documentation Standards and Repository Structure

Before making changes, inspect the documentation rules and actual project structure.

### 6.1 Documentation inventory

Read:

`docs/DOCUMENTATION_INVENTORY.md`

Use it to understand:

- Existing documents.
- Document locations.
- Document categories.
- Document purposes.
- Document status.
- Relevant relationships.

The inventory is a registry of existing documentation, not a roadmap of planned documents.

### 6.2 Inspect the actual repository

Verify:

- Whether the target document exists.
- Its actual path and filename.
- Its current contents.
- Related documents.
- Existing links and references.
- Project-specific conventions.

Do not rely exclusively on the inventory. Verify the actual file system before creating, moving, renaming, or deleting documents.

### 6.3 Preserve repository conventions

Follow:

- Documentation naming conventions.
- Markdown formatting standards.
- Project documentation hierarchy.
- Established metadata and status conventions.
- Existing document templates where applicable.

Do not introduce a new documentation structure without justification and appropriate approval.

## 7. Stage 3: Identify the Correct Document and Source of Truth

Determine where the information belongs.

### 7.1 Select the appropriate document

Use the document that owns the information.

Examples:

| Information | Appropriate document |
|---|---|
| Game identity and direction | Game vision |
| Core gameplay priorities | Core pillars |
| Gameplay rules and behavior | Gameplay specification |
| Individual mechanic behavior | Mechanic specification |
| Technical implementation approach | Technical design document |
| Significant architectural decision | Architecture Decision Record |
| Testing approach | Test plan or testing documentation |
| Individual test procedures | Test cases |
| Current production priorities | Roadmap |
| Planned work items | Backlog |
| Sprint commitments and outcomes | Sprint record |
| Completed milestone evaluation | Postmortem |

Do not create a new document when the information already has an appropriate authoritative location.

### 7.2 Single source of truth

Each important piece of information should have a clear authoritative source.

When information is needed in multiple documents:

- Maintain the full definition in its authoritative document.
- Reference the authoritative document from related documents.
- Include only the context necessary for the reader.
- Avoid independently maintaining duplicate versions of the same rules.

For example, a gameplay specification may reference a technical design document rather than reproducing its complete implementation details.

### 7.3 Studio-wide and project-specific documentation

Maintain the distinction between:

- **Studio standards:** Reusable rules and practices shared across projects.
- **Project documentation:** Decisions, specifications, plans, and records belonging to one game.
- **Templates:** Reusable structures used to generate project-specific documents.
- **Agent workflows:** Procedures that guide AI-assisted work.

Do not copy the entire studio documentation library into an individual game project.

Project-specific documents should reference applicable studio standards when useful.

Changes to studio-wide standards require appropriate authorization and must not be made simply to accommodate one project's preferences.

## 8. Stage 4: Establish Information Accuracy and Authority

Before writing, establish where the information comes from.

Possible sources include:

- Explicit user instructions.
- Approved project decisions.
- Existing authoritative documents.
- Actual implementation.
- Verified test results.
- Production records.
- Playtesting observations.
- External technical references, when relevant.

### 8.1 Classify information

Distinguish between:

- **Confirmed:** Explicitly established or verified information.
- **Approved:** A decision accepted by the authorized project owner.
- **Observed:** Information obtained from actual implementation, testing, or playtesting.
- **Derived:** A reasonable conclusion based on confirmed information.
- **Proposed:** A recommendation that has not been approved.
- **Assumed:** An unverified assumption.
- **Unknown:** Information that cannot currently be established.

Use these distinctions when they materially affect the document.

Do not present proposed, assumed, or unknown information as confirmed project facts.

### 8.2 Resolve conflicting information

When sources disagree:

1. Identify the conflicting information.
2. Inspect document status and revision history.
3. Check whether an explicit decision supersedes earlier information.
4. Inspect implementation or test evidence when relevant.
5. Determine whether the conflict can be resolved from authoritative sources.
6. Ask the user when a decision is required.

Do not silently choose between conflicting approved requirements.

### 8.3 Implementation versus specification

When documenting implementation:

- Inspect the actual implementation.
- Verify relevant behavior.
- Distinguish intended behavior from implemented behavior.
- Identify incomplete functionality.
- Do not claim a feature is complete based solely on its design document.

When updating specifications:

- Preserve approved design intent.
- Do not automatically redefine intended behavior based on an implementation that may contain defects.
- Identify discrepancies between implementation and approved design.

If a discrepancy is found, report it and determine whether the documentation or implementation should change.

## 9. Stage 5: Determine the Required Documentation Changes

Before editing, define the smallest sufficient change.

Identify:

- Sections to create.
- Sections to modify.
- Sections to remove.
- References to update.
- Related documents to synchronize.
- Metadata changes.
- Inventory changes.
- Approval requirements.

### 9.1 Minimal and focused updates

Prefer focused changes over unnecessary rewrites.

Preserve:

- Existing valid information.
- Document structure.
- Relevant history.
- Existing identifiers.
- Approved decisions.
- Useful references.

Do not rewrite a complete document merely to change a few outdated statements.

### 9.2 Preserve meaning

When editing existing content:

- Preserve the original intent.
- Avoid changing approved requirements accidentally.
- Keep terminology consistent.
- Avoid introducing contradictions.
- Maintain relevant examples and constraints.
- Clearly identify proposed changes.

If a requested update would materially change an approved design or technical decision, obtain human authorization before treating the change as approved.

## 10. Stage 6: Update the Document

Modify the appropriate document using the established standards.

### 10.1 Document structure

Follow the applicable template and documentation conventions.

Use:

- A clear document title.
- Purpose and scope when appropriate.
- Descriptive section headings.
- Consistent terminology.
- Short, understandable paragraphs.
- Lists and tables when useful.
- Code blocks for technical examples.
- References to related documents.
- Metadata and status when required.

Avoid unnecessary sections that add maintenance overhead without improving clarity.

### 10.2 Markdown quality

Verify:

- Correct heading hierarchy.
- Consistent list formatting.
- Valid Markdown syntax.
- Readable tables.
- Correct code fences.
- Appropriate inline code formatting.
- Valid relative links.
- No accidental duplicate sections.
- No unnecessary blank lines.
- No empty placeholders presented as completed content.

Use the first line for the document title. Do not add unnecessary blank lines at the beginning of the file.

### 10.3 Metadata and status

Maintain applicable metadata, such as:

- Document title.
- Document ID, if required.
- Owner.
- Status.
- Creation date.
- Last updated date.
- Version, if required.
- Related documents.

Use only the metadata fields required by the applicable standard or template.

Valid document statuses include:

- **Draft:** Initial work or incomplete documentation.
- **In Review:** Awaiting review or approval.
- **Approved:** Explicitly approved by the authorized owner.
- **Deprecated:** Retained for reference but no longer authoritative.

Do not mark a document as Approved without explicit human authorization.

### 10.4 Templates

When creating a project document from a reusable template:

1. Locate the appropriate template.
2. Preserve its intended structure.
3. Replace instructions with project-specific content.
4. Remove irrelevant optional sections when appropriate.
5. Clearly identify unresolved questions.
6. Preserve the distinction between confirmed and proposed information.

Do not leave template instructions or placeholder text in a document presented as complete.

## 11. Stage 7: Synchronize Related Documentation

After updating a document, identify other documents that may be affected.

Examples:

- A change to the game vision may affect core pillars and the GDD.
- A change to a gameplay mechanic may affect system specifications, balance documentation, and test cases.
- A change to an architecture decision may affect technical design documents and implementation guidance.
- A change to an acceptance criterion may affect test plans and test cases.
- A change to a production milestone may affect the roadmap and backlog.

### 11.1 Synchronization process

For each potentially affected document:

1. Determine whether it contains outdated information.
2. Check whether it owns that information.
3. Identify the minimum required update.
4. Update it only when justified.
5. Preserve its authority and approval status.
6. Verify cross-document consistency.

Do not update unrelated documents merely because they are conceptually connected.

### 11.2 Reference maintenance

Update references when:

- A document is renamed.
- A document is moved.
- A document is replaced.
- A referenced section changes significantly.
- A link becomes invalid.

Use relative paths where appropriate.

Do not create references to documents that do not exist.

## 12. Stage 8: Validate Documentation

Review the updated documentation before considering the work complete.

### 12.1 Accuracy

Verify:

- Statements are supported by authoritative information.
- Technical examples match the actual project.
- Requirements reflect approved decisions.
- Implementation descriptions match observed behavior.
- Proposed information is not presented as approved.
- Dates, identifiers, and statuses are accurate.

### 12.2 Consistency

Check:

- Terminology.
- Naming conventions.
- Document hierarchy.
- Requirements.
- Cross-document references.
- Related design and technical decisions.
- Project-specific constraints.

### 12.3 Completeness

Determine whether the document contains enough information for its intended purpose.

Check for:

- Missing required sections.
- Unresolved contradictions.
- Important undefined terms.
- Missing dependencies.
- Incomplete instructions.
- Unexplained assumptions.
- Placeholder text.
- Missing references where necessary.

### 12.4 Links and references

Verify:

- Internal links resolve.
- Relative paths are correct.
- Referenced files exist.
- Referenced sections exist when applicable.
- Document identifiers are valid.
- No obsolete paths remain.

### 12.5 Technical examples

When documentation contains code, configuration, commands, or technical instructions:

- Check syntax.
- Check compatibility with the project's tools and versions.
- Verify paths and filenames.
- Verify commands where possible.
- Avoid presenting untested examples as verified.

## 13. Stage 9: Update the Documentation Inventory

After creating, modifying, renaming, moving, deprecating, or deleting documentation, inspect and update:

`docs/DOCUMENTATION_INVENTORY.md`

### 13.1 Inventory requirements

The inventory MUST:

- Include documents that actually exist.
- Use exact repository-relative paths.
- Reflect actual filenames.
- Identify document categories where applicable.
- Describe document purposes accurately.
- Reflect known document statuses.
- Avoid duplicate entries.
- Remove or update obsolete paths when appropriate.

### 13.2 Inventory maintenance rules

The agent MUST NOT:

- Register planned documents that do not exist.
- Invent filenames or paths.
- Mark documents Approved without authorization.
- Remove entries merely because a document is incomplete.
- Treat the inventory as a list of future documentation tasks.
- Assume that every referenced document is present.

If a requested document is not yet created, do not register it until it exists.

If the inventory itself contains inconsistencies, correct only those that can be verified. Report unresolved discrepancies.

## 14. Stage 10: Review the Final Changes

Inspect the complete documentation diff.

Verify:

- Only intended files were modified.
- No unrelated changes were introduced.
- Existing information was not accidentally removed.
- Document links are correct.
- Metadata is accurate.
- Inventory changes are correct.
- No placeholders remain unintentionally.
- No unsupported statements were introduced.

For significant updates, use the applicable documentation review criteria and request human review when necessary.

### 14.1 Git considerations

When documentation changes are part of a development task:

- Follow the project's branching strategy.
- Use the appropriate task branch.
- Do not commit directly to protected branches.
- Do not merge pull requests.
- Do not rewrite Git history without authorization.
- Keep documentation changes related to the task.

A documentation-only change should not automatically trigger unrelated source code modifications.

## 15. Stage 11: Report the Documentation Update

Provide a concise summary of the work performed.

Include:

- Documents created.
- Documents modified.
- Documents renamed or moved.
- Documents deprecated or deleted.
- Related documents synchronized.
- Inventory changes.
- Validation performed.
- Unresolved issues.
- Approval requirements.

Distinguish completed changes from proposed changes.

Do not claim that documentation was updated if the files were not actually modified.

## 16. Special Cases

### 16.1 Documentation conflicts with implementation

If documentation and implementation disagree:

1. Identify the conflicting behavior.
2. Determine the intended behavior from approved requirements.
3. Inspect the actual implementation.
4. Identify whether the discrepancy is a documentation defect or implementation defect.
5. Report the discrepancy.
6. Update the appropriate source only after the necessary decision is established.

Do not automatically change approved specifications to match potentially incorrect implementation.

### 16.2 Documentation conflicts with an approved decision

Treat the approved decision as authoritative unless it has been explicitly superseded.

Update outdated documentation accordingly.

Preserve historical records when required.

### 16.3 Missing information

When required information is unavailable:

- Do not invent it.
- Record the missing information when useful.
- Use clear unresolved-question markers.
- Identify the information needed from the user.
- Avoid presenting incomplete work as approved or complete.

### 16.4 Document deprecation

When a document is no longer authoritative:

1. Verify that a replacement or reason for deprecation exists.
2. Update its status to Deprecated.
3. Explain why it is deprecated.
4. Reference its replacement when applicable.
5. Update incoming references where appropriate.
6. Update the documentation inventory.
7. Preserve historical content unless deletion is explicitly authorized.

### 16.5 Deleting documentation

Deletion requires explicit authorization when it removes meaningful project history, approved decisions, or important records.

Before deletion:

- Identify incoming references.
- Determine whether a replacement exists.
- Preserve necessary historical information.
- Update the inventory.
- Verify that no required information is lost.

Prefer deprecation over deletion when historical traceability matters.

## 17. Completion Criteria

The documentation update is complete when:

- The requested documentation task is understood.
- Relevant documentation standards have been inspected.
- The actual repository structure has been checked.
- The correct authoritative document has been identified.
- Information accuracy and approval status have been established.
- Required changes have been implemented.
- Related documentation has been synchronized where necessary.
- Markdown structure and formatting have been validated.
- Links and references have been checked.
- The documentation inventory reflects actual files.
- The final diff contains only intended changes.
- Unresolved issues and approval requirements have been reported.

Completion does not imply that a document has been approved.

## 18. AI Agent Rules

The agent MUST:

- Read `docs/DOCUMENTATION_INVENTORY.md` before documentation changes.
- Inspect the actual repository structure.
- Follow documentation standards.
- Preserve the single source of truth.
- Use exact existing paths and filenames.
- Verify information before documenting it.
- Distinguish confirmed facts from proposals and assumptions.
- Preserve approved decisions.
- Update related documents when genuinely necessary.
- Update the documentation inventory when required.
- Verify every inventory path.
- Preserve historical and traceable decisions.
- Report unresolved inconsistencies.
- Obtain human approval for significant changes requiring authorization.

The agent MUST NOT:

- Invent project facts.
- Create duplicate authoritative documents.
- Introduce unapproved design decisions.
- Mark documents Approved without authorization.
- Register nonexistent files.
- Rename or move documents without justification and appropriate authorization.
- Rewrite entire documents unnecessarily.
- Remove meaningful historical information without authorization.
- Claim validation that was not performed.
- Modify unrelated documentation.
- Treat the documentation inventory as a roadmap.

## 19. Final Report Format

After completing the workflow, provide the following report:

### Documentation Update Report

**Task:** [Short description]

**Related feature or project area:** [Reference or None]

**Documents created:**
- [Path or None]

**Documents modified:**
- [Path and summary or None]

**Documents renamed or moved:**
- [Old path → New path or None]

**Documents deprecated or deleted:**
- [Path and reason or None]

**Related documentation synchronized:**
- [Path and summary or None]

**Documentation inventory:**
- Updated / Not Required
- [Summary of changes]

**Validation performed:**
- Markdown structure: Passed / Failed / Not Run / Not Applicable
- Links and references: Passed / Failed / Not Run / Not Applicable
- Content consistency: Passed / Failed / Not Run / Not Applicable
- Technical examples: Passed / Failed / Not Run / Not Applicable

**Unresolved issues:** [Issues or None]

**Approval required:** Yes / No

**Recommended next steps:** [Actions or None]

Report only changes that were actually performed and validations that were actually completed.