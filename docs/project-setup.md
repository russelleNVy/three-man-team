# Project Setup Guide

How to mount Three Man Team to any project and start your first session.

---

## Step 1 — Install Three Man Team

Global install (available in all projects):

```bash
git clone https://github.com/russelleNVy/three-man-team.git ~/.claude/skills/three-man-team
cd ~/.claude/skills/three-man-team && ./setup
```

Per-project install (only applies to this repo):

```bash
git clone https://github.com/russelleNVy/three-man-team.git .claude/skills/three-man-team
cd .claude/skills/three-man-team && ./setup
```

The setup script prints the exact lines to add to your CLAUDE.md.

---

## Step 2 — Copy the Template Files Into Your Project

Choose a template and copy it into your project root (or wherever your AI is mounted):

```bash
# Named personas (Arch, Bob, Richard) — customize from here
cp templates/project-folder/CLAUDE.md /path/to/your/project/
cp templates/project-folder/ARCHITECT.md /path/to/your/project/
cp templates/project-folder/BUILDER.md /path/to/your/project/
cp templates/project-folder/REVIEWER.md /path/to/your/project/

# Or start from a blank slate
cp templates/generic/CLAUDE.md /path/to/your/project/
cp templates/generic/ARCHITECT.md /path/to/your/project/
cp templates/generic/BUILDER.md /path/to/your/project/
cp templates/generic/REVIEWER.md /path/to/your/project/
```

Copy the handoff templates too:

```bash
cp handoff/ARCHITECT-BRIEF.md /path/to/your/project/
cp handoff/REVIEW-REQUEST.md /path/to/your/project/
cp handoff/REVIEW-FEEDBACK.md /path/to/your/project/
cp handoff/BUILD-LOG.md /path/to/your/project/
cp handoff/SESSION-CHECKPOINT.md /path/to/your/project/
```

---

## Step 3 — Customize CLAUDE.md

Open the CLAUDE.md you copied and fill in:
- Your name as Project Owner
- Your project name
- Your production URL and deploy target (or leave blank for now)
- Your stack-specific skills (add as you discover what you need)

---

## Step 4 — Mount Your AI to the Project Directory

For Claude Code CLI:

```bash
cd /path/to/your/project
claude
```

For VS Code, Cursor, or Codex — open the project folder. The CLAUDE.md in the root is
picked up automatically by any agent that supports context files.

---

## Step 5 — Start Your First Session

Paste this into your AI session:

```
You are [Architect name] on this project.
Read CLAUDE.md, then ARCHITECT.md.
Report project status in one paragraph, then wait for me.
```

Architect will read the files, report what they see, and wait. Tell them what you want
to work on. That's the start of a sprint.

---

## Optional — Token Optimizer

If you use Claude Code CLI heavily, install the token-optimizer skill:

```bash
# Place your token-optimizer skill at:
~/.claude/skills/token-optimizer/SKILL.md
```

Then reference it in your CLAUDE.md and role files as the first thing every session loads.

For bash output compression, see [RTK](https://github.com/rtk-ai/rtk). Install separately.
Both tools together compound your token savings significantly.
