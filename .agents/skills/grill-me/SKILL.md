---
name: grill-me
description: Interview the user one decision at a time to sharpen a requirement, plan, or design before files or implementation are needed. Use when the user wants to stress-test an idea, uncover hidden decisions, or says to grill them without creating project documentation.
---

# Grill Me

## Goal

Reach a shared understanding of the requirement without writing files or starting implementation.

## Procedure

1. Summarize the current goal, known constraints, assumptions, working hypotheses, and open decisions.
2. Inspect available files or tools for facts that can be discovered without asking the user.
3. Build a decision tree and resolve decisions in dependency order, starting with the ones that can change scope, behaviour, architecture, risk, cost, or validation.
4. Ask one question at a time and wait for the answer.
5. For each question, explain why it matters, give concise options with tradeoffs, and recommend one option.
6. Test vague answers with concrete scenarios or edge cases.
7. Update the shared understanding as decisions resolve.
8. Stop when the remaining unknowns do not block a reliable specification.

## Completion

Present a short alignment summary containing:

- goal and user value;
- confirmed decisions;
- constraints and non-goals;
- assumptions;
- working hypotheses;
- open and deferred decisions;
- expected behaviours and success criteria.

Ask the user to confirm that shared understanding has been reached.

After confirmation, recommend `to-spec` when the result should become a durable project definition or task contract.

## Boundaries

- Do not ask several unrelated questions at once.
- Do not ask for facts that the environment can answer.
- Do not turn reversible implementation details into user decisions.
- Do not write files, edit code, or begin implementation.
- Do not claim alignment until the user confirms it.
