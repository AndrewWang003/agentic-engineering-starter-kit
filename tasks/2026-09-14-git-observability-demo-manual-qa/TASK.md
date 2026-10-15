# Task Contract

## Task ID And Name

2026-09-14-git-observability-demo-manual-qa — Refine project initialization and delivery guidance

## Task State And Authorization

- Contract: Accepted
- Execution: Paused
- Acceptance: Pending QA
- Authorized slice or scope: Refine the existing three workflows and templates with Git baselines, verified-slice commits, tool and observability readiness, localized manual QA handoff, and a conditional Demo decision.
- Next gate before implementation or continuation: User follows the manual acceptance handoff and reports the acceptance decision.

The user approved the minimal incremental design and explicitly asked Codex to perform the upgrade.

## Risk And Delivery Profile

- Risk tier: Medium
- Risk drivers: Persistent workflow behaviour changes across project initialization, task execution, review, templates, and guidance; no runtime or production code changes.
- Base state: `main` at `0fe78f406d95eb9989cf507eac03579c1faac5bf` with intentional uncommitted workflow changes, an untracked `show-me` Skill, and the prior source-evidence/risk-delivery task records.
- Isolation: Existing working tree retained because this task extends the same overlapping workflow files.
- Security validation triggers: None beyond preserving the existing source-evidence and authorization rules.
- Delivery method: Reviewable local diff and task review; no remote is configured.
- Repair and stop conditions: Stop for scope expansion, destructive cleanup, a new Skill/workflow/dependency, conflict with existing edits, or repeated validation failure without new evidence.

## Checkpoint Commit Policy

- Checkpoint commits: Not authorized
- Commit boundary: Verified task completion remains uncommitted for user review
- Base branch and commit: `main` at `0fe78f406d95eb9989cf507eac03579c1faac5bf`
- Relevant pre-existing changes: Existing workflow edits, the untracked `show-me` Skill, and the prior task records
- Commit-message convention: Not applicable for this task

## Background

The current Starter Kit already defines project discovery, vertical slices, automated validation, task review, risk controls, and human acceptance states. It lacks explicit guidance for initializing a Git recovery baseline, committing verified slices, checking whether the agent can run and observe the product, handing users a localized manual QA guide, and asking whether a Demo would reduce uncertainty.

## Confirmed Facts

- `start-project` already creates a minimal project foundation but does not include `DEVELOPMENT.md` or Git initialization.
- Generated `AGENTS.md` already requires maintaining `DEVELOPMENT.md`, so the initialization set is inconsistent.
- `start-task` already defines vertical slices but does not record commit authorization or verified commit checkpoints.
- Task templates do not record tool and observability readiness.
- Review templates do not provide a detailed user-facing manual acceptance guide.
- Static RED checks for all five missing behaviours failed before implementation.

## Goal

Make the existing workflow more explicit and recoverable without changing its architecture or adding a new workflow, Skill, dependency, service, or automation layer.

## User Value

New projects start with a recoverable Git baseline, agents disclose whether they can genuinely run and observe the product, completed slices can become clean recovery points, and users receive actionable QA instructions in their customary language.

## Current Behaviour

- Project initialization creates `PROJECT.md`, `AGENTS.md`, `README.md`, `tasks/`, and a technology-appropriate `.gitignore`.
- Demo suitability, tool readiness, checkpoint commit policy, and manual acceptance guidance are implicit or absent.

## Expected Behaviour

- New independent projects include `DEVELOPMENT.md`, a retained `tasks/` directory, and an approved Git initialization plan.
- A verified initial foundation can be committed when the initialization summary authorizes it and Git is usable.
- Projects and tasks identify the commands, tools, Skills, fixtures, credentials, and observation surfaces required for verification.
- Missing capabilities lead to a relevant Skill suggestion or an explicit unverified area, never an unsupported completion claim.
- Checkpoint commits occur only after a complete vertical slice passes its required validation and only when the task contract authorizes commits.
- Demo suitability is raised only when a prototype could reduce material product or implementation risk, and the user decides whether to proceed.
- Review produces a detailed manual QA checklist and test guide in the user's customary conversation language unless the user or project requires another language.
- Acceptance remains pending until the user reports the manual result or explicitly accepts documented limitations.

