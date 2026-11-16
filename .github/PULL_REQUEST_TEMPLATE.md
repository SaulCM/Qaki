# Pull Request

> Status: Draft
> Last updated: 2026-11-15

<!--
Complete this description before requesting review.

Required content is defined by:
- `docs/00_studio_standards/BRANCHING_STRATEGY.md` (section 13.2) — required description content.
- `docs/00_studio_standards/DEFINITION_OF_DONE.md` (sections 4, 13, and 16.1) — completion states and report contents.
- `docs/00_studio_standards/GIT_CONVENTIONS.md` (section 5) — pull request rules.
- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md` (sections 4.1 and 8.1) — author responsibilities and approval criteria.

Replace every placeholder. Do not delete a section that applies; mark it as not applicable and state why.
-->

## 1. Task

- **Task or purpose:**
- **Requirement or acceptance criteria used:**
- **Related issue, backlog item, or design document:**

## 2. Branch and Target

- **Source branch:**
- **Target branch:** `develop` (or the branch the project owner has authorized)
- **Owner authorization, when the target is not `develop`:** Not applicable / stated here:

## 3. Scope of the Change

- **Files and systems affected:**
- **Why each change belongs to this task:**
- **Explicitly out of scope:**

## 4. Completion State

Using the six states defined in `DEFINITION_OF_DONE.md` section 4:

- **Highest state reached:** Implemented / Locally validated / Automatically tested / Reviewed / Approved / Integrated
- **States not reached, and why:**

A state above `Reviewed` is not claimed without the evidence the Definition of Done requires for it.

## 5. Validation Performed

Report each check, the exact method or command, and the actual result.

| Check | Method or command | Result |
|---|---|---|
|  |  |  |

## 6. Validation Not Performed

For each check that was skipped or unavailable:

- **Check:**
- **Reason it was not performed:**
- **What remains unverified as a result:**

## 7. Tests

- **Tests executed:**
- **Result:**
- **Tests skipped, and why:**

State explicitly when no test framework, test runner, or automated test suite is configured in the repository.

## 8. Automated Checks

`.github/workflows/ci.yml` defines the automated checks for this repository: project import validation, a GDScript parse check, and GdUnit4 test execution when test suites exist (`docs/02_technical_standards/TESTING_STRATEGY.md`, sections 11.6 and 13). Record which checks actually ran, with their results. When no automated check ran — because the workflow is disabled, was not triggered, or no test suite exists — state that explicitly. Do not claim automated validation, required status checks, or continuous integration that did not run.

- **Automated checks executed:**
- **Checks not configured, and why:**

## 9. Regression Assessment

- **What the change could affect:**
- **What was checked:**
- **What remains unverified:**

## 10. Performance

- **Measured:**
- **Considered without measurement:**
- **Not applicable, because:**

## 11. Documentation

- **Documents updated:**
- **Documentation inventory updated:** Yes / No, with reason
- **Documentation not updated, and why:**

## 12. Assets

- **Assets added, changed, or removed:**
- **Import and in-context checks performed:**
- **Not applicable, because:**

## 13. Review and Approval

- **Review performed by:**
- **Review findings by severity, and their resolution:**
- **Owner approval:** Not requested / Requested / Given (quote the explicit approval)

An AI-assisted review is advisory and is not approval. A reviewer does not approve their own change.

## 14. Known Limitations and Assumptions

-

## 15. Out-of-Scope Observations

Issues noticed but deliberately not addressed because they belong to separate work.

-

## 16. Git Actions

- **Commits included:**
- **Commits, pushes, merges, or branch operations intentionally not performed:**
