# Three Man Team — Session Router

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

1. Load your token-optimizer skill if you have one — first, before anything else.
2. Check `SESSION-CHECKPOINT.md` — if active and recent, read it. That is your state.
3. Load your role file. Path depends on your setup:
   - Cloned into `agents/` → `agents/ARCHITECT.md` · `agents/BUILDER.md` · `agents/REVIEWER.md`
   - Copied to project root → `ARCHITECT.md` · `BUILDER.md` · `REVIEWER.md`
4. If no checkpoint — Architect reads `BUILD-LOG.md` + `ARCHITECT-BRIEF.md` only.

**Project Owner role is set by the human. Do not ask.**

---

## Reference Files — On Demand Only

| File | Load when |
|---|---|
| Project spec | Architect needs it; checkpoint doesn't cover it |
| ARCHITECT-BRIEF.md | Builder and Reviewer load at task start |
| BUILD-LOG.md | Architect checks status; Builder updates when done |
| REVIEW-REQUEST.md | Reviewer loads at review start |
| REVIEW-FEEDBACK.md | Builder loads after Reviewer signals done |

---

## Handoff Files

All team communication flows through files in `handoff/`:
- `ARCHITECT-BRIEF.md` — Architect writes, Builder reads
- `REVIEW-REQUEST.md` — Builder writes, Reviewer reads
- `REVIEW-FEEDBACK.md` — Reviewer writes, Builder reads
- `BUILD-LOG.md` — shared record, Architect owns
- `SESSION-CHECKPOINT.md` — Architect writes at session end

Run `./setup` to copy agent files into your project.
