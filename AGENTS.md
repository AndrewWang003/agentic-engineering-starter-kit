# AGENTS.md

These instructions apply to this repository.

## Development Rules

1. Develop new features in a modular manner when possible.
2. Maintain all functional changes in `development log.md`.
3. Treat repository files as the source of truth. Do not rely on chat history for durable system behavior.
4. Keep the central system separate from any real project it bootstraps.
5. Prefer Markdown templates, explicit workflows, and small validation scripts over custom infrastructure.

## Codex Operating Rules

When working in this repository, Codex should:

- inspect the current repository state before editing;
- keep changes scoped to the requested task;
- update `development log.md` for every functional change;
- preserve terminology from `SYSTEM_CHARTER.md`;
- avoid building runtime orchestration unless a task contract explicitly approves it;
- produce verification evidence before claiming completion.

## Approval Boundaries

Codex must stop and request approval before:

- changing the system charter or autonomy policy in a material way;
- adding a major dependency;
- creating a web app, service, database, or multi-agent runtime;
- bootstrapping a real product project;
- widening the task scope beyond the approved contract;
- changing stable templates in a way that breaks existing projects.

## Standard Task Shape

For non-trivial work, use:

1. Repository inspection.
2. Assumptions.
3. Implementation plan.
4. Scoped edits.
5. Verification.
6. Development log update.
7. Summary of changed files and unresolved decisions.

