# Claude Code

> **Official Docs**: [docs.anthropic.com/claude-code](https://docs.anthropic.com/en/docs/claude-code)
> **Category**: CLI

Claude Code is Anthropic's official command-line interface for working with Claude. It provides a powerful terminal-based AI coding experience.

## Quick Links

- [Official Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [GitHub Repository](https://github.com/anthropics/claude-code)
- [Anthropic Discord](https://discord.gg/anthropic)

!!! info "Works With"
    Claude Code uses [Claude](../models/claude.md) models exclusively - Sonnet, Opus, and Haiku.

## Configuration

> See [Understanding Config Directories](../config-directories.md) for general concepts.

Claude Code stores its configuration in `~/.claude/`:

| File/Directory | Purpose |
|----------------|---------|
| `settings.json` | User settings, API keys, preferences |
| `settings.local.json` | Machine-specific settings (not synced) |
| `CLAUDE.md` | Global agent instructions |
| `agents/` | Custom agent definitions |
| `skills/` | Custom skills and commands |
| `statusline.sh` | Custom statusline script |
| `projects/` | Project-specific settings |

### Global Instructions (CLAUDE.md)

The `~/.claude/CLAUDE.md` file contains instructions that apply to all your Claude Code sessions:

```markdown
# My Development Preferences

- Use TypeScript with strict mode
- Prefer functional programming patterns
- Always include error handling
- Write tests for new functions
```

### Project Instructions

Create a `CLAUDE.md` in your project root for project-specific instructions:

```markdown
# Project: My App

This is a Next.js 14 app with:
- App Router
- Prisma + PostgreSQL
- Tailwind CSS

Follow the patterns in existing code.
```

## Tips & Tricks

!!! tip "Community Tips"
    This section collects tips from real users. [Contribute your tips](../../community/contributing.md)!

**Useful commands:**

- `/help` - Show available commands
- `/clear` - Clear conversation
- `/compact` - Summarize conversation
- `/cost` - Show token usage

**Workflow tips:**

- Start sessions with clear context about what you're working on
- Use CLAUDE.md files to avoid repeating instructions
- The `/compact` command helps when conversations get long

**Custom statusline:**

Customize your terminal statusline to show model, tokens, and git info:

```bash
# ~/.claude/statusline.sh
echo "Claude | $MODEL | $TOKENS tokens | $GIT_BRANCH"
```

## Common Issues

**"API key not found"**

- Set `ANTHROPIC_API_KEY` environment variable
- Or add to `~/.claude/settings.json`

**"Context too long"**

- Use `/compact` to summarize
- Start a new session with `/clear`
- Be more specific in your requests

**"CLAUDE.md not loading"**

- Check file is in project root or `~/.claude/`
- Verify file permissions
- Restart Claude Code

## Community Resources

- [agents-environment-config](../../resources/agents-environment-config.md) - Shared Claude configurations
- [Anthropic Discord](https://discord.gg/anthropic) - Official community

---

!!! note "Help Improve This Page"
    Know a tip that's not listed? Found a helpful video tutorial? [Contribute to this page](../../community/contributing.md).
