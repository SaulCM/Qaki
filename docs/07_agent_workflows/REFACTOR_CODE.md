# Refactor Code

## 1. Purpose

This workflow defines how an AI agent should restructure existing code, scenes, resources, or documentation structure without changing observable behavior.

A refactor improves internal structure — readability, cohesion, duplication, dependency direction, naming, or file organization — while preserving the behavior the project already has. It is not a feature change, a defect fix, or a redesign.

The objective is to make structural improvement safe and reviewable in a project where automated tests may not exist. Behavior preservation must therefore be evidenced explicitly, not assumed.

## 2. Scope

Use this workflow when:

- Renaming an internal identifier whose consumers have been identified.
- Extracting or merging responsibilities without changing observable behavior.
- Moving code, scenes, or resources between directories within the allowed structure.
- Replacing duplicated logic with an existing equivalent implementation.
- Reducing coupling or improving dependency direction without changing behavior.
- Reorganizing files to comply with `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`.
- Restructuring tests, fixtures, or documentation organization without changing their meaning.

Do not use this workflow for:

- Changing gameplay, UI, audio, or any observable behavior.
- Implementing a feature or extending functionality; use `IMPLEMENT_FEATURE.md`.
- Correcting a confirmed defect; use `FIX_BUG.md`.
- Designing a new system or making a significant architectural change; use `CREATE_TECHNICAL_DESIGN.md`.
- General cleanup unrelated to a stated refactoring goal.
- Introducing a new abstraction, dependency, or pattern that the project does not already use.

If the work cannot be completed without changing observable behavior, stop and reclassify it as a behavior change. Do not perform the behavior change silently inside a refactor.

## 3. Authoritative References

### 3.1 Studio references

- `docs/00_studio_standards/DEFINITION_OF_DONE.md`
- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md`
- `docs/00_studio_standards/BRANCHING_STRATEGY.md`
- `docs/00_studio_standards/GIT_CONVENTIONS.md`
- `docs/00_studio_standards/NAMING_CONVENTIONS.md`
- `docs/00_studio_standards/PROJECT_STRUCTURE_STANDARDS.md`
- `docs/00_studio_standards/QUALITY_STANDARDS.md`
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md`
- `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md`
- `docs/02_technical_standards/GDSCRIPT_STANDARDS.md`
- `docs/02_technical_standards/SCENE_AND_NODE_CONVENTIONS.md`
- `docs/02_technical_standards/RESOURCE_MANAGEMENT.md`
- `docs/02_technical_standards/EVENT_AND_SIGNAL_GUIDELINES.md`
- `docs/02_technical_standards/TESTING_STRATEGY.md`
- `docs/02_technical_standards/PERFORMANCE_GUIDELINES.md`
- `docs/02_technical_standards/adr/ADR_PROCESS.md`

### 3.2 Project references

- Approved project-specific requirements and technical designs in `game_project/docs/`.
- The current implementation, scenes, resources, tests, and fixtures.
- Project ADRs in `game_project/docs/technical/adr/`.

Inspect the actual implementation before relying on documentation alone.

## 4. Required Inputs

Before starting, identify:

- The structural problem the refactor addresses.
- The behavior that must be preserved.
- The scope to change and the scope to leave untouched.
- The consumers of every identifier, scene, resource, or path that moves.
- The validation method available in this repository.
- Any approval the change requires.

If the goal or the preserved behavior cannot be stated precisely, do not begin editing. Report the missing input.

## 5. Workflow Principles

- **Preserve behavior.** The observable behavior before and after the refactor must be the same.
- **One purpose.** The refactor addresses one structural problem. Unrelated improvements are out of scope.
- **Smallest safe step.** Prefer several small, reversible changes over one large rewrite.
- **Evidence before and after.** Capture the baseline before editing, and validate against it afterwards.
- **No parallel implementation.** Reuse or restructure existing code; do not leave an old and a new implementation of the same behavior in place.
- **Honest reporting.** An unvalidated refactor is not complete, even when the code reads better.

## 6. Execution Procedure

### Step 1: Classify the Change

Determine whether the change is behavior-preserving.

