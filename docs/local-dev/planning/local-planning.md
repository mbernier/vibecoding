# Local Planning

Effective planning is crucial for AI-assisted development. This guide covers approaches to planning your work locally, without external tools.

## Why Plan?

AI coding assistants work best when given clear direction:

- **Better results** - Clear plans lead to more accurate AI output
- **Less iteration** - Upfront planning reduces back-and-forth
- **Maintainable code** - Planned architecture beats ad-hoc decisions
- **Team alignment** - Documented plans help collaboration

## Planning Approaches

### 1. Markdown Planning Files

The simplest approach: write plans in markdown files in your project.

```
project/
├── plans/
│   ├── feature-auth.md
│   ├── refactor-api.md
│   └── bug-fix-123.md
├── src/
└── ...
```

**Example plan file:**

```markdown
# Feature: User Authentication

## Goal
Add email/password authentication with session management.

## Requirements
- [ ] Sign up with email/password
- [ ] Sign in with existing account
- [ ] Password reset flow
- [ ] Session management with JWT

## Technical Approach
- Use NextAuth.js for auth handling
- Store users in PostgreSQL via Prisma
- JWT tokens for API authentication

## Files to Create/Modify
- `src/app/api/auth/[...nextauth]/route.ts`
- `src/lib/auth.ts`
- `prisma/schema.prisma` (add User model)

## Open Questions
- Should we support OAuth providers initially?
- What's the session duration?
```

### 2. In-File Planning with Comments

For smaller tasks, plan directly in the code:

```typescript
// TODO: Implement user authentication
//
// Requirements:
// - Sign up with email/password
// - Sign in with existing account
// - Session management
//
// Approach:
// 1. Add User model to Prisma schema
// 2. Create auth API routes
// 3. Add session middleware

export async function signUp(email: string, password: string) {
  // Implementation coming...
}
```

### 3. CLAUDE.md as a Planning Tool

Use your project's `CLAUDE.md` to communicate plans to AI:

```markdown
# Project: My App

## Current Focus
Working on authentication feature. See `plans/feature-auth.md` for details.

## Conventions
...

## Recent Decisions
- Using NextAuth.js for auth (decided 2024-01-15)
- JWT for API tokens, sessions for web
```

### 4. Git Branch + Plan Pairing

Pair each feature branch with a planning document:

```bash
# Create branch
git checkout -b feature/user-auth

# Create plan
touch plans/feature-user-auth.md
```

## Planning Templates

### Feature Template

```markdown
# Feature: [Name]

## Problem
What problem does this solve?

## Solution
High-level approach.

## Requirements
- [ ] Requirement 1
- [ ] Requirement 2

## Technical Design
How will it be built?

## Files Affected
- `path/to/file.ts` - description
- `path/to/other.ts` - description

## Testing Strategy
How will it be tested?

## Rollout Plan
How will it be deployed?
```

### Bug Fix Template

```markdown
# Bug: [Description]

## Symptoms
What's happening?

## Root Cause
Why is it happening?

## Fix
What change will fix it?

## Files to Change
- `path/to/file.ts`

## Testing
How to verify the fix?

## Regression Prevention
How to prevent this in future?
```

### Refactoring Template

```markdown
# Refactor: [Name]

## Current State
What exists now?

## Desired State
What should it look like?

## Motivation
Why refactor?

## Approach
Step-by-step plan.

## Risk Assessment
What could go wrong?

## Rollback Plan
How to undo if needed?
```

## Working with AI

When planning with AI tools:

### Give Context First

```
I'm planning to add user authentication. Here's my plan:
[paste plan]

Please review and suggest improvements before we start coding.
```

### Use Plans as Checkpoints

```
We've completed steps 1-3 of the auth plan.
Current status: [describe]
Let's move to step 4: [describe]
```

### Update Plans Based on AI Feedback

AI might identify issues or improvements. Update your plans:

```markdown
## Technical Design

### Original Plan
- Use JWT stored in localStorage

### Updated (AI recommendation)
- Use HTTP-only cookies for better security
- Reasoning: Prevents XSS attacks from accessing tokens
```

## Organization Tips

### Folder Structure

```
plans/
├── completed/          # Done plans (for reference)
├── in-progress/        # Current work
│   ├── feature-auth.md
│   └── refactor-api.md
└── backlog/            # Future work
    ├── feature-notifications.md
    └── feature-analytics.md
```

### Naming Conventions

- `feature-[name].md` - New features
- `bug-[id]-[description].md` - Bug fixes
- `refactor-[name].md` - Refactoring
- `spike-[name].md` - Research/exploration

### Version Control

Commit plans alongside code:

```bash
git add plans/feature-auth.md
git commit -m "docs: add authentication feature plan"
```

## When to Use External Tools

Local planning works well for:

- Individual developers
- Small teams
- Simple to medium complexity
- When you want full control

Consider external tools like [BrainGrid](braingrid.md) when:

- You need structured requirement management
- Working with non-technical stakeholders
- Complex multi-phase projects
- When you want AI-assisted planning itself

[:octicons-arrow-right-24: Learn about BrainGrid](braingrid.md)

## Related Resources

- [Environment Setup](../environment-setup.md) - Set up your local environment
- [IDE vs CLI](../ide-vs-cli.md) - Choose your workflow
- [Config Directories](../../tools/config-directories.md) - Tool configuration
