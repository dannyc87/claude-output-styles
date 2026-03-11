# Claude Output Styles

Custom output styles for [Claude Code](https://claude.ai/claude-code) — personality, tone, and behavioral presets that change how Claude communicates.

## Styles

| Style | Description |
|-------|-------------|
| [Jean Claude](styles/jean-claude.md) | The Muscles from Brussels of coding — bilingual (English/French), martial arts metaphors, JCVD philosophy |

## Installation

Copy a style file to your Claude Code output styles directory:

```bash
# User-level (available in all projects)
cp styles/jean-claude.md ~/.claude/output-styles/

# Project-level (shared with team via git)
cp styles/jean-claude.md .claude/output-styles/
```

Then activate it in Claude Code:

```
/output-style Jean Claude
```

## Anatomy of an Output Style

Output styles are Markdown files with YAML frontmatter:

```yaml
---
name: Style Name                # Display name in /output-style menu
description: Brief description   # Shown in the selection UI
keep-coding-instructions: true   # Keep software engineering behavior (default: false)
---

# Instructions follow as markdown...
```

### Frontmatter Options

| Option | Type | Default | Purpose |
|--------|------|---------|--------|
| `name` | string | filename | Display name in the `/output-style` menu |
| `description` | string | — | Brief description shown in selection UI |
| `keep-coding-instructions` | boolean | `false` | When `true`, preserves Claude Code's built-in software engineering instructions. Set to `false` for non-coding personas |

### Writing Effective Styles

- **Structure clearly**: Role (1 line) → Behavior (bullets) → Constraints (bullets) → Examples
- **Be specific**: Concrete examples of desired output work better than abstract descriptions
- **Use imperatives**: "Always do X", "Never do Y" — these are system prompt instructions
- **Layer with CLAUDE.md**: Style controls *how* Claude talks; CLAUDE.md controls *what* it knows
- **Scope appropriately**: User-level (`~/.claude/output-styles/`) for personal styles, project-level (`.claude/output-styles/`) for team styles

## Contributing

To add a new style:

1. Create a `.md` file in `styles/`
2. Add frontmatter with `name` and `description`
3. Write your instructions
4. Update the table in this README
