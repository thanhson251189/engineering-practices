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

## Generated files

Lockfiles, codegen, snapshots: say so in the description. Reviewers need not read every generated line if the tool is trusted; they must still understand *why* it was regenerated.
