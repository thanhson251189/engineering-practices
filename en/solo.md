# Solo / one human

[Tiếng Việt](../vi/solo.md)

"Require 1 approval", "pick the owner of that area", and "respond within one business day" assume a second person. They do not run as written on a repo with one human who pushes to the default branch.

The rest of the guide still applies: small changes, floor vs approval bar, tests, docs, no fake splits.

## What replaces a second reviewer

1. **Self-review** using the [author checklist](review/author.md) before you merge. Read the diff as a stranger. Same size cap.
2. **An agent may review.** That is extra eyes, not an LGTM. It counts only after the change already passed size, required tests, and docs/contract updates. Do not treat "the model said LGTM" as approval.
3. Prefer a PR even when you will merge it yourself. The description is the record. Pushing straight to the default branch is allowed for tiny chore/fix work; it is not the default for behavior changes.

## What you must not do

- Invent a second approver (including an agent) to satisfy a branch-protection checkbox you do not have.
- Skip tests because nobody will look.
- Stack a foundation API and never land the consumer.

When a second human appears, switch to the team rules in [principles.md](principles.md) and [adopting.md](adopting.md) without rewriting this page.
