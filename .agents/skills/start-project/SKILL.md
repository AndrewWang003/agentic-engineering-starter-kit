---
name: start-project
description: Guide a user through discovery, approval, and lightweight initialization of a new software project, or route an existing repository to onboarding or task work. Use when the user wants to start a project, define a first version, or adopt the Starter Kit in an existing repository.
---

# start-project

Use this skill when a user wants to start a small software project, plugin, or simple system with Codex.

## Goal

Run an interactive project discovery and initialization workflow.

The goal is not to immediately generate files. The goal is to help the user define a real small project well enough to initialize it in a user-approved independent project directory.

Do not create files until discovery is sufficient, the user has approved the project summary, and the destination has been confirmed.

## Phase 0: Route The Request

Before detailed discovery, classify the user's situation.

Determine whether the request is:

- `Route A: New project`
- `Route B: Existing project change`
- `Route C: Existing project onboarding`

Keep this routing step short. Determine:

- whether an existing repository already represents the software project;
- whether the user is defining the whole project or changing something inside it;
- whether the user wants to initialize project-level Codex instructions for an existing repository;
- whether a destination path or repository has already been identified.

If the route is evident from the user request and repository context, route without unnecessary questions.

If uncertain, ask no more than two focused clarification questions before routing.

### Route A: New Project

Use this route when:

- no existing repository or project exists for the idea;
- the user is creating a new application, plugin, tool, or system;
- the destination is empty or has not yet been created.

Then continue with the normal project discovery and initialization workflow below.

### Route B: Existing Project Change

Use this route when:

- an existing repository already represents the software project;
- the user wants to add, change, investigate, fix, or improve something inside it;
- the requested work is a feature, bug fix, refactor, algorithm improvement, migration, or release.

In this route:

- do not create a new project;
- do not create a nested project foundation;
- do not create a separate planning repository by default;
- stop the `start-project` workflow;
- explain briefly why the request belongs to `start-task`;
- recommend switching to the `start-task` skill.

Do not continue detailed task discovery inside `start-project`.

### Route C: Existing Project Onboarding

Use this route when:

- an existing repository already exists;
- the user wants to use this Starter Kit with it;
- the repository lacks sufficient project-level documentation or Codex working instructions.

In this route:

- do not treat the repository as a new project;
- do not redesign or reorganize the repository;
- inspect only what is needed to propose a lightweight onboarding;
- propose a minimal `PROJECT.md`, if missing;
- propose a minimal `AGENTS.md`, if missing;
- identify basic development and test commands when they are obvious;
- propose a `tasks/` directory, if useful;
- require user approval before writing files.

After onboarding, recommend `start-task` for the actual requested change.

## Phase 1: Begin Project Discovery

When invoked, clearly state that project discovery is starting.

Also state that no files will be created until:

- enough information has been collected;
- the user approves the project summary;
- the destination path is confirmed.

If `to-spec` already produced a Project Definition Draft, verify and reuse it. Do not repeat questions that `grill-me` or `grill-with-docs` already resolved.

## Ask About

Ask only for information needed to begin:

- problem;
- intended user;
- first version;
- main inputs and outputs;
- important constraints;
- non-goals;
- success criteria.

Do not ask all questions as one large questionnaire. Use a guided conversation with small groups of questions.

## Discovery Method

- Inspect available repository or reference material before asking questions it can answer.
- Resolve one high-impact decision topic at a time when the project is ambiguous.
- Explain why a decision matters and offer a recommended answer with tradeoffs.
- Resolve decisions that block later decisions before moving downstream.
- Capture important domain terms in the user's language and use them consistently.
- Record hard-to-reverse decisions under `Confirmed Decisions`; do not create extra decision documents by default.
- Do not turn reversible implementation details into approval gates.

## Classification

Separate information into:

- `Confirmed`
- `Assumed`
- `Working hypotheses`
- `Open`
- `Deferred`

Evidence rules:

- Repository behaviour directly observed in code, data, or commands may be `Confirmed`.
- A possible root cause must be a `Working hypothesis`.
- Words such as "likely cause", "suspected failure source", or "probably caused by" must not appear under `Confirmed`.
- Do not recommend implementation changes before working hypotheses are investigated.

## Phase 2: Control Discovery Length

Do not ask questions indefinitely.

Stop when:

- the project purpose is understandable;
- the first delivery scope is clear;
- the main input and output are known;
- major constraints and non-goals are recorded;
- the project can be evaluated;
- remaining unknowns do not prevent work from beginning.

Do not design the entire future product.

## Phase 3: Present Approval Summary

Before creating files, present a concise project initialization summary containing:

- proposed project name;
- project purpose;
- intended user;
- first-version scope;
- inputs and outputs;
- constraints;
- non-goals;
- success criteria;
- key domain terms;
- assumptions;
- working hypotheses, if any;
- open and deferred decisions.

Ask the user to approve or correct this summary.

Do not create files before approval.

## Phase 4: Confirm Destination

After the project definition is approved, ask for or confirm:

- project folder name;
- absolute destination path;
- whether the destination already exists;
- whether the user approves creating files there.

Safety rules:

- Never overwrite a non-empty directory.
- Never create a real initialized project inside this Starter Kit's `examples/` directory unless the user explicitly requests an example.
- Do not modify unrelated files.
- State exactly where files will be created before creating them.

## Phase 5: Initialize Independent Project

Create only the minimal project foundation:

- `PROJECT.md`
- `AGENTS.md`
- `README.md`
- `tasks/`

Also establish a minimal `.gitignore` appropriate to the selected technology
when one is missing, and explain which common rebuildable or system-generated
files it excludes. Do not add broad ignore patterns that could hide user data.

Use the templates in this kit as the starting point.

The generated files must contain the actual information agreed during discovery.

Do not use generic placeholder project details when confirmed information is available.

Record open and deferred decisions honestly instead of inventing them.

## Phase 6: Report Result

After initialization, report:

- destination path;
- files and folders created;
- assumptions used;
- working hypotheses, if any;
- remaining open or deferred decisions;
- a suggested first real task.

Do not automatically begin the first task. Wait for the user to invoke or approve `start-task`.

## Examples Versus Real Projects

The `examples/` directory is only for static documentation examples and controlled skill tests.

A normal `start-project` invocation should initialize an independent project in a user-approved external folder.

## Boundaries

- Do not ask questions indefinitely.
- Do not choose major technical decisions without evidence or user approval.
- Do not create a database, service, or framework unless the user clearly asks for it.
- Never overwrite an existing non-empty project directory without explicit approval.
- Never silently skip discovery.
- Never create a generic real project without user approval.
- Never treat a feature, bug fix, refactor, investigation, migration, release, or algorithm improvement inside an existing repository as a new project's first-version scope.
