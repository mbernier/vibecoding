# Cursor

> **Official Docs**: [cursor.com/docs](https://docs.cursor.com/)
> **Category**: IDE

Cursor is a VS Code fork with AI deeply integrated into the editing experience. It's become one of the most popular AI coding tools due to its intuitive interface and powerful features.

## Quick Links

- [Official Documentation](https://docs.cursor.com/)
- [Cursor Forum](https://forum.cursor.com/)
- [Download Cursor](https://cursor.com/)

!!! info "Works With"
    Cursor supports multiple AI models including [Claude](../models/claude.md), [GPT-4](../models/openai.md), and [Gemini](../models/gemini.md). You can switch models based on your needs.

## Configuration

> See [Understanding Config Directories](../config-directories.md) for general concepts.

Cursor stores its configuration in `~/.cursor/`:

| File/Directory | Purpose |
|----------------|---------|
| `mcp.json` | MCP server definitions |
| `rules/` | Development rules (`.mdc` files) |
| `commands/` | Custom slash commands |

### MCP Configuration

```json
// ~/.cursor/mcp.json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@context7/mcp"]
    }
  }
}
```

### Cursor Rules

Cursor rules (`.mdc` files) define coding standards and AI behavior. Place them in `~/.cursor/rules/` for global rules or `project/.cursor/rules/` for project-specific rules.

[:octicons-arrow-right-24: Cursor Rules Guide](../../resources/cursor-rules.md)

## Tips & Tricks

!!! tip "Community Tips"
    This section collects tips from real users. [Contribute your tips](../../community/contributing.md)!

**Keyboard shortcuts:**

- `Cmd/Ctrl + K` - Open AI chat inline
- `Cmd/Ctrl + L` - Open AI chat panel
- `Cmd/Ctrl + Shift + K` - Generate code

**Workflow tips:**

- Use `@codebase` to give the AI context about your entire project
- Use `@docs` to reference documentation
- Create custom rules for your coding standards

## Common Issues

**"Model not responding"**

- Check your API key in settings
- Verify your subscription status
- Try switching to a different model

**"Rules not loading"**

- Ensure rules are in `.cursor/rules/` directory
- Check file extension is `.mdc`
- Restart Cursor after adding rules

## Community Resources

- [agents-environment-config](../../resources/agents-environment-config.md) - Shared Cursor configurations
- [Cursor Rules Guide](../../resources/cursor-rules.md) - How to write effective rules

---

!!! note "Help Improve This Page"
    Know a tip that's not listed? Found a helpful video tutorial? [Contribute to this page](../../community/contributing.md).
