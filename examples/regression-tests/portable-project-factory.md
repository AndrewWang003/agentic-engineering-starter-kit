# Regression Scenario: Portable Project Factory

## Purpose

Verify that an Agent using the source kit can initialize an independent managed project whose workflow operates from local files.

## Setup

Use a temporary empty directory outside this repository as the approved destination. Do not use `examples/` as a real destination.

## Scenario

1. Ask an Agent with access to this source kit to create a new project at the temporary destination.
2. Confirm that the Agent reads the source kit's `AGENTS.md` and invokes the local `start-project` workflow.
3. Approve the project summary and destination when presented.
4. Inspect the generated project.

## Expected Result

The generated project contains:

- `AGENTIC_ENGINEERING.md`
- `AGENTS.md`, `PROJECT.md`, `DEVELOPMENT.md`, and `README.md`
- `.gitignore` and `tasks/.gitkeep`
- `templates/` with the project, agent, development, task, and review templates
- `.agents/skills/` with `grill-me`, `grill-mode`, `to-spec`, `qa-planning-checkpoint`, `show-me`, `start-project`, `start-task`, and `review-task`, including local references and metadata

The generated project does not contain source-kit `tasks/` history, `examples/`, `CHANGELOG.md`, `.git/`, an absolute source-kit path, or a source-kit remote. Its root instructions point only to local files, and later source-kit adoption requires an explicit task.

## Failure Evidence

Record the missing or prohibited file, the Agent's reported destination, the exact instruction or command that produced the result, and the temporary project status before cleanup.