- If observable behavior changes, stop; use `IMPLEMENT_FEATURE.md` or `FIX_BUG.md`.
- If a public surface, feature boundary, resource ownership, or persistence format changes, treat the work as an architectural change and check the ADR requirement in `docs/02_technical_standards/ARCHITECTURE_GUIDELINES.md` (section 14.2).
- If the classification is unclear, ask before editing.

**Expected result:** A stated classification and, when needed, the applicable approval.

### Step 2: Define the Behavior to Preserve

Write down the observable contract the refactor must not change. Consider:

- Public methods, their parameters, return types, and failure results.
- Signals: names, payloads, emission conditions, and ordering.
- Scene entry points, node paths used by other scenes, and resource paths referenced elsewhere.
- Saved data: field names, types, format version, and compatibility.
- Input actions and the behavior they trigger.
- UI text, layout, and interaction outcomes.
- Diagnostics that other tooling or tests depend on.

Record only behavior that can actually be observed. Do not list internal structure as behavior.

**Expected result:** A behavior-preservation list that the validation step can check.

### Step 3: Capture the Baseline

Before editing, record how the current implementation behaves.

- If automated tests exist, run the relevant suites and record the command and result.
- If no automated tests exist, build a characterization record as described in section 7.
- Record the repository state and the exact scene, build, or inputs used.
- Keep the baseline evidence where the final report can reference it.

A refactor MUST NOT begin without a baseline, unless section 7.4 applies and the limitation is recorded.

**Expected result:** Reproducible before-evidence.

### Step 4: Inspect Context and Dependencies

Inspect the code, scenes, resources, and tests that the change touches.

Search for:

- Direct references, `preload()`, `load()`, and hardcoded `res://` paths.
- Signal connections and callers.
- Resource dependencies and shared instances.
- Autoloads, groups, and global state.
- Saved data and serialized field names.
- Documentation that names the affected identifiers or paths.

Identify which features depend on the code and whether the change crosses a feature boundary.

**Expected result:** A dependency list and a boundary assessment.

### Step 5: Define Scope, Non-Goals, and the Safe Sequence

State:

- What will change.
- What will not change.
- The order of steps.
- Which steps are reversible and how.

Prefer a sequence that keeps the project runnable after each step. If the project cannot remain runnable between steps, state that explicitly and limit the intermediate state to the shortest possible interval.

**Expected result:** A scoped sequence that another developer could review.

### Step 6: Plan Validation Before Editing

Decide how each preserved behavior will be checked after the change:

- Automated tests, when a framework and runner are configured.
- Script parse check and project import.
- Scene execution and manual observation.
- Save/load round-trip.
- Diff review of public surfaces and references.

State which checks are unavailable. Do not plan a check that cannot be executed.

**Expected result:** A validation plan tied to the behavior list.

### Step 7: Implement in Small Steps

- Make one logical change at a time.
- Keep naming and formatting consistent with the surrounding code.
- Update every reference in the same change as the rename or move.
- Do not leave dangling paths, unused files, or duplicate implementations.
- Do not perform drive-by changes outside the declared scope.
- After each step, run the cheapest applicable checks.

**Expected result:** A sequence of scoped, verifiable changes.

### Step 8: Validate Behavior Preservation

Validate every item in the behavior list against the baseline.

| Check | Method | Before | After | Result |
|---|---|---|---|---|
| [Behavior] | [Test, observation, or diff] | [Baseline] | [Post-change] | [Match / Difference] |

If a difference appears:

1. Determine whether it is an unintended regression or an intended behavior change.
2. A regression MUST be corrected before the refactor is reported complete.
3. An intended behavior change means the work is no longer a refactor. Stop, report the discovery, and reclassify it.

Do not claim preservation on the strength of the diff alone.

**Expected result:** Recorded after-evidence for every preserved behavior.

### Step 9: Review Scope and Unintended Changes

Review the complete diff and verify:

- Every changed file belongs to the refactor.
- No unrelated formatting, renaming, or cleanup was introduced.
- References, resource paths, and scene dependencies resolve.
- No behavior changed silently.
- No user-owned or unrelated working-tree changes were included.

Run `git diff --check` and report its result.

**Expected result:** A clean, scoped diff.

### Step 10: Update Documentation

Update documentation when the refactor changes:

- File or directory structure.
- Documented identifiers, paths, or examples.
- The architecture summary or technical overview.
- The documentation inventory, when a document is created, renamed, moved, or deleted.

