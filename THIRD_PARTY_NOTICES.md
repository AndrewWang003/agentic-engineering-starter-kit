# Third-Party Notices

This kit adapts ideas from the projects below. The adapted text was rewritten for this kit; it is not a copy of the original files.

## mattpocock/skills

- Source: https://github.com/mattpocock/skills (last compared at commit `49dd158`, 2026-10-09)
- Also published as AIHero's Main Flow: https://www.aihero.dev/skills
- Licence: MIT (full notice below)
- Adapted in this kit:
  - `.agents/skills/grill-me/` (including `references/interview-rounds.md`) — from `grill-me` and `grilling`
  - `.agents/skills/grill-mode/` — from `grill-with-docs`
  - `.agents/skills/to-spec/` — from `to-spec`
  - Practices in `start-task`, `start-project`, `qa-planning-checkpoint` and `review-task` — from `to-tickets`, `implement`, `tdd`, `code-review` and `retro`
  - `.agents/skills/review-task/references/smell-baseline.md` — from the smell baseline in `code-review`
- What was changed: local files instead of an issue tracker, separate approval for the spec and for execution, risk and delivery gates, evidence rules, and a manual QA handoff. See the "Design Influence" section in `README.md` and `tasks/2026-10-15-upstream-skills-refresh/`.

```text
MIT License

Copyright (c) 2026 Matt Pocock

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Martin Fowler, *Refactoring* (2nd edition), chapter 3

The code smell names in `smell-baseline.md` come from this book. The short descriptions are written for this kit.

## Superpowers plugin

The files in `docs/superpowers/` are a design spec and a plan written during development with the Superpowers plugin's planning skills. They are records of how this kit was built, not part of the kit.
