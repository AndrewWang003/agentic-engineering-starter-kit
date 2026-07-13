# ae-task-execution

Use this skill after a task contract is approved and the user has authorized implementation.

## Goal

Execute the task autonomously within the approved contract boundaries.

## Required Input

- Approved task contract
- Current project contract
- Relevant repository state
- Approved validation commands

## Procedure

1. Re-read the task contract.
2. Inspect relevant files before editing.
3. Create a concise implementation plan.
4. Make only allowed changes.
5. Run approved validation commands.
6. Fix task-caused failures when allowed.
7. Update task records and `development log.md`.
8. Prepare notes for verification.

## Output

Implementation changes, updated task records, and a verification handoff.

## Stopping Condition

Stop when the task is ready for verification or when the current contract is insufficient.

## Approval Boundary

Create an amendment and stop if implementation requires scope expansion, project contract changes, major dependency changes, unexpected public interface changes, destructive data changes, or unresolved product decisions.

