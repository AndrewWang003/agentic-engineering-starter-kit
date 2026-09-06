# AGENTS.md

These instructions apply to the Codex Engineering Starter Kit repository.

## How Codex Should Work Here

- Inspect the repository before editing.
- Keep the kit lightweight and understandable.
- Prefer simple Markdown and small scripts over frameworks.
- Avoid adding infrastructure without clear evidence.
- Do not turn this kit into a multi-agent platform, runtime, workflow engine, database, or project management app.
- Maintain clear terminology: project foundation, task contract, task review.
- Run relevant checks before declaring completion.
- Report assumptions and unverified work.
- Do not add new rules based on one isolated incident.
- Maintain current project status in `DEVELOPMENT.md`.

## Workspace Hygiene

- At the start of a medium or large task, inspect `git status --short --ignored` and identify pre-existing changes, untracked files, and rebuildable output.
- Keep temporary scripts, scratch files, downloaded artifacts, and ad-hoc debugging output outside the repository. Do not leave them in the project root, source tree, or test tree.
- Keep dependencies, build output, coverage, test reports, screenshots, editor metadata, and system metadata out of version control through `.gitignore`.
- Preserve durable evidence only in a deliberate project location such as `docs/` or `tasks/evidence/`, with enough context to explain its purpose. Do not treat routine test output as durable evidence.
- Before committing, inspect every untracked file that would be added and remove or relocate temporary material. Do not delete user-created, contractual, architectural, fixture, or unknown files without approval.
- At task or release completion, identify rebuildable output that can be safely cleaned. Perform cleanup only with explicit approval when it deletes material from the workspace.

## Requirement Entry

- When a requirement is materially unclear, recommend `grill-me` for a file-free interview or `grill-with-docs` when project terminology and consequential decisions should be preserved.
- After shared understanding is confirmed, recommend `to-spec` to create a local project definition draft or task contract.
- Route the resulting specification to `start-project` for a new project or `start-task` for a change inside an existing project.
- Skip the requirement-entry skills when the request is already clear, small, and safe to execute directly.
- Keep requirement shaping separate from implementation and task review.

## QA Planning

- For behavior-changing tasks, use `qa-planning-checkpoint` before implementation when edge cases, acceptance scenarios, or validation strategy could change the correct solution.
- Keep the checkpoint lightweight: acceptance scenarios, test strategy, test interface, and one approval question when needed.
- Do not introduce Selenium, MCP, Java test generation, or any QA automation platform unless the user explicitly approves that scope.
- Skip the checkpoint for documentation-only, typo, static text, or other low-risk changes where normal validation is sufficient.

## Approval Required

Ask before:

- adding a dependency;
- adding scripts or automation;
- changing the three-workflow structure;
- introducing a new Skill;
- deleting user-created project material;
- expanding the kit beyond project start, task start, and task review.
