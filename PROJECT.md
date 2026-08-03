# PROJECT.md

## Name

Codex Engineering Starter Kit

## Purpose

Help users start and manage small software projects, plugins, and simple systems with Codex in a structured but lightweight way.

## Problem

Pure chat-driven development often loses important context. Tasks can grow beyond their original scope, and completion can be claimed without clear evidence.

## Target User

A non-expert or semi-technical user who wants Codex to help build small projects while keeping decisions, scope, and verification visible in files.

## First Version Includes

- A project foundation template.
- A project-specific AGENTS template.
- A concise task contract template.
- A concise task review template.
- A lightweight clarify, specify, slice, implement, and review flow.
- Three optional requirement-entry skills:
  - `grill-me`
  - `grill-with-docs`
  - `to-spec`
- Three core workflow skills:
  - `start-project`
  - `start-task`
  - `review-task`
- A minimal example.

## Intentionally Excluded

- Multi-agent orchestration.
- Autonomous software factories.
- Custom agent runtimes.
- Databases or vector search.
- Web interfaces or API servers.
- Automatic cross-project feedback systems.
- Automatic self-improvement.
- Complex evaluation frameworks.

## Success Criteria

The kit succeeds when a user can:

- understand the workflow by reading the README;
- clarify a fuzzy requirement and preserve it as a local project draft or task contract;
- start a small project with `PROJECT.md`, `AGENTS.md`, `README.md`, and `tasks/`;
- create a task contract for medium or large work;
- review completed work with evidence;
- keep requirement fit separate from engineering-standard review;
- stop using the kit without damaging the real project.
