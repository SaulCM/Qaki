---
description: Execute the authoritative test-generation workflow.
agent: build
---

Read and follow `AGENTS.md` and the applicable `.opencode/rules/` instructions.

Read `docs/07_agent_workflows/GENERATE_TESTS.md` in full and execute it. This command is a thin adapter; do not restate, reorder, or replace the procedure.

Use GdUnit4 v6.2.3 conventions. GdUnit4 is not installed in `game_project/addons/`, no test suite exists, and `.github/workflows/ci.yml` has never executed. Do not install or upgrade GdUnit4 without owner approval. If tests cannot be executed, state exactly what was generated and what remains unverified.

Do not commit, push, stage, merge, or change branches unless this task explicitly authorizes it.

Task: $ARGUMENTS
