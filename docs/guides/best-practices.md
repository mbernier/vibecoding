# Best Practices

Guidelines for effective and responsible vibecoding. These practices will help you get better results while maintaining code quality and security.

## Code Quality

### Always Review Generated Code

AI can generate code that looks correct but has subtle issues:

- **Logic errors** - The code runs but doesn't do what you expect
- **Performance issues** - Inefficient algorithms or unnecessary operations
- **Security vulnerabilities** - SQL injection, XSS, insecure defaults
- **Missing edge cases** - Happy path works, error cases don't

!!! danger "Never Commit Without Review"

    Treat AI-generated code like code from a junior developer - it needs review before going to production.

### Understand What You Ship

If you can't explain how code works, you shouldn't ship it:

```
Good: "I used this caching decorator because it memoizes expensive
      function calls and invalidates after 5 minutes."

Bad:  "The AI suggested this and it seems to work."
```

### Test Thoroughly

AI-generated code needs the same (or more) testing as human-written code:

- Unit tests for individual functions
- Integration tests for component interactions
- Edge case testing (empty inputs, large inputs, invalid data)
- Security testing for user-facing code

## Security

### Review for Vulnerabilities

Always check generated code for common security issues:

| Vulnerability | What to Look For |
|--------------|------------------|
| SQL Injection | String concatenation in queries |
| XSS | Unescaped user input in HTML |
| CSRF | Missing token validation |
| Auth bypass | Missing permission checks |
| Secrets | Hardcoded API keys or passwords |

### Don't Share Sensitive Data

Be careful what you include in prompts:

!!! warning "Never Include in Prompts"

    - API keys and secrets
    - Production database credentials
    - Customer data or PII
    - Proprietary business logic you don't want shared
    - Access tokens

### Sanitize Before Sharing

When pasting code for review, remove or redact:

```python
# Before
api_key = "sk-abc123realkey456"
db_url = "postgresql://user:realpassword@prod.server.com/db"

# After
api_key = "sk-REDACTED"  # Replace with your API key
db_url = "postgresql://user:password@localhost/db"
```

## Efficiency

### Break Down Large Tasks

Instead of asking for an entire application, break it down:

```
Step 1: "Help me design the data model"
Step 2: "Create the database schema"
Step 3: "Build the authentication system"
Step 4: "Add the core API endpoints"
Step 5: "Implement the frontend components"
```

### Provide Relevant Context

Give the AI what it needs, but not more:

```
Good: "I have a FastAPI app using SQLAlchemy. Here's my User model:
      [paste model]. I need to add an endpoint to update user profiles."

Bad:  [Pastes entire codebase of 50 files]
```

### Iterate Quickly

Don't try to get everything perfect in one prompt:

1. Get a working version
2. Test it
3. Refine with follow-up prompts
4. Repeat until satisfied

## Learning

### Ask for Explanations

Use AI to learn, not just to generate:

```
"Can you explain why you used a generator here instead of returning
a list? What are the trade-offs?"
```

### Compare Approaches

Learn about different solutions:

```
"Show me how to implement this using:
1. A class-based approach
2. A functional approach
3. Using a library

What are the pros and cons of each?"
```

### Document Your Learnings

Keep notes on patterns that work well:

```markdown
## Vibecoding Notes

### Effective Patterns
- Using docstrings first helps generate better implementations
- Breaking authentication into steps: validation, verification, token generation
- Asking for error handling separately improves code structure

### Lessons Learned
- Always verify regex patterns with edge cases
- Generated SQL needs review for N+1 queries
- Date handling needs explicit timezone specification
```

## Workflow

### Version Control Everything

Commit frequently so you can revert if needed:

```bash
git add .
git commit -m "feat: add user validation (AI-assisted)"
```

### Use Descriptive Commits

Indicate when AI assisted with the code:

```
feat: add email validation

- Validates email format using regex
- Checks for common typo domains
- AI-assisted implementation, reviewed for security
```

### Maintain Your Standards

AI should adapt to your codebase, not the other way around:

```
"Here's our code style guide: [summary]
Please follow these conventions in all code you generate."
```

## Checklist

Before shipping AI-generated code:

- [ ] I understand how this code works
- [ ] I've reviewed for security vulnerabilities
- [ ] I've tested with normal inputs
- [ ] I've tested with edge cases
- [ ] I've tested with invalid inputs
- [ ] The code follows project conventions
- [ ] The code is properly documented
- [ ] I've removed any sensitive data
- [ ] The code passes all existing tests
- [ ] I can explain this code in a code review
