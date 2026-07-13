# Project Bootstrap Workflow

## Purpose

Project bootstrap creates a new independent project repository from an approved project contract.

## Input

- Approved project contract.
- Approved target path.
- Any approved technology constraints.

## Output

A project repository containing at least:

- `README.md`
- `AGENTS.md`
- `PROJECT_CONTRACT.md`
- `CHANGELOG.md`
- `development log.md`
- `docs/`
- `tasks/active/`
- `tasks/completed/`
- `tasks/templates/`
- `.agentic-engineering/`
- `tests/` when applicable

## Required Metadata

The generated project should record:

- central system version;
- bootstrap date;
- source project contract;
- assumptions;
- open decisions;
- validation commands if known.

## Stopping Condition

Bootstrap is complete when:

- the target path contains the approved project structure;
- the project contract is present;
- unclear items are explicitly marked instead of invented;
- the first recommended task contract is proposed;
- no application feature has been built unless explicitly approved.

## Approval Boundary

Codex must request approval before:

- choosing a target path if not provided;
- selecting a major technology stack;
- installing dependencies;
- creating external services;
- bootstrapping a real project from the central repository task itself.

