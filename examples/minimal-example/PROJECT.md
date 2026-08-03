# PROJECT.md

## Project Purpose

Create a tiny local note cleanup helper.

## Problem

Short notes often contain messy spacing, inconsistent headings, and unfinished bullets.

## Target User

A single user cleaning up personal notes.

## First-Version Scope

Accept pasted Markdown and return cleaner Markdown.

## Inputs

- Pasted Markdown text.

## Outputs

- Cleaned Markdown text.

## Constraints

- Keep it local.
- Do not require a database.

## Non-Goals

- Syncing notes.
- User accounts.
- Mobile app.

## Success Criteria

- A sample messy note becomes easier to read without losing content.

## Confirmed Decisions

- Markdown is the input and output format.

## Key Terms

- `Messy note`: Markdown whose formatting is inconsistent but whose content must be preserved.
- `Cleaned Markdown`: normalized formatting with no intentional content removed.

## Assumptions

- A simple script or local interface is enough for the first version.

## Open Questions

- Preferred interface is not decided.

## Deferred Decisions

- File watching and folder sync.