Do not update unrelated documents.

**Expected result:** Documentation consistent with the new structure.

### Step 11: Report the Result

Report using the format in section 11. State the classification, the preserved behavior, the evidence, and every limitation.

**Expected result:** A completion report that distinguishes implemented work from validated work.

## 7. Behavior-Preservation Evidence Without Automated Tests

When the project has no automated tests for the affected area, behavior preservation must be evidenced by a characterization record.

### 7.1 Characterization Record

Record the following for each preserved behavior:

| Field | Content |
|---|---|
| Behavior ID | A short identifier. |
| Behavior | What is observed, stated precisely. |
| Observation method | The scene, input, command, or test scenario used. |
| Baseline observation | The result before the change, recorded verbatim where possible. |
| Post-change observation | The same observation repeated after the change. |
| Match | `Match`, `Difference`, or `Not verified`, with the reason. |

### 7.2 What Counts as Evidence

- The same scene or build, the same inputs, and the same configuration before and after.
- Recorded console output, signal order, saved file contents, or a screenshot.
- A diff showing that a public surface is unchanged.
- A script parse check and a successful project import.
- A manual smoke check with the exact steps written down.

### 7.3 What Does Not Count as Evidence

- "The code looks equivalent."
- "The project still opens."
- A refactor with no baseline, where the reviewer must infer the old behavior.
- A passing check that does not exercise the preserved behavior.
- An unrecorded manual impression of correctness.

### 7.4 When a Baseline Cannot Be Captured

If the behavior cannot be observed before the change — for example, because it was already broken, or because the required scene or build does not exist — do not invent a baseline.

Record:

1. Which behavior could not be baselined.
2. Why it could not be baselined.
3. How the refactor's scope was limited so it cannot affect that behavior.
4. What remains unverified.

The refactor may proceed only within that limitation, and the final report MUST state it.

## 8. Git and Branching Requirements

- Follow `docs/00_studio_standards/BRANCHING_STRATEGY.md` and `docs/00_studio_standards/GIT_CONVENTIONS.md`.
- Use the `refactor/` branch prefix.
- Do not mix a behavior change into the same branch or commit as the refactor.
- Do not merge, push, tag, or rewrite history without explicit authorization.
- Preserve unrelated user changes in the working tree.
- Prefer commits that each represent one reviewed step of the sequence.

## 9. Completion Criteria

The refactor is complete only when:

- The declared structural problem is addressed.
- No behavior outside the declared scope changed.
- The behavior-preservation record is complete, or the limitation is stated.
- References resolve and no dangling paths remain.
- The diff contains no unrelated changes.
- Diagnostics show no new errors or warnings.
- Required documentation is updated.
- The completion report distinguishes implemented work from validated work.

## 10. AI Agent Rules

AI agents MUST:

- Inspect the implementation and its consumers before editing.
- State the classification and the preserved behavior before changing anything.
- Capture a baseline before editing.
- Keep the change scoped to the stated structural goal.
- Report differences, unavailable checks, and limitations honestly.

AI agents MUST NOT:

- Present a behavior change as a refactor.
- Claim behavior preservation without recorded evidence.
- Rename public identifiers without checking every consumer.
- Leave two implementations of the same behavior in place.
- Perform unrelated cleanup.
- Suppress warnings or diagnostics to make the result look clean.
- Introduce a new dependency, abstraction, or architecture without approval.

## 11. Final Report Format

### Refactor Report

- **Task:** the structural problem and the refactor's scope.
- **Classification:** behavior-preserving refactor, and why.
- **Branch and repository state:** branch, upstream state, working-tree state.
- **Changes:** files created, modified, moved, or deleted.
- **Behavior preserved:** the behavior list and how each item was checked.
- **Baseline evidence:** where it is recorded, or the limitation under section 7.4.
- **Validation performed:** every check, method, and actual result.
- **Validation not performed:** every unavailable check and why.
- **Tests:** executed tests and results, or an explicit statement that none exist.
- **Regression assessment:** what could be affected and what remains unverified.
- **Documentation:** updated documents, or a statement that none required updating.
- **Git actions:** performed, and intentionally not performed.
- **Known limitations:** unverified behavior and assumptions.
- **Out-of-scope observations:** issues noticed but not addressed.
