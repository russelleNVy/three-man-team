# Three Man Team — Methodology

Why this works, and the research behind it.

---

## Personas Over Labels

Telling an AI "you are a reviewer" produces generic reviewing behavior. Giving the AI
a character — a backstory, a set of values, a voice, a specific reason they care about
the work — activates a richer cluster of behavior.

This is vocabulary routing: precise role framing activates relevant training patterns
more effectively than abstract job titles. The Reviewer in Three Man Team is not "a code reviewer." They are someone who has seen what happens when corners get cut and will not let it happen again. That framing produces different — better — behavior.

The personas in Three Man Team are defaults. Name them, age them, give them a history that fits your team and your domain. The specificity is the point.

---

## Three Is the Right Number

DeepMind's multi-agent scaling research shows that structured teams of 3-5 agents with
defined artifact handoffs consistently outperform both solo agents and larger teams.
Solo agents drift. Large teams generate coordination overhead that eats the productivity
gain. Three is the sweet spot: enough for meaningful review, minimal enough for clean
handoffs.

Three Man Team is exactly three agents by design. Resist adding a fourth.

---

## Handoffs Through Files, Not Conversation

In Three Man Team, the agents communicate through structured files:
- Architect writes to ARCHITECT-BRIEF.md
- Builder writes to REVIEW-REQUEST.md
- Reviewer writes to REVIEW-FEEDBACK.md

This is not just organization. It means each agent starts with a clean context window
reading only what they need for their specific job. Builder never loads the full spec.
Reviewer never loads the schema. Token waste is structural, not behavioral — fix the
structure and the behavior follows.

---

## The Deploy Gate

Nothing ships without Architect's sign-off and the Project Owner's awareness. This is
not bureaucracy — it is accountability. The Project Owner knows what is going live.
The Architect has confirmed it passed review. The Builder and Reviewer never touch
the deploy target directly.

This pattern eliminates the most expensive class of AI mistake: changes that were
technically correct but wrong for the project, shipping without anyone noticing.

---

## Token Discipline as Infrastructure

Token waste is not a Claude problem or a prompt problem. It is a context architecture
problem. The five rules in Three Man Team's CLAUDE.md are not guidelines — they are operating rules that fire before every tool call. The cost of re-reading a file you already have in context is paid every time. The cost of the rules is paid once, at session start.

Grep before Read. Never speculate. Parallelize when possible. Route large outputs to
subagents. Never restate what the user said.

---

## Scope Lock

One step at a time. The next step does not start until the current step is reviewed,
cleared, and deployed. Anything that surfaces out of scope during a step goes to
BUILD-LOG Known Gaps — it does not get fixed. This single rule eliminates the most
common AI productivity failure: doing 40% of five things instead of 100% of one.
