---
name: qa-planning-checkpoint
description: Use when a task changes user-visible behavior, business rules, data transformations, permissions, integrations, or other behavior where missing edge cases could make implementation pass checks while violating intent.
---

# QA Planning Checkpoint

## Goal

Define what must be proven before implementation starts. Keep this checkpoint lightweight: it produces testable scenarios, a validation strategy, and any approval question needed to avoid silently guessing business behavior.

## When To Use

Use before `start-task` implementation when the task affects behavior, correctness, data integrity, UI flows, permissions, external integrations, or bug reproduction.

Skip for documentation-only changes, typo fixes, static text edits, mechanical renames, or other low-risk changes where normal validation is enough.

## Procedure

1. Read the task contract or aligned conversation, plus relevant project guidance and nearby tests when available.
2. Extract the behavior under test and any stated acceptance criteria.
3. Identify boundary, negative, error, state-transition, concurrency, accessibility, security, or integration cases that matter for this task.
4. Produce the checkpoint output below.
5. Ask for approval only when a product rule, boundary decision, or validation cost cannot be safely inferred.
6. Hand the approved checkpoint to `start-task`; do not implement code inside this skill.

## Output Shape

### Acceptance Scenarios

Use concise Given/When/Then scenarios or equivalent bullets. Cover the happy path, important boundaries, and at least one meaningful negative or failure case when applicable.

### Test Strategy

Map each scenario to the right validation level: unit, integration, browser/UI, API, manual verification, or not worth testing. Prefer the smallest reliable test that proves the behavior.

### Test Interface

Name the stable public behavior, API, function, command, UI flow, or artifact that should be tested. Do not invent a new public interface unless the task already requires one.

### Approval Question

Ask one question only when a decision changes behavior, scope, risk, or validation. Include the recommended answer and the reason.

## Quality Bar

- Scenarios test behavior, not implementation details.
- Expected results come from the spec, examples, domain rules, or user confirmation.
- Ambiguities are marked as open instead of silently becoming tests.
- Slow or expensive tests are justified by risk.
- The checkpoint is short enough to review before coding.

## Common Mistakes

- Writing test code before the scenarios and expected results are clear.
- Treating all validation as browser tests when unit or integration tests would prove the behavior faster.
- Testing only happy paths.
- Asserting internal calls instead of user-visible or system-visible outcomes.
- Letting generated scenarios expand the approved task scope.
