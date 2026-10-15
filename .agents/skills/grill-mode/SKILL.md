---
name: grill-mode
description: Use when the user explicitly requests an escalated grill process, or when grill-me cannot safely resolve unclear, high-impact, cross-system, architectural, risky, or documentation-worthy work. Do not use when the task is already bounded, low-risk, reversible, and independently verifiable.
---

# Grill Mode

## Goal

Reach shared understanding before specification, file creation, or implementation, while preserving confirmed terminology or consequential decisions only when explicitly authorized.

Grill Mode is the escalated version of `grill-me`. Prefer `grill-me` for normal requirement shaping.

## Mode Selection

Use Grill Mode only when the user explicitly requests it, `grill-me` cannot safely resolve the requirement, the work is high-risk, architectural, cross-system, expensive, hard to reverse, or data-sensitive, or confirmed terminology or major decisions should survive beyond the conversation.

Do not use Grill Mode when the task is already bounded, low-risk, reversible, and independently verifiable.

## Before The Interview

1. Identify whether this is file-free mode or documentation mode.
2. If there is a target project, inspect existing context before asking the user to restate discoverable facts. Read relevant `PROJECT.md`, `AGENTS.md`, `CONTEXT.md`, ADRs, task contracts, and nearby code when present.
3. Summarize confirmed facts separately from assumptions, working hypotheses, and open decisions.
4. State the current interview mode and its boundaries.

## Interview Procedure

1. Read `.agents/skills/grill-me/references/interview-rounds.md` and follow it for the whole interview, including its authorization-question rules.
2. Summarize the current goal, user value, constraints, assumptions, working hypotheses, and open decisions.
3. Ask the decision frontier in rounds. Test vague or conflicting answers against project evidence as well as concrete scenarios.
4. Update the shared understanding after each consequential decision, and stop when the stop condition holds for a reliable specification, task contract, or project definition.

Requests to write documentation, create an ADR, or change modes are authorization questions, never part of a round.

## Documentation Mode

Documentation mode does not automatically authorize file changes.

Before the first documentation write, say exactly what files you intend to modify or create, such as `CONTEXT.md` or `docs/adr/ADR-xxx-title.md`, then wait for explicit user authorization.

Update `CONTEXT.md` only for canonical project or domain terms confirmed by the user. Offer an ADR only when the decision is hard to reverse, surprising without its context, and the result of a meaningful tradeoff. Create an ADR only after the user confirms both the decision and the documentation write. Include Status, Context, Decision, Consequences, and Alternatives Considered.

Keep ADRs rare. Do not record ordinary preferences, temporary plans, or reversible implementation choices as architecture decisions.

## Completion

For project-level, architectural, high-risk, expensive, cross-system, or hard-to-reverse work, present an alignment summary and ask for explicit confirmation. For small reversible work discovered during Grill Mode, present the alignment summary and state that the user's next execution instruction will be treated as confirmation.

The alignment summary should include the goal and user value, confirmed decisions, expected behaviours, constraints and non-goals, assumptions, working hypotheses, open or deferred decisions, success criteria and validation ideas, and documentation changed or proposed.

After confirmation, recommend converting the result into a specification, project definition, or task contract before implementation.

## Boundaries

- Do not begin implementation or write a specification during Grill Mode.
- Do not claim alignment for high-risk work until the user confirms it.
- Do not invent project facts, terminology, or decisions.
- Do not modify files in file-free mode.
- In documentation mode, do not modify any file until the user explicitly authorizes the exact target files.
- Do not modify files outside approved glossary or ADR updates during the interview.
- Do not treat every unclear detail as blocking; defer unknowns that do not affect a reliable next specification.
