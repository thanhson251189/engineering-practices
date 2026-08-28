# Handling review comments

[Tiếng Việt](../../vi/review/handling-comments.md)

This page is for the **author receiving comments**. How reviewers write them: [comments.md](comments.md).

## Default response

Change the code. A comment on the tool is the last move, after the diff is clearer.

If the reviewer did not understand the change, the code or the description is not clear enough. Do not treat “I explained it in a reply” as the fix.

## Do

- Reply to every blocking comment: done, or why not, with a pointer to the new commit.
- Take Nits when cheap. Skip Nits when they fight the idea of the PR; say so once.
- After two rounds on the same point: 10–15 minute talk, write the decision on the PR, merge or split. Do not let the PR idle.
- Assume the comment is about the change, not about you.

## Do not

- Answer a design question only with text and leave the code as-is.
- Debate taste the formatter does not enforce. Author preference wins there ([principles](../principles.md) §2).
- Wait days for the perfect wording of a reply. Push the fix first.
- Treat an agent’s “LGTM” as a resolved human comment ([solo.md](../solo.md)).
