# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is Anthropic's official Agent Skills repository - a collection of skills that extend Claude's capabilities for specialized tasks. Skills are folders containing a `SKILL.md` file with YAML frontmatter and markdown instructions.

The Agent Skills specification is maintained at https://agentskills.io/specification

## Repository Structure

```
/skills/          # 16 skill implementations organized by category
/spec/            # Agent Skills specification (redirects to agentskills.io)
/template/        # Minimal skill template for creating new skills
/.claude-plugin/  # Plugin marketplace configuration
```

### Skill Categories

**Document Skills** (production-grade, source-available):
- `docx/` - Word document creation/editing with OOXML support
- `pdf/` - PDF manipulation, form filling, merge/split operations
- `pptx/` - PowerPoint presentation creation
- `xlsx/` - Excel spreadsheet operations

**Example Skills** (Apache 2.0, for learning/inspiration):
- `skill-creator/` - Guide for creating effective skills
- `mcp-builder/` - MCP server generation utilities
- `algorithmic-art/`, `canvas-design/`, `frontend-design/`, `theme-factory/` - Creative/design skills
- `brand-guidelines/`, `internal-comms/`, `doc-coauthoring/` - Enterprise/communication skills
- `webapp-testing/`, `web-artifacts-builder/`, `slack-gif-creator/` - Technical skills

## Skill Structure

Every skill follows this pattern:
```
skill-name/
├── SKILL.md              # Required: YAML frontmatter + instructions
├── scripts/              # Optional: Python/Bash utilities
├── reference/            # Optional: Additional documentation
└── [resources]/          # Optional: Templates, themes, data files
```

### SKILL.md Format

```yaml
---
name: skill-name          # Required: lowercase, hyphens for spaces
description: What it does # Required: when Claude should use it
---

# Skill Title

[Markdown instructions for Claude]
```

## Plugin Bundles

Skills are bundled into plugins via `.claude-plugin/marketplace.json`:
- **document-skills**: xlsx, docx, pptx, pdf
- **example-skills**: All other example skills

## Working with Skills

When creating or modifying skills:
- The `template/SKILL.md` provides the minimal starting structure
- Complex skills may include Python scripts (see `pdf/scripts/`, `skill-creator/scripts/`)
- Reference documentation can be added as additional markdown files
- The `skill-creator` skill contains comprehensive authoring guidance
