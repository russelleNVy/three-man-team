# [Project Name] — Session Router
*[Your Name] — [your-domain.com] — Confidential*

---

## Token Rules — Always Active

```
Is this in a skill or memory?   → Trust it. Skip the file read.
Is this speculative?            → Kill the tool call.
Can calls run in parallel?      → Parallelize them.
Output > 20 lines you won't use → Route to subagent.
About to restate what user said → Delete it.
```

Grep before Read. Never read a whole file to find one thing.
Do not re-read files already in context this session.

---

## Session Start — Every Role

1. Load token-optimizer skill — first, before anything else.
2. Check SESSION-CHECKPOINT.md — if dated within 7 days, read it. That is your state.
3. Load your role file: ARCHITECT.md · BUILDER.md · REVIEWER.md
4. If no active checkpoint — Architect reads BUILD-LOG.md + ARCHITECT-BRIEF.md only.

**Project Owner is [Your Name]. Do not ask their role.**

---

## Reference Files — On Demand Only

| File | Load when |
|---|---|
| Project spec | Architect only, when no checkpoint covers it |
| ARCHITECT-BRIEF.md | Builder and Reviewer load at task start |
| BUILD-LOG.md | Architect checks status; Builder updates when done |
| REVIEW-REQUEST.md | Reviewer loads at review start |
| REVIEW-FEEDBACK.md | Builder loads after Reviewer signals done |

Add project-specific reference files here as your project grows.

---

## Skills — On Demand Only

Load the skill the task needs. Not at session start.

`token-optimizer` — always first. Controls how the team reads, thinks, and responds.

For bash output compression, see [RTK](https://github.com/rtk-ai/rtk) — a separate install
that compresses `find`, `ls`, `grep` output before it hits context. Not required, but
pairs with token-optimizer for significant additional savings in heavy CLI sessions.

Add your stack-specific skills below:
[your skills here]
