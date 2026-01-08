# Quick Start Guide

Get up and running with vibecoding in minutes. This guide will help you set up your environment and start your first AI-assisted coding session.

## Prerequisites

Before you begin, you'll need:

- A code editor (VS Code, Cursor, or similar)
- Access to an AI coding assistant (Claude, ChatGPT, GitHub Copilot, etc.)
- Basic familiarity with your programming language of choice

## Step 1: Choose Your AI Assistant

There are several AI coding assistants available. Here are some popular options:

=== "Claude"

    Claude is Anthropic's AI assistant, available through:

    - [Claude.ai](https://claude.ai) - Web interface
    - [Claude Code](https://claude.ai/claude-code) - CLI tool for developers
    - API access for custom integrations

=== "GitHub Copilot"

    GitHub Copilot integrates directly into your editor:

    1. Install the Copilot extension for VS Code
    2. Sign in with your GitHub account
    3. Start typing and Copilot will suggest completions

=== "Cursor"

    Cursor is an AI-native code editor:

    1. Download from [cursor.sh](https://cursor.sh)
    2. Open your project
    3. Use `Cmd+K` (Mac) or `Ctrl+K` (Windows/Linux) to chat

## Step 2: Set Up Your Project

Create a workspace for your vibecoding experiments:

```bash
mkdir my-vibe-project
cd my-vibe-project
git init
```

## Step 3: Start a Conversation

The key to vibecoding is clear communication. Here's a template to get started:

```
I want to build [WHAT YOU WANT].

Context:
- I'm using [LANGUAGE/FRAMEWORK]
- This is for [PURPOSE/USE CASE]
- It should [KEY REQUIREMENTS]

Can you help me [SPECIFIC FIRST STEP]?
```

### Example Prompt

```
I want to build a simple REST API endpoint.

Context:
- I'm using Python with FastAPI
- This is for a todo list application
- It should handle CRUD operations for tasks

Can you help me create the basic project structure and a simple
GET endpoint that returns a list of tasks?
```

## Step 4: Iterate and Refine

After receiving a response:

1. **Review** - Read through the generated code
2. **Test** - Run it and see what happens
3. **Ask questions** - If something is unclear, ask for explanations
4. **Refine** - Request changes or improvements

### Useful Follow-up Prompts

- "Can you explain how [specific part] works?"
- "Can you add error handling to this?"
- "How would I test this?"
- "What are the security considerations?"
- "Can you refactor this to be more [readable/efficient/maintainable]?"

## Step 5: Build Your Workflow

As you get comfortable, develop your own vibecoding workflow:

1. **Start with intent** - What are you trying to accomplish?
2. **Provide context** - What does the AI need to know?
3. **Review critically** - Don't accept code blindly
4. **Iterate rapidly** - Make small changes and test often
5. **Document learnings** - Note patterns that work well

## Next Steps

- Explore [Prompting Strategies](../guides/prompting-strategies.md) for more effective AI interactions
- Learn about different [AI Coding Assistants](../guides/ai-coding-assistants.md)
- Read our [Best Practices](../guides/best-practices.md) guide

## Tips for Success

!!! tip "Be Specific"

    The more specific your prompts, the better the results. Instead of "make a function", try "create a Python function that validates email addresses using regex".

!!! tip "Provide Examples"

    When possible, show the AI what you want through examples of input/output or similar code patterns.

!!! tip "Break It Down"

    Large tasks work better when broken into smaller pieces. Ask for one component at a time.
