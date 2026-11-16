---
description: Execute the authoritative bug-fix workflow.
agent: build
---

Read and follow `AGENTS.md` and the applicable `.opencode/rules/` instructions.

Read `docs/07_agent_workflows/FIX_BUG.md` in full and execute it. This command is a thin adapter; do not restate, reorder, or replace the procedure.

The defect must be tracked in GitHub Issues, which is the authoritative defect tracker. Require the issue reference or report that it is missing. Use the `fix/` branch prefix; never use `bugfix/`.

Do not commit, push, stage, merge, or change branches unless this task explicitly authorizes it.

Task: $ARGUMENTS
