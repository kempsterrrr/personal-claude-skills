# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an agent skills repository following the Anthropic Agent Skills Specification (https://agentskills.io/specification). Agent skills are folders containing instructions, scripts, and resources that AI agents can discover and use to perform tasks.

## Skill Structure

Each skill is a directory in `skills/` containing at minimum a `SKILL.md` file:

```
skills/
└── skill-name/
    ├── SKILL.md           # Required: frontmatter + markdown instructions
    ├── scripts/           # Optional: executable code
    ├── references/        # Optional: additional documentation
    └── assets/            # Optional: templates, images, data files
```

## SKILL.md Format

```yaml
---
name: skill-name              # Required: kebab-case, max 64 chars, must match directory
description: What it does...  # Required: max 1024 chars
license: MIT                  # Optional
compatibility: Claude Code    # Optional: environment requirements
metadata:                     # Optional
  author: name
  version: "1.0"
allowed-tools: Bash Read      # Optional: space-delimited pre-approved tools
---

# Skill Name

[Markdown instructions for the agent]
```

## Naming Rules

- Lowercase letters, numbers, and hyphens only
- Cannot start or end with hyphen
- No consecutive hyphens
- Directory name must match `name` field in frontmatter

## Validation

Use the skills-ref library to validate skills:
```bash
skills-ref validate ./skills/my-skill
```

## Creating a New Skill

1. Copy `skills/template/` to `skills/your-skill-name/`
2. Update frontmatter in SKILL.md
3. Write agent instructions in markdown body
4. Keep main SKILL.md under 500 lines; use `references/` for detailed docs
