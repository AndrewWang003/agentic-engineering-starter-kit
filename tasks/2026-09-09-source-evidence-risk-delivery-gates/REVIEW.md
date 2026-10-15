# Task Review

## Task Summary

Added conditional source-and-evidence intake and risk-and-delivery controls to the existing Starter Kit task lifecycle without adding a workflow, Skill, dependency, runtime, or service.

## Files Changed

- `.agents/skills/start-task/SKILL.md`
- `.agents/skills/review-task/SKILL.md`
- `AGENTS.md`
- `templates/AGENTS.template.md`
- `templates/TASK.template.md`
- `templates/REVIEW.template.md`
- `PROJECT.md`
- `README.md`
- `DEVELOPMENT.md`
- `CHANGELOG.md`
- `tasks/2026-09-09-source-evidence-risk-delivery-gates/TASK.md`
- `tasks/2026-09-09-source-evidence-risk-delivery-gates/REVIEW.md`

## Review Baseline

- Reference or comparison: Working tree against `0fe78f406d95eb9989cf507eac03579c1faac5bf` on `main`, plus the initial `git status --short --ignored` captured in the task contract.
- Baseline confirmed: Yes for the repository HEAD and initial dirty-file inventory. Git cannot mechanically separate this task's edits from pre-existing edits in the same files, so the review treats the working-tree diff as a combined change and uses the task contract and patch record for task-specific attribution.

## Spec Fit

### Findings

- No actionable P0, P1, or P2 findings.
- Both authorized checkpoints are present in the live task and review Skills, project rules, generated-project agent template, task and review templates, README, project definition, continuity file, and changelog.
- No new core workflow, Skill, dependency, script, runtime, database, scanner, queue, or observability platform was added.

### Summary

The implementation fits the approved two-checkpoint design and preserves the lightweight three-workflow structure.

## Project Standards

### Findings

- No actionable P0, P1, or P2 findings.
- Existing pre-task edits and the untracked `show-me` Skill were preserved.
- Persistent content is English, Markdown-first, and organized within existing responsibilities.
- No HTML explanation artifact, temporary file, rebuildable output, dependency, or destructive cleanup was introduced.

### Summary

The change follows repository scope, authorization, hygiene, language, and lightweight-design rules.

## Acceptance Criteria Results

| Criterion | Result | Evidence |
| --- | --- | --- |
| Checkpoints are consistent across live skills, templates, rules, and README | Pass | Focused heading and terminology search across `.agents/skills`, templates, `AGENTS.md`, and `README.md` |
| External content remains evidence rather than authority | Pass | Authority rules in `AGENTS.md`, its template, `start-task`, `review-task`, and README |
| Source versions and useful locators are supported | Pass | Source-evidence workflow and task-template table include version, format reader, locator, confidence, and intended use |
| Consequential uncertainty has a human-review path | Pass | `start-task`, project rules, task template, and review template all cover low-confidence or conflicting evidence |
| Risk controls are proportional | Pass | `Low`, `Medium`, and `High` behaviours are defined; Low explicitly avoids mandatory worktrees, scanners, and pull requests |
| Security, repair-stop, and delivery controls are represented | Pass | Risk gate covers security triggers, repeated-failure stops, production prohibition, and human-controlled delivery |
| No infrastructure or workflow expansion | Pass | Full file inventory and diff inspection found only Markdown workflow and task-record changes |
| Project status and release notes are current | Pass | `DEVELOPMENT.md` and `CHANGELOG.md` describe both checkpoints |
| Repository validation passes | Pass | Eight Skill validations, five YAML parses, and `git diff --check` completed successfully |

## Acceptance Scenario Results

| Scenario | Result | Evidence |
| --- | --- | --- |
| Embedded instruction remains evidence | Pass | Explicit authority and embedded-content rules in live and generated project guidance |
| Consequential source claim is traceable | Pass | Source/version and medium-specific locator requirements plus task/review fields |
| Uncertain evidence is escalated | Pass | Human escalation is required when uncertainty or conflicts affect a consequential decision |
| Lightweight work stays lightweight | Pass | Low-risk path explicitly uses focused validation and avoids mandatory infrastructure |
| Higher-risk work gets stronger controls | Pass | Medium/high paths add base-state, isolation, broader checks, security, approval, and delivery controls |
| Failure loop terminates honestly | Pass | Repeated failure, conflicting evidence, failed quality gates, missing authority, and scope expansion are explicit stop conditions |

## Source And Evidence Review

