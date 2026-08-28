# Docs

[Tiếng Việt](../vi/docs.md)

Write docs when a **contract** changes, not when you feel guilty.

## Must update when

- User-facing behavior changes.
- A public API, event, or schema changes.
- How to run, env vars, feature flags, or deploy/rollback runbooks change.
- A design decision will live longer than one sprint → short ADR (context, decision, consequences).

## Do not

- Comment every line to restate *what* a clear name already says.
- Grow a README into team history.
- Document an abstraction "just in case".

## Where it lives

- Dev/run instructions: product repo README.
- API contract: next to the code or in the spec repo you already use.
- Durable decisions: `/docs/adr/` in the product repo.
- Review process: **this** repo.
