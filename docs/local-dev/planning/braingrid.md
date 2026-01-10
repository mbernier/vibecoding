# BrainGrid

BrainGrid is an AI-powered tool for transforming vague ideas into structured specifications and development tasks.

!!! tip "Support Our Community"
    Support community members by using their affiliate links:

    - **Matt Bernier**: [braingrid.link/matt-bernier](https://braingrid.link/matt-bernier)

    *Want to add your affiliate link? [Edit this page on GitHub](https://github.com/mbernier/vibecoding/edit/main/docs/local-dev/planning/braingrid.md) and submit a PR!*

## What is BrainGrid?

BrainGrid helps you go from "I want to build X" to actionable development tasks:

```
Vague idea → Structured specification → AI-ready tasks
```

It's particularly useful when:

- You have a fuzzy idea that needs structure
- You want AI to help refine requirements
- You need tasks formatted for AI coding agents
- You're working with non-technical stakeholders

## Local Planning vs BrainGrid

| Aspect | Local Planning | BrainGrid |
|--------|---------------|-----------|
| **Setup** | Just markdown files | External service |
| **AI assistance** | Manual prompting | Built-in refinement |
| **Collaboration** | Git-based | Web-based |
| **Structure** | Flexible | Standardized |
| **Cost** | Free | Subscription |
| **Best for** | Individual devs, simple projects | Teams, complex requirements |

## When to Use BrainGrid

**Good fit:**

- Complex features with many requirements
- Cross-functional teams
- When you need AI help structuring thoughts
- Projects requiring formal documentation

**May be overkill:**

- Quick bug fixes
- Personal projects
- Simple, well-understood features
- When you prefer local control

## BrainGrid Workflow

### 1. Start with a Prompt

```
/specify "Add user authentication with OAuth support"
```

BrainGrid uses AI to ask clarifying questions and structure your requirements.

### 2. Get Structured Specification

The output is a detailed spec including:

- Goals and success criteria
- Technical requirements
- Edge cases
- Testing requirements

### 3. Break Down into Tasks

```
/breakdown REQ-123
```

Creates AI-ready tasks that can be fed to coding agents.

### 4. Execute Tasks

Each task is formatted to work with AI coding tools like Claude Code, Cursor, or Aider.

## Integration with Local Development

BrainGrid complements local workflows:

```
┌─────────────────────────────────────────────┐
│  BrainGrid                                  │
│  ├─ Define requirements                     │
│  ├─ Generate tasks                          │
│  └─ Export specs                            │
├─────────────────────────────────────────────┤
│  Local Development                          │
│  ├─ Import specs to plans/                  │
│  ├─ Execute with AI tools                   │
│  └─ Track progress locally                  │
└─────────────────────────────────────────────┘
```

### Example Integration

1. Define requirement in BrainGrid
2. Export specification as markdown
3. Save to `plans/` in your project
4. Reference in CLAUDE.md
5. Execute with your preferred tool

## Getting Started

1. **Sign up** at [braingrid.io](https://braingrid.link/matt-bernier) (affiliate link)
2. **Install CLI** (optional): `npm install -g @braingrid/cli`
3. **Link project**: `braingrid init`
4. **Start specifying**: `/specify "your idea"`

## CLI Commands Reference

```bash
# Authentication
braingrid login                    # OAuth login
braingrid whoami                   # Show current user

# Specifications
braingrid specify --prompt "..."   # Create requirement
braingrid requirement show REQ-123 # View requirement
braingrid requirement build REQ-123 --format markdown

# Tasks
braingrid requirement breakdown REQ-123  # Generate tasks
braingrid task list -r REQ-123          # List tasks
braingrid task update TASK-456 --status COMPLETED
```

## Tips

- Start broad, then refine
- Use `/specify` for initial ideation
- Use `/breakdown` when requirements are stable
- Export to markdown for local reference
- Combine with git branches for traceability

## Alternatives

If BrainGrid isn't right for you, consider:

- **[Local Planning](local-planning.md)** - Markdown files in your repo
- **Linear/Jira** - Traditional project management
- **Notion** - Flexible documentation
- **GitHub Issues** - Native to your repository

## Related Resources

- [Local Planning Guide](local-planning.md) - Markdown-based planning
- [Environment Setup](../environment-setup.md) - Set up your dev environment
- [AI Tools Overview](../../tools/index.md) - Coding tools to execute tasks

---

!!! note "Affiliate Disclosure"
    Some links on this page are affiliate links. Using them supports the vibecoding community at no extra cost to you.
