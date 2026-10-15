# Task Contract

## Task ID And Name

2026-09-18-risk-adaptive-autonomy — Reduce unnecessary workflow confirmation gates

## Task State And Authorization

- Contract: Accepted
- Execution: Paused
- Acceptance: Accepted
- Acceptance authority: Agent
- Authorized slice or scope: Refine the existing task and review workflows so safe work proceeds without repeated confirmation, while preserving explicit gates for consequential decisions.
- Next gate before implementation or continuation: None; task accepted under delegated Agent acceptance authority

The user approved the audited risk-adaptive autonomy design and explicitly asked Codex to implement it.

## Risk And Delivery Profile

- Risk tier: Medium
- Risk drivers: Persistent workflow behaviour changes across repository-local Skills, templates, and user guidance; no application runtime or production system is changed.
- Base state: `main` at `0fe78f406d95eb9989cf507eac03579c1faac5bf` with the intentional overlapping workflow changes and task records shown by `git status --short --ignored`.
- Isolation: Existing working tree retained because this task extends the same uncommitted workflow files; a new worktree would omit or complicate those changes.
- Security validation triggers: None beyond preserving existing authority, destructive-action, external-write, and validation-integrity boundaries.
- Delivery method: Reviewable local diff and task review; no remote is configured.
- Repair and stop conditions: Stop for scope expansion, destructive cleanup, a new Skill/workflow/dependency/runtime, conflict with authoritative task state, repeated validation failure without new evidence, or inability to distinguish this task's changes safely.

## Checkpoint Commit Policy

- Checkpoint commits: Not authorized
- Commit boundary: Verified task completion remains uncommitted for user review
- Base branch and commit: `main` at `0fe78f406d95eb9989cf507eac03579c1faac5bf`
- Relevant pre-existing changes: Existing workflow edits, untracked local Skills and task records, and two earlier tasks at `Pending QA`
- Commit-message convention: Not applicable

## Background

The current workflow already permits small low-risk work to proceed directly and permits an authorized medium task to implement, test, repair, and review without per-step approval. A RED pressure test confirmed both behaviours. The material automation gap is final acceptance: current `review-task` unconditionally leaves every reviewed task at `Pending QA`, even when all acceptance criteria are deterministic, executable, and directly observable by Codex.

## User Value

Routine development can complete without unnecessary user confirmation, while product judgment, unobserved behaviour, high-risk actions, scope changes, and destructive or external effects remain human-controlled.

## Confirmed Facts

- Small, clear, low-risk work already proceeds without a task contract or extra approval.
- Once a medium task is accepted and execution is authorized, current guidance already permits autonomous in-scope implementation, repair, validation, task updates, and review.
- Current `review-task` requires `Acceptance: Pending QA` after review without distinguishing fully automated acceptance from behaviour that needs human judgment.
- Existing guidance does not yet state an explicit acceptance authority in the task contract.
- Existing checkpoint and dirty-worktree rules already prevent unsafe automatic commits.

## Source And Evidence Intake

| Source And Version | Format And Reader | Useful Locator | Extracted Claim | Confidence Or Conflict | Intended Use |
| --- | --- | --- | --- | --- | --- |
| User-approved design in the active conversation, 2026-09-18 | Conversation, direct reading | Approval following the risk-adaptive autonomy audit | Move toward autonomous development while retaining consequential human gates | High; governing user instruction | Scope and authorization |
| `development log.md`, current working-tree version | Markdown, direct reading | 2026-07-14 routing and initialization corrections | Agents should resolve routine routing, but new-project creation needs consequential approval | High | Preserve proven gates |
| Prior task reviews, current working-tree versions | Markdown, direct reading | Remaining risks and lessons learned | Dirty overlapping work limits automatic commits; observability and destructive cleanup require explicit boundaries | High | Define safe autonomy limits |
| DeepMind paper `Advancing Mathematics Research with AI-Driven Formal Proof Search`, arXiv:2605.22763v1 | Native web text | Sections 2, 5, Appendix A | Generate-verify-repair loops work when validation and integrity checks are native to execution | High for the formal-proof system; software adaptation is an interpretation | Design evidence only |

- Duplicate or superseded sources: The video transcript and earlier AI summary describe the same paper; the paper is the primary source.
- Consequential interpretation requiring user confirmation: Resolved by the user's approval of the audited design.
- Embedded instructions or executable content: None treated as authority.