## Specification Summary

Add concise conditional guidance and fields to the existing project, task, and review flows. Add one `DEVELOPMENT` template to make the initialized foundation internally consistent. Update the minimal example and public guidance to reflect the same foundation.

## Implementation Decisions

- Keep the change bounded inside the current three workflows.
- Do not add or copy Skills automatically; inspect available capabilities and recommend relevant missing Skills, with user approval required before installation.
- Include Git initialization and the initial checkpoint in the project approval summary; do not initialize nested repositories or create remotes automatically.
- Record checkpoint-commit authorization once in the task contract. Never commit unrelated or unverified changes.
- Keep Demo optional and distinguish throwaway prototypes from production seeds.
- Keep canonical project records in the project language while localizing the user-facing manual QA handoff to the user's customary conversation language.

## Tool And Observability Readiness

- Install command: Not applicable
- Development or launch command: Not applicable
- Test command: Skill validation, YAML parsing, static contract searches, and Markdown checks recorded below
- Build command: Not applicable
- Test interface through which the real result is observed: Project-local Skill Markdown, templates, and a temporary initialized Git repository
- Codex can execute the behaviour: Partial; the initialization foundation and Git checkpoint can be forward-simulated
- Codex can observe the outcome: Yes for generated files, Git status, and commit history; no separate user project is modified
- Required fixtures, sample inputs, accounts, credentials, devices, or services: Temporary directory and local Git only
- Relevant available Skills: `start-task`, `qa-planning-checkpoint`, `review-task`, and `superpowers:writing-skills`
- Suggested missing Skills or capabilities: None
- Behaviour that will remain unverified: Real-world use across different application stacks and user-language QA handoffs

## Testing Interface

- Stable public behaviour or interface: The instructions and fields exposed by `start-project`, `start-task`, `review-task`, their templates, and the minimal initialized example.
- Comparable existing tests: Project Skill validation, YAML parsing, Markdown whitespace checks, cross-file contract searches, and a temporary forward initialization simulation outside the repository.

## Acceptance Scenarios

| Scenario | Given | When | Then | Priority |
| --- | --- | --- | --- | --- |
| Independent new project gets a recovery baseline | The approved destination is not already inside a Git repository | Initialization runs | Git is initialized only as approved, the foundation is validated, and an initial commit is attempted only when authorized and usable | P0 |
| Existing repository is protected | The destination is already inside a Git worktree | Initialization runs | No nested repository is created and existing changes remain protected | P0 |
| Slice commit is evidence-backed | A complete vertical slice passes its required checks and checkpoint commits are authorized | The slice closes | Only task-owned changes are committed and the commit reference is recorded | P0 |
| Missing capability is disclosed | The agent cannot run or observe a required test interface | Readiness is assessed | A relevant available or missing Skill is suggested and the behaviour remains unverified | P1 |
| Demo is optional and purposeful | Product or interaction uncertainty could be reduced by a prototype | Discovery reaches the Demo decision | The user chooses whether to create a scoped throwaway or production-seed Demo | P1 |
| User receives actionable QA | Automated review is ready for human acceptance | The task is handed off | A detailed checklist and test guide appears in the user's customary language and acceptance stays pending | P0 |

## Test Strategy

| Scenario | Validation Level | Command Or Check | Notes |
| --- | --- | --- | --- |
| All workflow scenarios | Static contract test | Re-run the five previously failing focused searches | Each must find the new behaviour in the correct Skill and template |
| Skill integrity | Automated validation | Run `quick_validate.py` over all project-local Skills | All Skills must validate |
| UI metadata integrity | Automated validation | Parse all project-local `agents/openai.yaml` files | All YAML must parse |
| Initialized foundation | Forward simulation | Build a temporary foundation from templates outside the repository and inspect required files and placeholders | Do not preserve simulation output |
| Repository integrity | Static validation | Run `git diff --check` and Markdown trailing-whitespace checks | No whitespace errors |
| Scope and hygiene | Review | Inspect complete diff, status, and untracked files | No unrelated deletion, dependency, Skill, or workflow expansion |

## Vertical Slices

