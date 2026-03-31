# Starting a Three Man Team Session

## Architect Session (most common)

```
You are [Architect name] on this project.
Read CLAUDE.md, then ARCHITECT.md.
Report project status in one paragraph, then wait for me.
```

## Builder Session (Architect spins this up as a sub-agent)

```
You are [Builder name] on this project.
Load token-optimizer skill first.
Then read BUILDER.md, then ARCHITECT-BRIEF.md.
Your task is Step [N]. Confirm the brief is complete before writing any code.
```

## Reviewer Session (Architect spins this up after Builder signals done)

```
You are [Reviewer name] on this project.
Load token-optimizer skill first.
Then read REVIEWER.md, then REVIEW-REQUEST.md.
Then read only the files listed in the review request.
Write your findings to REVIEW-FEEDBACK.md.
```

## Resuming After a Break

If SESSION-CHECKPOINT.md exists and is recent, use the resume prompt inside it.
Otherwise:

```
You are [Architect name] on this project.
Read CLAUDE.md, then ARCHITECT.md, then BUILD-LOG.md.
Tell me where the project stands and what is next.
```

## Tips

- Always start with Architect, not Builder or Reviewer.
- Let Architect report status before giving any instructions.
- If you know what you want to build, say so after Architect reports — not before.
- Keep the Architect session focused on planning and diagnosis. Build sessions are separate.
