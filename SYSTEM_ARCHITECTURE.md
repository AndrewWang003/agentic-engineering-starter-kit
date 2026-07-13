# System Architecture

## Overview

Agentic Engineering System is a file-based method library. It does not require a database, server, queue, or custom agent runtime.

The first version has four layers:

1. System definition files.
2. Workflow documentation.
3. Reusable templates.
4. Codex skill entrypoints.

## Layer 1: System Definition

The central repository defines stable rules:

- `SYSTEM_CHARTER.md`
- `SYSTEM_ARCHITECTURE.md`
- `AGENTS.md`
- `ROADMAP.md`
- `CHANGELOG.md`
- `VERSION`

These files describe what the system is, how it evolves, and what Codex may do.

## Layer 2: Workflows

Workflow documents define repeatable procedures:

- project discovery;
- project bootstrap;
- task lifecycle;
- task execution;
- verification;
- retrospective;
- system improvement.

Every workflow should specify input, output, stopping condition, and approval boundary.

## Layer 3: Templates

Templates create consistent artifacts in real projects:

- project contracts;
- task contracts;
- amendments;
- verification reports;
- retrospectives;
- system improvement proposals.

Templates should include explicit status labels such as `Confirmed`, `Assumed`, `Open`, and `Deferred` when uncertainty matters.

## Layer 4: Skills

Skills are lightweight Codex instructions stored under `.agents/skills/`.

First-version skills are not independent agents. They are reusable workflows that guide Codex through a phase of work.

## Central Repository vs Project Repository

The central repository stores reusable method and governance.

A real project repository stores project-specific contracts, code, task records, validation commands, and feedback generated from real execution.

The central system may bootstrap a project, but it should not become the project's application repository.
