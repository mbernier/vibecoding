# AI Coding Tools

The AI coding landscape is evolving rapidly. This section helps you navigate the tools available for AI-assisted development.

## Tool Categories

<div class="grid cards" markdown>

-   :material-application:{ .lg .middle } **IDEs & Editors**

    ---

    Full-featured development environments with integrated AI capabilities.

    [:octicons-arrow-right-24: Cursor](ides/cursor.md) · [:octicons-arrow-right-24: Windsurf](ides/windsurf.md) · [:octicons-arrow-right-24: VS Code](ides/vscode-copilot.md)

-   :material-console:{ .lg .middle } **CLI & Terminal**

    ---

    Command-line tools for AI-assisted coding in your terminal.

    [:octicons-arrow-right-24: Claude Code](cli/claude-code.md) · [:octicons-arrow-right-24: Codex](cli/codex.md) · [:octicons-arrow-right-24: Aider](cli/aider.md)

-   :material-brain:{ .lg .middle } **AI Models & APIs**

    ---

    The underlying AI models that power these tools.

    [:octicons-arrow-right-24: Claude](models/claude.md) · [:octicons-arrow-right-24: Gemini](models/gemini.md) · [:octicons-arrow-right-24: Qwen](models/qwen.md) · [:octicons-arrow-right-24: OpenAI](models/openai.md)

</div>

## How Tools Work Together

Many tools use multiple AI models under the hood. Understanding these relationships helps you choose the right combination:

| Tool | Type | Models Supported |
|------|------|------------------|
| [Cursor](ides/cursor.md) | IDE | Claude, GPT-4, Gemini |
| [Windsurf](ides/windsurf.md) | IDE | Claude, GPT-4 |
| [VS Code + Copilot](ides/vscode-copilot.md) | IDE | GPT-4 (Copilot) |
| [Claude Code](cli/claude-code.md) | CLI | Claude |
| [Codex CLI](cli/codex.md) | CLI | GPT-4 |
| [Aider](cli/aider.md) | CLI | Claude, GPT-4, others |

## Configuration Fundamentals

Most AI coding tools store their configuration in your home directory. Understanding this is key to customizing your setup.

[:octicons-arrow-right-24: Understanding Config Directories](config-directories.md)

## Choosing the Right Tool

**New to AI coding?** Start with [Cursor](ides/cursor.md) - it has the gentlest learning curve.

**Prefer the terminal?** Try [Claude Code](cli/claude-code.md) or [Aider](cli/aider.md).

**Already using VS Code?** Add [GitHub Copilot](ides/vscode-copilot.md) to your existing setup.

**Want flexibility?** [Cursor](ides/cursor.md) and [Aider](cli/aider.md) let you switch between models.

## Community Resources

- [agents-environment-config](../resources/agents-environment-config.md) - Shared configurations for multiple tools
- [Cursor Rules Guide](../resources/cursor-rules.md) - Customize Cursor's behavior
