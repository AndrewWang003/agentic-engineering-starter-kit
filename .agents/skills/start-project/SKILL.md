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

If `to-spec` already produced a Project Definition Draft, verify and reuse it. Do not repeat questions that `grill-me` or `grill-mode` already resolved.

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

## Demo Decision

Mention a Demo only when a visual or interactive prototype could materially reduce uncertainty or expensive rework. Typical signals are unclear interaction, competing product directions, costly backend implementation, or a need for the user to experience the flow before committing to it.

When those signals exist, recommend whether to make a Demo and ask the user to decide. Record:

- the question the Demo should answer;
- whether it is visual, interactive, or a technical spike;
- whether it uses fake, sample, or real data;
- whether it is throwaway or an approved production seed;
- what is deliberately not implemented.

Do not create a Demo without approval, present one as a finished product, or let throwaway code silently become production code. Skip the question when a Demo would not change a consequential decision.

## Tool And Observability Readiness

Before initialization, identify the minimum capabilities needed to build and verify the first version:

- install, development, test, build, and launch commands when known;
- the stable interface through which behaviour will be observed, such as browser, desktop app, API, CLI, generated artifact, or data output;
- required fixtures, sample files, test accounts, credentials, devices, or external services;
- whether Codex can execute the project and observe the real result rather than only edit files;
- relevant Skills already available and any missing capability worth recommending.

Recommend Skills by capability and only when relevant to the selected project and test interface. If a useful Skill is unavailable, mention the gap and suggest discovery or installation; do not install a Skill or plugin without user approval. Record behaviour that cannot be exercised or observed as unverified.

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
- Demo decision and its boundary, when relevant;
- tool and observability readiness, including any unverified behaviour or suggested Skill;
- Git baseline plan: existing repository status, whether `git init` is proposed, whether the initial checkpoint commit is authorized, and remote-backup status;
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
- whether the destination is already inside a Git worktree and, if not, whether the approved initialization summary includes creating a Git repository and initial checkpoint commit.

Safety rules:

- Never overwrite a non-empty directory.
- Never create a nested Git repository inside an existing worktree.
- Never create a real initialized project inside this Starter Kit's `examples/` directory unless the user explicitly requests an example.
- Do not modify unrelated files.
- State exactly where files will be created before creating them.

## Phase 5: Initialize Independent Project

Before writing the destination, validate that this source kit contains the complete portable set:

- `templates/AGENTIC_ENGINEERING.template.md`
- `templates/AGENTS.template.md`
- `templates/DEVELOPMENT.template.md`
- `templates/PROJECT.template.md`
- `templates/REVIEW.template.md`
- the local Skill directories `grill-me`, `grill-mode`, `to-spec`, `qa-planning-checkpoint`, `show-me`, `start-project`, `start-task`, and `review-task`;
- every local Skill metadata file and referenced file, including `start-task/references/unknowns-first-workflow.md`.

If a required source file is missing, stop before writing the destination and report the incomplete source kit. Do not create a partial managed project.

Create the managed project foundation:

- `AGENTIC_ENGINEERING.md`
- `PROJECT.md`
- `AGENTS.md`
- `DEVELOPMENT.md`
- `README.md`
- `templates/`, containing the project, agent, development, task, and review templates
- `.agents/skills/`, containing the complete local Skill set and its metadata or references
- `tasks/`, with `.gitkeep` while it is otherwise empty

Also establish a minimal `.gitignore` appropriate to the selected technology
when one is missing, and explain which common rebuildable or system-generated
files it excludes. Do not add broad ignore patterns that could hide user data.

Use the templates in this kit as the starting point.

Create `AGENTIC_ENGINEERING.md` from `templates/AGENTIC_ENGINEERING.template.md`. Fill its source-kit identity and source-kit version or commit when available. It must identify the destination as a managed project, point only to local rules, local Skills, local templates, project state, and task records, and state that later source-kit adoption requires an explicit task.

Copy only the validated `templates/` and `.agents/skills/` portable sets. Do not copy this source kit's `tasks/` history, `examples/`, `CHANGELOG.md`, `.git/`, source-kit absolute paths, remotes, or uncommitted working-tree content. The generated `AGENTS.md` must direct Agents to the generated project's local files and must not point back to this source kit.

The generated files must contain the actual information agreed during discovery.

Do not use generic placeholder project details when confirmed information is available.

Record open and deferred decisions honestly instead of inventing them.

After creation, validate that the managed project contains the required foundation, the exact local Skill set, each referenced local file, and no prohibited source-kit history or Git metadata. Run available local Skill structure checks and confirm generated instructions contain only local workflow paths before continuing to the Git baseline.

### Establish The Git Baseline

After the foundation is created:

1. Inspect whether the destination is already inside a Git worktree and record existing changes before any Git action.
2. When the approved initialization summary authorizes it and the destination is an independent non-repository directory, run `git init`. Otherwise preserve the existing repository or the user's decision to remain without Git.
3. Run the available foundation checks before creating a commit.
4. When the same approval authorizes an initial checkpoint commit, Git identity is usable, and only intended foundation files are included, create a commit such as `chore: initialize project foundation` and record its hash.
5. If Git initialization or commit creation is unavailable, preserve the initialized files and report the exact limitation instead of claiming a recovery point exists.

Do not create a remote, push, publish, or place secrets in version control without separate user authorization. A remote backup may be recommended, especially for important projects, but local Git remains a valid starting state.

## Phase 6: Report Result

After initialization, report:

- destination path;
- files and folders created;
- Git repository, baseline commit, and remote-backup status;
- what Codex can run and observe, suggested Skills, and unverified behaviour;
- Demo decision and disposition, when relevant;
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
