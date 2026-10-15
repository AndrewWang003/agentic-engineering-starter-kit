# Portable Project Factory Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use `superpowers:executing-plans` to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Turn this repository into a source kit that any Agent can use to initialize a separate, self-contained project governed by Agentic Engineering SYS.

**Architecture:** Keep the existing three core workflows. Make source-kit bootstrap intent explicit in root guidance, extend `start-project` to generate a complete local governance package, and record the copied system in a concise generated manifest. The generated project remains independent: it carries local Skills and templates but no historical source-kit material or automatic update link.

**Tech Stack:** Markdown documentation, repository-local Skills, templates, shell-based validation, and Git inspection. No new dependency, script, plugin, runtime, service, or remote.

**Spec:** `docs/superpowers/specs/2026-09-19-portable-project-factory-design.md`

## Global Constraints

- Preserve exactly three core workflows: `start-project`, `start-task`, and `review-task`.
- Generated projects must use only their local `.agents/skills/` and templates for this system.
- Do not copy source-kit task history, examples, changelog, Git metadata, source paths, remotes, or uncommitted changes.
- Do not overwrite a non-empty destination or create a nested Git repository.
- Do not add scripts, dependencies, plugins, runtimes, remote services, automatic synchronization, or a new Skill.
- Keep all persistent project content in English.
- Do not create a Git commit; checkpoint commits are not authorized for this task.

## Review Focus

- Incomplete portable package: initialization must stop before writing a partial managed project when required source files are missing.
- Source-path leakage: generated instructions and manifest must not contain an absolute source-kit path.
- Historical leakage: generated foundation must not copy `tasks/` history, `examples/`, `CHANGELOG.md`, `.git/`, or source-kit working-tree changes.
- Fresh-Agent discoverability: an Agent opening only the managed project must find its local rules, local Skills, templates, state files, and next task entrypoint.
- Upgrade safety: a later source-kit version must require an explicit managed-project task rather than silently changing the instance.

### Task 1: Define the portable managed-project identity

**Files:**
- Create: `templates/AGENTIC_ENGINEERING.template.md`
- Modify: `templates/AGENTS.template.md`
- Modify: `AGENTS.md`
- Modify: `README.md`

**Interfaces:**
- Consumes: the source-kit and managed-project definitions in `docs/superpowers/specs/2026-09-19-portable-project-factory-design.md`.
- Produces: a source-kit bootstrap declaration and a generated-project manifest contract used by `start-project`.

- [ ] **Step 1: Write the failing static contract check**

Run:

```bash
test -f templates/AGENTIC_ENGINEERING.template.md
rg -n 'Bootstrap Agent|source kit|managed instance|local `.agents/skills`|explicit task' \
  AGENTS.md README.md templates/AGENTS.template.md templates/AGENTIC_ENGINEERING.template.md
```

Expected: FAIL because the manifest template and the required bootstrap or managed-instance wording do not yet exist everywhere.

- [ ] **Step 2: Add the smallest source and managed-project contracts**

Add `templates/AGENTIC_ENGINEERING.template.md` with these fields:

```markdown
# Agentic Engineering System

## Instance Identity

- System: Agentic Engineering SYS
- Instance type: Managed project
- Source-kit identity: Status: Recorded at initialization
- Source-kit version or commit: Status: Recorded at initialization

## Local Workflow

- Canonical project rules: `AGENTS.md`
- Canonical local Skills: `.agents/skills/`
- Canonical templates: `templates/`
- Project state: `PROJECT.md` and `DEVELOPMENT.md`
- Task records: `tasks/`

## Upgrade Policy

Do not synchronize from a source kit automatically. Adopt a later system version only through an approved task in this project that records the proposed source identity, affected files, validation, and acceptance result.
```

Add a concise source-kit role and Bootstrap Agent reading order to root `AGENTS.md` and README. Add generated-project instructions to `templates/AGENTS.template.md` requiring an Agent to read local rules and the applicable local Skill before matching work.

