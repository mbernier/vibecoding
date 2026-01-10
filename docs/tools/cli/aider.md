# Aider

> **Official Docs**: [aider.chat](https://aider.chat/)
> **Category**: CLI

Aider is an open-source AI pair programming tool that works in your terminal. It supports multiple AI models and integrates with git.

## Quick Links

- [Official Website](https://aider.chat/)
- [GitHub Repository](https://github.com/paul-gauthier/aider)
- [Documentation](https://aider.chat/docs/)
- [Discord Community](https://discord.gg/Tv2uQnR88V)

!!! info "Works With"
    Aider supports multiple models including [Claude](../models/claude.md), [GPT-4](../models/openai.md), and local models via Ollama.

## Configuration

> See [Understanding Config Directories](../config-directories.md) for general concepts.

Aider can be configured via:

| Method | Location |
|--------|----------|
| Command line flags | Per-session |
| Environment variables | `AIDER_*` variables |
| Config file | `.aider.conf.yml` in project or home |
| Git config | `.aider` section in `.git/config` |

### Configuration File

```yaml
# ~/.aider.conf.yml or project/.aider.conf.yml
model: claude-3-5-sonnet-20241022
auto-commits: true
dark-mode: true
```

### Environment Variables

```bash
export ANTHROPIC_API_KEY="sk-ant-..."
export OPENAI_API_KEY="sk-..."
export AIDER_MODEL="claude-3-5-sonnet-20241022"
```

## Tips & Tricks

!!! tip "Community Tips"
    This section collects tips from real users. [Contribute your tips](../../community/contributing.md)!

**Useful commands:**

- `/add file.py` - Add file to context
- `/drop file.py` - Remove file from context
- `/undo` - Undo last change
- `/diff` - Show pending changes
- `/commit` - Commit changes

**Workflow tips:**

- Start with small, focused changes
- Use `/add` to give Aider context about related files
- Review diffs before committing
- Aider auto-commits by default - use `--no-auto-commits` if you prefer manual control

**Model selection:**

```bash
# Use Claude
aider --model claude-3-5-sonnet-20241022

# Use GPT-4
aider --model gpt-4-turbo

# Use local model via Ollama
aider --model ollama/codellama
```

## Common Issues

**"Model not found"**

- Check you have the correct API key set
- Verify the model name is correct
- For Ollama, ensure the model is downloaded

**"Git repository required"**

- Aider works best in git repos
- Initialize with `git init` if needed
- Or use `--no-git` flag

**"Context too large"**

- Use `/drop` to remove unnecessary files
- Be selective about which files to `/add`
- Consider using a model with larger context

## Community Resources

- [Aider Discord](https://discord.gg/Tv2uQnR88V) - Active community
- [GitHub Discussions](https://github.com/paul-gauthier/aider/discussions)
- [Aider Blog](https://aider.chat/blog/)

---

!!! note "Help Improve This Page"
    Know a tip that's not listed? Found a helpful video tutorial? [Contribute to this page](../../community/contributing.md).
