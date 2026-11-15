# Git Workflow

> Status: Draft (pending owner review)
> Last updated: 2026-11-15

## 1. Purpose

This rule defines how Cline must inspect and operate the Git repository for the Qaki workspace.

It exists to protect the owner's work. Cline never assumes it owns the working tree, never discards existing changes, and never treats Git operations as a by-product of a coding task.

## 2. Authoritative Documents

| Concern | Authoritative document | Status |
|---|---|---|
| Branch naming, commit message format, commit rules, branch and PR rules, agent Git requirements | `docs/00_studio_standards/GIT_CONVENTIONS.md` | Approved |
| Branching model, integration practices, branch protection expectations | `docs/00_studio_standards/BRANCHING_STRATEGY.md` | Draft — currently contains only TODO placeholders |
| Pull request description expectations | `.github/PULL_REQUEST_TEMPLATE.md` | Present |

`docs/00_studio_standards/BRANCHING_STRATEGY.md` exists but does not yet define any policy. Until the owner completes it, the binding branch and pull-request rules are `docs/00_studio_standards/GIT_CONVENTIONS.md` sections 1 and 5, plus this rule.

Do not invent a branching model, protection policy, or integration workflow to fill that gap. Report the gap and ask for direction when a task actually depends on it.

## 3. Protected Branches

- `main` and `develop` are protected branches.
- Never commit directly to `main` or `develop`.
- Never merge into, rebase, force-push, or otherwise modify a protected branch.
- Never push to a protected branch, even with a fast-forward change.
- Never delete a protected branch.
- Do not attempt to bypass branch protection, required reviews, or required status checks.
- If a task appears to require work on `main` or `develop`, stop and request explicit owner authorization. Until it is granted, use a task branch or wait.

## 4. Branch Naming and Task Branches

Branch prefixes (`docs/00_studio_standards/GIT_CONVENTIONS.md`, section 1):

- `feature/` — new functionality.
- `fix/` — bug fixes.
- `refactor/` — restructuring without behavior change.
- `test/` — test additions or modifications.
- `docs/` — documentation changes.
- `chore/` — maintenance, configuration, tooling.

Rules:

- One task per branch. Keep branches focused and short-lived.
- Use lowercase `kebab-case` descriptions after the prefix, for example `feature/player-movement`.
- Inspect the existing local and remote branches before assuming a name is free.
- Create or switch branches only when the task authorizes it. Do not create branches as preparation for work that was not requested.
- Do not delete, rename, or force-move existing branches without explicit authorization.
- Pull requests target `develop`, not `main`.

## 5. Inspect State Before Any Git Operation

Before any Git command that reads or changes repository state:

1. Run `git status` including untracked files.
2. Identify the current branch and its upstream tracking branch.
3. Inspect the recent commit history of the current branch.
4. Identify which changes are already committed, which are staged, and which are untracked.
5. Determine whether any of those changes belong to the user rather than the current task.

Read-only inspection (`git status`, `git diff`, `git log`, `git branch`, `git show`, `git stash list`) is always allowed.

State-changing operations (commit, checkout, switch, branch, merge, rebase, reset, restore, clean, stash, push, tag) require authorization for the current task. Never perform them because they seem convenient.

## 6. User Changes Are User-Owned

- Treat every existing uncommitted or untracked change as the user's work unless it is clearly established otherwise.
- Never discard, reset, overwrite, revert, delete, or stash-drop user work without explicit approval.
- Never include unrelated user changes in a commit, a patch, or a file rewrite.
- When user changes overlap the files a task must edit, stop and ask before proceeding.
- Never run commands that would silently normalize, reformat, or re-encode files the task does not own.

## 7. Commits

Follow `docs/00_studio_standards/GIT_CONVENTIONS.md` sections 2 to 4.

