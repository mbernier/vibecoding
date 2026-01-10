# VS Code + GitHub Copilot

> **Official Docs**: [docs.github.com/copilot](https://docs.github.com/en/copilot)
> **Category**: IDE Extension

GitHub Copilot brings AI code completion to Visual Studio Code, integrating with your existing VS Code workflow.

## Quick Links

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [Copilot Chat Extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-chat)

!!! info "Works With"
    GitHub Copilot is powered by [OpenAI's models](../models/openai.md), including GPT-4.

## Configuration

> See [Understanding Config Directories](../config-directories.md) for general concepts.

Copilot configuration lives in VS Code's settings:

| Setting Location | Purpose |
|------------------|---------|
| VS Code Settings | Enable/disable, keybindings |
| GitHub Account | Subscription, organization access |
| `.github/copilot-instructions.md` | Project-specific instructions |

### Project Instructions

Create a `.github/copilot-instructions.md` file in your repository to give Copilot context about your project:

```markdown
# Copilot Instructions

This is a React + TypeScript project using:
- React 18
- TypeScript 5
- Tailwind CSS

Prefer functional components with hooks.
Use TypeScript strict mode.
```

## Tips & Tricks

!!! tip "Community Tips"
    This section collects tips from real users. [Contribute your tips](../../community/contributing.md)!

**Keyboard shortcuts:**

- `Tab` - Accept suggestion
- `Esc` - Dismiss suggestion
- `Alt + ]` / `Alt + [` - Next/previous suggestion

**Getting better suggestions:**

- Write clear comments describing what you want
- Use descriptive function and variable names
- Keep files focused on single responsibilities

## Common Issues

**"Copilot not suggesting"**

- Check you're signed in to GitHub
- Verify your subscription is active
- Ensure the file type is supported

**"Suggestions are off-topic"**

- Add a `.github/copilot-instructions.md` file
- Write clearer comments before code
- Check if the context window is cluttered

## Community Resources

- [GitHub Copilot Community](https://github.com/orgs/community/discussions/categories/copilot)
- [VS Code Extension Marketplace](https://marketplace.visualstudio.com/)

---

!!! note "Help Improve This Page"
    Know a tip that's not listed? Found a helpful video tutorial? [Contribute to this page](../../community/contributing.md).
