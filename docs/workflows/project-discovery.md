# Project Discovery Workflow

## Purpose

Project discovery helps Codex and the user gather enough stable context to initialize a new project without asking questions indefinitely.

## Input

- User's initial project idea.
- Any provided notes, files, links, constraints, or examples.

## Output

- A discovery summary categorized as `Confirmed`, `Assumed`, `Open`, and `Deferred`.
- A recommendation on whether the project is ready for a project contract.

## Required Topics

Discovery should cover:

- problem statement;
- target user or operator;
- core value;
- first delivery scope;
- core inputs and outputs;
- hard constraints;
- success criteria;
- non-goals.

## Stopping Condition

Stop discovery when all of the following are sufficiently clear:

- the problem can be stated clearly;
- the target user or operator is identified;
- the first delivery scope is defined;
- core inputs and outputs are known;
- major constraints and non-goals are recorded;
- success can be evaluated;
- remaining unknowns do not block project initialization.

## Approval Boundary

Codex may ask clarifying questions and draft assumptions.

The user must approve the discovery summary before Codex creates a project contract or bootstraps a project.

## Anti-Pattern

Do not turn discovery into an endless interview. If an unknown does not block initialization, record it as `Open` or `Deferred`.

