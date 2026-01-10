# Codex CLI

> **Official Docs**: [openai.github.io/codex-cli](https://openai.github.io/codex-cli/)
> **Category**: CLI

OpenAI's Codex CLI is a command-line tool for AI-assisted coding using OpenAI's models.

## Quick Links

- [GitHub Repository](https://github.com/openai/codex-cli)
- [OpenAI Documentation](https://platform.openai.com/docs)
- [OpenAI Community](https://community.openai.com/)

!!! info "Works With"
    Codex CLI uses [OpenAI models](../models/openai.md) including GPT-4 and GPT-4 Turbo.

## Configuration

> See [Understanding Config Directories](../config-directories.md) for general concepts.

Codex CLI stores its configuration in `~/.codex/`:

| File | Purpose |
|------|---------|
| `config.toml` | Main configuration (TOML format) |

### Configuration File

```toml
# ~/.codex/config.toml
[model]
name = "gpt-4"
temperature = 0.7

[api]
key = "sk-..."  # Or use OPENAI_API_KEY env var
```

## Tips & Tricks

!!! tip "Community Tips"
    This section collects tips from real users. [Contribute your tips](../../community/contributing.md)!

*Tips coming soon! [Be the first to contribute](../../community/contributing.md).*

## Common Issues

**"API key invalid"**

- Check your OpenAI API key
- Verify billing is set up on OpenAI account
- Try regenerating the key

## Community Resources

- [OpenAI Community Forum](https://community.openai.com/)
- [OpenAI Discord](https://discord.gg/openai)

---

!!! note "Help Improve This Page"
    Know a tip that's not listed? Found a helpful video tutorial? [Contribute to this page](../../community/contributing.md).
