# Changelog

## v1.1.0 — 2026-04-03

- Added `new-setup.md` — guided first-session onboarding handled by Arch: team naming, project context file, RTK install
- Architect now spins up Builder and Reviewer via Agent tool (foreground only) — documented in ARCHITECT.md and INSTALL.md
- Foreground-only requirement documented — background agents stall on Edit approval
- Reviewer protocol upgraded: APPROVED / APPROVED WITH CONDITIONS / REJECTED replaces Must Fix / Should Fix
- Reviewer now runs `git diff` first — diff is primary source of truth, not REVIEW-REQUEST
- Builder self-review and linting gate added before handing off to Reviewer
- Setup script rewritten as guided walkthrough — detects global vs per-project, prints tailored instructions
- `handoff/` folder added to both templates so `cp` command includes it
- `CLAUDE.md` removed from templates — setup script is the only source of truth for that step
- `team.yml.example` removed — renaming handled by Arch during setup
- Stale docs removed: `customizing-your-team.md`, `project-setup.md`
- README Quick Start restructured — two clearly labeled install paths
- Path mismatch in `CLAUDE.md` session router resolved

## v1.0.0 — 2026-03-31

Initial public release.

- Three-agent team: Architect, Builder, Reviewer
- Generic agents in `agents/` with customizable personas and [CUSTOMIZE] placeholders
- Named persona template in `templates/project-folder/` (Arch, Bob, Richard)
- Generic clean-slate template in `templates/generic/`
- Structured handoff files: ARCHITECT-BRIEF, REVIEW-REQUEST, REVIEW-FEEDBACK, BUILD-LOG, SESSION-CHECKPOINT
- Token optimization rules baked into every session router
- RTK integration guidance in docs/token-optimization.md
- Setup script with CLAUDE.md instructions printed on install
- Full documentation suite
