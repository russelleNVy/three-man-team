# Installing Three Man Team

## Global Install — All Your Projects

Three Man Team installs into `~/.claude/skills/three-man-team` and is available in every project.

```bash
git clone https://github.com/russelleNVy/three-man-team.git ~/.claude/skills/three-man-team
cd ~/.claude/skills/three-man-team && ./setup
```

Then add to your global `~/.claude/CLAUDE.md`:
```
## Three Man Team
Available agents: /architect, /builder, /reviewer
Token rules always active — see three-man-team/CLAUDE.md
```

## Per-Project Install

Three Man Team installs into `.claude/skills/three-man-team` inside your repo and only applies to that project.

```bash
git clone https://github.com/russelleNVy/three-man-team.git .claude/skills/three-man-team
cd .claude/skills/three-man-team && ./setup
```

Add to your project's `CLAUDE.md`:
```
## Three Man Team
Available agents: /architect, /builder, /reviewer
```

## VS Code / Cursor / Codex

Three Man Team uses the SKILL.md standard and works with any agent that supports context files.
Copy the `agents/` directory and `CLAUDE.md` into your project root.

## Requirements

- Claude Code CLI (for slash command support)
- Git
- Any agent supporting CLAUDE.md / SKILL.md context (for other tools)

## Critical: Always Run Builder and Reviewer in the Foreground

**Do not run Builder or Reviewer as background agents.**

Background agents cannot receive tool approval prompts. The first time Builder tries to
write a file, it will stall with nobody to approve it. If Builder or Reviewer seems to
never run or stops silently — this is why.

When using the Agent tool: leave `run_in_background` unset (defaults to foreground).
When using manual paste: the fresh conversation is inherently foreground.
