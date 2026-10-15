# Portable Project Factory Design

## Status

Proposed. This design is not implementation authorization.

## Intent

Make this repository a portable Agentic Engineering SYS source kit. Any Agent that opens this repository can use its repository-local instructions to initialize a separate, self-contained project that is governed by the same Agentic Engineering SYS workflow.

The generated project must remain operable after losing access to this source kit and without relying on machine-global Skills.

## Terms

- **Source kit**: this repository. It defines the reusable system and does not become part of a generated application's history.
- **Bootstrap Agent**: any Agent that has access to the source kit and is asked to create or onboard a project.
- **Managed project**: an independently initialized project containing its own local Agentic Engineering SYS files.
- **System manifest**: a concise generated file that records the source-kit version or commit, copied components, and the controlled upgrade rule.

## Goals

- Let a Bootstrap Agent discover the source kit's role and reading order from ordinary repository files.
- Generate a managed project with all instructions needed for project start, task start, task review, requirement shaping, QA planning, and compact visual explanation.
- Preserve the source kit's existing authority, safety, and approval boundaries in each managed project.
- Make the generated project's provenance and upgrade boundary explicit.

## Non-Goals

- No machine-global Skill dependency.
- No automatic installation, remote service, plugin, runtime, database, or background automation.
- No copying source-kit task history, examples, changelog, Git history, or uncommitted source-kit changes into generated projects.
- No silent synchronization from the source kit into existing managed projects.
- No changes to the three core workflows: `start-project`, `start-task`, and `review-task`.

## Architecture

```text
Source kit
  AGENTS.md + README.md identify bootstrap mode
  .agents/skills/ + templates/ define the portable workflow
          |
          | user-approved start-project initialization
          v
Managed project
  AGENTIC_ENGINEERING.md identifies source and upgrade policy
  AGENTS.md selects repository-local workflows
  .agents/skills/ + templates/ carry the workflow implementation
  PROJECT.md + DEVELOPMENT.md + README.md + tasks/ carry project state
```

## Bootstrap Contract

The source-kit `AGENTS.md` and README will explicitly state that an Agent opening this repository may act as a Bootstrap Agent only when the user asks to create or onboard a project.

The Bootstrap Agent must:

1. Read the source kit's `AGENTS.md`, applicable local Skill, templates, and the user's request.
2. Use `start-project` to route the request and collect or reuse project discovery.
3. Obtain the required approval for the project summary and destination before writing outside the source kit.
4. Generate a managed-project foundation at the approved destination.
5. Report the copied system components, source-kit identity, Git decision, and first task gate.

The Bootstrap Agent must not infer permission to overwrite a directory, create a nested Git repository, install anything, create a remote, or begin the first implementation task.

## Managed Project Foundation

`start-project` will create the existing foundation plus the following portable-system files:

```text
AGENTIC_ENGINEERING.md
AGENTS.md
PROJECT.md
DEVELOPMENT.md
README.md
.gitignore
tasks/.gitkeep
templates/
.agents/skills/
```

The copied `templates/` directory will contain the project, agent, development, task, and review templates. The copied `.agents/skills/` directory will contain the complete repository-local workflow set: `grill-me`, `grill-mode`, `to-spec`, `qa-planning-checkpoint`, `show-me`, `start-project`, `start-task`, and `review-task`, including each required local reference and Skill metadata file.

`AGENTIC_ENGINEERING.md` will be concise. It will state that the project is a managed instance, identify the source-kit commit or version available at initialization, list the copied workflow components, require use of local Skills before any matching action, and require an explicit task to adopt later source-kit improvements.

The generated `AGENTS.md` will contain no path back to the source kit. It will direct Agents to local `AGENTS.md`, local `.agents/skills/`, the task contract, project state, and README in the established reading order.

## Initialization Behaviour

Before writing the foundation, `start-project` will validate the portable set exists in the source kit. If any required template, Skill, metadata file, or referenced material is missing, it must stop and report the incomplete source kit rather than create a partial managed project.

After creation, it will validate that the managed project contains the required files, that each copied local Skill is structurally valid where a validator is available, and that generated root instructions point only to local paths. Git initialization and the first commit remain separately controlled by the already-approved initialization decision.

## Upgrade Behaviour

The source kit is a versioned starting point, not a controller of existing projects. A later source-kit update does not alter a managed project automatically. To adopt an update, an Agent must open a bounded task in the managed project, compare the local system manifest with the proposed source version, identify affected files, obtain execution authorization, and validate the upgrade like any other project change.

## Validation Plan

1. Static consistency: inspect source-kit instructions, templates, and `start-project` for the same component list and local-only rule.
2. Forward simulation: initialize a temporary, independent project from the source kit after required discovery and approval conditions are represented.
3. Portable inspection: from the generated project alone, verify that its `AGENTS.md`, manifest, local Skills, templates, and task directory tell a fresh Agent how to operate.
4. Negative checks: verify no historical tasks, examples, changelog, source Git metadata, remote, or source-kit absolute path is copied.
5. Foundation checks: run applicable local Skill validation, YAML parsing, Markdown whitespace checks, and `git diff --check`.

## Open Decisions

None blocking. The manifest is intentionally a Markdown file rather than a script or configuration runtime so that the system remains inspectable and dependency-free.
