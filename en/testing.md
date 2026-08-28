# Testing

[Tiếng Việt](../vi/testing.md)

Rules below do not name a framework. Each product repo fills in commands.

## Rules

- A PR that changes behavior **must** add tests for the new behavior, or explain why it cannot be tested and why that gap is acceptable.
- Pure refactor: existing tests must keep their signal. If coverage is missing, **add tests first**, refactor second — preferably as two PRs.
- Test behavior, not implementation details (private names, exact mock call counts) unless that *is* the contract.

## What "enough" means

Enough to:

1. catch a regression of this exact bug/feature,
2. let the next person edit the file without guessing.

Do not chase a coverage percentage unless this product repo already chose a threshold and CI measures it.

## Bad tests

- Flaky.
- Depend on wall-clock time, the real network, or test order.
- 200 lines of setup for one assertion.
- Copied fixtures that differ by one field.

If a PR adds tests like this: `Blocking`, or ask for a split. Do not defer to "next time".

## Fill in per product repo (not in this guide)

- Default test command
- Which layers CI requires (unit / integration / contract / e2e)
- What may be mocked
- What must not be mocked
