---
name: review-task
description: Review completed or in-progress project work against its approved task contract and the repository's engineering standards. Use after a contracted task, for a completion review, or when checking a diff before declaring work complete.
---

# review-task

Use this skill after Codex finishes a task that had a task contract, or when the user asks for a completion review.

## Goal

Check the result against the task contract and project standards on two separate axes, then record evidence before calling the task complete.

## Procedure

1. Read the task contract, `PROJECT.md`, `AGENTS.md`, and relevant repository guidance.
2. Identify and confirm the review baseline. Use a supplied commit, branch, tag, or merge base when available; otherwise report the best available working-tree comparison.
3. Inspect the complete diff and changed files.
4. Review `Spec Fit` against the task goal, scope, expected behaviours, vertical slices, and acceptance criteria.
5. If a QA planning checkpoint exists, compare implemented validation against its acceptance scenarios and test strategy.
6. Separately review `Project Standards` against repository instructions, established patterns, maintainability, and relevant safety constraints.
7. Record commands and tests run, including focused and broader checks.
8. Identify unverified behaviour, scope deviations, and remaining risks.
9. Record lessons learned without blending them into the two review verdicts.
10. Check workspace hygiene: distinguish intentional durable files from temporary or rebuildable output, and report any cleanup candidate without deleting it.
11. Recommend project rule changes only when justified.
12. Recommend a new reusable Skill only when a workflow has repeated or clearly has cross-project value.

## Two-Axis Review

Keep findings separate even when one issue appears on both axes.

### Spec Fit

Ask whether the change implements the approved task contract completely and only within scope. Do not invent requirements when no contract or acceptance criterion exists; report the missing evidence instead.

### Project Standards

Ask whether the change follows `AGENTS.md`, repository conventions, existing architecture, test patterns, and maintainability expectations. Treat general code-quality heuristics as judgement, while explicit project rules take precedence.

Do not combine both axes into one score that lets success on one hide failure on the other.

## Output

Create or update a review report using `templates/REVIEW.template.md`.

## Boundaries

- Require evidence for completion.
- Report an invalid baseline or empty diff before continuing the review.
- Report skipped checks honestly.
- Do not automatically modify global rules.
- Do not hide scope expansion.
