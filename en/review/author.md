# Guide for PR authors

[Tiếng Việt](../../vi/review/author.md)

Goal: a reviewer can understand and decide in one sitting.

## Before you open the PR

1. Read your own diff as a stranger. Remove debug leftovers, junk files, commented-out code.
2. Run that repo's local tests and linters.
3. Ship **tests for the new behavior in this same PR**. A follow-up “I’ll add tests later” is not a PR. Test-only PRs are fine. Foundation PRs test what they introduce (types, schema, stubs), not the consumer that does not exist yet.
4. Finish the description *before* you request review ([template](../../templates/PULL_REQUEST_TEMPLATE.md)).
5. If the PR is larger than ~400 net lines (ignore lockfiles, generated code, whole-file deletes) — split. Reviewers may bounce a PR for size alone.

"Small enough" means **one idea**, reviewable in 15–25 minutes. ~100 lines is usually fine; ~1000 usually is not. File count counts: 200 lines in one file is not the same as 200 lines across 40 files.

These numbers are heuristics for every language. Generated protobufs, lockfiles, and snapshots do not use the same budget as logic you wrote by hand.

## The description must answer

- **What** (1–3 sentences).
- **Why** (bug, constraint, issue link).
- **What you deliberately did not do**.
- **How to verify** (commands, cases, screenshot if UI).
- **Risk and rollback**.

### First line

The first line must stand alone in `git log`. Write it as an action the change performs, not a label for a phase of work. Body may add Why; the first line must still make sense with the body deleted.

| Avoid | Prefer |
|-------|--------|
| Fix bug | Reject revoked refresh tokens after logout |
| Update | Read timeout from config instead of a constant |
| Phase 1 / WIP | Add `BlobStore` trait; caller lands in the next PR |
| as discussed | Delete the unused `parse_header` export |

"Fix bug", "Update", "Phase 1", "WIP", "as discussed" are not descriptions.

## Reviewers

Pick someone who *owns that area of the code*, not "whoever is online".  
One primary reviewer is enough for a normal PR. Add a second when you touch a public API, security, money, or a data migration.

Solo: [solo.md](../solo.md).

## When comments arrive

Follow [handling comments](handling-comments.md). Short version: fix the code; do not win the thread.

## Must not

- Mix a repo-wide formatter sweep with a feature.
- "While I am here" edits in unrelated areas.
- Pressure for approval because of a self-imposed deadline. Hard deadlines: [emergencies.md](../emergencies.md).
- Leave the default branch unbuildable between stacked PRs. See [git.md](../git.md#do-not-break-the-build-between-stacked-prs).
