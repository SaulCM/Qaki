
# Project Context

## 1. Project Overview

This repository contains a solo-developed video game project built with the Godot Engine.

The project is developed with assistance from AI coding agents, including Cline.

The development approach prioritizes:

- Clear and maintainable architecture.
- Modular and reusable systems.
- Professional development practices adapted to a solo developer.
- Controlled scope and manageable complexity.
- Reliable version control.
- Documented technical and design decisions.
- Incremental implementation and validation.

## 2. Project Identity

The project's actual identity, genre, setting, player experience, mechanics, and scope must be established by approved project-specific documentation.

Do not assume that previous concepts, brainstorming discussions, or unapproved proposals are final design decisions.

Treat approved project documentation as the source of truth.

When project identity or requirements are missing:

1. Inspect the existing project documentation.
2. Identify what is known and unknown.
3. Ask for clarification when the missing information materially affects implementation.
4. Do not invent major design decisions.

## 3. Development Environment

The project uses:

- Game engine: Godot.
- Primary scripting language: GDScript.
- Version control: Git.
- Remote repository: GitHub.
- Development environment: Visual Studio Code.
- AI development assistance: Cline.

Always inspect the actual project configuration before assuming specific versions, plugins, dependencies, or technical capabilities.

Do not upgrade the engine or introduce major dependencies without approval.

## 4. Development Approach

The project follows incremental development.

General workflow:

1. Understand the requirement.
2. Inspect the existing implementation.
3. Identify dependencies and applicable documentation.
4. Plan the implementation.
5. Implement a focused change.
6. Validate the change.
7. Update relevant documentation.
8. Report results.

Avoid implementing large, unrelated features in a single task.

Prefer small, independently reviewable changes.

## 5. Documentation Sources

The repository may contain:

- Studio standards.
- Game design documentation.
- Technical specifications.
- Architecture Decision Records (ADRs).
- Art and audio documentation.
- Production documentation.
- QA documentation.
- Agent workflows.

Before implementing a feature, identify which documents are relevant.

Do not assume every document applies to every task.

## 6. Authority and Conflict Resolution

Follow this order of authority:

1. Explicit instructions from the human maintainer for the current task.
2. Approved project-specific requirements and specifications.
3. Approved Architecture Decision Records.
4. Applicable studio standards.
5. Applicable domain guidelines.
6. General engineering and game-development practices.

If two authoritative sources conflict:

- Identify the conflict.
- Explain its impact.
- Do not silently choose one.
- Request clarification when necessary.

Do not treat brainstorming notes, generated drafts, or unapproved proposals as approved requirements.

## 7. Scope Control

- Work only on the requested task.
- Avoid unrelated refactoring.
- Avoid introducing features that were not requested.
- Do not modify unrelated systems.
- Do not create unnecessary documentation.
- Do not replace existing functionality without justification.
- Identify scope expansion before implementing it.

If a task reveals a necessary dependency or architectural issue, explain it before expanding the implementation scope.

## 8. AI Agent Responsibilities

The AI agent is responsible for:

- Understanding the task and existing implementation.
- Following repository rules and applicable standards.
- Producing maintainable code and documentation.
- Identifying risks and missing requirements.
- Validating its changes.
- Reporting limitations and incomplete work honestly.

The AI agent does not have independent authority to:

- Redefine the game's vision.
- Change approved design pillars.
- Replace established architecture.
- Change protected Git branches or security policies.
- Approve its own pull requests.
- Make irreversible project decisions without authorization.

## 9. Project Status

Before starting substantial work:

- Inspect the current project status documentation if present.
- Review relevant backlog items.
- Check existing work and active branches.
- Identify blockers and dependencies.

After completing authorized work:

- Update status documentation when relevant.
- Report verified progress.
- Identify unfinished work.
- Do not mark tasks complete without validating their acceptance criteria.

## 10. Definition of Completion

A task is complete only when:

- The requested functionality or documentation has been implemented.
- The change follows applicable standards.
- Relevant validation has been performed.
- No known critical regression has been ignored.
- Related documentation has been updated when necessary.
- The agent has reported results and remaining limitations.

Generating files or writing code alone does not constitute completion.

## 11. AI Tool Configuration Protection

- Never modify Cline settings, API provider selection, API keys, model selection, API endpoints, authentication credentials, or other AI tool configuration.
- Never change the configured AI provider from its current selection.
- Never attempt to optimize, repair, replace, or reconfigure the AI provider.
- Treat all AI tool configuration as user-managed and outside repository task scope.
- If a task appears to require changing AI tool configuration, stop and request explicit owner approval.
- These restrictions apply even when a configuration change appears necessary to complete a task.