## Goal

Make task autonomy risk-adaptive and acceptance-aware without adding a new workflow, Skill, dependency, script, runtime, or multi-agent system.

## Expected Behaviour

- Preserve direct execution for small, clear, low-risk work.
- Preserve one bundled approval for a medium task's contract, execution scope, and checkpoint policy rather than requiring separate user interactions.
- Once execution is authorized, do not re-request approval for ordinary in-scope implementation, repair, validation, review, state updates, or authorized checkpoints.
- Record whether final acceptance authority belongs to Codex or the user.
- Permit Agent acceptance only when every acceptance criterion can be reliably executed and observed, all required validation passes, review has no unresolved actionable findings, and the contract delegates acceptance authority.
- Keep acceptance at `Pending QA` when human judgment, product experience, real credentials/devices/data, production observation, or any material observability gap remains.
- Reject false-green validation caused by weakened tests, fixtures, snapshots, mocks, expected outputs, filters, or validation configuration.

## Specification Summary

Add a compact acceptance-authority rule to `start-task`, `review-task`, and their templates. Clarify that user interaction may bundle logically separate approvals, and that authorized execution proceeds by exception rather than per-step confirmation. Add validation-integrity review without creating another workflow phase.

## Tool And Observability Readiness

- Install, development, and build commands: Not applicable
- Test commands: Skill pressure scenarios, `quick_validate.py`, YAML parsing, focused contract checks, Markdown checks, and `git diff --check`
- Test interface: Agent behaviour under controlled task scenarios plus the repository-local Skill and template interfaces
- Codex can execute the behaviour: Yes for read-only pressure scenarios and static workflow validation
- Codex can observe the outcome: Yes for agent decisions, file content, validation exit codes, and diff scope
- Required fixtures or services: Existing repository files only
- Relevant Skills: `start-task`, `qa-planning-checkpoint`, `review-task`, `superpowers:writing-skills`, `superpowers:test-driven-development`, `superpowers:verification-before-completion`
- Behaviour that will remain unverified: Use across unrelated real-world repositories and long-running production tasks

## Testing Interface

- Stable public behaviour or interface: The instructions and fields exposed by `start-task`, `review-task`, `AGENTS.md`, and the task/review templates.
- Comparable existing tests: Skill structure validation, YAML parsing, pressure-scenario behaviour, focused contract checks, and repository diff checks.

## Acceptance Scenarios

| Scenario | Given | When | Then | Priority |
| --- | --- | --- | --- | --- |
| Small work remains lightweight | A clear, local, reversible change has focused validation | Codex receives the request | It proceeds without a task contract or extra approval | P0 |
| Authorized execution stays autonomous | A medium task has accepted scope and authorized execution | An ordinary slice or in-scope repair is required | Codex continues without asking again and records material deviations | P0 |
| Fully observable work can finish autonomously | Every criterion is deterministic, executable, observed, and passing, with Agent acceptance authority | Review completes with no actionable findings | Acceptance becomes `Accepted` without a manual QA gate | P0 |
| Human judgment remains human-controlled | UX, product judgment, real environment, production observation, or another material gap remains | Review completes | Acceptance remains `Pending QA` with a focused handoff | P0 |
| False green is rejected | Tests or validation inputs are weakened to make a failure pass | Review inspects validation changes | The task is not accepted without evidence and authorized contract change | P0 |
| Consequential deviation pauses | Scope, behaviour, dependency, public interface, destructive action, production effect, or risk changes materially | Codex encounters the deviation | Execution pauses and requests the needed decision | P0 |
| Unsafe checkpoint is skipped | The worktree contains overlapping or unrelated changes | A slice passes | Codex records verified-but-uncommitted state instead of creating a misleading commit | P1 |

## Test Strategy

| Scenario | Validation Level | Command Or Check | Notes |
| --- | --- | --- | --- |
| Current autonomy baseline | Behaviour pressure test | Run fresh agents against current Skills before editing | RED should isolate actual gaps instead of assuming them |
| Revised autonomy and acceptance | Behaviour pressure test | Re-run the same scenarios with revised Skills | Agents must preserve safe autonomy and apply acceptance authority correctly |
| Validation integrity | Behaviour pressure test | Present a false-green scenario before and after the change | Review must reject weakened validation |
| Skill integrity | Automated validation | Run `quick_validate.py` for every local Skill | All Skills must validate |
| Metadata integrity | Automated validation | Parse every local `agents/openai.yaml` | All YAML must parse |
| Repository integrity | Static validation | Run focused contract checks, Markdown checks, and `git diff --check` | No contradictory wording or whitespace errors |

