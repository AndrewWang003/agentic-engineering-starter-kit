# ae-project-bootstrap

Use this skill after a project contract has been approved and the user wants to create a new independent project repository.

## Goal

Create a minimal, file-based project structure that can support task-contract-driven development.

## Required Input

- Approved project contract
- Approved target path
- Approved first-phase scope

## Procedure

1. Inspect the target path.
2. Confirm the bootstrap will not overwrite existing work.
3. Create the project structure.
4. Add project-specific `AGENTS.md`, `README.md`, `PROJECT_CONTRACT.md`, logs, docs, task folders, and `.agentic-engineering/` metadata.
5. Mark unknowns explicitly instead of inventing decisions.
6. Propose the first task contract.

## Output

A bootstrapped project repository and a short bootstrap report.

## Stopping Condition

Stop when the repository structure exists, the project contract is present, open decisions are recorded, and the first task is proposed.

## Approval Boundary

Ask for approval before selecting a major stack, installing dependencies, creating services, or writing application code.

