# Interview Rounds

Shared interview procedure for `grill-me`, `grill-mode`, and the alignment steps of `start-project` and `start-task`. Each caller adds its own boundaries and completion rules.

## Design Tree And Frontier

Map the requirement as a **design tree**: every decision branches into the decisions that depend on it.

The **frontier** is every open decision whose prerequisites are already settled: the questions that can be asked now without guessing at answers not yet heard. A question that depends on another question still open in the same round belongs to a later round.

Build only as much of the tree as needed to find the frontier. Prioritize decisions that change scope, behaviour, architecture, risk, cost, validation, permission boundaries, or user value. Leave reversible implementation details to the Agent.

## Facts Versus Decisions

Finding facts is the Agent's job. Inspect files, tests, history, and tools before asking; never ask the user for something the environment can answer. When a lookup is slow, ask the frontier questions that do not depend on it and hold back only the dependent ones. A sub-agent may perform the lookup when the harness supports it; none is required.

Decisions belong to the user. Put each one to them and wait.

## Round Format

Ask the whole frontier in one round, numbered, each with a recommended answer. Keep a round answerable in one reply; when the frontier is large, ask the highest-impact questions first.

```text
**Q1 — <question title>**: <why it matters, options with tradeoffs, what changes depending on the answer>

Recommended: <answer and reason>

---

**Q2 — <question title>**: ...

Recommended: ...
```

Word each question so "yes" accepts the recommendation. The user may answer per number, or "yes" for all.

After each round, test vague or conflicting answers with concrete examples, edge cases, or failure scenarios; update the shared understanding; recompute the frontier; ask the next round.

## Limits Of "Yes"

- "Yes" accepts recommended answers to the questions asked. It never authorizes file writes, commands, tool access, mode changes, or implementation.
- For high-risk, architectural, expensive, or hard-to-reverse work, the final alignment summary still requires explicit user confirmation.

## Authorization Questions

Authorization questions are not part of a round. When permission is needed to inspect files, run a command, access a tool, write documentation, change modes, or act outside the interview boundary, ask it separately and clearly. Frontier questions that do not depend on that permission may still go in the same response.

Do not hide scope, design, priority, acceptance, or documentation decisions inside an authorization request.

## Stop Condition

Stop when the frontier holds no decision that blocks a reliable specification, task contract, project definition, or bounded next action. Record non-blocking unknowns as assumptions, working hypotheses, open questions, or deferred decisions instead of asking about them. Keep confirmed facts separate from assumptions and working hypotheses throughout.
