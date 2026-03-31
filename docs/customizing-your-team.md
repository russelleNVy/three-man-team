# Customizing Your Team

## Rename the Roles

Architect, Builder, Reviewer are defaults. Change them to anything.

Update `config/team.yml`:
```yaml
architect:
  name: "Ada"
builder:
  name: "Dev"
reviewer:
  name: "Rex"
```

Then rename the files: `agents/ARCHITECT.md` → `agents/ADA.md` and update references
in CLAUDE.md.

## Change the Personas

The **Who You Are** section in each role file is where persona lives. Rewrite it
completely. Give your Architect a different background. Make your Reviewer younger or
older. Ground the persona in your domain — a seasoned veteran is different from a
Python data engineer. The more specific the persona, the better the behavior.

## Add Domain-Specific Standards

In BUILDER.md, the **While You Build** section lists coding standards. Replace the
generic examples with your stack's actual standards — linting rules, security patterns,
framework conventions, naming conventions.

## Add Skills

If you use skills (Claude Code SKILL.md files), reference them in the role files under
a Skills section. List the skill name and when to load it. Do not load all skills at
session start — load them when the task requires them.

## Use a Template

For projects with specific established conventions, copy `templates/project-folder/`
into your project root and customize the persona files and CLAUDE.md router to match
your stack, your standards, and your deploy target.
