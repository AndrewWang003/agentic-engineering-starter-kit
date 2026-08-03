# Development Log

## 2026-08-03

### Added three project-adapted requirement-entry Skills

- Installed upstream `grill-me`, `grill-with-docs`, and `to-spec` from `mattpocock/skills` into `.agents/skills/`, then adapted them to this Starter Kit.
- Made `grill-me` a self-contained, file-free interview that resolves one high-impact decision at a time and hands confirmed understanding to `to-spec`.
- Made `grill-with-docs` self-contained and limited its writes to a lazily created `CONTEXT.md` glossary and user-approved ADRs under `docs/adr/`.
- Removed runtime dependence on separate `grilling`, `domain-modeling`, and `setup-matt-pocock-skills` installations.
- Changed `to-spec` from issue-tracker publishing to local routing: existing-project work creates or updates `tasks/<task-id>/TASK.md`; new-project work remains a Project Definition Draft until `start-project` confirms the destination.
- Updated `start-project` and `start-task` to reuse completed entry work instead of repeating the interview.
- Updated `AGENTS.md`, README, and project metadata so the three new Skills are the optional requirement entrance and the original three Skills remain the core project, task, and review workflows.
- Added explicit-only UI metadata for all three entry Skills.
- Forward-tested all three entries without writing simulation files; tightened `to-spec` so slice blockers can only reference earlier slices or `None`.
- Changed files: `.agents/skills/grill-me/`, `.agents/skills/grill-with-docs/`, `.agents/skills/to-spec/`, `.agents/skills/start-project/SKILL.md`, `.agents/skills/start-task/SKILL.md`, `AGENTS.md`, `README.md`, `PROJECT.md`, `CHANGELOG.md`, and `development log.md`.
- No issue tracker, dependency, script, runtime, automation, or additional hidden Skill was introduced.

### Integrated a lightweight Main Flow into the three existing Skills

- Reviewed AIHero's `grill-with-docs`, `to-spec`, `to-tickets`, `implement`, `tdd`, and `code-review` Main Flow skills and adapted their clarification, specification, vertical-slice, implementation, test-feedback, and two-axis review practices.
- Kept the Starter Kit's existing `start-project`, `start-task`, and `review-task` structure; no new Skill, dependency, script, tracker integration, runtime, or multi-agent layer was added.
- Updated `start-project` to investigate available evidence before asking questions, resolve one high-impact decision topic at a time, offer recommendations with tradeoffs, and preserve key domain terms.
- Updated `start-task` to follow a compact alignment, specification, vertical-slice, implementation, and validation sequence.
- Added task-contract fields for user value, specification summary, implementation decisions, stable testing interface, vertical slices, and blockers.
- Added conditional test-first guidance: one public behaviour per red-green cycle, refactor only while green, and derive expected results from an independent source.
- Updated `review-task` and the review template to identify a review baseline and report Spec Fit separately from Project Standards.
- Added valid Skill frontmatter to all three existing Skills and updated README workflow guidance and project metadata.
- Changed files: `.agents/skills/start-project/SKILL.md`, `.agents/skills/start-task/SKILL.md`, `.agents/skills/review-task/SKILL.md`, `templates/PROJECT.template.md`, `templates/TASK.template.md`, `templates/REVIEW.template.md`, `PROJECT.md`, `README.md`, `CHANGELOG.md`, `development log.md`, and `examples/minimal-example/PROJECT.md`.
- Deliberately excluded AIHero's issue-tracker publishing, automatic commits, multi-agent review execution, extra domain-document scaffolding, and additional Skills to preserve the Starter Kit's scope.

## 2026-07-14

### Added start-project routing gate

- Recorded a failed real-world `start-project` test where an existing repository improvement was treated as though it might need a new project foundation.
- Identified why this was incorrect: feature, bug fix, refactor, investigation, migration, release, and algorithm-improvement work inside an existing repository belongs to `start-task`, not new-project initialization.
- Added a three-route decision model to `start-project`: new project, existing project change, and existing project onboarding.
- Updated terminology guidance so project-level language is reserved for whole projects and task-level language is used for work inside an existing project.
- Added `Working hypotheses` to evidence classification so suspected causes are not recorded as confirmed facts.
- Added a lightweight regression test at `examples/regression-tests/start-project-existing-project-change.md`.
- Changed files: `.agents/skills/start-project/SKILL.md`, `.agents/skills/start-task/SKILL.md`, `README.md`, `templates/PROJECT.template.md`, `templates/TASK.template.md`, `CHANGELOG.md`, and `examples/regression-tests/start-project-existing-project-change.md`.
- Unresolved limitation: ambiguous requests may still require up to two focused routing questions before choosing a route.

### Added Unknowns-First reference for start-task

- Moved `Unknowns-First Agentic Workflow.md` into `.agents/skills/start-task/references/unknowns-first-workflow.md`.
- Kept it as an optional `start-task` reference rather than introducing a fourth Skill.
- Updated `start-task` and `README.md` to default to the Quick Start five-step version and ask before using the full workflow.

### Corrected start-project workflow after first test

- The first `start-project` test generated `examples/initialized-project-demo/` directly, which only tested file generation.
- Identified a workflow defect: `start-project` did not enforce discovery, user approval, destination confirmation, and independent project initialization before file creation.
- Updated `start-project` to require a guided discovery conversation, Confirmed/Assumed/Open/Deferred classification, approval summary, destination confirmation, and a real independent project folder.
- Updated README guidance to match the corrected discovery-first workflow.
- Removed the invalid `examples/initialized-project-demo/` output so the corrected workflow can be tested cleanly.

### Simplified into Codex Engineering Starter Kit

- Reduced the broader Agentic Engineering System concept into the lightweight Codex Engineering Starter Kit.
- Removed central governance, system improvement, evaluation, upgrade, and multi-workflow platform concepts.
- Reduced the kit to three workflows: start project, start task, and review task.
- Replaced the larger template set with `PROJECT`, `AGENTS`, `TASK`, and `REVIEW` templates.
- Replaced seven Codex skills with three practical skills.
- Added a minimal example project.
