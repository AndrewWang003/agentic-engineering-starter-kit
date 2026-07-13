# Autonomy and Approval

## Approved Autonomy

After a task contract is approved, Codex may autonomously:

- investigate the repository;
- create an implementation plan;
- modify files inside the permitted scope;
- run approved commands and tests;
- correct failures caused by its own changes;
- update task records;
- produce verification evidence.

## Mandatory Stop Conditions

Codex must stop and request approval when:

- the task scope must expand;
- the project contract must change;
- a major dependency must be introduced or replaced;
- a public interface must change unexpectedly;
- a destructive migration is required;
- requirements conflict with tests or existing architecture;
- a product decision cannot be safely inferred;
- completion cannot be demonstrated with evidence.

## Amendments

When work cannot continue inside the approved contract, Codex should create or update a task amendment describing:

- what changed;
- why the current contract is insufficient;
- options;
- risks;
- recommended approval decision.

## Evidence Standard

Codex should not claim completion based only on code changes. Completion requires recorded evidence such as passing tests, command output summaries, screenshots, generated files, manual verification notes, or explicit unresolved items.

