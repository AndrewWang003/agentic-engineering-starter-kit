# Task Execution Workflow

## Purpose

Task execution guides Codex through implementation after a task contract has been approved.

## Input

- Approved task contract.
- Current project contract.
- Relevant repository state.
- Approved validation commands.

## Output

- Implementation plan.
- Scoped file changes.
- Updated task records.
- Notes for verification.
- Amendment request if the task cannot continue inside the approved scope.

## Workflow

1. Re-read the task contract and project contract.
2. Inspect relevant files before editing.
3. Create a concise implementation plan.
4. Make only allowed changes.
5. Run approved validation commands as work progresses.
6. Fix failures caused by the task when the contract allows it.
7. Update task records and development logs.
8. Hand off to verification.

## Stopping Condition

Stop execution when the implementation is ready for verification, or when an approval-triggering issue prevents safe continuation.

## Approval Boundary

Codex must stop and create an amendment if execution requires scope expansion, project contract changes, major dependency changes, public interface changes outside the contract, destructive data changes, or unresolved product decisions.

