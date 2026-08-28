# How to write review comments

[Tiếng Việt](../../vi/review/comments.md)

Comments exist to **change code or lock a decision**, not to prove you read the diff.

## Form

- Point at behavior, risk, or a principle — not at the person.
- If you know a fix, propose it or sketch it. Do not only write "this is off".
- One comment, one idea. No essays.
- Ask before you conclude, when you may have missed context:

  > "Is there a reason not to use the existing helper in `foo`?"

## Template

```
Blocking: this function swallows network errors. Callers cannot tell timeout from 4xx.
Propagate or wrap using the error type this package already uses.

Nit: `d` → `delay` to match the neighboring functions.
```

Same prefixes in every language of the product codebase.

## Tone

Direct and civil. No sarcasm.  
Prefer "we" over "you got this wrong".  
Do not teach a whole topic inside a review — link a doc; mark it Nit if it must not block.
