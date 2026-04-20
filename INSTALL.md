# Installing Three Man Team

For the full quick start, see [README.md](README.md).

---

## Per-Project Install

Clone into your project folder, then run setup:

```bash
git clone https://github.com/russelleNVy/three-man-team.git .claude/skills/three-man-team
cd .claude/skills/three-man-team && ./setup
```

Setup handles the rest — follow what it prints.

---

## Global Install

Install once, use in any project:

```bash
git clone https://github.com/russelleNVy/three-man-team.git ~/.claude/skills/three-man-team
cd ~/.claude/skills/three-man-team && ./setup
```

Then for each project:

```bash
cp -r ~/.claude/skills/three-man-team/templates/project-folder/* /path/to/your/project/
cd /path/to/your/project
```

Open Claude Code and paste:

```
You are the Architect on this project. Please read new-setup.md.
```

---

## Requirements

- Claude Code CLI — install at https://claude.ai/code
- Git

### Windows

Three Man Team's setup script requires bash. On Windows, use Git Bash or WSL — the script will not run in PowerShell or Command Prompt.

Manual setup alternative: copy the files from `templates/project-folder/` into your project directory yourself, then open Claude Code and paste:

```
You are the Architect on this project. Please read new-setup.md.
```

RTK is not currently supported on Windows. Skip the RTK setup step.

## Critical: Always Run Builder and Reviewer in the Foreground

**Do not run Builder or Reviewer as background agents.**

Background agents cannot receive tool approval prompts. The first time Builder tries to
write a file, it will stall with nobody to approve it. If Builder or Reviewer seems to
never run or stops silently — this is why.

When using the Agent tool: leave `run_in_background` unset (defaults to foreground).
When using manual paste: the fresh conversation is inherently foreground.
