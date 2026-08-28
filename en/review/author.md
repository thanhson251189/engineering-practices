# Guide for PR authors

[Tiếng Việt](../../vi/review/author.md)

Goal: a reviewer can understand and decide in one sitting.

## Before you open the PR

1. Read your own diff as a stranger. Remove debug leftovers, junk files, commented-out code.
2. Run that repo's local tests and linters.
3. Finish the description *before* you request review ([template](../../templates/PULL_REQUEST_TEMPLATE.md)).
4. If the PR is larger than ~400 net lines (ignore lockfiles, generated code, whole-file deletes) — split. Reviewers may bounce a PR for size alone.

"Small enough" means **one idea**, reviewable in 15–25 minutes. ~100 lines is usually fine; ~1000 usually is not. File count counts: 200 lines in one file is not the same as 200 lines across 40 files.

These numbers are heuristics for every language. Generated protobufs, lockfiles, and snapshots do not use the same budget as logic you wrote by hand.

## The description must answer

- **What** (1–3 sentences; the first line is the summary).
- **Why** (bug, constraint, issue link). Not "update code".
- **What you deliberately did not do**.
- **How to verify** (commands, cases, screenshot if UI).
- **Risk and rollback**.

## Reviewers

Pick someone who *owns that area of the code*, not "whoever is online".  
One primary reviewer is enough for a normal PR. Add a second when you touch a public API, security, money, or a data migration.

## When comments arrive

- Fix or explain. Do not ignore in silence.
- You are not required to take every Nit.
- Same disagreement after two rounds → 10–15 minute call, write the conclusion on the PR, move on.
- After you push, reply "done" on resolved comments so the reviewer does not guess.

## Must not

- Mix a repo-wide formatter sweep with a feature.
- "While I am here" edits in unrelated areas.
- Pressure for approval because of a self-imposed deadline. Hard deadlines: [emergencies.md](../emergencies.md).