- Format: `<type>(<scope>): <description>`.
- Allowed types: `feat`, `fix`, `refactor`, `test`, `docs`, `chore`, `build`, `ci`, `perf`, `style`.
- Use imperative, lowercase descriptions, preferably under 72 characters, with no trailing period.
- One commit represents one logical change.
- Do not use vague messages such as `update`, `changes`, or `fixes`.
- Never include secrets, credentials, API keys, or personal data.

Procedure:

1. Review the full diff of what will be committed (`git diff`, `git diff --staged`).
2. Confirm every changed file belongs to the assigned task.
3. Stage files explicitly by path. Do not use `git add -A` or `git add .` without verifying the resulting file list.
4. Commit only when the task explicitly authorizes committing.
5. Report the resulting commit hash and message.

Never use `--no-verify` or any other mechanism to bypass hooks or checks. Never amend a commit that has already been pushed. Never rewrite committed history.

## 8. Merges, Releases, and Shared History

- Never merge branches, including your own work branch into `develop`, without explicit owner authorization.
- Never create or delete tags, create releases, or publish a build without explicit owner authorization.
- Never push to a remote, open a pull request, or approve a pull request unless the task authorizes it.
- Never force-push, `push --force-with-lease`, or rewrite history that other branches or remotes may depend on.
- Never assume a merge is safe because the current diff looks small. Report the intended integration and wait for approval.
- The agent must never approve its own changes or present its own assessment as human approval.

## 9. Destructive Commands

Do not run these unless the owner explicitly authorizes the exact command for the exact target:

- `git reset --hard`
- `git checkout -- <path>` or `git restore` on files you did not create
- `git clean -f`, `git clean -fd`, `git clean -fdx`
- `git stash drop`, `git stash clear`, or `git stash pop` that could discard conflicts
- `git branch -D`, `git push --delete`
- `git rebase` on shared branches
- `git filter-branch`, `git filter-repo`, or `git reflog expire`
- `git gc --prune=now`

If the working tree is not in the expected state, report what you observed and ask. Do not "repair" the repository by discarding content.

## 10. Reporting Requirements

After any Git operation, report:

- The branch that was active before and after the operation.
- The commands executed and their results.
- The files staged, committed, or otherwise affected.
- Commit hashes and commit messages, when commits were created.
- Any changes intentionally left uncommitted and why.
- Any pre-existing user changes that were preserved.
- Any Git state that looks unsafe or unexpected.
- Issues discovered outside the current task scope.

Do not claim a clean working tree, a successful push, or a merged state without verifying it.

## 11. Request Owner Approval Before

- Committing, pushing, opening a pull request, merging, or tagging.
- Creating, renaming, deleting, or force-moving branches.
- Any operation on `main` or `develop`.
- Any history rewrite, force-push, or destructive reset.
- Resolving a merge or rebase conflict in a way that changes behavior the owner did not request.
- Modifying `.gitignore`, `.gitattributes`, hooks, or CI configuration.
- Changing repository settings, branch protection, or remote configuration.

## 12. Prohibited Git Operations

Cline must not:

- Commit, merge, push, tag, or create releases without authorization for the current task.
- Discard, reset, overwrite, or revert user changes.
- Commit unrelated or unintended files.
- Use `git add -A`, `git add .`, or similar broad staging without verifying the file list.
- Bypass hooks, branch protection, or required reviews.
- Force-push or rewrite shared history.
- Delete branches, tags, stashes, or remotes without approval.
- Fabricate validation evidence in a commit message or report.
- Include credentials, tokens, or secrets in any committed content.

## 13. Related Workspace Rules

- `.cline/rules/project-context.md` — repository roots, directory responsibilities, AI tool configuration protection.
- `.cline/rules/gdscript-standards.md` — validation expectations before a change is committed.
- `.cline/rules/asset-rules.md` — which generated files must never be committed.
- `.cline/rules/architecture-rules.md` — architectural review expectations before integration.
- `.cline/rules/documentation-management.md` — documentation duties that may affect the commit contents.
- `.clinerules/workflows/` — task workflows that depend on this rule, including `implement-feature.md` and `fix-bug.md`.
