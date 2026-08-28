# Git and change size

[Tiếng Việt](../vi/git.md)

## Branches

- Default branch stays shippable.
- Branches live a few days. Suggested prefixes: `feat/`, `fix/`, `refactor/`, `chore/`, `hotfix/`.
- One branch ≈ one PR ≈ one idea.

## Commits

Conventional Commits are optional and language-agnostic:

```
feat(auth): reject revoked refresh tokens
fix(api): do not return 500 when field X is missing
```

First line is a complete sentence for `git log`.  
Squash on merge if the branch history is noisy — pick once for the team and record it here.

## Oversized PRs

Reviewers may reject on size alone.

Ways to split (any language):

- **Stack:** foundation PR (types, stubs, schema) → consumer PR.
- **By layer:** contract first, implementation second.
- **By vertical slice:** one use-case through the stack, then the next.
- Refactor first so the feature PR stays thin.

Do not fake-split: five PRs that cannot merge independently, with a red build in the middle of the chain.

## Stacked PRs and unused APIs

Principle 5 forbids leaving unused public APIs as the **finished** state of the work. It does not forbid a foundation PR.

A new API (or stub, type, trait, exported function) may land with no in-repo caller yet when **all** of these hold:

1. The PR description names the follow-up PR that will call it (link or title).
2. Required CI is configured so unused-item / dead-code warnings do not fail **this** foundation PR. How you do that is per language (visibility narrower than public, allow-list for that crate/package, keep the symbol unexported until the consumer exists). Do not weaken the check on the default branch forever.
3. The follow-up lands before the API is treated as a stable contract.

If the consumer is dropped, revert or delete the unused API in the next change. Do not let it sit.

## Generated files

Lockfiles, codegen, snapshots: say so in the description. Reviewers need not read every generated line if the tool is trusted; they must still understand *why* it was regenerated.
