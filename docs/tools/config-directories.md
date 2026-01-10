# Understanding AI Tool Config Directories

Most AI coding tools store configuration files in your home directory. Understanding this pattern is essential for customizing your setup and sharing configurations across machines.

## The Concept

When you install an AI coding tool, it typically creates a hidden directory in your home folder (prefixed with `.`). This directory contains:

- **Settings files** - Your preferences and API keys
- **Rules/Instructions** - Custom behavior and coding standards
- **Extensions** - Plugins, skills, or commands
- **Cache** - Model responses and session data

## Directory Locations by Platform

| Tool | macOS/Linux | Windows |
|------|-------------|---------|
| Claude Code | `~/.claude/` | `%USERPROFILE%\.claude\` |
| Cursor | `~/.cursor/` | `%USERPROFILE%\.cursor\` |
| Gemini | `~/.gemini/` | `%USERPROFILE%\.gemini\` |
| Qwen | `~/.qwen/` | `%USERPROFILE%\.qwen\` |
| Codex | `~/.codex/` | `%USERPROFILE%\.codex\` |

!!! tip "Finding Your Home Directory"
    === "macOS/Linux"
        ```bash
        echo $HOME
        # Usually /Users/yourname (macOS) or /home/yourname (Linux)
        ```

    === "Windows"
        ```powershell
        echo %USERPROFILE%
        # Usually C:\Users\yourname
        ```

## Common Directory Contents

### Claude Code (`~/.claude/`)

```
~/.claude/
├── settings.json          # User settings and preferences
├── settings.local.json    # Machine-specific settings (not synced)
├── CLAUDE.md              # Global agent instructions
├── agents/                # Custom agent definitions
├── skills/                # Custom skills and commands
├── statusline.sh          # Custom statusline script
└── projects/              # Project-specific settings
```

**Key files:**

- `CLAUDE.md` - Instructions that apply to all your Claude Code sessions
- `settings.json` - API keys, model preferences, allowed tools
- `agents/` - Reusable agent personalities and behaviors

[:octicons-arrow-right-24: Claude Code details](cli/claude-code.md)

### Cursor (`~/.cursor/`)

```
~/.cursor/
├── mcp.json               # MCP server configuration
├── commands/              # Custom slash commands
└── rules/                 # Development rules (.mdc files)
```

**Key files:**

- `mcp.json` - Defines which MCP servers Cursor can use
- `rules/` - Contains `.mdc` files with coding standards and behaviors
- `commands/` - Custom commands accessible via `/command-name`

[:octicons-arrow-right-24: Cursor details](ides/cursor.md)

### Gemini (`~/.gemini/`)

```
~/.gemini/
└── settings.json          # MCP and model configuration
```

[:octicons-arrow-right-24: Gemini details](models/gemini.md)

### Qwen (`~/.qwen/`)

```
~/.qwen/
└── settings.json          # MCP and model configuration
```

[:octicons-arrow-right-24: Qwen details](models/qwen.md)

### Codex (`~/.codex/`)

```
~/.codex/
└── config.toml            # Configuration in TOML format
```

[:octicons-arrow-right-24: Codex details](cli/codex.md)

## What Goes Where: Global vs Project

| Scope | Location | Use For |
|-------|----------|---------|
| **Global** | `~/.tool/` | Personal preferences, API keys, reusable rules |
| **Project** | `project/.tool/` | Project-specific settings, team-shared rules |

Most tools check both locations and merge configurations, with project settings taking precedence.

!!! example "Example: Cursor Rules"
    ```
    ~/.cursor/rules/           # Your personal coding standards
    myproject/.cursor/rules/   # Project-specific standards (shared with team)
    ```

    Cursor loads both, with project rules overriding global ones for conflicts.

## MCP (Model Context Protocol)

Many tools support MCP servers - external services that extend AI capabilities:

```json
// Example ~/.cursor/mcp.json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@context7/mcp"]
    },
    "playwright": {
      "command": "npx",
      "args": ["-y", "@anthropic/mcp-playwright"]
    }
  }
}
```

MCP servers can provide:

- Documentation lookup
- Browser automation
- Database access
- API integrations

## Sharing Configuration

### Manual Sharing

Copy your config directory to a new machine:

```bash
# Backup
cp -r ~/.cursor ~/cursor-backup

# Restore on new machine
cp -r ~/cursor-backup ~/.cursor
```

### Using Git

Track your configs in a git repository and symlink them:

```bash
# Clone your config repo
git clone https://github.com/you/dotfiles ~/dotfiles

# Symlink configs
ln -s ~/dotfiles/.cursor ~/.cursor
ln -s ~/dotfiles/.claude ~/.claude
```

### Community Solution: agents-environment-config

The [agents-environment-config](../resources/agents-environment-config.md) repository provides a complete setup for managing configurations across multiple AI tools.

[:octicons-arrow-right-24: Learn more about agents-environment-config](../resources/agents-environment-config.md)

## Security Considerations

!!! warning "Protect Your API Keys"
    Config directories often contain API keys. Never commit them to public repositories.

    - Use `.gitignore` to exclude sensitive files
    - Use environment variables for keys when possible
    - Consider using a secrets manager

**Files to keep private:**

- `settings.json` (often contains API keys)
- `settings.local.json`
- Any `.env` files

**Files safe to share:**

- `rules/` directories
- `CLAUDE.md` / `AGENTS.md` (instructions without keys)
- `mcp.json` (unless it contains secrets)

## Troubleshooting

### "Config not loading"

1. Check the directory exists: `ls -la ~/.cursor`
2. Verify file permissions: `chmod 644 ~/.cursor/mcp.json`
3. Check for syntax errors in JSON/YAML files

### "Changes not taking effect"

1. Restart the tool after config changes
2. Check for project-level overrides
3. Verify you're editing the right location (global vs project)

### "Tool can't find config directory"

Some tools create the directory on first run. Try:

1. Run the tool once to initialize
2. Create the directory manually: `mkdir ~/.cursor`
