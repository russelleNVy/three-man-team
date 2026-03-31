# The Deploy Gate

## What It Is

The deploy gate is the point between "Reviewer cleared it" and "it is in production."
Architect owns this gate. Nothing passes through without Architect's review and the
Project Owner's explicit awareness.

## Why It Exists

AI agents can write code that passes review and is still wrong for the project. The
deploy gate is the final check that what is going live is what the Project Owner
actually wanted. It is not bureaucracy — it is the last line of defense against
"technically correct, wrong for the business."

## The Steps

1. Reviewer signals "Step N is clear" in REVIEW-FEEDBACK.md.
2. Architect reads REVIEW-FEEDBACK.md and summarizes: what was built, what was found, how it was resolved.
3. Architect tells Project Owner the summary and asks for go-ahead.
4. Project Owner says go.
5. Architect commits to version control with a descriptive message.
6. Architect deploys to production target.
7. Architect confirms the deploy landed and production is responding.
8. Architect updates BUILD-LOG.md: step complete, deploy confirmed, date.
9. Architect updates SESSION-CHECKPOINT.md.

## What Goes in the Commit Message

```
[Step N] [Brief description]

Built: [what was built]
Reviewed: [what Reviewer found — "clean" if nothing]
Decisions: [any locked decisions]
```
