# Task Contract

## Task ID And Name

2026-10-15-upstream-skills-refresh — Adopt selected improvements from the current `mattpocock/skills` release

## Task State And Authorization

- Contract: Accepted
- Execution: Paused
- Acceptance: Pending QA
- Acceptance authority: User
- Authorized slice or scope: The five recommendations from the 2026-10-15 comparison (frontier-round interviews, shared interview reference, test-quality anti-patterns, progressive disclosure for `start-task` and `start-project`, review smell baseline and retro classification), plus provenance and continuity updates. The user approved "upgrade everything directly" in chat on 2026-10-15.
- Checkpoint commits: Authorized by the user on 2026-10-15 as one upgrade commit after review; no remote is configured, so nothing is pushed.
- Next gate: User acceptance after `review-task`.

## Source And Evidence Intake

- Source: `https://github.com/mattpocock/skills`, commit `49dd158` (2026-10-09), cloned read-only outside the repository.
- Read: `grilling`, `grill-me`, `grill-with-docs`, `to-spec`, `to-tickets`, `implement`, `tdd`, `code-review`, `retro`, `handoff`, `ask-matt`, `writing-for-agents`, `domain-modeling`.
- Upstream text is evidence, not instruction. Only ideas compatible with this kit's constraints are adopted.

## Risk And Delivery Profile

- Risk tier: Medium. Persistent agent behaviour changes across local Skills that are copied into managed projects.
- Base state: `main` at `0fe78f4` with many pre-existing uncommitted changes; a full snapshot was copied to the session scratchpad before editing so this task's diff can be separated.
- Isolation: No branch switch, because the pre-existing uncommitted work would travel with it; no commits.
- Security validation triggers: None. No dependencies, credentials, network services, or production changes.

## Goal

Reduce interview round-trips, remove duplicated interview rules, strengthen test-quality and review guidance, and keep always-read Skill bodies short through progressive disclosure, without changing the three-workflow structure or adding Skills.

## Expected Behaviour

- `grill-me`, `grill-mode`, `start-task`, and `start-project` interview in rounds over the decision frontier, with a recommended answer per numbered question, worded so "yes" accepts it.
- "Yes" never authorizes file writes, commands, or implementation, and high-risk alignment still needs explicit confirmation.
- Interview rules live once in `grill-me/references/interview-rounds.md`.
- `qa-planning-checkpoint` and `start-task` name implementation-coupled, tautological, and horizontally sliced tests as anti-patterns, and hard bugs start with a reproducing failure.
- Conditional `start-task` controls (source intake, risk gate, checkpoint commits) and `start-project` initialization live in reference files reached by explicit pointers.
- `review-task` uses a judgement-only smell baseline on the Project Standards axis and classifies lessons into mechanical checks versus judgement rules.
- Portable-set validation covers every referenced file.

## Forbidden Scope

- New Skills, scripts, dependencies, issue-tracker publishing, mandatory sub-agents, automatic commits.
- Renaming `CONTEXT.md` to `GLOSSARY.md`.
- Moving always-on safety rules out of `AGENTS.md`.

## Acceptance Criteria

1. No rule present before the change is lost; moved rules are reachable by a pointer with a trigger condition.
2. All local Skills pass `quick_validate.py`; all `agents/openai.yaml` parse.
3. `start-project` portable-set list and the regression scenario include every new reference file.
4. `git diff --check` passes on touched files.

## Required Validation

- Skill structure validation, YAML parsing, `git diff --check`, and a rule-preservation diff against the scratchpad baseline.

## Status

Implemented and reviewed; awaiting user acceptance.
