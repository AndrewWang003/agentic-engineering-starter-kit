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
- A concise current-state DEVELOPMENT template.
- A concise task contract template.
- A concise task review template.
- A lightweight clarify, specify, slice, implement, and review flow.
- A workspace-hygiene checkpoint for task start, commit review, and task completion.
- A QA planning checkpoint for behavior-changing tasks.
- A compact visual explanation aid for reducing cognitive load.
- A lightweight handoff and authority discipline for medium and large tasks.
- A conditional source-and-evidence intake checkpoint for consequential external artifacts.
- A conditional risk-and-delivery gate for proportional isolation, security validation, repair stops, and human-controlled delivery.
- A Git baseline and verified-slice checkpoint policy.
- A tool-and-observability readiness check with relevant Skill suggestions.
- A conditional Demo decision and a localized manual acceptance handoff.
- Three optional requirement-entry skills:
  - `grill-me`
  - `grill-mode`
  - `to-spec`
- One optional QA checkpoint skill:
  - `qa-planning-checkpoint`
- One optional explanation aid:
  - `show-me`
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
- start a small project with `PROJECT.md`, `AGENTS.md`, `DEVELOPMENT.md`, `README.md`, `.gitignore`, and `tasks/`;
- establish an approved Git baseline without creating nested repositories or automatic remotes;
- create a task contract for medium or large work;
- keep contract acceptance separate from execution authorization;
- record explicit `Contract`, `Execution`, and `Acceptance` state for medium and large tasks;
- approve a medium or large task's contract, execution scope, checkpoint policy, and acceptance authority in one clear interaction;
- let contracted work proceed through implementation, validation, and review without another routine confirmation;
- delegate final acceptance to Codex only when every criterion is reliably executable and observable and no human-only judgment remains;
- define acceptance scenarios and validation strategy before behavior-changing implementation;
- keep instructions extracted from external sources separate from user and project authority;
- preserve source versions and useful locators for consequential evidence;
- scale isolation, security validation, repair stops, and delivery controls to task risk;
- distinguish commands that ran from product behaviour Codex actually observed;
- create recovery checkpoints only for authorized, complete, verified vertical slices;
- receive a detailed manual QA checklist and test guide in the user's customary language when human acceptance is needed;
- identify the owning task or bounded addendum when a repair affects another accepted behaviour boundary;
- use compact Markdown-native visuals to understand scope, flow, structure, or review findings;
- review completed work with evidence;
- keep requirement fit separate from engineering-standard review;
- keep durable project material distinct from rebuildable or temporary workspace output;
- stop using the kit without damaging the real project.