- External artifacts materially affected the task: Yes. Three user-supplied architecture images shaped the two checkpoints.
- Source identity, version, and useful locators preserved: Partial by necessity. Filenames, diagram regions, and observed concepts are recorded; hashes and current disk versions could not be verified because all three supplied paths were unavailable during implementation.
- Extracted content kept separate from interpretation and authority: Yes. The task record distinguishes visible concepts, interpretation, user approval, and unverified file identity.
- Duplicate, conflicting, or low-confidence evidence handled: Yes. The first two images are recorded as visually duplicate without claiming byte identity. No material source conflict was found.
- Embedded instructions or executable content remained untrusted: Yes. Diagram text was used only as design evidence.

## Task State And Authorization Review

- Contract status: Accepted based on the user's approval of the previously presented two-checkpoint design.
- Execution authorization: Authorized and exercised only within the recorded scope.
- Acceptance status: Pending QA and user acceptance.
- Authorized slice or scope respected: Yes.
- Next gate: User review and acceptance of the combined working-tree result.

## Risk And Delivery Review

- Risk tier and drivers: Medium; persistent agent behaviour changed across multiple Markdown interfaces, with no runtime or production code.
- Base state and isolation appropriate: The dirty `main` base and commit were recorded. A new worktree would have excluded or complicated the overlapping pre-existing edits, so the existing working tree was retained.
- Triggered security validation completed or explicitly deferred: The untrusted-input control was statically verified. No dependency, credential, permission, sensitive-data, or network change triggered another security check.
- Repair loop stopped or escalated when required: No repeated implementation or validation failure occurred. Unavailable attachment paths were recorded as an evidence limitation instead of retried or concealed.
- Delivery and human-control requirements respected: Changes remain an uncommitted local diff for user review. No production action occurred; pull-request delivery is unavailable because no remote is configured.

## Owning Task Or Addendum Review

- Primary owning task: `2026-09-09-source-evidence-risk-delivery-gates`
- Cross-task repairs found: None.
- Owning contract or bounded addendum present: This task contract owns all new behaviour.

## Test Strategy Fit

- Planned validation covered: Yes. All static workflow scenarios, Skill validation, YAML parsing, whitespace validation, and diff inspection were completed.
- Deviations from planned validation: Attachment hashes and on-disk versions could not be checked because the supplied download paths were no longer available.
- Untested high-risk scenarios: No high-risk runtime behaviour was introduced. Real-world forward testing in a separate project remains unverified.

## Commands And Tests Run

| Command or Check | Result | Notes |
| --- | --- | --- |
| Initial `git status --short --ignored`, branch, and HEAD inspection | Pass | Recorded dirty `main` baseline at `0fe78f4` and preserved pre-existing work |
| `quick_validate.py` over every `.agents/skills/*` directory | Pass | 8 of 8 Skills valid |
| Ruby YAML parse over every `.agents/skills/*/agents/openai.yaml` | Pass | 5 of 5 YAML files valid |
| `git diff --check` | Pass | No whitespace errors |
| Focused cross-file terminology and heading search | Pass | Both checkpoints and their key safety rules are represented across required surfaces |
| Full working-tree diff and file inventory inspection | Pass | No unexpected dependency, script, runtime, HTML, or generated output introduced |
| SHA-256 and metadata checks for the three supplied images | Not run | All three supplied paths returned `No such file or directory`; limitation recorded in the task contract |

## Unverified Areas

- The checkpoints have not yet been forward-tested on a separate real project.
- Attachment byte identity, metadata, and hashes remain unverified.
- Pull-request delivery cannot be tested until a Git remote exists.

## Scope Deviations

- None.

## Remaining Risks

- The combined diff includes pre-existing work in the same files, so task-only attribution depends on the recorded starting state rather than a clean Git delta.
- Future use will require judgment about when evidence is consequential and when Medium/High isolation is practical; the workflow deliberately avoids a rigid scoring system.

## Lessons Learned

- The new source-evidence rule exposed a real limitation immediately: a displayed attachment can remain understandable in conversation after its filesystem path becomes unavailable, so version confidence and content confidence must be recorded separately.
- Conditional checkpoints preserve useful production discipline without recreating the infrastructure-heavy system the project previously removed.

## Suggested Project Rule Changes

- Implemented in this task: source authority and provenance rules plus proportional risk, security, repair-stop, and delivery controls.

## Possible Future Reusable Workflow

- None. These controls belong inside the existing task lifecycle; a separate Skill is not justified.

## Final Status

Pending user acceptance. Automated and static checks pass; the documented evidence limitations remain non-blocking for this Markdown workflow change.