## Vertical Slices

| Slice | Complete Behaviour | Acceptance Criteria | Blocked By | Status | Checkpoint |
| --- | --- | --- | --- | --- | --- |
| 1. Autonomous acceptance | Fully observable tasks can finish under delegated Agent acceptance; human-dependent tasks remain pending | Acceptance authority and evidence conditions are explicit in live Skills and templates | RED baseline | Complete | Verified but not committed; commits not authorized |
| 2. Integrity and consistency | False greens remain rejected and public guidance matches the revised behaviour | Existing contract protections reject false greens; generated-project guidance and README remain consistent | Slice 1 | Complete | Verified but not committed; commits not authorized |
| 3. Review and validation | Revised behaviour survives pressure tests and repository checks | GREEN scenarios and all static validations pass | Slice 2 | Complete | Verified but not committed; commits not authorized |

## Allowed Scope

- `.agents/skills/start-task/SKILL.md`
- `.agents/skills/review-task/SKILL.md`
- `AGENTS.md` and `templates/AGENTS.template.md`
- `templates/TASK.template.md` and `templates/REVIEW.template.md`
- `PROJECT.md`, `README.md`, `DEVELOPMENT.md`, and `CHANGELOG.md`
- This task contract and its review record

## Forbidden Scope

- New workflow or Skill
- Changes to `start-project`, requirement-entry Skills, or QA-planning behaviour unless a newly observed contradiction requires a separately approved addendum
- Dependencies, scripts, services, databases, background jobs, CI, or multi-agent orchestration
- Automatic production, release, push, remote, credential, destructive cleanup, or external-write actions
- Broad project-level blanket authorization that bypasses task scope or risk controls
- Committing existing or new work without explicit checkpoint authorization

## Acceptance Criteria

- Existing safe autonomy for Low and authorized Medium work is preserved.
- Acceptance authority is explicit and does not conflate automated evidence with human judgment.
- Agent acceptance requires complete executable and observable evidence plus a clean review.
- Human-dependent behaviour remains `Pending QA`.
- Validation-integrity review prevents false-green acceptance.
- Existing scope, risk, authorization, checkpoint, observability, and destructive-action gates remain intact.
- No new workflow, Skill, dependency, script, runtime, or orchestration layer is introduced.

## Required Validation

- Complete RED/GREEN pressure scenarios for the changed Skill behaviour.
- Validate all project-local Skills.
- Parse all project-local Skill YAML files.
- Run focused cross-file contract checks.
- Run Markdown and `git diff --check` validation.
- Inspect the full diff and all untracked files.

## Approval-Required Situations

- Scope expands beyond the listed files or changes another workflow's product behaviour.
- A dependency, script, runtime, service, new Skill, or new workflow is proposed.
- Existing user work must be deleted, incompatibly overwritten, committed, or cleaned.
- Acceptance authority would cover behaviour Codex cannot reliably execute and observe.
- Validation would be weakened, a public interface changed, or production/external state affected.

## Owning Task Or Addendum

- Primary owning task: This task
- Related accepted behaviours affected: `2026-09-09-source-evidence-risk-delivery-gates` and `2026-09-14-git-observability-demo-manual-qa`
- Cross-task bugs or repairs: None known
- Required addendum before acceptance: None; the user approved this additive refinement as a separate task

## Assumptions

- The user's approval covers the audited design and autonomous implementation inside the recorded scope.
- Checkpoint commits remain unauthorized because the user approved implementation but did not explicitly authorize commits.
- Agent acceptance is suitable for this documentation-only task only if the revised behaviour is exercised through fresh pressure scenarios and all repository checks pass.

## Working Hypotheses

- The current workflow already handles Low and authorized Medium autonomy correctly; the only baseline behaviour failure is unconditional manual acceptance.
- An explicit validation-integrity check may close a false-green loophole without adding a new workflow phase.

## Open Questions

- None blocking.

## Status

Contract: Accepted; Execution: Paused; Acceptance: Accepted
