# Environment Setup

Setting up your local environment for AI-assisted development involves configuring tools, API keys, and project settings.

## Prerequisites

Before starting, ensure you have:

- [ ] A code editor or IDE
- [ ] Terminal/command line access
- [ ] Git installed
- [ ] API keys for your chosen AI services

## API Keys

Most AI tools require API keys. Here's how to set them up:

### Anthropic (Claude)

1. Create account at [console.anthropic.com](https://console.anthropic.com/)
2. Generate API key
3. Set environment variable:

```bash
export ANTHROPIC_API_KEY="sk-ant-..."
```

### OpenAI

1. Create account at [platform.openai.com](https://platform.openai.com/)
2. Generate API key and set up billing
3. Set environment variable:

```bash
export OPENAI_API_KEY="sk-..."
```

### Google (Gemini)

1. Go to [Google AI Studio](https://aistudio.google.com/)
2. Generate API key
3. Set environment variable:

```bash
export GOOGLE_API_KEY="..."
```

## Persisting Environment Variables

Add keys to your shell profile so they persist:

=== "Zsh (macOS default)"
    ```bash
    # Add to ~/.zshrc
    export ANTHROPIC_API_KEY="sk-ant-..."
    export OPENAI_API_KEY="sk-..."

    # Reload
    source ~/.zshrc
    ```

=== "Bash"
    ```bash
    # Add to ~/.bashrc or ~/.bash_profile
    export ANTHROPIC_API_KEY="sk-ant-..."
    export OPENAI_API_KEY="sk-..."

    # Reload
    source ~/.bashrc
    ```

=== "Fish"
    ```fish
    # Add to ~/.config/fish/config.fish
    set -gx ANTHROPIC_API_KEY "sk-ant-..."
    set -gx OPENAI_API_KEY "sk-..."
    ```

=== "Windows (PowerShell)"
    ```powershell
    # Add to $PROFILE
    $env:ANTHROPIC_API_KEY = "sk-ant-..."
    $env:OPENAI_API_KEY = "sk-..."

    # Or set system-wide via System Properties
    ```

!!! warning "Security Note"
    Never commit API keys to git. Use environment variables or `.env` files (and add `.env` to `.gitignore`).

## Tool Installation

### IDEs

=== "Cursor"
    ```bash
    # Download from cursor.com
    # Or via Homebrew (macOS)
    brew install --cask cursor
    ```

=== "VS Code + Copilot"
    ```bash
    # Install VS Code
    brew install --cask visual-studio-code

    # Install Copilot extension from marketplace
    ```

=== "Windsurf"
    ```bash
    # Download from codeium.com/windsurf
    ```

### CLI Tools

=== "Claude Code"
    ```bash
    # Install via npm
    npm install -g @anthropic-ai/claude-code

    # Or via Homebrew
    brew install anthropic/tap/claude-code
    ```

=== "Aider"
    ```bash
    # Install via pip
    pip install aider-chat

    # Or via pipx (recommended)
    pipx install aider-chat
    ```

=== "Codex CLI"
    ```bash
    # Install via npm
    npm install -g @openai/codex-cli
    ```

## Configuration Directories

After installation, create your configuration directories:

```bash
# Create config directories
mkdir -p ~/.claude
mkdir -p ~/.cursor/rules

# Create global instructions
touch ~/.claude/CLAUDE.md
```

[:octicons-arrow-right-24: Config Directory Reference](../tools/config-directories.md)

## Project Setup

### Initialize a Project

```bash
# Create project directory
mkdir my-project && cd my-project

# Initialize git
git init

# Create AI instructions
touch CLAUDE.md  # For Claude Code
mkdir -p .cursor/rules  # For Cursor
```

### Project Instructions Template

Create a `CLAUDE.md` (or similar) in your project root:

```markdown
# Project: My App

## Tech Stack
- Next.js 14 with App Router
- TypeScript (strict mode)
- Prisma + PostgreSQL
- Tailwind CSS

## Conventions
- Use functional components with hooks
- Prefer server components where possible
- Follow existing code patterns

## Important Files
- `src/app/` - App router pages
- `src/lib/` - Shared utilities
- `prisma/schema.prisma` - Database schema
```

## Verification

Test your setup:

### Test API Keys

```bash
# Test Anthropic
curl https://api.anthropic.com/v1/messages \
  -H "x-api-key: $ANTHROPIC_API_KEY" \
  -H "anthropic-version: 2023-06-01" \
  -H "content-type: application/json" \
  -d '{"model":"claude-3-haiku-20240307","max_tokens":10,"messages":[{"role":"user","content":"Hi"}]}'
```

### Test Tools

```bash
# Test Claude Code
claude --version

# Test Aider
aider --version

# Open Cursor
cursor .
```

## Troubleshooting

### "API key not found"

1. Verify the key is set: `echo $ANTHROPIC_API_KEY`
2. Check for typos in variable name
3. Reload shell config: `source ~/.zshrc`

### "Command not found"

1. Verify installation: `which claude` or `which aider`
2. Check PATH includes install location
3. Try reinstalling the tool

### "Permission denied"

1. Check file permissions: `ls -la ~/.claude/`
2. Fix if needed: `chmod 755 ~/.claude/`

## Next Steps

- [Compare IDE vs CLI workflows](ide-vs-cli.md)
- [Explore available tools](../tools/index.md)
- [Set up shared configurations](../resources/agents-environment-config.md)
