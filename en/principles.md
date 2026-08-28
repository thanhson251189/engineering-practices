# Principles

[Tiếng Việt](../vi/principles.md)

Priority order: a lower rule must not break a higher one.

Applies to every language and runtime. If a suggestion only works in one language, it does not belong here.

One human on the repo? Read [solo.md](solo.md). Principles 4's SLA and "pick an owner" do not apply as written.

## 1. Code health improves over time

**Floor:** a change must not make overall code health worse.  
**Approval bar:** reviewers **should approve** when the PR clearly improves health — easier to understand, safer to change, or less risky than yesterday — **even if it is not perfect**.

"Does not worsen" is not enough to treat as the goal. It is only the line you must not cross.  
Perfect PRs do not exist. Seek continuous improvement.  
Do not merge something that makes the codebase worse — except an [emergency](emergencies.md).

## 2. Facts beat preference

- Argue with behavior, risk, data, and design principles.
- Pure taste that the formatter does not enforce → the author's preference wins, unless it breaks consistency already present in that file.
- Design is almost never preference. If several approaches are sound, the author chooses. Reviewers must not force a rewrite because "I usually write it the other way."

## 3. One PR, one idea

A PR must be self-contained: the reviewer can see *why* and *what is affected* without reading four other PRs (unless the stack is named in the description).

Split:

- refactor from feature / bugfix
- schema / API contract from consumers when they can merge independently
- config / flags from implementation when rollback must be independent

Stacked foundation PRs: see [git.md](git.md#stacked-prs-and-unused-apis).

## 4. Team speed beats individual speed

Applies when more than one human reviews. Solo: [solo.md](solo.md).

Slow review slows the whole team, encourages "just merge it", and kills cleanups.

- First review response within **one business day** (approval can come later).
- Do not interrupt a coding flow just to review; review at a breakpoint.
- You may **Approve** with leftover comments when you trust the author to finish them, or when they are Nits.

## 5. Default branch stays shippable

Every merge:

- must not fail required tests
- must not leave unused public APIs or dead flags **as the finished state of the work**
- must be reversible with revert or a flag

A foundation PR may land an API with no in-repo caller yet. That is not a dead API if the description names the follow-up PR and required CI is set so unused-item warnings do not fail *that* PR. Details: [git.md](git.md#stacked-prs-and-unused-apis).

## 6. Write for the person who edits this in six months

Clear names. Comments explain *why*. Update docs when user-facing behavior or an API contract changes.  
Do not implement "we might need this later."
