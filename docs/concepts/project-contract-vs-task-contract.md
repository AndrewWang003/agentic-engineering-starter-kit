# Project Contract vs Task Contract

## Project Contract

A project contract is the durable agreement for a real software project.

It defines stable context:

- mission;
- users or operators;
- core problem;
- product boundaries;
- primary workflow;
- inputs and outputs;
- non-goals;
- quality baseline;
- project-level constraints;
- first-phase success criteria.

A project contract should change rarely. Changing it may alter the meaning of future tasks, so material changes require human approval.

## Task Contract

A task contract is the bounded agreement for one unit of work.

It defines:

- objective;
- allowed changes;
- forbidden changes;
- files or modules in scope;
- approval triggers;
- validation commands;
- acceptance criteria;
- completion evidence.

A task contract should be specific enough for Codex to work autonomously inside its limits.

## Key Difference

The project contract answers: "What is this project and what boundaries govern it?"

The task contract answers: "What is Codex allowed to do right now, and how will completion be proven?"

## Change Rule

If a task requires changing the project contract, Codex must stop and request approval instead of silently expanding the task.

