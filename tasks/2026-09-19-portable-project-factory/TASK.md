# Task Contract

## Task ID And Name

2026-09-19-portable-project-factory — Make the Starter Kit initialize self-contained managed projects

## Task State And Authorization

- Contract: Accepted
- Execution: Paused
- Acceptance: Pending QA
- Acceptance authority: User
- Authorized slice or scope: Implement the approved portable-project-factory design within source-kit instructions, templates, examples, task records, and continuity files. No commit or external project write.
- Next gate before implementation or continuation: User acceptance of the completed portable-project-factory workflow or a bounded repair request.

## Background

The Starter Kit can initialize a project foundation, but its current instructions do not explicitly establish the source kit as a project factory or require a generated project to receive a complete repository-local workflow package. A new project should be independently governed by Agentic Engineering SYS after initialization.

## Goal

Enable any Agent with access to this source kit to initialize a separate project that contains its own portable Agentic Engineering SYS workflow and governance files.

## Expected Behaviour

- A Bootstrap Agent can identify this repository as the source kit and follow its local initialization workflow.
- A generated project receives local rules, templates, Skills, state files, a task directory, and a concise system manifest.
- A generated project does not depend on source-kit paths or machine-global Skills.
- Adoption of later source-kit changes is explicit and reviewable, never automatic.

## Risk And Delivery Profile

- Risk tier: Medium.
- Risk drivers: Changes persistent agent behaviour and generated project structure across Skills, templates, and user guidance.
- Base state: To be recorded when execution is approved.
- Isolation: To be decided at execution approval after checking the working tree.
- Security validation triggers: No credentials, dependencies, external services, or production changes are proposed.
- Delivery method: Local reviewable diff; no remote or release action is in scope.

## Tool And Observability Readiness

- Test interface: Repository-local Markdown, templates, and a temporary independent generated project.
- Available capability: File inspection, isolated temporary-directory simulation, local Skill validation, YAML parsing, and Git checks.
- Unverified until implementation: A fresh Agent's actual behaviour in a new external project session.

## Acceptance Scenarios

| Scenario | Expected result |
| --- | --- |
| Bootstrap discovery | An Agent reading the source kit can identify the exact local workflow and required approval gates. |
| Managed-project creation | A simulation creates all required foundation, template, Skill, and manifest files. |
| Independent operation | A fresh Agent reading only the generated project can find the local workflow and governing state. |
| Incomplete source kit | Initialization stops before producing a partial managed project. |
| Upgrade boundary | Instructions require an explicit task for later source-kit adoption. |

## Allowed Scope

- Source-kit instructions, local workflow Skill, templates, minimal example, user guidance, task records, and continuity files needed to implement the approved design.

## Forbidden Scope

- New core workflows, scripts, dependencies, plugins, runtimes, remote services, automatic synchronization, or modification of an external user project.

## Required Validation

- Static cross-file consistency checks.
- Temporary independent initialization simulation.
- Local Skill structure and metadata validation where available.
- Markdown and Git-diff integrity checks.

## Approval-Required Situations

- Any change beyond the approved portable-project-factory design.
- Adding a script, automation, dependency, plugin, or new Skill.
- Writing into a real external project directory.
- Creating, committing to, pushing, or publishing a Git repository beyond the approved scope.

## Status

Contract: Accepted; Execution: Paused; Acceptance: Pending QA
