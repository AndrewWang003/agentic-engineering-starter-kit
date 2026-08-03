# Codex Engineering Starter Kit

Codex Engineering Starter Kit is a small set of Markdown templates and Codex skills for starting and managing small software projects with more structure than pure vibe coding.

It helps with four practical habits:

- keep important project knowledge in files, not only in chat;
- use a clear task contract for medium and large work;
- keep Codex inside explicit scope and boundaries;
- require verification evidence before calling work complete.

This kit is intentionally small. It is not a multi-agent platform, workflow engine, project management app, database, memory system, or autonomous software factory.

Its task workflow follows a compact chain:

```text
clarify important unknowns
  -> specify the agreed behaviour
  -> split larger work into vertical slices
  -> implement and verify each slice
  -> review spec fit and project standards separately
```

## What Is Included

- `templates/PROJECT.template.md` for a small project foundation.
- `templates/AGENTS.template.md` for project-specific Codex rules.
- `templates/TASK.template.md` for medium and large work.
- `templates/REVIEW.template.md` for checking finished work.
- Three Codex skills:
  - `start-project`
  - `start-task`
  - `review-task`
- A minimal example project.

## Workflow 1: Start A Project

Use `start-project` when you have a new project idea and want Codex to help make it concrete.

The workflow begins with routing. Codex should first classify whether the request is:

- `Route A: New project`
- `Route B: Existing project change`
- `Route C: Existing project onboarding`

If the user wants a feature, bug fix, refactor, investigation, algorithm improvement, migration, or release inside an existing repository, `start-project` should stop and recommend `start-task`.

If the user wants to apply the Starter Kit to an existing repository that lacks project-level Codex instructions, `start-project` may offer lightweight onboarding. It should not treat the repository as a new project or suggest a nested project by default.

For a true new project, the workflow continues with project discovery. Codex should not create files immediately.

First, it clarifies only what is needed to begin:

- the problem;
- the intended user;
- the first version;
- core inputs and outputs;
- important constraints;
- non-goals;
- how success will be checked.

Codex should gather this through a short guided conversation, not one large questionnaire.

Before creating files, Codex should summarize:

- confirmed decisions;
- assumptions;
- working hypotheses, if any;
- open questions;
- deferred decisions.

The user should approve or correct that summary before initialization.

After approval, Codex should confirm the project folder name and absolute destination path. A normal project should be initialized in an independent user-approved folder, not inside this kit's `examples/` directory.

The result is a small project foundation with `PROJECT.md`, `AGENTS.md`, `README.md`, and a `tasks/` folder.

Discovery should stop when the project is understandable, the first delivery scope is clear, and remaining unknowns do not block work from beginning.

## Workflow 2: Start A Task

Use `start-task` for a medium or large feature, bug fix, refactor, or version iteration.

For ambiguous or higher-risk tasks, `start-task` can use an Unknowns-First Quick Start check before implementation. This is a five-step lightweight pass: current understanding, blind spot scan, plan, execution with deviation notes, and verification with explanation.

Use the full Unknowns-First workflow only when the lightweight pass is not enough and you explicitly want the extra process.

After alignment, Codex synthesizes what is already known into a concise specification instead of restarting the interview. Questions that can be answered from the repository should be investigated there. When user input is needed, Codex should handle one high-impact decision at a time, explain the tradeoffs, and offer a recommendation.

The task contract records:

- background and goal;
- user value and expected behaviours;
- current and expected behavior;
- material implementation decisions;
- the stable behaviour or interface used for testing;
- vertical slices and genuine blockers when the work is larger than one focused change;
- allowed and forbidden scope;
- acceptance criteria;
- required checks;
- approval-required situations;
- assumptions and risks.

Each vertical slice should deliver a narrow, complete, independently verifiable behaviour. Ordinary feature work should not be split into separate frontend, backend, data, and test phases.

During implementation, the approved task contract defines what to build. New evidence that materially changes it should trigger a pause and contract update. When automated tests fit the project, Codex should work one behaviour at a time through a red-green loop, testing stable public behaviour and deriving expected results independently from the implementation.

