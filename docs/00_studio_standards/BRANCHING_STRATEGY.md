# Branching Strategy

> Status: Draft (pending owner review)
> Scope: All human and AI contributors

## 1. Purpose

This document defines how branches are created, used, integrated, and retired in the studio Git repositories.

It establishes:

- The branch hierarchy and the responsibility of each branch type.
- Protected-branch expectations.
- Branch naming, creation, and synchronization rules.
- Pull request targets and requirements.
- Review, approval, and merge requirements.
- Branch cleanup and deletion rules.
- AI agent responsibilities and restrictions.

The objective is a branching model that is:

- Simple enough for a solo developer working with AI agents to follow consistently.
- Safe, so that work is never silently lost, rewritten, or integrated without an explicit decision.
- Traceable, so that an integrated change can be related to a task, a review, and a validation record.

Commit message format, commit types, and the approved branch-name prefixes are owned by `GIT_CONVENTIONS.md`. This document defines the branch lifecycle and integration workflow around them.

## 2. Scope

This document applies to:

- The studio workspace repository.
- The Godot game project maintained under `game_project/`.
- Human contributors.
- AI agents acting on the repository.

It covers branch-level behavior only. The following subjects remain with their authoritative documents:

| Subject | Authoritative document |
|---|---|
| Branch-name prefixes, commit message format, commit types, commit rules | `docs/00_studio_standards/GIT_CONVENTIONS.md` |
| Review principles, severity, approval criteria | `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md` |
| Completion and acceptance criteria | `docs/00_studio_standards/DEFINITION_OF_DONE.md` |
| Branch-name casing and descriptive conventions | `docs/00_studio_standards/NAMING_CONVENTIONS.md` |
| Sprint-level integration expectations | `docs/04_production_standards/SPRINT_WORKFLOW.md` |
| Release preparation, release types, hotfix release process | `docs/04_production_standards/RELEASE_PROCESS.md` |
| Version numbers and release tags | `docs/04_production_standards/VERSIONING_STANDARDS.md` |
| Mandatory agent Git behavior | `.cline/rules/git-workflow.md` |

## 3. Authority and Relationship with Git Conventions

### 3.1 Authority Order

`docs/00_studio_standards/GIT_CONVENTIONS.md` is an approved studio standard and remains authoritative for the policies it defines. This document must not contradict it.

When this document and `GIT_CONVENTIONS.md` disagree:

1. `GIT_CONVENTIONS.md` takes precedence.
2. The contradiction must be reported rather than silently resolved in practice.
3. One of the two documents must be corrected through owner-approved documentation work.

`.cline/rules/git-workflow.md` defines mandatory AI agent behavior and contains protections that this document does not weaken. Nothing in this document authorizes an action that the workspace rules prohibit.

### 3.2 Requirement Keywords

- **MUST / MUST NOT** — mandatory requirement.
- **SHOULD / SHOULD NOT** — expected practice; a deviation requires a stated reason.
- **MAY** — permitted, not required.
- **Recommendation (requires owner approval)** — a proposed policy that is not yet binding. It is recorded as a decision still owed by the project owner, not as an established rule.

### 3.3 Origin of the Rules in This Document

This document was previously an empty placeholder. Every mandatory statement below is derived from an existing source:

