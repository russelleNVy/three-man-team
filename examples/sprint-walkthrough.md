# A Complete Three Man Team Sprint

This is what a full step looks like from start to deploy.

## 1. Project Owner describes a problem to Architect

> "The user registration form doesn't validate email format on the server side.
> It only validates in JavaScript."

## 2. Architect diagnoses

Architect reads the relevant file, confirms the gap, and describes what the code
currently does. Then asks: do you want server-side validation only, or both?

Project Owner: "Both. JS for UX, server-side for security."

## 3. Architect writes the brief

Updates ARCHITECT-BRIEF.md:

```
## Step 12 — Server-side email validation on registration
- Add server-side email format validation to the registration handler
- Validate after sanitization, before DB write
- Return error message matching the existing error format
- JS validation already exists — do not modify it
- Flag: use the framework's built-in validator, not a custom regex
```

## 4. Architect spins up Builder

> You are Bob on this project. Load token-optimizer skill first.
> Then read BUILDER.md, then ARCHITECT-BRIEF.md.
> Your task is Step 12.

## 5. Builder builds

Builder reads the brief, shows a one-line plan, gets Architect's nod, and makes
the change. Updates BUILD-LOG. Writes REVIEW-REQUEST.md.

## 6. Architect spins up Reviewer

> You are Richard on this project. Load token-optimizer skill first.
> Then read REVIEWER.md, then REVIEW-REQUEST.md.
> Review only the file Builder listed.

## 7. Reviewer reviews

Reviewer reads the change. Confirms the validator is used correctly. Confirms the
error format matches existing patterns. Flags: the error message is not translatable
— must fix. Sets Ready for Builder: NO.

## 8. Builder fixes

Wraps the error string in the project's i18n helper. Re-submits.

## 9. Reviewer clears

"Step 12 is clear." Sets Ready for Builder: YES.

## 10. Architect deploys

Tells Project Owner: "Server-side email validation added. Richard flagged the error
string wasn't translatable — Bob fixed it. Clean."

Project Owner: "Ship it."

Architect commits, deploys, confirms, updates BUILD-LOG and SESSION-CHECKPOINT.
