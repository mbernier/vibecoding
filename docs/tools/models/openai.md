# OpenAI / ChatGPT

> **Official Docs**: [platform.openai.com/docs](https://platform.openai.com/docs)
> **Category**: AI Model

OpenAI's GPT models power GitHub Copilot and many other AI coding tools.

## Quick Links

- [OpenAI Platform Documentation](https://platform.openai.com/docs)
- [API Reference](https://platform.openai.com/docs/api-reference)
- [OpenAI Developer Forum](https://community.openai.com/)
- [ChatGPT](https://chat.openai.com/)

!!! info "Used By"
    OpenAI models power [GitHub Copilot](../ides/vscode-copilot.md), [Cursor](../ides/cursor.md), [Codex CLI](../cli/codex.md), and [Aider](../cli/aider.md).

## Model Variants

| Model | Best For | Context Window |
|-------|----------|----------------|
| GPT-4 Turbo | Complex coding tasks | 128K tokens |
| GPT-4o | Balanced performance | 128K tokens |
| GPT-4o Mini | Cost-effective tasks | 128K tokens |
| o1 | Complex reasoning | Varies |

## API Setup

### Get an API Key

1. Create an account at [platform.openai.com](https://platform.openai.com/)
2. Navigate to API Keys
3. Create a new key
4. Set up billing

### Set Environment Variable

```bash
export OPENAI_API_KEY="sk-..."
```

Or add to your shell profile:

```bash
echo 'export OPENAI_API_KEY="sk-..."' >> ~/.zshrc
```

## Tips & Tricks

!!! tip "Community Tips"
    This section collects tips from real users. [Contribute your tips](../../community/contributing.md)!

**Model selection:**

- **GPT-4 Turbo**: Best for complex coding tasks
- **GPT-4o**: Good balance of speed and capability
- **GPT-4o Mini**: Cost-effective for simpler tasks
- **o1**: Use for problems requiring deep reasoning

**Prompting tips:**

- Be specific about the programming language and framework
- Provide examples of desired output format
- Use system prompts to set coding style preferences

## Common Issues

**"Rate limited"**

- Check your tier and limits at platform.openai.com
- Implement exponential backoff
- Consider upgrading your tier

**"Unexpected behavior"**

- GPT models can be more creative/variable than Claude
- Be more explicit in your instructions
- Consider using a system prompt for consistency

## Community Resources

- [OpenAI Developer Forum](https://community.openai.com/)
- [r/OpenAI](https://reddit.com/r/OpenAI)
- [OpenAI Discord](https://discord.gg/openai)

---

!!! note "Help Improve This Page"
    Know a tip that's not listed? Found a helpful video tutorial? [Contribute to this page](../../community/contributing.md).
