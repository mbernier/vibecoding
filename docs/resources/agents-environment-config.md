# agents-environment-config

A community resource for managing AI tool configurations across Claude, Cursor, Gemini, Qwen, and Codex.

> **Repository**: [github.com/bernierllc/agents-environment-config](https://github.com/bernierllc/agents-environment-config)
>
> **Full Documentation**: See the repo README for complete details

## What This Solves

Managing configurations across multiple AI tools is tedious:

- Each tool has its own config directory
- Rules and settings need to be synced
- Sharing configurations across machines is manual
- Keeping everything updated is error-prone

This repository provides:

- **One place** to manage all tool configs
- **Pre-built rules** you can use or customize
- **Automation scripts** to keep things in sync
- **MCP configurations** for multiple tools

## Quick Start

### Option 1: Clone and Symlink (Recommended)

```bash
# Clone the repository
git clone https://github.com/bernierllc/agents-environment-config ~/agents-environment-config

# Create symlinks to your home directory
ln -s ~/agents-environment-config/.claude ~/.claude
ln -s ~/agents-environment-config/.cursor ~/.cursor
ln -s ~/agents-environment-config/.gemini ~/.gemini
ln -s ~/agents-environment-config/.qwen ~/.qwen
ln -s ~/agents-environment-config/.codex ~/.codex
```

This approach means updates to the repo automatically apply to your tools.

### Option 2: Copy What You Need

```bash
# Clone temporarily
git clone https://github.com/bernierllc/agents-environment-config /tmp/agent-config

# Copy just what you need
cp -r /tmp/agent-config/.cursor/rules ~/.cursor/
cp /tmp/agent-config/.cursor/mcp.json ~/.cursor/

# Clean up
rm -rf /tmp/agent-config
```

### Option 3: Fork and Customize

1. Fork the repository on GitHub
2. Clone your fork
3. Customize for your needs
4. Symlink to your home directory

## What's Included

| Component | Description |
|-----------|-------------|
| **Cursor Rules** | 43+ development rules in `.cursor/rules/` |
| **MCP Configs** | Pre-configured MCP servers for each tool |
| **Agent Instructions** | `CLAUDE.md`, `AGENTS.md`, `GEMINI.md`, `QWEN.md` |
| **Agents** | Reusable agent definitions (via submodule) |
| **Skills** | Custom skills for Claude Code (via submodule) |
| **Sync Scripts** | Automation for keeping configs in sync |
| **Statusline** | Custom Claude Code statusline scripts |

### Agents & Skills (Submodules)

The repository includes two Git submodules that provide reusable agents and skills:

#### Agents ([bernierllc/agency-agents](https://github.com/bernierllc/agency-agents))

Custom agent definitions that extend Claude Code's capabilities. Agents are reusable personalities/behaviors you can invoke for specific tasks.

- Located in `.claude/agents/`
- Synced to Cursor commands automatically
- See the [agency-agents README](https://github.com/bernierllc/agency-agents) for available agents and usage

#### Skills ([bernierllc/skills](https://github.com/bernierllc/skills))

Custom skills that add new capabilities to Claude Code. Skills are like plugins that teach Claude new workflows.

- Located in `.claude/skills/`
- Can be invoked during Claude Code sessions
- See the [skills README](https://github.com/bernierllc/skills) for available skills and how to create your own

!!! note "Submodule Updates"
    When you `git pull` the main repo, also update submodules:
    ```bash
    git pull
    git submodule update --init --recursive
    ```

### Directory Structure

```
agents-environment-config/
├── .claude/
│   ├── agents/           # Custom agents
│   ├── skills/           # Custom skills
│   ├── statusline.sh     # Statusline customization
│   └── CLAUDE.md         # Global instructions
├── .cursor/
│   ├── mcp.json          # MCP server config
│   ├── commands/         # Custom commands
│   └── rules/            # Development rules (43+ files)
├── .gemini/
│   └── settings.json     # Gemini MCP config
├── .qwen/
│   └── settings.json     # Qwen MCP config
├── .codex/
│   └── config.toml       # Codex config
└── scripts/
    ├── generate-agent-files.py
    └── sync-agents-skills.py
```

## Cursor Rules

The repository includes 43+ cursor rules organized by category:

### Categories

| Category | Rules | Examples |
|----------|-------|----------|
| **General** | 9 rules | Architecture, workflow, documentation |
| **Languages** | 2 rules | Python, TypeScript |
| **Stacks** | 3 rules | Next.js, FastAPI, React Native |
| **Frameworks** | 8 rules | Prisma, Supabase, Tailwind |
| **Topics** | 11+ rules | API design, Git, Testing |

[:octicons-arrow-right-24: Full Cursor Rules Guide](cursor-rules.md)

## MCP Configuration

Pre-configured MCP servers for enhanced AI capabilities:

```json
// .cursor/mcp.json example
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

## Automation Scripts

### generate-agent-files.py

Generates tool-specific instruction files from cursor rules:

```bash
python scripts/generate-agent-files.py
# Creates: CLAUDE.md, AGENTS.md, GEMINI.md, QWEN.md
```

### sync-agents-skills.py

Syncs agents and skills to Cursor commands:

```bash
python scripts/sync-agents-skills.py
```

## Keeping Updated

If you used the symlink approach:

```bash
cd ~/agents-environment-config
git pull
```

Your tools automatically get the updates.

## Customization

### Adding Your Own Rules

Create rules in `.cursor/rules/`:

```markdown
---
description: My custom rule
alwaysApply: true
---

# My Rule

[Your rule content]
```

### Modifying MCP Config

Edit `.cursor/mcp.json` to add/remove MCP servers for your needs.

### Local Overrides

Create `settings.local.json` files (gitignored) for machine-specific settings.

## Troubleshooting

### "Symlink already exists"

```bash
# Remove existing symlink/directory first
rm -rf ~/.cursor
ln -s ~/agents-environment-config/.cursor ~/.cursor
```

### "Rules not loading"

1. Check symlinks are correct: `ls -la ~/.cursor`
2. Restart your tool
3. Verify file permissions

### "MCP server not starting"

1. Install required npm packages: `npm install -g @context7/mcp`
2. Check server logs
3. Verify configuration syntax

## Related Pages

- [Cursor Rules Guide](cursor-rules.md) - How to write and use rules
- [Config Directories](../tools/config-directories.md) - Where configs live
- [Cursor Setup](../tools/ides/cursor.md) - Cursor-specific setup

---

> For complete documentation and the latest updates, see the [GitHub repository](https://github.com/bernierllc/agents-environment-config).
