# Cursor Rules Guide

Cursor rules (`.mdc` files) customize how Cursor's AI behaves in your projects. They define coding standards, patterns, and instructions that the AI follows.

## What Are Cursor Rules?

Cursor rules are markdown files with special frontmatter that tell Cursor how to behave:

```markdown
---
description: TypeScript strict mode standards
alwaysApply: false
globs:
  - "**/*.ts"
  - "**/*.tsx"
---

# TypeScript Standards

- Use strict mode
- No `any` types
- Explicit return types on public functions
```

## Rule Locations

| Location | Scope | Use For |
|----------|-------|---------|
| `~/.cursor/rules/` | Global | Your personal standards |
| `project/.cursor/rules/` | Project | Team/project standards |

Project rules take precedence when they conflict with global rules.

## Anatomy of a Rule

```markdown
---
description: Brief description of what this rule does
alwaysApply: true          # Apply to all files?
globs:                      # Or apply to specific patterns
  - "**/*.ts"
  - "**/*.tsx"
tags:
  - typescript
  - frontend
---

# Rule Title

Your rule content in markdown...

## Section 1
Guidelines...

## Section 2
More guidelines...
```

### Frontmatter Options

| Field | Type | Description |
|-------|------|-------------|
| `description` | string | Brief description (shown in UI) |
| `alwaysApply` | boolean | If true, applies to all files |
| `globs` | array | File patterns to match (if not alwaysApply) |
| `tags` | array | Categorization tags |

## Creating Rules

### Step 1: Create the Directory

```bash
mkdir -p ~/.cursor/rules
# or for project-specific
mkdir -p .cursor/rules
```

### Step 2: Create a Rule File

```bash
touch ~/.cursor/rules/my-standards.mdc
```

### Step 3: Write Your Rule

```markdown
---
description: My coding standards
alwaysApply: true
---

# My Coding Standards

## Code Style
- Use 2-space indentation
- Prefer const over let
- Use descriptive variable names

## Comments
- Comment complex logic
- Use JSDoc for public functions
```

### Step 4: Restart Cursor

Rules are loaded when Cursor starts. Restart to pick up changes.

## Rule Examples

### TypeScript Standards

```markdown
---
description: TypeScript strict typing standards
alwaysApply: false
globs:
  - "**/*.ts"
  - "**/*.tsx"
---

# TypeScript Standards

## Zero Tolerance for `any`
- NEVER use `any` type
- Prefer `unknown` when type is truly unknown
- Always define explicit types for function parameters

## Type Safety
- Enable strict mode in tsconfig.json
- Explicit return types on public functions
- Use proper interface/type definitions

## React Components
- All props must be typed
- Use `React.FC<Props>` or explicit prop types
```

### Python Style

```markdown
---
description: Python code style and conventions
alwaysApply: false
globs:
  - "**/*.py"
---

# Python Standards

## Formatting
- Follow PEP 8
- Use Black formatter (line length 88)
- Use type hints everywhere

## Imports
- Group: standard library, third-party, local
- Use absolute imports

## Documentation
- Google-style docstrings
- Document all public functions
```

### Project Architecture

```markdown
---
description: Project architecture and patterns
alwaysApply: true
---

# Architecture Guidelines

## Directory Structure
- `src/app/` - Next.js app router pages
- `src/components/` - React components
- `src/lib/` - Utilities and helpers
- `src/types/` - TypeScript types

## Patterns
- Use server components by default
- Client components only when needed (state, effects)
- Prefer composition over inheritance

## Naming
- PascalCase for components
- camelCase for functions and variables
- SCREAMING_SNAKE for constants
```

## Organization

### Recommended Structure

```
.cursor/rules/
├── general/
│   ├── architecture.mdc
│   ├── documentation.mdc
│   └── security.mdc
├── languages/
│   ├── typescript.mdc
│   └── python.mdc
├── frameworks/
│   ├── nextjs.mdc
│   └── react.mdc
└── project/
    └── conventions.mdc
```

### Naming Conventions

- Use descriptive, lowercase names
- Use hyphens for spaces
- Group related rules in directories

## Community Rules

The [agents-environment-config](agents-environment-config.md) repository includes 43+ pre-built rules:

- Architecture and design patterns
- Language-specific standards (TypeScript, Python)
- Framework patterns (Next.js, FastAPI, React Native)
- Testing standards
- Security guidelines
- Git workflow

[:octicons-arrow-right-24: Get community rules](agents-environment-config.md)

## Best Practices

### Keep Rules Focused

❌ One giant rule file with everything

✅ Multiple focused rules by topic

### Be Specific

❌ "Write good code"

✅ "Use TypeScript strict mode, no `any` types, explicit return types"

### Include Examples

```markdown
## Naming Conventions

### Good
```typescript
const userProfile = getUserProfile();
const isAuthenticated = checkAuth();
```

### Bad
```typescript
const x = getUP();
const flag = check();
```
```

### Update Regularly

Rules should evolve with your codebase. Review and update periodically.

## Troubleshooting

### "Rule not being applied"

1. Check file extension is `.mdc`
2. Verify glob patterns match your files
3. Restart Cursor
4. Check for syntax errors in frontmatter

### "Conflicting rules"

Project rules override global rules. Be intentional about what goes where.

### "Rules too verbose"

The AI reads entire rules. Keep them concise but complete.

## Related Resources

- [Cursor Setup](../tools/ides/cursor.md) - Full Cursor configuration
- [agents-environment-config](agents-environment-config.md) - Pre-built rules
- [Config Directories](../tools/config-directories.md) - Where configs live