Small, low-risk changes do not need the full workflow. Codex can handle them directly after inspecting the repository and stating assumptions.

## Terminology

Use project-level terms for a whole software project:

- project purpose;
- first-version scope;
- project contract or project definition;
- project inputs and outputs;
- project success criteria.

Use task-level terms for work inside an existing project:

- task goal;
- expected behaviour;
- deliverable;
- acceptance criteria;
- investigation;
- feature;
- bug fix;
- refactor;
- algorithm improvement.

Do not describe an individual feature or algorithm change as a new project's first-version scope unless it genuinely creates a separate product.

## Evidence Classification

Use `Confirmed` for facts observed in repository files, data, or command output.

Use `Assumptions` for reasonable operating assumptions that have not been verified.

Use `Working hypotheses` for possible root causes, likely explanations, or suspected failure sources.

Use `Open` for questions that still need answers, and `Deferred` for decisions that do not block the next step.

Possible root causes must not be recorded as confirmed facts, and implementation changes should wait until the relevant working hypotheses have been investigated or explicitly accepted as the basis for a task.

## Workflow 3: Review A Task

Use `review-task` after Codex finishes a contracted task. The review first identifies the comparison baseline, then keeps two questions separate:

- `Spec Fit`: Did the result implement the approved task contract completely and without scope creep?
- `Project Standards`: Does the change follow repository instructions, established patterns, safety constraints, and maintainability expectations?

The review records:

- what changed;
- which acceptance criteria were satisfied;
- which commands or tests were run;
- what was not verified;
- remaining risks;
- whether Codex stayed inside scope;
- whether any lesson should be added to the project rules.

The review does not automatically change global rules.

## Design Influence

This lightweight flow adapts selected ideas from AIHero's [Main Flow](https://www.aihero.dev/skills): guided clarification, specification before implementation, tracer-bullet vertical slices, test-first feedback, and separate standards-versus-spec review. The Starter Kit keeps those disciplines inside three local, file-based workflows and does not require an issue tracker, plugin runtime, multi-agent setup, or extra infrastructure.

| Main Flow skill | Starter Kit adaptation |
| --- | --- |
| `grill-with-docs` | Repository-first clarification, one high-impact decision at a time, and consistent domain terms in `start-project` and `start-task`. |
| `to-spec` | A concise specification summary, implementation decisions, scope, and stable testing interface inside the task contract. |
| `to-tickets` | Independently verifiable vertical slices with acceptance criteria and genuine blockers, kept in one lightweight task record. |
| `implement` | Contract-driven execution, focused checks after each slice, and a pause when new evidence materially changes the contract. |
| `tdd` | Conditional one-behaviour-at-a-time red-green guidance that tests public behaviour with independently derived expectations. |
| `code-review` | A confirmed review baseline plus separate Spec Fit and Project Standards findings. |

## How To Use In A Real Project

1. Ask Codex to use `start-project`.
2. Complete the guided discovery conversation.
3. Approve or correct the project summary.
4. Confirm the project folder name and absolute destination path.
5. Let Codex create `PROJECT.md`, `AGENTS.md`, `README.md`, and `tasks/` in that independent folder.
6. For medium and large work, ask Codex to use `start-task` to clarify, specify, slice, and implement the change.
7. Approve the task contract and slice breakdown before implementation.
8. After the work is done, ask Codex to use `review-task`.

You can also copy or adapt the templates manually if you do not want the guided workflow.

## When Not To Use The Full Workflow

Skip the full task contract when the change is small, local, low-risk, and easy to verify.

Examples:

- fix a typo;
- rename a heading;
- adjust a small style rule;
- run a simple check;
- answer a direct code question.

Even for small work, Codex should still inspect before editing and report what was verified.

## How To Stop Using The Kit

The kit is file-based and removable. A real project can stop using it by deleting or archiving:

- `PROJECT.md`
- `AGENTS.md`
- `tasks/`

This does not damage the project's source code. There is no database, server, runtime, or hidden state to migrate.
