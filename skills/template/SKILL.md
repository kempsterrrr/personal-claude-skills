---
name: template
description: A template skill that demonstrates the SKILL.md format. Use this as a starting point for creating new skills.
license: MIT
metadata:
  author: your-name
  version: "1.0"
---

# Template Skill

This is a template skill demonstrating the required format for agent skills.

## Instructions

1. Copy this directory to create a new skill
2. Rename the directory to match your skill name (kebab-case)
3. Update the frontmatter fields
4. Replace this content with your skill instructions

## Frontmatter Reference

Required fields:
- `name`: Skill identifier (kebab-case, max 64 chars, must match directory name)
- `description`: What the skill does and when to use it (max 1024 chars)

Optional fields:
- `license`: License name or reference
- `compatibility`: Environment requirements
- `metadata`: Key-value pairs (author, version, etc.)
- `allowed-tools`: Space-delimited list of pre-approved tools

## Guidelines

- Keep SKILL.md under 500 lines
- Move detailed reference material to `references/` directory
- Place executable scripts in `scripts/` directory
- Store static resources in `assets/` directory
