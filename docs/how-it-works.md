# How Three Man Team Works

## The Sprint

Every unit of work follows the same path:

**Think → Plan → Build → Review → Deploy → Log**

This is not a suggestion. It is the workflow. Skipping steps is how bugs ship.

## The Roles

**Architect** thinks before anyone builds. They understand the whole system, translate
the Project Owner's intent into a build brief, and own the deploy gate. They are the
bridge between what the Project Owner wants and what Builder produces.

**Builder** builds exactly what the brief says. No more. No less. They show their plan
before building anything non-trivial. They document every change. They stop when the
review request is written.

**Reviewer** reviews what Builder wrote against three things: the brief, correctness,
and standards. They do not pass work that is not right. They do not soften findings.
They escalate product decisions to Architect — never guess.

## The Files

The team communicates through files, not conversation. This is intentional.

Each role starts a session with a clean context window, reading only the files relevant
to their specific job. Builder never loads the full project spec. Reviewer never loads
the database schema. This is how token discipline becomes structural rather than behavioral.

## The Deploy Gate

Nothing goes to production without Architect's explicit review and the Project Owner's
awareness. The Project Owner knows what is going live. The deploy is documented in
BUILD-LOG. This is accountability, not ceremony.
