# Change Management

## Source of Truth

Stable behavior changes must be recorded in repository files. Chat-only decisions are not durable.

## Change Classes

### Patch

Clarifies wording, fixes typos, or improves examples without changing behavior.

### Minor

Adds a template, workflow step, skill instruction, or evaluation case without breaking existing projects.

### Major

Changes autonomy policy, approval boundaries, project contract semantics, or existing template requirements in a way that may affect project behavior.

## Required Records

Every functional change must update:

- `development log.md`
- `CHANGELOG.md` when the change is released or user-visible

Version changes must update:

- `VERSION`

## Approval

Major changes require explicit user approval. Minor changes may proceed within an approved task contract. Patch changes may proceed when they are inside the requested scope.

## Evaluation

Reusable improvements should include an evaluation case when practical. If evaluation is skipped, the reason should be recorded in the development log or improvement proposal.

