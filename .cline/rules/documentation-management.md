# Documentation Inventory Management

Whenever creating, modifying, renaming, moving, deprecating, or deleting documentation, follow the documentation standards defined in `docs/00_studio_standards/documentation_standards.md`.

## Documentation Management Rules

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

## Documentation Inventory Audits

When auditing documentation:

- Identify existing documents missing from the inventory.
- Identify inventory entries pointing to nonexistent files.
- Identify incorrect paths, categories, and statuses.
- Identify deprecated documents without replacement references, where applicable.
- Identify duplicate entries and inconsistent document references.
- Identify documents whose status cannot be reasonably verified.
- Report inconsistencies before making potentially destructive changes.

## Completion Requirements

After documentation changes:

- Ensure the inventory reflects the actual repository state.
- Verify all affected paths and references.
- Report inventory changes in the task completion summary.
- Explicitly report unresolved inconsistencies rather than silently assuming they are correct.

The documentation inventory must always reflect the actual repository state. It is a record of existing documentation, not a documentation roadmap or a list of planned work.