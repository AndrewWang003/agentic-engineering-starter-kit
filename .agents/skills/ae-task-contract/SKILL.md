# ae-task-contract

Use this skill when a user asks Codex to perform a feature, bug fix, refactor, migration, release, or other non-trivial project task.

## Goal

Create a bounded task contract that makes autonomous execution safe.

## Procedure

1. Inspect the project contract and relevant repository state.
2. Define the task objective.
3. Identify allowed changes.
4. Identify forbidden changes.
5. List approval triggers.
6. Define acceptance criteria.
7. Define validation commands.
8. Define completion evidence.
9. Ask for user approval when the task is non-trivial.

## Output

A task contract stored in the project task folder.

## Approval Boundary

Do not execute non-trivial implementation work until the task contract is approved, unless the user has explicitly authorized immediate implementation and the task is low risk.

