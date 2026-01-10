# Local Development with AI

Working with AI coding assistants locally gives you the most control over your development environment. This section covers how to set up and optimize your local AI-assisted workflow.

## Getting Started

<div class="grid cards" markdown>

-   :material-swap-horizontal:{ .lg .middle } **IDE vs CLI**

    ---

    Choose between graphical IDEs and terminal-based tools based on your workflow.

    [:octicons-arrow-right-24: Compare approaches](ide-vs-cli.md)

-   :material-cog:{ .lg .middle } **Environment Setup**

    ---

    Configure your local environment for AI-assisted development.

    [:octicons-arrow-right-24: Set up your environment](environment-setup.md)

-   :material-clipboard-list:{ .lg .middle } **Planning Your Work**

    ---

    Approaches to planning and organizing AI-assisted projects.

    [:octicons-arrow-right-24: Planning strategies](planning/local-planning.md)

</div>

## Why Work Locally?

Working with AI tools on your local machine offers several advantages:

| Benefit | Description |
|---------|-------------|
| **Privacy** | Your code stays on your machine (depending on tool) |
| **Speed** | No network latency for file operations |
| **Control** | Full access to your development environment |
| **Integration** | Works with your existing tools and workflows |
| **Customization** | Extensive configuration options |

## The Local AI Stack

A typical local AI development setup includes:

```
┌─────────────────────────────────────────────┐
│              Your Codebase                  │
├─────────────────────────────────────────────┤
│     IDE (Cursor, VS Code, Windsurf)         │
│              or                              │
│     CLI (Claude Code, Aider, Codex)         │
├─────────────────────────────────────────────┤
│     Config (~/.cursor, ~/.claude, etc.)     │
├─────────────────────────────────────────────┤
│     AI Model API (Claude, GPT-4, etc.)      │
└─────────────────────────────────────────────┘
```

## Quick Comparison

| Approach | Best For | Learning Curve | Flexibility |
|----------|----------|----------------|-------------|
| **IDE-based** | Visual learners, integrated workflows | Gentle | Medium |
| **CLI-based** | Power users, automation, scripting | Steeper | High |
| **Hybrid** | Complex projects, team collaboration | Medium | Highest |

[:octicons-arrow-right-24: Detailed comparison](ide-vs-cli.md)

## Essential Concepts

### Configuration Directories

AI tools store settings in your home directory (`~/.cursor`, `~/.claude`, etc.). Understanding these is key to customization.

[:octicons-arrow-right-24: Config directory guide](../tools/config-directories.md)

### MCP (Model Context Protocol)

MCP servers extend what AI tools can do - from browsing documentation to controlling browsers.

[:octicons-arrow-right-24: Learn about MCP](../tools/config-directories.md#mcp-model-context-protocol)

### Project vs Global Config

Most tools support both global settings (your preferences) and project settings (team standards).

[:octicons-arrow-right-24: Global vs project config](../tools/config-directories.md#what-goes-where-global-vs-project)

## Planning Your Work

How you plan and organize your AI-assisted work significantly impacts results:

- **[Local Planning](planning/local-planning.md)** - Using markdown files, comments, and local tools
- **[BrainGrid](planning/braingrid.md)** - External tool for structured requirements

## Next Steps

1. **[Compare IDE vs CLI](ide-vs-cli.md)** - Decide which approach fits your workflow
2. **[Set up your environment](environment-setup.md)** - Get your local setup ready
3. **[Explore tools](../tools/index.md)** - Deep dive into specific tools
4. **[Community resources](../resources/index.md)** - Shared configurations and best practices
