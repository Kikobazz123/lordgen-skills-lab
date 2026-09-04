# Skills

This directory holds Claude Code skills for this project. Each skill is a
subdirectory containing a `SKILL.md` file, invoked with `/<skill-name>`.

## Layout

```
.claude/skills/
  <skill-name>/
    SKILL.md          # required: frontmatter + instructions
    scripts/           # optional: helper scripts the skill can run
    references/         # optional: docs the skill reads for context
    assets/             # optional: templates, images, etc.
```

## SKILL.md format

```markdown
---
name: skill-name
description: One line describing what this skill does and when to use it.
---

Instructions for Claude to follow when this skill is invoked.
```

- `name` should match the directory name (kebab-case).
- `description` is shown in the skill listing and used to decide relevance —
  be specific about trigger phrases and use cases.
- Keep instructions focused; link out to `references/` for long-form docs
  instead of inlining everything.

See `example-skill/SKILL.md` for a working template.
