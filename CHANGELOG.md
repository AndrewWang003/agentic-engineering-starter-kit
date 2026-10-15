# Changelog

## Unreleased

- Added `qa-planning-checkpoint` as an optional project-local skill for behavior-changing tasks.
- Added `show-me` as an optional project-local skill for compact visual explanations.
- Added lightweight handoff, authorization-gate, and cross-task repair-ownership guidance adapted from applying the workflow in FillNest.
- Clarified task state fields, `DEVELOPMENT.md` update boundaries, explanatory HTML exceptions, and P0/P1/P2 review closure.
- Added conditional source-and-evidence intake guidance that preserves provenance, separates extraction from interpretation and authority, and escalates consequential uncertainty.
- Added a proportional risk-and-delivery gate covering risk tiers, optional isolation, security-validation triggers, repair-stop conditions, and human-controlled delivery.
- Refined project initialization with a conditional Demo decision, tool-and-observability readiness, a `DEVELOPMENT.md` foundation template, and an approved Git baseline.
- Added authorized checkpoint commits after complete verified vertical slices and a localized manual acceptance checklist and test guide.
- Added acceptance scenario and test strategy fields to task and review templates.
- Added `DEVELOPMENT.md` as the current project continuity file.
- Added bundled task authorization, automatic post-implementation review, and explicit User-or-Agent acceptance authority for fully observable work.
- Added portable source-kit bootstrap guidance, managed-project identity, and local workflow-package initialization rules.

## 0.3.0 - 2026-08-03

- Added project-adapted `grill-me`, `grill-with-docs`, and `to-spec` as optional requirement-entry skills.
- Made both grill skills self-contained instead of depending on separately installed `grilling` or `domain-modeling` skills.
- Adapted `to-spec` to create local project-definition drafts or task contracts instead of requiring an issue tracker.
- Added explicit handoffs from the entry skills to `start-project` and `start-task` while preserving the three core workflows.
- Added project-local Skill UI metadata and kept the entry skills explicitly invoked.

## 0.2.0 - 2026-08-03

- Adapted the AIHero Main Flow into the existing three-workflow Starter Kit without adding new Skills or infrastructure.
- Added decision-focused clarification and repository-first investigation to project and task discovery.
- Added concise specification, stable testing-interface, vertical-slice, blocker, and implementation-discipline guidance to `start-task`.
- Added one-behaviour-at-a-time red-green guidance for tasks where automated tests are appropriate.
- Split `review-task` into independent Spec Fit and Project Standards axes and added baseline confirmation.
- Updated project, task, and review templates to carry the new workflow outputs.

## 0.1.0 - 2026-07-14

- Reduced the project from the broader Agentic Engineering System concept into the minimal Codex Engineering Starter Kit.
- Kept only three workflows: start project, start task, and review task.
- Replaced central governance, system improvement, and evaluation structure with short templates and three practical Codex skills.
- Added `start-project` routing for new projects, existing-project changes, and existing-project onboarding.
- Added evidence classification guidance for working hypotheses.
