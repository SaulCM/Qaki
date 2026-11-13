
# Documentation Inventory Management

Whenever creating, modifying, renaming, moving, deprecating, or deleting documentation:

1. Read `docs/DOCUMENTATION_INVENTORY.md` before making documentation changes.
2. Inspect the actual documentation directory structure.
3. Update the inventory whenever a document is created, renamed, moved, deprecated, or deleted.
4. Register only documents that physically exist.
5. Use exact repository-relative paths and filenames.
6. Assign the correct category and current document status.
7. Keep document descriptions concise and accurate.
8. Include related documents only when a meaningful relationship exists.
9. Never change a document's status to `Approved` without explicit project owner approval.
10. Never remove an inventory entry merely because a document is incomplete.
11. Do not create placeholder entries for planned documents.
12. Verify that every inventory entry resolves to an existing file before completing the task.

When auditing documentation:

- Identify existing documents missing from the inventory.
- Identify inventory entries pointing to nonexistent files.
- Identify incorrect paths, categories, and statuses.
- Identify deprecated documents without replacement references.
- Report inconsistencies before making potentially destructive changes.

The documentation inventory must always reflect the actual repository state.
