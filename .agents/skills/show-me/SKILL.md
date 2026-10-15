---
name: show-me
description: Use when a user asks to make an explanation easier to understand visually, or when a diagram, tree, diff-shaped sketch, or compact structure would reduce cognitive load during planning, specification, implementation, QA planning, or review.
---

# show-me

## Goal

Reduce cognitive load by showing the smallest visual structure that explains the current point.

## When To Use

Use when a user asks to see, visualize, map, compare, simplify, or make an explanation clearer. Also use when a workflow decision, code structure, file responsibility, test strategy, or review finding would be easier to understand as a compact shape than as prose.

Do not use for ordinary short answers where text is already clearer.

## Preferred Formats

Choose the smallest useful format:

- pseudocode for rules, algorithms, and state changes;
- call trees for runtime control flow;
- component trees for UI structure and ownership;
- shallow file trees for module responsibility;
- Mermaid for data flow, sequence, state, or dependency diagrams;
- diff-shaped sketches for before/after structure.

Keep prose brief and place the visual next to the point it explains.

## HTML Authorization Boundary

Markdown-native formats are preferred. Do not create, write, or open an HTML explanation artifact unless the user explicitly approves that specific HTML action first.

This does not restrict opening product UI, source HTML, test fixtures, or ordinary web pages for implementation, debugging, or QA.

If HTML would help, ask plainly:

```text
This may be clearer as a small HTML visual. May I create and open one?
```

If approved, keep temporary HTML outside the repository. Save HTML inside the project only when the user explicitly asks to preserve it as durable documentation or task evidence.

## Project Workflow Fit

- During requirement shaping, show decision trees or user-flow sketches.
- During `to-spec`, show the specification structure or scope boundary.
- During `qa-planning-checkpoint`, show scenario matrices or edge-case maps.
- During `start-task`, show slice plans, file responsibility, or call flow.
- During `review-task`, show before/after structure, risk maps, or diff-shaped findings.

## Quality Bar

- Show only the calls, files, states, options, and boundaries needed for the current decision.
- Prefer Markdown that remains readable in plain text.
- Do not make visuals decorative.
- Do not let the visual introduce new scope or unconfirmed facts.
- Mark assumptions and working hypotheses clearly when they appear in a visual.
