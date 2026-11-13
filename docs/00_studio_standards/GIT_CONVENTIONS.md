# Git & Commit Conventions

> Status: Approved
> Scope: All human and AI contributors

## 1. Branch Naming

Use the following prefixes:

- `feature/` — New functionality.
- `fix/` — Bug fixes.
- `refactor/` — Code restructuring without behavior changes.
- `test/` — Test additions or modifications.
- `docs/` — Documentation changes.
- `chore/` — Maintenance, configuration, tooling.

Examples:
- `feature/player-movement`
- `feature/procedural-mine-generation`
- `fix/inventory-duplication`
- `docs/game-design-document`

## 2. Commit Message Format

Follow Conventional Commits:

`<type>(<scope>): <description>`

Examples:
- `feat(player): add movement controller`
- `feat(mining): implement resource extraction`
- `fix(inventory): prevent item duplication`
- `test(mining): add extraction unit tests`
- `docs(narrative): document protagonist background`
- `refactor(player): separate movement logic`
- `chore(ci): configure automated validation`

## 3. Allowed Commit Types

| Type      | Purpose                             |
|-----------|-------------------------------------|
| feat      | New functionality                   |
| fix       | Bug fix                             |
| refactor  | Internal restructuring              |
| test      | Testing changes                     |
| docs      | Documentation                       |
| chore     | Maintenance and configuration       |
| build     | Build system or dependencies        |
| ci        | CI/CD configuration                 |
| perf      | Performance improvement             |
| style     | Formatting without behavior changes |

## 4. Commit Message Rules

- Use imperative descriptions.
- Keep the subject concise (preferably under 72 characters).
- Do not end the subject with a period.
- Use lowercase descriptions.
- One commit should represent one logical change.
- Avoid vague messages such as `update`, `changes`, or `fixes`.
- Never include API keys, credentials, or sensitive information.

## 5. Branch and Pull Request Rules

- Never commit directly to `main` or `develop`.
- Create a separate branch for each task.
- Keep branches focused and short-lived.
- Target `develop` when opening pull requests.
- Include a meaningful PR description and testing evidence.
- Never merge without explicit project-owner approval.

## 6. AI Agent Requirements

Before committing:

1. Inspect `git status`.
2. Review all modified files.
3. Ensure changes are related to the assigned task.
4. Run relevant tests and validation.
5. Use the required commit message format.
6. Never commit unrelated changes.

AI agents must never merge their own pull requests or bypass repository protections.

## 7. Commit Examples

feat(shooting): add shooting mechanics
fix(player): prevent movement through mine walls
test(inventory): add item stacking tests
docs(art): define environment asset standards
chore(godot): configure project settings