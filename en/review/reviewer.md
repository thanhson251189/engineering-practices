# Guide for reviewers

[Tiếng Việt](../../vi/review/reviewer.md)

Job: protect code health. You are not here to rewrite the PR in your style.

Language-independent. Do not demand idioms from a language you prefer if this repo is written in another.

## Look at things in this order

1. **Design** — right place in the system? Right layer? Dead branches or premature abstraction?
2. **Behavior** — does it do what the author claims? Is that good for users of this code?
3. **Complexity** — can it be simpler? Can a stranger read it?
4. **Tests** — do they cover the new behavior? Are they brittle / testing internals?
5. **Names** — the name should carry the job.
6. **Comments / docs** — why, not what. User-facing or API contract updated?
7. **Style** — let machines catch it. Comment on style only when the linter missed it or the change breaks consistency in the files being edited.

Read **every line** you were asked to review. Read file context, not only the green/red hunks.

## Approval bar

Approve when the PR **improves code health**, not when you have run out of nits.

Prefix `Nit:` for polish.  
Prefix `Blocking:` when merge is not allowed until it is fixed (use sparingly).

Praise what is done well — review is also mentoring.

## Speed

- Not in flow → review soon.
- First response within one business day.
- Too large → ask for a split; do not rubber-stamp.
- Time zones: try to comment before the author starts their next workday.

Approve with open comments when:

- you trust the author to handle the rest, or
- the comments are optional, or
- they are tiny (imports, typo, unused dep).

Say which items are required.

## Must not

- Force a design change because of preference.
- Review on behalf of CI: if required tests/lint are red, send it back before going deep.
- Sit on a PR because you have not had the conversation yet. Escalate: author ↔ reviewer → module owner → lead. PRs must not stall.
