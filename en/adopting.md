# Adopt these rules in a product repo

[Tiếng Việt](../vi/adopting.md)

This practices repo only matters when it is **wired into the place people open PRs**. Until the product repo has a PR template and a required check, these pages are unread markdown.

Stack-agnostic. Same steps for any language.

One human? Do the template + CI + link first. Skip "1 approval" until a second person exists. See [solo.md](solo.md).

## Minimum, one session

1. Copy `templates/PULL_REQUEST_TEMPLATE.md` → product repo `.github/PULL_REQUEST_TEMPLATE.md`.
2. If two or more humans: require 1 approval on PRs to the default branch.
3. Required CI must be green (tests + lint/format).
4. Link this practices repo from the product README and the PR template. Point agent/skill docs at **this** repo, not at Google's archived text.
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
