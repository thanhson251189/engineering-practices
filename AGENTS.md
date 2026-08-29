# Agent contract

[Tiếng Việt](vi/AGENTS.md)

This file is the working agreement for **any coding agent** in a repo that adopts these practices. Humans still read the pages below. You must follow this file first.

English is the source of truth if translations drift.

## Load before you edit

1. [en/principles.md](en/principles.md)
2. [en/review/author.md](en/review/author.md)
3. [en/testing.md](en/testing.md)
4. [en/review/handling-comments.md](en/review/handling-comments.md)
5. One human on the repo? [en/solo.md](en/solo.md)

Do not invent a language style guide. Do not load Google's archived `eng-practices` as a substitute.

## Must

- One idea per PR. Split before you add a second concern.
- Tests for new behavior land in **the same diff**. “Tests in a follow-up” is not done.
- Description fills the product PR template: What, Why, out of scope, how to test, risk/rollback.
- First line of the description stands alone in `git log`. Not `Fix bug`, `Update`, `WIP`, `Phase 1`, `as discussed`.
- Do not mix a repo-wide format sweep or unrelated refactor with the feature.
- Do not leave unused public APIs as the finished state. Foundation PRs must name the consumer PR and must not rely on a permanently weakened CI check.
- Each stacked PR must build and pass required checks on its own.
- Prefer changing code over winning a review thread.

## Must not claim done

- Your own “LGTM” / “looks good”. That is not approval.
- Required CI red (tests, format, lint) in the **product** repo.
- Empty Why, or a title that is only a phase label.
- Files outside the idea of the PR.

## Stop and ask the human

- Public API, schema, wire format, or event contract.
- Secrets, credentials, prod data, destructive migration.
- Diff larger than ~400 net hand-written lines, or many files for one idea.
- You cannot explain Why in two sentences.
- Product CI command is unknown — do not guess a stack and “make it work”.

## Done means

1. Required product-repo checks are green, or you report exactly which command failed.
2. PR template sections are filled.
3. Diff contains only the stated idea.
4. New behavior has tests in this diff, or the description says why it cannot and why that is acceptable.

Product-repo `AGENTS.md` may add commands (test, lint, run). It must not weaken this file.
