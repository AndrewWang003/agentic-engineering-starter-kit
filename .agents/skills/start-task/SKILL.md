---
name: start-task
description: Clarify, specify, slice, implement, and verify a meaningful change inside an existing project. Use for features, bug fixes, refactors, investigations, migrations, releases, or version iterations that need an explicit task contract and controlled execution.
---

# start-task

Use this skill when a user asks Codex to perform a feature, bug fix, refactor, version iteration, or other meaningful project change.

## Goal

Turn a meaningful project change into an approved task contract, then implement it without silently redefining what should be built.

## Procedure

1. Inspect `PROJECT.md`, `AGENTS.md`, relevant repository files, tests, task history, and `git status --short --ignored`.
2. Decide whether the work is small, medium, or large.
3. For small, low-risk work, state assumptions and proceed if appropriate.
4. For medium or large work, align on unresolved high-impact decisions.
5. Synthesize the agreed request and repository evidence into a concise specification.
6. Split multi-step work into independently verifiable vertical slices and identify blockers.
7. Create the task contract and ask for approval before autonomous execution.
8. Implement the approved contract, record meaningful deviations, and run risk-matched validation.

## Unknowns-First Reference

For ambiguous, cross-file, unfamiliar, data-sensitive, or higher-risk tasks, use the Quick Start section of `references/unknowns-first-workflow.md`.

Default to the five-step Quick Start:

1. Current understanding
2. Blind spot scan
3. Plan
4. Execution and deviation record
5. Verification and explanation

Do not run the full Unknowns-First workflow unless the Quick Start is not enough and the user approves the extra process.

## Alignment Pass

When important decisions remain unclear:

- investigate the repository before asking the user;
- ask one decision question at a time;
- explain why the answer changes scope, behaviour, risk, or validation;
- provide a recommended answer and concise tradeoffs;
- stop when remaining unknowns do not block a safe specification.

Do not repeat questions already answered in the conversation or repository.

## Specification

Synthesize the current conversation and repository evidence into the task contract. Do not restart discovery from zero.

If `to-spec` already created a task contract, verify it against the live repository and reuse it. Ask only about newly discovered high-impact gaps; do not repeat the completed interview.

The specification should state:

- the user-visible or system-visible problem;
- the expected solution and behaviours;
- user value, when relevant;
- implementation decisions that materially constrain the work;
- the stable public behaviour or interface through which the result will be tested;
- testing decisions and comparable existing tests;
- explicit out-of-scope behaviour.

Prefer an existing stable testing interface over introducing a new one. Confirm a new public interface with the user before implementation.

## Vertical Slices

For work that cannot be completed safely as one small change, create a short sequence of vertical slices.

Each slice should:

- deliver a narrow but complete path through the affected layers;
- be independently demoable or verifiable;
- fit within one focused implementation pass;
- list genuine blockers;
- carry its own acceptance criteria.

Do not split ordinary feature work into separate data, backend, frontend, and test phases. A broad mechanical refactor may instead use an expand, migrate, contract sequence when individual vertical slices cannot remain valid.

Ask the user to approve the granularity and blockers as part of task-contract approval.

## Implementation Discipline

- Treat the approved task contract as the definition of what to build.
- Do not reopen settled product decisions during implementation without new evidence.
- Pause when a discovery requires a material contract change.
- Run focused checks after each verifiable slice and the broader relevant checks at the end.
- Record deviations that affect scope, behaviour, architecture, risk, or validation.
- Keep scratch scripts and routine generated output outside the repository; record the intended location of any durable evidence.
- Before committing or declaring completion, inspect untracked files and report any rebuildable output that can be safely cleaned with user approval.

When automated tests are appropriate, prefer a red-green loop one behaviour at a time:

1. Write one failing test for public behaviour.
2. Add only enough implementation to make it pass.
3. Refactor only while the relevant tests are green.
4. Continue with the next behaviour.

Expected values must come from the specification, a worked example, or another independent source rather than reproducing the implementation logic inside the test.

## Task Contract Must Include

- Task ID and name
- Background
- User value, when relevant
- Goal
- Current behaviour, when relevant
- Expected behaviour
- Specification summary
- Testing interface
- Vertical slices and blockers, when needed
- Allowed scope
- Forbidden scope
- Acceptance criteria
- Required validation
- Approval-required situations
- Assumptions
- Working hypotheses, when relevant
- Status

## Evidence Classification

Keep verified facts separate from theories:

- Use `Confirmed` for repository behaviour directly observed in code, data, or commands.
- Use `Assumptions` for reasonable operating assumptions that are not yet verified.
- Use `Working hypotheses` for possible root causes, likely explanations, or suspected failure sources.
- Use `Open questions` for facts that must be answered before safe implementation.

Do not record possible root causes as confirmed facts. Do not recommend implementation changes before the relevant working hypotheses are investigated or accepted as the basis for the task.

## Autonomy Boundary

After approval, Codex may inspect, plan, edit files inside scope, run relevant commands, fix its own failures, update the task record, and prepare a review.

Codex must stop when scope must expand, destructive action is required, a major dependency is needed, a public interface must change unexpectedly, a product decision cannot be inferred, or acceptance criteria cannot be satisfied as written.

## Anti-Pattern

Do not turn minor changes into bureaucratic workflows.