- [ ] **Step 3: Re-run the static contract check**

Run the command from Step 1.

Expected: PASS; all four files exist and describe source-kit bootstrap, local-only operation, managed-instance identity, and explicit upgrades.

- [ ] **Step 4: Inspect scope and formatting**

Run:

```bash
git diff --check -- AGENTS.md README.md templates/AGENTS.template.md templates/AGENTIC_ENGINEERING.template.md
```

Expected: PASS with no whitespace errors. Do not commit.

### Task 2: Make `start-project` create a complete portable foundation

**Files:**
- Modify: `.agents/skills/start-project/SKILL.md`
- Modify: `templates/PROJECT.template.md` only if a concise managed-instance link is needed for generated-project consistency

**Interfaces:**
- Consumes: the manifest and generated-agent contract from Task 1.
- Produces: an exact portable component inventory, preflight failure condition, copy rules, generated manifest fields, and post-creation validation requirements.

- [ ] **Step 1: Write the failing initialization-contract check**

Run:

```bash
rg -n 'AGENTIC_ENGINEERING.md|portable package|validate.*required|templates/|\.agents/skills/|do not copy.*tasks|do not.*synchronize' \
  .agents/skills/start-project/SKILL.md
```

Expected: FAIL because the existing initialization phase does not yet require the complete portable package, source preflight, exclusion list, manifest, or explicit upgrade boundary.

- [ ] **Step 2: Add precise initialization and validation instructions**

Extend `start-project` Phase 5 so it:

```text
1. Verifies every required source template, local Skill directory, Skill metadata file, and referenced local file before destination writes.
2. Creates AGENTIC_ENGINEERING.md from its template and fills source-kit identity or commit when available.
3. Copies the complete templates directory and the complete local Skill set, including references and metadata.
4. Copies no source tasks, examples, changelog, Git metadata, source paths, remotes, or working-tree content.
5. Validates the managed-project file inventory, local-only references, and copied local Skills after creation.
6. Preserves existing destination, Git, remote, approval, and first-task boundaries.
```

Use the exact Skill inventory from the design: `grill-me`, `grill-mode`, `to-spec`, `qa-planning-checkpoint`, `show-me`, `start-project`, `start-task`, and `review-task`.

- [ ] **Step 3: Re-run the initialization-contract check**

Run the command from Step 1.

Expected: PASS; the Skills document all required portable creation and safety conditions.

- [ ] **Step 4: Validate the edited Skill structure**

Run:

```bash
python3 /Users/myclaws/.codex/skills/.system/skill-creator/scripts/quick_validate.py .agents/skills/start-project
git diff --check -- .agents/skills/start-project/SKILL.md templates/PROJECT.template.md
```

Expected: both commands PASS. Do not commit.

### Task 3: Provide a reproducible portable-foundation example and verify it end-to-end

**Files:**
- Modify: `examples/minimal-example/AGENTS.md`
- Modify: `examples/minimal-example/README.md`
- Create: `examples/minimal-example/AGENTIC_ENGINEERING.md`
- Create: `examples/minimal-example/templates/AGENTIC_ENGINEERING.template.md`
- Create: `examples/regression-tests/portable-project-factory.md`
- Modify: `DEVELOPMENT.md`
- Modify: `CHANGELOG.md`
- Modify: `tasks/2026-09-19-portable-project-factory/TASK.md`
- Create: `tasks/2026-09-19-portable-project-factory/REVIEW.md`

**Interfaces:**
- Consumes: Task 1's source and managed-project contracts and Task 2's initialization inventory.
- Produces: a small inspectable managed-project example, a regression scenario, current project status, and review evidence.

- [ ] **Step 1: Write the failing portable-example check**

Run:

```bash
test -f examples/minimal-example/AGENTIC_ENGINEERING.md
test -f examples/minimal-example/templates/AGENTIC_ENGINEERING.template.md
rg -n 'managed project|local `.agents/skills`|explicit task|source-kit' \
  examples/minimal-example/AGENTIC_ENGINEERING.md examples/minimal-example/AGENTS.md examples/minimal-example/README.md
test -f examples/regression-tests/portable-project-factory.md
```

