# Emergencies

[Tiếng Việt](../vi/emergencies.md)

Skip normal review **only** when delay would cause real damage.

## Is an emergency

- A security hole that is exposed or exploitable.
- Clear production harm (wide outage, data loss, wrong money).
- Legal / contractual hard deadline — missing it is expensive.
- A rollback that stops an incident.

## Is not an emergency

- Wanting this week instead of next week.
- The feature took a long time and you want it merged.
- The reviewer is away or slow.
- An internal demo.
- CI red because of your PR — fix it in the normal process.

## How to cut the line

1. Keep the PR as small as possible.
2. Start the description with `EMERGENCY:` and the reason.
3. Someone who knows that area still reads the diff (pairing counts as review).
4. Follow-up PR within **one business day** if tests/docs/cleanup were skipped.
5. Afterward: 5–10 lines of postmortem (what happened, why the shortcut, how to avoid a repeat).

Hotfix must not become the default path.
