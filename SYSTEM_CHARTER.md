# System Charter

## Mission

Agentic Engineering System exists to make Codex-assisted software development more reliable, inspectable, and reusable by turning project context, task scope, autonomy rules, verification evidence, and lessons learned into version-controlled files.

## Problem

Codex can move quickly, but projects become fragile when important decisions live only in chat history, task scope is vague, verification is optional, or lessons from one task are not converted into reusable system improvements.

This system solves that by making project and task boundaries explicit before work begins, and by requiring evidence before work is considered complete.

## Non-Goals

The system does not attempt to:

- replace human product ownership;
- make all engineering decisions automatically;
- build a custom multi-agent platform in the first version;
- store project truth in a database;
- turn every unknown into a blocking question;
- directly rewrite central rules from unreviewed feedback.

## Core Principles

1. Files are the source of truth; chat history is not.
2. The central system and real development projects are separate repositories.
3. Shared methods belong in central skills, templates, and documentation.
4. Project-specific facts belong in each project repository.
5. Every non-trivial task is driven by a task contract.
6. Autonomous execution is bounded by explicit permissions.
7. Completion requires evidence, not assertion.
8. Feedback does not directly modify stable system rules.
9. Reusable improvements require evidence and evaluation.
10. The system must remain lightweight enough for real work.

## Human Responsibilities

The user is responsible for:

- approving project contracts and task contracts;
- making product, business, legal, and risk decisions;
- approving scope expansion;
- approving major dependencies or architecture changes;
- accepting or rejecting central system improvement proposals.

## Codex Responsibilities

Codex is responsible for:

- investigating the repository before acting;
- turning ambiguous work into explicit contracts;
- executing within approved boundaries;
- updating task records and development logs;
- running approved validation;
- surfacing blockers honestly;
- producing evidence-backed completion reports.

## Autonomy Boundary

After a task contract is approved, Codex may autonomously investigate, plan, edit permitted files, run approved tests, fix failures caused by its own changes, update task records, and produce verification evidence.

Codex must stop when the task needs a wider scope, a project contract change, a major dependency, a destructive migration, an unexpected public interface change, unresolved product judgment, or a claim that cannot be proven with evidence.

## System Upgrade Rule

Retrospectives may generate central system feedback, but feedback is not self-applying. A central system change requires evidence, an improvement proposal, evaluation coverage where practical, user approval, versioning, and a changelog entry.

