# Task Lifecycle Workflow

## Purpose

The task lifecycle governs features, bugs, refactors, migrations, releases, and documentation changes in a real project.

## Input

- User request or project backlog item.
- Current project contract.
- Relevant repository state.

## Output

- Task contract.
- Implementation plan.
- Changed files within scope.
- Verification report.
- Retrospective.
- Optional central system feedback.

## Workflow

1. Inspect the project contract and relevant files.
2. Draft a task contract.
3. Get user approval when the task is non-trivial.
4. Create an implementation plan.
5. Execute within allowed changes.
6. Run validation commands.
7. Fix failures caused by the task when allowed.
8. Produce a verification report.
9. Produce a retrospective.
10. Generate central feedback only for reusable workflow or central-system issues.

## Stopping Condition

The task is complete when all acceptance criteria are satisfied or explicitly marked unresolved, validation evidence is recorded, and no approval-triggering issue remains unaddressed.

## Approval Boundary

Codex must stop and request approval if:

- scope must expand;
- the project contract must change;
- a public interface changes unexpectedly;
- a major dependency is needed;
- destructive data changes are required;
- requirements conflict with tests or architecture;
- completion cannot be demonstrated.