Expected: FAIL because the portable manifest and regression scenario do not yet exist.

- [ ] **Step 2: Add the smallest representative example and regression scenario**

Create the manifest and its template in the minimal example. Update its AGENTS and README to describe the project as a self-contained managed instance and point to its local workflow location. Create a regression scenario that asks a fresh Agent to initialize a project from this source kit and checks the complete portable inventory, absence of prohibited copied content, and explicit upgrade requirement.

- [ ] **Step 3: Re-run the portable-example check**

Run the command from Step 1.

Expected: PASS; the minimal example and regression scenario demonstrate the portable contract.

- [ ] **Step 4: Run a temporary independent forward simulation**

Run:

```bash
sim_dir=$(mktemp -d /private/tmp/agentic-engineering-sim.XXXXXX)
mkdir -p "$sim_dir/.agents" "$sim_dir/templates" "$sim_dir/tasks"
cp -R .agents/skills "$sim_dir/.agents/skills"
cp templates/*.template.md "$sim_dir/templates/"
cp templates/AGENTIC_ENGINEERING.template.md "$sim_dir/AGENTIC_ENGINEERING.md"
cp templates/AGENTS.template.md "$sim_dir/AGENTS.md"
cp templates/PROJECT.template.md "$sim_dir/PROJECT.md"
cp templates/DEVELOPMENT.template.md "$sim_dir/DEVELOPMENT.md"
touch "$sim_dir/tasks/.gitkeep"
test -f "$sim_dir/AGENTIC_ENGINEERING.md"
test -d "$sim_dir/.agents/skills/start-project"
test -f "$sim_dir/.agents/skills/start-task/references/unknowns-first-workflow.md"
test -d "$sim_dir/templates"
test ! -e "$sim_dir/.git"
test ! -e "$sim_dir/CHANGELOG.md"
test ! -d "$sim_dir/examples"
rm -rf "$sim_dir"
```

Expected: PASS; the temporary project contains the portable system and no prohibited historical or Git content. The final removal applies only to the validated temporary directory created by `mktemp`.

- [ ] **Step 5: Run full repository checks and record evidence**

Run:

```bash
for skill_dir in .agents/skills/*; do
  python3 /Users/myclaws/.codex/skills/.system/skill-creator/scripts/quick_validate.py "$skill_dir" || exit 1
done
ruby -e 'require "yaml"; Dir[".agents/skills/*/agents/openai.yaml"].sort.each { |f| YAML.load_file(f) }'
find . -name '*.md' -type f -print0 | xargs -0 awk '/[ \t]+$/ { print FILENAME ":" FNR; bad=1 } END { exit bad }'
git diff --check
```

Expected: PASS. Update `DEVELOPMENT.md`, the task contract, and review report with exact evidence and any limitations. Do not commit.

## Plan Self-Review

- Spec coverage: Task 1 implements source-kit discovery, managed identity, local-only governance, and upgrades. Task 2 implements portable initialization and incomplete-source safety. Task 3 covers an inspectable example, regression scenario, independent simulation, exclusions, and evidence recording.
- Placeholder scan: No `TBD`, `TODO`, unspecified test, or deferred implementation language is present.
- Interface consistency: Task 1 produces `AGENTIC_ENGINEERING.md`, a source-kit bootstrap declaration, and generated-agent local-skill rules. Task 2 consumes and creates those exact files. Task 3 verifies the same inventory and wording.
- Review focus coverage: Task 2 owns incomplete-package and source-path checks; Task 3 owns historical leakage, fresh-Agent discoverability, and upgrade safety checks.

## Execution Handoff

The user authorized modification after plan creation. Review this plan against the approved design before implementation. Execute natively in this session because the three tasks share one evolving documentation and workflow interface, and no independent implementation stream exists.
