---
name: grill-me
description: Interview the user one decision at a time to clarify a fuzzy requirement before specification or implementation. Use when the user explicitly asks to grill, grill me, clarify, stress-test, or sharpen an idea, plan, feature, project, or task, especially when no project documentation should be changed. Do not use when the task is already bounded, low-risk, reversible, and independently verifiable.
---

# Grill Me

## Goal

Reach shared understanding of a requirement without writing files, editing code, or starting implementation.

Use this as the default lightweight grill skill for everyday requirement shaping. Escalate to `grill-mode` only when the user explicitly asks for it or when this interview cannot resolve the requirement safely.

## Procedure

1. Summarize the current goal, known facts, constraints, assumptions, working hypotheses, and open decisions.
2. Inspect available files or tools for facts that can be discovered without asking the user.
3. Build only as much of the decision tree as needed to identify the next blocking or high-impact decision.
4. Resolve decisions in dependency order, starting with decisions that can change scope, behaviour, architecture, risk, cost, validation, or user value.
5. Ask one question at a time and wait for the answer.
6. For each question, explain why it matters, offer concise options with tradeoffs, recommend one option, and state what changes depending on the answer.
7. Test vague answers with concrete examples, edge cases, or failure scenarios.
8. Keep confirmed facts separate from assumptions and working hypotheses.
9. Update the shared understanding as decisions resolve.
10. Stop when remaining unknowns do not block a reliable specification or bounded next action.

## Authorization Questions

Authorization questions do not count as the one substantive Grill Me question for the turn.

If you must ask for permission to inspect files, run a command, access a tool, change modes, or perform any action outside the current interview boundary, ask that authorization question separately and clearly. You may still ask one additional requirement-shaping question in the same response when it is concise, directly relevant, and not dependent on the authorization answer.

Keep permission gating separate from requirement decisions. Do not hide scope, design, priority, or acceptance choices inside an authorization request.

## Completion

For project-level, architectural, high-risk, expensive, or hard-to-reverse work, present an alignment summary and ask the user to explicitly confirm it.

For small, reversible work, present an alignment summary and state that the user's next execution instruction will be treated as confirmation.

The alignment summary should include:

- goal and user value;
- confirmed decisions;
- constraints and non-goals;
- assumptions;
- working hypotheses;
- open and deferred decisions;
- expected behaviours;
- success criteria or validation ideas.

After confirmation, recommend converting the result into a specification, project definition, or task contract when the work should become durable.

## Escalate To Grill Mode

Recommend `grill-mode` when the user explicitly asks for it, project terminology must be preserved, hard-to-reverse decisions need documentation, the requirement spans multiple systems or repositories, risk or architecture choices dominate, or the lightweight interview cannot produce a reliable next specification.

## Boundaries

- Do not ask for facts that the environment can answer.
- Do not turn reversible implementation details into user decisions.
- Do not begin implementation, write a specification, or modify files.
- Do not claim alignment for high-risk work until the user confirms it.
- Do not invent project facts, terminology, or decisions.
- Do not treat every unclear detail as blocking; defer unknowns that do not affect a reliable next step.
