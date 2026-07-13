# Verification Workflow

## Purpose

Verification proves whether a task satisfies its acceptance criteria.

## Input

- Approved task contract.
- Implementation changes.
- Validation commands.
- Relevant manual check requirements.

## Output

- Verification report.
- Passing, failing, skipped, or blocked status for each acceptance criterion.
- Evidence for the completion claim.

## Workflow

1. Read the task contract.
2. Map every acceptance criterion to a check.
3. Run approved validation commands.
4. Perform manual checks when needed.
5. Record evidence and unresolved items.
6. State whether the task is complete, incomplete, or blocked.

## Stopping Condition

Stop when every acceptance criterion has a result and the completion claim is supported by evidence.

## Approval Boundary

Request approval before adding new validation tools, changing acceptance criteria, using external services, or performing destructive operations.

