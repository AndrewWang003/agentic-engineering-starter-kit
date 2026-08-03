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
- Maintain functional changes in `development log.md`.

## Requirement Entry

- When a requirement is materially unclear, recommend `grill-me` for a file-free interview or `grill-with-docs` when project terminology and consequential decisions should be preserved.
- After shared understanding is confirmed, recommend `to-spec` to create a local project definition draft or task contract.
- Route the resulting specification to `start-project` for a new project or `start-task` for a change inside an existing project.
- Skip the requirement-entry skills when the request is already clear, small, and safe to execute directly.
- Keep requirement shaping separate from implementation and task review.

## Approval Required

Ask before:

- adding a dependency;
- adding scripts or automation;
- changing the three-workflow structure;
- introducing a new Skill;
- deleting user-created project material;
- expanding the kit beyond project start, task start, and task review.