- `docs/00_studio_standards/GIT_CONVENTIONS.md` (approved), sections 1, 5, and 6.
- `.cline/rules/git-workflow.md` (branch protection, destructive-command limits, reporting duties).
- `.clinerules/workflows/implement-feature.md` and `.clinerules/workflows/fix-bug.md` (task branch creation from `develop`, pull request target).
- `docs/07_agent_workflows/IMPLEMENT_FEATURE.md` (section 10) and `docs/07_agent_workflows/FIX_BUG.md` (section 15).
- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md` (section 8).
- `docs/04_production_standards/RELEASE_PROCESS.md` (sections 7 and 16).

Where no existing document establishes a policy, this document does not invent one. Each gap is identified in section 19 as a decision requiring project owner approval.

## 4. Branch Hierarchy and Lifecycle

The repository uses two permanent branches and short-lived task branches.

| Branch | Lifetime | Created from | Integrates into | Purpose |
|---|---|---|---|---|
| `main` | Permanent | — | — | Stable integrated line representing release-ready work |
| `develop` | Permanent | — | `main` (owner-approved merges only) | Integration branch for completed, reviewed task work |
| Task branches (`feature/`, `fix/`, `refactor/`, `test/`, `docs/`, `chore/`) | Short-lived | `develop` | `develop` | One focused unit of work |

Lifecycle of a task branch:

1. Created from an up-to-date `develop`, once the task authorizes it.
2. Used only for that task's changes.
3. Validated and reviewed.
4. Integrated into `develop` through an owner-approved pull request.
5. Deleted after merge, when the owner authorizes or performs the deletion.

Both permanent branches were established during initial repository setup (`game_project/PROJECT_STATUS.md`, section 3). This is not a full Git Flow implementation. `release/` and `hotfix/` branches are not currently approved or required; see section 10.

## 5. Protected Branches

`main` and `develop` are protected branches.

The following are mandatory:

- No direct commits to `main` or `develop`.
- No direct pushes to `main` or `develop`.
- No force-push, rebase, or history rewrite affecting `main` or `develop`.
- No deletion of `main` or `develop`.
- No merge into a protected branch without explicit project owner authorization.
- No attempt to bypass branch protection, required reviews, or required status checks.

These protections are defined in `GIT_CONVENTIONS.md` (section 5) and `.cline/rules/git-workflow.md` (sections 3 and 9). They apply equally to human contributors and AI agents.

Branch protection is enforced by the hosting platform. The configured protection rules are not currently documented in this repository; see recommendation R-5 in section 19.

## 6. The `main` Branch

`main` represents the stable, integrated line of the repository.

- `main` MUST NOT receive direct commits or direct pushes.
- Changes reach `main` only through an owner-approved pull request or an explicitly authorized merge.
- Released versions are identified by annotated tags in the `vMAJOR.MINOR.PATCH` format, created only with owner authorization (`RELEASE_PROCESS.md`, sections 7.4 and 7.5; `VERSIONING_STANDARDS.md`).
- Existing tags MUST NOT be moved, reused, or deleted to identify a different release.
- The source branch used to promote integrated work from `develop` to `main` is not yet established. See recommendation R-3 in section 19.

A contributor or AI agent that believes work must be committed to `main` MUST stop and request explicit owner authorization rather than proceeding.

## 7. The `develop` Branch

`develop` is the integration branch. Task branches are created from it and target it.

- `develop` MUST NOT receive direct commits or direct pushes.
- Task branches MUST be based on an up-to-date `develop` for feature and bug-fix work (`docs/07_agent_workflows/IMPLEMENT_FEATURE.md`, section 10; `docs/07_agent_workflows/FIX_BUG.md`, section 15).
- Pull requests from task branches MUST target `develop` unless the owner directs otherwise (`GIT_CONVENTIONS.md`, section 5).
- Only changes that satisfy the review and completion requirements should reach `develop`.
- Because `develop` is the base for new work, an integration that leaves the project unable to open or run SHOULD be reported promptly and corrected before further work builds on it.

## 8. Task Branches

### 8.1 Approved Prefixes

The approved branch prefixes, with their intended purpose, are:

| Prefix | Purpose | Example |
|---|---|---|
| `feature/` | New functionality | `feature/player-movement` |
| `fix/` | Bug fixes | `fix/inventory-duplication` |
| `refactor/` | Restructuring without behavior change | `refactor/damage-calculation` |
| `test/` | Test additions or modifications | `test/inventory-stacking` |
| `docs/` | Documentation changes | `docs/branching-strategy` |
| `chore/` | Maintenance, configuration, tooling | `chore/godot-project-settings` |

This list is owned by `GIT_CONVENTIONS.md` (section 1). No additional prefix is approved.

### 8.2 Task Branch Rules

- One task per branch. A task branch MUST address one clearly defined task.
- Task branches MUST be short-lived and integrated promptly once validated and approved.
- A task branch MUST contain only changes belonging to its task.
- Unrelated refactoring, formatting, or feature work MUST NOT be added to a task branch.
- Unrelated or user-owned working-tree changes MUST NOT be included.
- A task branch name MUST use one of the approved prefixes followed by a lowercase `kebab-case` description (section 11).

The branch name is part of the task record and SHOULD be reported in the task's completion report.

### 8.3 The `bugfix/` Prefix

`NAMING_CONVENTIONS.md` (section 12.1) and `docs/07_agent_workflows/FIX_BUG.md` (section 15) contain `bugfix/` in their examples, while the approved prefix list in `GIT_CONVENTIONS.md` (section 1) defines only `fix/`.

Resolution for this strategy:

- `fix/` is the approved bug-fix prefix, because `GIT_CONVENTIONS.md` is the approved standard for branch prefixes.
- New branches MUST NOT use `bugfix/`.
- The conflicting examples are documentation inconsistencies to be reconciled by the project owner. See recommendation R-8 in section 19.

## 9. Bug-Fix Branches

- Bug-fix work uses the `fix/` prefix and starts from an up-to-date `develop`.
- The correction follows the fix-bug workflow (`.clinerules/workflows/fix-bug.md`, `docs/07_agent_workflows/FIX_BUG.md`).
- A bug-fix branch MUST contain the correction, the relevant regression validation, and any required test or documentation update.
- A bug-fix branch MUST NOT include unrelated changes or speculative refactoring.
- If the defect affects an already published release, the correction is handled as an urgent fix under `RELEASE_PROCESS.md` (section 16). The branch convention for that case is not yet established; see section 10.

## 10. Hotfix and Release Branches (Not Established)

`RELEASE_PROCESS.md` refers to release branches conditionally: section 7.2 states that release branches SHOULD follow the studio naming conventions "when the branching strategy uses release branches", and gives `release/1.0.0` as an example. Section 4.5 and section 16 define a hotfix release process, and `VERSIONING_STANDARDS.md` (section 13.4) defines how a hotfix is versioned.

No approved branch prefix exists for either branch type, and this strategy does not adopt one on its own authority. Therefore:

- `release/` and `hotfix/` branches MUST NOT be created until the project owner approves them.
- Release and hotfix work MUST follow `RELEASE_PROCESS.md` for validation, approval, tagging, and publication regardless of how the source revision is organized.
- Publishing a release, creating a release tag, or preparing a release build requires explicit owner authorization.

The proposals in R-1 and R-2 (section 19) are recommendations only.

## 11. Branch Naming Conventions

### 11.1 Mandatory Rules

- A branch name MUST consist of an approved prefix, a `/`, and a lowercase `kebab-case` description (`NAMING_CONVENTIONS.md`, section 12.1).
- Branch names MUST NOT contain uppercase letters, spaces, underscores, or characters unsuitable for a shell or URL.
- A branch name MUST describe the task, not the person performing it.
- A branch name MUST NOT be reused for a different task after integration.

### 11.2 Descriptive Guidance

- Prefer names that identify the affected feature or system and the intended outcome: `fix/save-data-corruption`, not `fix/issue-42`.
- Avoid vague or temporary terms such as `new`, `final`, `temp`, `test2`, or `v2`.
- Avoid unnecessary length; the description should remain readable in branch listings and pull request views.
- Referencing a backlog or issue identifier is permitted when it is combined with a meaningful description.

### 11.3 Validation Pattern

The following pattern is derived from the rules above and MAY be used to check a branch name before creating it:

```text
^(feature|fix|refactor|test|docs|chore)/[a-z0-9]+(-[a-z0-9]+)*$
```

A name that does not match this pattern does not comply with the approved prefixes and casing rules.

## 12. Branch Creation and Synchronization

### 12.1 Authorization

- Creating, switching, renaming, or deleting a branch requires authorization for the current task (`.cline/rules/git-workflow.md`, section 4).
- An AI agent MUST NOT create a branch as preparation for work that was not requested.
- An AI agent MUST NOT create, rename, or move a branch that already exists.

### 12.2 Before Creating a Branch

1. Inspect `git status`, including untracked files.
2. Confirm the current branch and its upstream.
3. Confirm that no uncommitted change would be displaced.
4. Confirm that the intended name is not already in use locally or on the remote.
5. Confirm the starting point is the intended branch.

Uncommitted or untracked changes are treated as user-owned work. They MUST NOT be discarded, stashed away, or carried into an unrelated branch.

### 12.3 Starting Point

- Feature and bug-fix task branches MUST start from an up-to-date `develop`.
- Other task branches SHOULD start from `develop` unless the task justifies otherwise; the deviation SHOULD be stated in the completion report.
- A task branch MUST NOT be created from `main` without owner authorization.

### 12.4 Synchronization

A method for keeping a task branch current with `develop` is not yet established by an approved standard. Until the owner decides (recommendation R-4 in section 19):

- The task branch MAY be brought up to date by merging `develop` into it.
- Rebasing, force-pushing, and history rewriting remain prohibited on shared branches and require explicit owner authorization elsewhere (`.cline/rules/git-workflow.md`, sections 8 and 9).
- Long-lived divergence SHOULD be avoided; a branch that can no longer be integrated cleanly SHOULD be reported to the owner instead of being forced into a mergeable state.

## 13. Pull Request Requirements

### 13.1 Target

- A task branch MUST target `develop` when a pull request is opened (`GIT_CONVENTIONS.md`, section 5; `docs/07_agent_workflows/IMPLEMENT_FEATURE.md`, section 10; `docs/07_agent_workflows/FIX_BUG.md`, section 15).
- A pull request targeting `main` or another protected branch requires explicit owner authorization.
- One pull request SHOULD represent one task.

### 13.2 Description

A pull request MUST include a meaningful description (`GIT_CONVENTIONS.md`, section 5) containing at least:

- The task or purpose of the change.
- The scope of the change and the systems or files affected.
- The validation performed, with actual results.
- The validation that could not be performed, and why.
- Known limitations, assumptions, or unfinished work.
- The source branch name and intended target branch.

These expectations follow `CODE_REVIEW_GUIDELINES.md` (section 4.1) and the reporting requirements of the task workflows.

### 13.3 Automated Checks

`.github/workflows/ci.yml` and `.github/workflows/validation.yml` are currently unconfigured placeholders. Until they are configured and documented:

- A pull request MUST NOT claim automated validation that did not run.
- Required status checks cannot be relied on as a quality gate.
- Local validation and review remain the available evidence.

See recommendation R-9 in section 19.

### 13.4 Template

`.github/PULL_REQUEST_TEMPLATE.md` is currently a placeholder. Until it is completed, the description requirements in section 13.2 apply directly. See recommendation R-6 in section 19.

## 14. Code Review and Approval

`docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md` is authoritative for review principles, scope, severity, and approval criteria.

### 14.1 Review Requirements

- A pull request MUST be reviewed before integration. Review depth is proportional to complexity, risk, and impact.
- Review findings MUST be classified by severity, and blocking findings MUST be resolved before approval (`CODE_REVIEW_GUIDELINES.md`, section 6).
- Approval requires the criteria in `CODE_REVIEW_GUIDELINES.md` (section 8.1), including that relevant automated checks pass where such checks exist.
- Material changes after approval MUST be re-reviewed (`CODE_REVIEW_GUIDELINES.md`, section 8.3).

### 14.2 Approver Authority

The project owner is the only approval authority.

- An author MUST NOT present their own inspection of the change as approval.
- An AI agent MUST NOT approve, or represent its assessment as approval, for any pull request (`.clinerules/workflows/code-review.md`; `CODE_REVIEW_GUIDELINES.md`, sections 3.6 and 11).
- Where the project owner is also the author, the owner still records the review decision; AI review output remains advisory support, not approval.
- Disclosing a review limitation is required; silence is not evidence of review.

## 15. Merge Policy

- No branch may be merged without explicit project owner authorization (`GIT_CONVENTIONS.md`, section 5; `.cline/rules/git-workflow.md`, section 8).
- The project owner performs the merge, or explicitly authorizes a specific merge by a specific actor.
- AI agents MUST NOT merge, including merging their own work into `develop`.
- Merges into protected branches MUST occur through a reviewed pull request.
- A merge MUST NOT bypass required reviews, protection rules, or available checks.
- Conflicts MUST be resolved by understanding both sides. Resolving a conflict by discarding one side, or by changing behavior the owner did not request, is prohibited (`.cline/rules/git-workflow.md`, section 11).
- The merge strategy (merge commit, squash, or rebase) is not yet established. See recommendation R-7 in section 19.
- After integration, the source branch is handled according to section 16.

## 16. Branch Cleanup and Deletion

- Merged task branches SHOULD be deleted so that the branch list reflects active work only.
- Deletion is performed by the project owner, or by an actor who has explicit authorization for that specific branch.
- AI agents MUST NOT delete local or remote branches (`.cline/rules/git-workflow.md`, sections 4 and 9).
- A branch containing unmerged work MUST NOT be deleted (`docs/07_agent_workflows/FIX_BUG.md`, section 15).
- Protected branches MUST NOT be deleted under any circumstance.
- Abandoned or superseded branches require an owner decision; they are reported, not removed.
- Remote branch deletion requires explicit authorization for the exact branch.

## 17. AI Agent Responsibilities and Restrictions

### 17.1 Required Behavior

An AI agent working in the repository MUST:

- Read this document and `.cline/rules/git-workflow.md` before performing Git operations.
- Inspect `git status` and the current branch before starting a task.
- Perform work only on the branch authorized for the task.
- Keep branch content limited to the task scope.
- Report the branch name and the repository state in the task completion report.
- Report any conflict between this document, `GIT_CONVENTIONS.md`, and the workspace rules instead of choosing silently.
- Preserve unrelated user changes and untracked files.
- Request authorization before creating, switching, renaming, deleting, merging, pushing, or tagging.
- State clearly which Git actions were performed and which were not.

### 17.2 Prohibited Behavior

An AI agent MUST NOT:

- Commit directly to `main` or `develop`.
- Push to a protected branch.
- Merge any branch, including its own work.
- Force-push or rewrite shared history.
- Rebase branches that other branches or remotes may depend on.
- Create a branch for work that was not requested.
- Switch branches in a way that could displace uncommitted user changes.
- Delete, rename, or force-move existing branches.
- Resolve conflicts by discarding a side of the change.
- Bypass branch protection, reviews, or checks.
- Invent a branch convention that is not established in the approved documentation.
- Claim a merge, push, or integration occurred when it did not.

### 17.3 Escalation

An AI agent MUST stop and request owner direction when:

- The task appears to require work on a protected branch.
- The working tree contains changes that overlap the intended files.
- The required branch or target does not match the documented workflow.
- A lifecycle rule in this document is not established for the situation at hand.
- A destructive Git operation appears necessary.

## 18. Examples of Valid Branch Names

| Prefix | Valid examples |
|---|---|
| `feature/` | `feature/player-movement`, `feature/procedural-mine-generation`, `feature/inventory-system` |
| `fix/` | `fix/inventory-duplication`, `fix/save-data-corruption`, `fix/player-fall-through-floor` |
| `refactor/` | `refactor/damage-calculation`, `refactor/input-handling` |
| `test/` | `test/inventory-stacking`, `test/mine-generation-regression` |
| `docs/` | `docs/branching-strategy`, `docs/game-design-document` |
| `chore/` | `chore/update-godot-version`, `chore/repository-metadata` |

Examples of names that do not comply:

| Invalid example | Reason |
|---|---|
| `Feature/Player-Movement` | Uses an unapproved case form; prefixes and descriptions are lowercase |
| `bugfix/inventory-duplication` | `bugfix/` is not an approved prefix (section 8.3) |
| `fix/Inventory_Duplication` | Contains uppercase letters and an underscore |
| `fix player duplication` | Contains spaces and omits the `/` separator |
| `release/1.0.0` | Release branches are not yet approved (section 10) |
| `fix/bug` | Vague description; it does not identify the defect or the affected system |

## 19. Open Decisions Requiring Owner Approval

The following policies are not established by an existing approved standard. They are recorded as recommendations. None of them is binding until the project owner approves it.

| ID | Decision needed | Current state | Recommendation (requires owner approval) |
|---|---|---|---|
| R-1 | Release branches | `RELEASE_PROCESS.md` (section 7.2) refers to release branches conditionally; no approved prefix exists | Adopt `release/<MAJOR.MINOR.PATCH>` (for example `release/1.0.0`) created from `develop`, used for stabilization only, integrated into `main` by owner approval, and merged back into `develop` |
| R-2 | Hotfix branches | `RELEASE_PROCESS.md` (section 16) defines hotfix releases without a branch convention | Adopt `hotfix/<PATCH version>` created from the released revision, integrated into `main` and then `develop`, and versioned as a PATCH increment per `VERSIONING_STANDARDS.md` (section 13.4) |
| R-3 | Source branch for `main` | Not specified | Promote integrated work from `develop` into `main` through an owner-approved pull request, and tag the released revision on `main` |
| R-4 | Task-branch synchronization | Not specified | Bring a task branch up to date by merging `develop` into it; prohibit rebase and force-push on any branch shared with the remote |
| R-5 | Branch protection documentation | The hosting platform configuration is not recorded in the repository | Document the actual `main` and `develop` protection rules in repository documentation and keep the configuration consistent with section 5 |
| R-6 | Pull request template | `.github/PULL_REQUEST_TEMPLATE.md` is a placeholder | Complete the template so that every pull request carries scope, validation evidence, and known limitations as required by section 13.2 |
| R-7 | Merge strategy | Not specified | Squash-merge task branches into `develop` for a linear history, keeping the pull request as the traceable record |
| R-8 | `bugfix/` examples | `NAMING_CONVENTIONS.md` (section 12.1) and `FIX_BUG.md` (section 15) use a prefix that is not approved | Update those examples to `fix/` so every document lists the same approved prefixes |
| R-9 | Continuous integration | `.github/workflows/ci.yml` and `.github/workflows/validation.yml` are placeholders | Configure and document required checks, then update section 13.3 and the Definition of Done |
| R-10 | Workspace rule references | `.cline/rules/git-workflow.md` describes this document as containing only placeholders and instructs agents to ask for direction | Once this document is approved, update the rule's references so it points to the established policy instead of the placeholder notice |

Approving a recommendation requires a documentation change and, where relevant, a configuration change. It must not be treated as approved merely because it appears here.

## 20. Compliance Checklist

Before completing branch-related work, verify:

- [ ] The current branch and working-tree state were inspected.
- [ ] The branch corresponds to the authorized task and uses an approved prefix.
- [ ] The branch was created from the intended base branch.
- [ ] No direct work was performed on `main` or `develop`.
- [ ] No protected branch was modified, merged into, or pushed to without authorization.
- [ ] The pull request targets the documented integration branch.
- [ ] The pull request describes scope, validation evidence, and known limitations.
- [ ] No automated validation was claimed without an executed check.
- [ ] Review and approval were obtained from the project owner.
- [ ] No merge, push, tag, or branch deletion occurred without authorization.
- [ ] Conflicts, if any, were resolved without discarding user work.
- [ ] Unrelated user changes were preserved.
- [ ] The final report states the branch, the Git actions performed, and any actions intentionally not performed.

Not every item applies to every task. A non-applicable item is identified rather than assumed satisfied.

## 21. Related Documentation

- `docs/00_studio_standards/GIT_CONVENTIONS.md` — Branch prefixes, commit conventions, pull request rules.
- `docs/00_studio_standards/CODE_REVIEW_GUIDELINES.md` — Review process, severity, approval criteria.
- `docs/00_studio_standards/DEFINITION_OF_DONE.md` — Completion and acceptance criteria.
- `docs/00_studio_standards/DEVELOPMENT_PHILOSOPHY.md` — Studio development principles.
- `docs/00_studio_standards/DOCUMENTATION_STANDARDS.md` — Documentation conventions and authority.
- `docs/00_studio_standards/NAMING_CONVENTIONS.md` — Branch naming and casing conventions.
- `docs/04_production_standards/SPRINT_WORKFLOW.md` — Task completion and integration expectations.
- `docs/04_production_standards/RELEASE_PROCESS.md` — Release preparation, protected-branch rules, hotfix process.
- `docs/04_production_standards/VERSIONING_STANDARDS.md` — Version numbers, tags, hotfix versioning.
- `docs/07_agent_workflows/IMPLEMENT_FEATURE.md` — Feature implementation workflow (branch preparation).
- `docs/07_agent_workflows/FIX_BUG.md` — Bug-fix workflow (Git and branching requirements).
- `docs/07_agent_workflows/REVIEW_CODE.md` — Review workflow.
- `.cline/rules/git-workflow.md` — Mandatory agent Git behavior.
- `.clinerules/workflows/implement-feature.md`, `.clinerules/workflows/fix-bug.md`, `.clinerules/workflows/code-review.md` — Agent execution workflows.
- `.github/PULL_REQUEST_TEMPLATE.md` — Pull request description template (currently a placeholder).

## 22. Maintenance

This document SHOULD be reviewed when:

- `GIT_CONVENTIONS.md` changes its prefixes, targets, or protections.
- The project adopts release, hotfix, or maintenance branches.
- Continuous integration changes what can be verified automatically.
- The hosting platform's branch protection changes.
- Repeated integration problems show that the workflow is unclear or impractical.
- New contributors or agents misinterpret the branch model.

Changes MUST preserve the authority relationship in section 3 and MUST NOT introduce rules that contradict `GIT_CONVENTIONS.md`. The project owner is responsible for approving changes and for resolving the open decisions recorded in section 19.
