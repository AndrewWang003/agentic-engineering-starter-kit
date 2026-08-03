---
name: grill-with-docs
description: Interview the user one decision at a time while maintaining a project glossary and rare architecture decision records. Use when requirements are still fuzzy and the shared terminology or hard-to-reverse decisions should survive beyond the conversation.
---

# Grill With Docs

## Goal

Reach a shared understanding while preserving confirmed domain terms and consequential decisions in the target project.

## Before The Interview

1. Confirm the target repository.
2. Read `PROJECT.md`, `AGENTS.md`, `CONTEXT.md`, relevant ADRs, and relevant code when present.
3. State that resolved terms may update `CONTEXT.md` and approved consequential decisions may create ADRs under `docs/adr/`.
4. Do not create either path until there is real content to record.

## Interview

1. Summarize the current goal, constraints, assumptions, working hypotheses, and open decisions.
2. Resolve decisions in dependency order, starting with those that can change scope, behaviour, architecture, risk, cost, or validation.
3. Ask one question at a time and wait for the answer.
4. Explain why each question matters, offer concise options with tradeoffs, and recommend one option.
5. Investigate repository facts instead of asking the user to supply them.
6. Challenge vague or conflicting terms with concrete scenarios and code evidence.
7. Stop when remaining unknowns do not block a reliable specification.

## Documentation

Update `CONTEXT.md` as soon as the user confirms a canonical domain term.

Keep each glossary entry concise and free of implementation details:

```markdown
## Term

Definition in the project's language.
```

Offer an ADR only when the decision is all three:

- hard to reverse;
- surprising without its context;
- the result of a meaningful tradeoff.

Create an ADR only after the user confirms the decision. Use the next available number and include Status, Context, Decision, Consequences, and Alternatives Considered.

## Completion

Present the aligned goal, confirmed decisions, expected behaviours, assumptions, working hypotheses, open decisions, and documentation changed. Ask the user to confirm shared understanding, then recommend `to-spec`.

## Boundaries

- Keep the glossary separate from implementation specifications.
- Keep ADRs rare; do not record reversible preferences as architecture decisions.
- Do not invent terms or decisions the user has not confirmed.
- Do not write a specification or begin implementation.
- Do not modify files outside `CONTEXT.md` and approved ADRs during the interview.
