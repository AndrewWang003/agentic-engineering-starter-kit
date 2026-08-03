---
name: to-spec
description: Synthesize an already-discussed requirement into a local project definition draft or task contract without restarting the interview. Use after grill-me, grill-with-docs, or another sufficiently detailed conversation when the user wants a durable specification before project or task execution.
---

# To Spec

## Goal

Convert the current conversation and repository evidence into a durable local specification. Do not implement the work and do not publish to an issue tracker.

## Route The Output

- For a change inside an existing project, create or update `tasks/<task-id>/TASK.md` using `templates/TASK.template.md` when available.
- For a new project whose destination is not yet approved, present a Project Definition Draft in the conversation and hand it to `start-project`; do not create files in an assumed destination.
- When the user explicitly requests an in-chat draft only, return the specification without writing files.

## Procedure

1. Read the relevant conversation, `PROJECT.md`, `AGENTS.md`, `CONTEXT.md`, ADRs, task records, code, and tests that are available.
2. Synthesize what is already known. Do not restart the interview or repeat resolved questions.
3. Use the project's canonical terms and respect confirmed decisions.
4. Separate Confirmed Facts, Assumptions, Working Hypotheses, Open Questions, and Deferred Decisions.
5. Identify the highest stable public behaviour or interface through which the result can be verified. Prefer an existing testing interface.
6. Write the specification at the routed destination.
7. For multi-step work, propose independently verifiable vertical slices and genuine blockers. `Blocked By` must name an earlier slice or `None`; record investigations and unresolved facts as open questions or validation prerequisites instead.
8. Report the output path or in-chat result and recommend the correct execution handoff.

## Existing-Project Task Specification

Include:

- task ID and name;
- background and problem statement;
- goal and user value;
- current and expected behaviour;
- concise user stories or behavioural scenarios when useful;
- confirmed facts;
- implementation decisions already agreed;
- testing interface and testing decisions;
- allowed and forbidden scope;
- acceptance criteria;
- required validation;
- vertical slices and blockers when needed;
- assumptions, working hypotheses, open questions, and deferred decisions;
- approval-required situations;
- status.

Set status to `Draft` when the contract is ready for user review. Set it to `Needs clarification` when a high-impact open question prevents safe execution.

After approval, hand the task contract to `start-task`. `start-task` should verify the contract against the live repository and avoid repeating completed discovery.

## New-Project Definition Draft

Include:

- proposed project name;
- problem and intended user;
- first-version scope;
- inputs and outputs;
- constraints and non-goals;
- success criteria;
- key terms and confirmed decisions;
- assumptions, working hypotheses, open questions, and deferred decisions.

Hand the draft to `start-project` for approval and destination confirmation.

## Open Questions

Do not invent missing decisions. Record non-blocking unknowns honestly. When a high-impact unknown blocks a reliable specification, stop with `Needs clarification` and recommend returning to `grill-me` or `grill-with-docs`.

## Boundaries

- Do not re-interview the user during synthesis.
- Do not publish to GitHub, Linear, Notion, or another tracker.
- Do not begin implementation or mark the task approved.
- Do not create a new-project file tree before `start-project` confirms the destination.
- Do not produce an exhaustive document when a concise specification is sufficient.
