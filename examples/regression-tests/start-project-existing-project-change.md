# Regression Test: start-project routes existing-project changes to start-task

## Input Condition

- A user invokes `start-project`.
- An existing repository is identified.
- The user describes an algorithm or feature improvement inside that repository.
- The user may provide observed repository facts and possible root-cause theories.

## Expected Result

- `start-project` identifies this as `Route B: Existing project change`.
- It does not create project files.
- It does not suggest a nested project foundation.
- It does not suggest a separate planning repository by default.
- It routes the user to `start-task`.
- It preserves repository facts separately from working hypotheses.

## Failure Result

- It continues new-project discovery.
- It asks where to create a project foundation.
- It treats a feature or algorithm improvement as a new project's first-version scope.
- It begins modifying the external repository.
- It records a suspected root cause as a confirmed fact.
