# Project Initialization

Phase 5 of `start-project`. Read this only after the project summary is approved and the destination is confirmed in Phase 4.

## Validate The Source Kit And Create The Foundation

Before writing the destination, validate that this source kit contains the complete portable set:

- `templates/AGENTIC_ENGINEERING.template.md`
- `templates/AGENTS.template.md`
- `templates/DEVELOPMENT.template.md`
- `templates/PROJECT.template.md`
- `templates/REVIEW.template.md`
- the local Skill directories `grill-me`, `grill-mode`, `to-spec`, `qa-planning-checkpoint`, `show-me`, `start-project`, `start-task`, and `review-task`;
- every local Skill metadata file and every file under each Skill's `references/` directory, including `grill-me/references/interview-rounds.md`, `start-project/references/initialization.md`, `start-task/references/execution-controls.md`, `start-task/references/unknowns-first-workflow.md`, and `review-task/references/smell-baseline.md`.

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

## Establish The Git Baseline

After the foundation is created:

1. Inspect whether the destination is already inside a Git worktree and record existing changes before any Git action.
2. When the approved initialization summary authorizes it and the destination is an independent non-repository directory, run `git init`. Otherwise preserve the existing repository or the user's decision to remain without Git.
3. Run the available foundation checks before creating a commit.
4. When the same approval authorizes an initial checkpoint commit, Git identity is usable, and only intended foundation files are included, create a commit such as `chore: initialize project foundation` and record its hash.
5. If Git initialization or commit creation is unavailable, preserve the initialized files and report the exact limitation instead of claiming a recovery point exists.

Do not create a remote, push, publish, or place secrets in version control without separate user authorization. A remote backup may be recommended, especially for important projects, but local Git remains a valid starting state.
