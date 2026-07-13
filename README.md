# Agentic Engineering System

Agentic Engineering System is a versioned, file-based engineering operating system for using Codex to initialize, manage, execute, verify, review, and improve software development projects.

The system treats files as the source of truth. Chat can help create, clarify, and execute work, but stable project knowledge must be captured in repository documents, templates, skills, task records, and evaluation cases.

## Purpose

This repository defines the central method library. It is not a product project. It provides reusable rules, templates, and Codex skills that future projects can use to:

- discover enough product and engineering context to initialize a project;
- create a durable project contract;
- bootstrap a project repository;
- create bounded task contracts;
- let Codex work autonomously inside approved limits;
- verify completion with evidence;
- turn retrospectives into reviewed improvement proposals.

## What This System Is Not

This system is not:

- a multi-agent orchestration platform;
- a web application framework;
- a database-backed project manager;
- a replacement for human product judgment;
- an automatic software factory.

Codex remains the execution agent. This repository defines how Codex should work.

## Core Loop

1. Discover the project context.
2. Produce an approved project contract.
3. Bootstrap an independent project repository.
4. Create a task contract for a specific unit of work.
5. Execute within the approved scope.
6. Verify against explicit acceptance criteria.
7. Produce a retrospective.
8. Submit reusable improvements back to the central system.

## Repository Layout

- `SYSTEM_CHARTER.md` defines purpose, principles, roles, autonomy, and limits.
- `SYSTEM_ARCHITECTURE.md` explains the file-based architecture.
- `docs/` contains concepts, workflows, and governance rules.
- `templates/` contains reusable project and task artifacts.
- `.agents/skills/` contains Codex skill entrypoints, including discovery, bootstrap, task contract, execution, verification, retrospective, and system improvement workflows.
- `evals/` contains evaluation design notes and future cases.
- `development log.md` records functional changes to this repository.

## Current Status

Version `0.1.0` initializes the central system repository. It does not yet bootstrap real product projects.
