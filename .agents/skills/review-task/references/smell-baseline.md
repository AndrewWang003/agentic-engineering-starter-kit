# Smell Baseline

A fixed set of code smells, adapted from Martin Fowler's *Refactoring* (chapter 3), for the `Project Standards` axis of `review-task`. It applies even when a repository documents no coding standards.

Two rules bind it:

- **The repository overrides.** A documented project standard always wins; where the project endorses something listed here, suppress the smell.
- **Always a judgement call.** Report each smell as a labelled heuristic ("possible Feature Envy"), never a hard violation, and skip anything tooling already enforces.

Each entry reads *what it is* → *how to fix*. Match it against the diff only:

- **Mysterious Name**: a name that does not reveal what something does or holds. → Rename it; if no honest name comes, the design is murky.
- **Duplicated Code**: the same logic shape in more than one hunk or file of the change. → Extract the shared shape and call it from both.
- **Feature Envy**: a function that reaches into another object's data more than its own. → Move it onto the data it envies.
- **Data Clumps**: the same few fields or parameters keep travelling together. → Bundle them into one type.
- **Primitive Obsession**: a primitive or string standing in for a domain concept. → Give the concept its own small type.
- **Repeated Switches**: the same conditional cascade on the same type recurs across the change. → Use polymorphism or one shared map.
- **Shotgun Surgery**: one logical change forces scattered edits across many files. → Gather what changes together into one module.
- **Divergent Change**: one module is edited for several unrelated reasons. → Split it so each module changes for one reason.
- **Speculative Generality**: abstractions, parameters, or hooks for needs the contract does not have. → Delete them until a real need appears.
- **Message Chains**: long navigation chains the caller should not depend on. → Hide the walk behind one method.
- **Middle Man**: a unit that mostly delegates onward. → Call the real target directly.
- **Refused Bequest**: a subtype that ignores or overrides most of what it inherits. → Replace inheritance with composition.