| Slice | Complete Behaviour | Acceptance Criteria | Blocked By | Status | Checkpoint |
| --- | --- | --- | --- | --- | --- |
| 1. Project initialization | Demo, tool readiness, `DEVELOPMENT.md`, Git baseline, and initial commit guidance are present | Independent and existing Git destinations are handled safely and foundation files agree | None | Complete | Verified but not committed; commits not authorized |
| 2. Task execution | Readiness and checkpoint commit policies control verified slices | Missing capabilities stay unverified and commits require contract authorization | Slice 1 | Complete | Verified but not committed; commits not authorized |
| 3. Human acceptance | Review emits a localized detailed QA handoff | Checklist covers setup, steps, expected results, evidence, limits, feedback, and decision | Slice 2 | Complete | Verified but not committed; commits not authorized |
| 4. Consistency and examples | Templates, README, project state, changelog, and minimal example agree | All static and forward checks pass | Slice 3 | Complete | Verified but not committed; commits not authorized |

## Allowed Scope

- `.agents/skills/start-project/SKILL.md`
- `.agents/skills/start-task/SKILL.md`
- `.agents/skills/review-task/SKILL.md`
- Existing templates plus one new `templates/DEVELOPMENT.template.md`
- `PROJECT.md`, `README.md`, `DEVELOPMENT.md`, and `CHANGELOG.md`
- `examples/minimal-example/`
- This task contract and its review

## Forbidden Scope

- A new workflow or Skill
- Dependencies, scripts, services, databases, CI, or Git hosting automation
- Automatic Skill or plugin installation
- Automatic remote creation or push
- A mandatory Demo, checkpoint commit, worktree, browser, or manual test platform for every task
- Committing or deleting pre-existing user work

## Acceptance Criteria

- All five RED checks become GREEN for the intended workflow behaviour.
- New projects receive an internally consistent minimal foundation including `DEVELOPMENT.md` and a retained `tasks/` directory.
- Git initialization, initial commit, and verified-slice commits have explicit authorization and safety boundaries.
- Tool readiness distinguishes execution from observation and handles missing capabilities honestly.
- Demo prompting is conditional and user-controlled.
- Manual QA handoff is detailed, localized, and required before acceptance unless limitations are explicitly accepted.
- Existing source-evidence, risk-delivery, workspace-hygiene, and authorization controls remain intact.
- Validation passes and the full diff stays within scope.

## Required Validation

- Re-run RED contract checks and confirm GREEN.
- Validate all project-local Skills.
- Parse all project-local Skill YAML.
- Run `git diff --check` and a Markdown whitespace check.
- Forward-simulate a minimal initialized foundation outside the repository.
- Inspect the complete diff and untracked files.

## Workspace Hygiene

- Pre-existing worktree state: Dirty `main` at `0fe78f4`; ten tracked workflow files modified; `.agents/skills/show-me/` and the prior task records untracked.
- New durable files expected from this task: `templates/DEVELOPMENT.template.md`, minimal-example `DEVELOPMENT.md`, this task contract, and its review.
- Rebuildable or temporary output expected from this task: A temporary initialization simulation outside the repository.
- Task-end cleanup or retention decision: Remove the temporary simulation automatically; preserve all deliberate templates, examples, and task records.

## Approval-Required Situations

- Scope expands beyond the listed files.
- A new Skill, workflow, dependency, script, automation, or remote operation is proposed.
- Existing user work must be deleted, overwritten incompatibly, committed, or cleaned.
- A Demo, commit, Skill installation, or external write would occur without recorded user authorization.

## Owning Task Or Addendum

- Primary owning task: This task
- Related accepted behaviours affected: `2026-09-09-source-evidence-risk-delivery-gates`; its source, risk, authorization, and review behaviour must remain intact.
- Cross-task bugs or repairs: None known.
- Required addendum before acceptance: None; this is a separately authorized additive refinement.

## Assumptions

- The user's customary conversation language should be inferred from the active conversation, with explicit user or project language requirements taking precedence.
- Static contract checks and a temporary forward simulation are sufficient because the repository contains workflow documentation rather than application runtime code.
- Checkpoint commits are a project behaviour being documented; this task itself has no commit authorization.

## Working Hypotheses

- None.

## Open Questions

- None blocking.

## Status

Contract: Accepted; Execution: Paused; Acceptance: Pending QA
