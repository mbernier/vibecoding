# Prompting Strategies

Effective prompting is the foundation of vibecoding. This guide covers strategies to get better results from AI coding assistants.

## The Anatomy of a Good Prompt

A well-structured prompt typically includes:

1. **Context** - Background information the AI needs
2. **Task** - What you want to accomplish
3. **Constraints** - Limitations or requirements
4. **Format** - How you want the response structured

### Template

```
[CONTEXT]
I'm working on [project type] using [tech stack].
[Any relevant background or existing code]

[TASK]
I need to [specific goal].

[CONSTRAINTS]
- [Requirement 1]
- [Requirement 2]
- [Limitation]

[FORMAT]
Please provide [code/explanation/both] and [any specific formatting].
```

## Strategy 1: Be Specific

Vague prompts lead to generic responses. Compare:

!!! failure "Vague Prompt"

    "Write a function to handle users"

!!! success "Specific Prompt"

    "Write a Python function that validates user registration data. It should check that the email is valid, the password is at least 8 characters with at least one number and one special character, and the username contains only alphanumeric characters."

## Strategy 2: Provide Context

Context helps the AI understand your specific situation:

```
I'm building a REST API with FastAPI. The project uses SQLAlchemy
for the ORM and PostgreSQL as the database. We follow the repository
pattern for data access.

I need to add a new endpoint for user authentication. The endpoint
should accept email and password, verify against the database,
and return a JWT token.
```

## Strategy 3: Show Examples

When you have specific formatting or patterns in mind, show them:

```
I need a function similar to this style:

def existing_function(data: dict) -> Result:
    """Process the data and return a Result object."""
    validated = validate(data)
    processed = transform(validated)
    return Result(success=True, data=processed)

Create a similar function for handling payment processing.
```

## Strategy 4: Chain Your Prompts

Break complex tasks into a series of smaller prompts:

1. "Help me design the data model for a todo list app"
2. "Now let's create the database schema based on this model"
3. "Create CRUD operations for the Task model"
4. "Add an endpoint to get all tasks for a user"
5. "Add filtering and pagination to the tasks endpoint"

## Strategy 5: Ask for Explanations

Don't just ask for code - ask for understanding:

```
Create a function to debounce user input.
Please explain:
1. What debouncing is and why it's useful
2. How the implementation works
3. When I should use this pattern
```

## Strategy 6: Iterate with Feedback

Treat the AI as a collaborator:

```
That looks good, but I need a few changes:
1. Add type hints to all function parameters
2. Include error handling for network failures
3. Add logging for debugging purposes
```

## Strategy 7: Request Multiple Options

When you're not sure of the best approach:

```
I need to implement caching for my API responses.
Can you show me 2-3 different approaches with their pros and cons?
```

## Common Patterns

### Code Review

```
Please review this code and suggest improvements:
[paste code]

Focus on:
- Performance
- Readability
- Error handling
- Security
```

### Debugging

```
This code is throwing [error]. Here's the code:
[paste code]

And here's the full error:
[paste error]

What's causing this and how can I fix it?
```

### Refactoring

```
Here's a function that works but is hard to read:
[paste code]

Please refactor it to:
1. Be more readable
2. Follow [language] best practices
3. Add appropriate error handling
```

### Learning

```
I'm trying to understand [concept]. Can you:
1. Explain it in simple terms
2. Show a basic example
3. Show a more complex real-world example
4. Explain common mistakes to avoid
```

## Anti-Patterns to Avoid

!!! warning "Don't Do This"

    - **Too vague**: "Make it better"
    - **Too broad**: "Build me a complete e-commerce platform"
    - **Ambiguous**: "Fix the bug" (which bug?)
    - **Missing context**: Asking about code the AI hasn't seen
    - **Assuming knowledge**: Referencing project-specific terms without explanation
