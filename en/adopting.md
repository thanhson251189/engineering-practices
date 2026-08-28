# Adopt these rules in a product repo

[Tiếng Việt](../vi/adopting.md)

This practices repo only matters when it is **wired into the place people open PRs**.

Stack-agnostic. Same steps for Go, TypeScript, Python, Java, or mixed repos.

## Minimum, one session

1. Copy `templates/PULL_REQUEST_TEMPLATE.md` → product repo `.github/PULL_REQUEST_TEMPLATE.md`.
2. Require 1 approval on PRs to the default branch.
3. Required CI must be green (tests + lint/format).
4. Link this practices repo from the product README and the PR template.
5. Turn on a formatter and linter with auto-format. Remove indent debates from review.
6. If ownership is clear, copy `templates/CODEOWNERS.example`.

## Do not do in week one

- Twenty language-specific style files.
- Conventional Commits + squash + rebase + signed commits all at once.
- 90% coverage.
- Two reviewers on every PR.

Add a rule when the same class of mistake happens ≥ 2 times. Do not add a rule because Google has one.

## Review this practices repo itself

Change rules by PR. First line of the description: why the old rule failed.  
Update **en/** and **vi/** together.  
A rule unused for 60 days → delete it or demote it to Nit.
