# Contributing to Vibecoding

We welcome contributions from everyone in the letsvibe.org community! This guide will help you get started.

## Ways to Contribute

### Documentation

The most impactful way to contribute is by improving our docs:

- **Fix typos and errors** - Even small corrections help!
- **Add examples** - Share prompts and patterns that work for you
- **Improve clarity** - Help make complex topics more accessible
- **Translate content** - Help make vibecoding accessible in more languages

### Share Your Knowledge

- **Write guides** - Share your expertise on specific topics
- **Add to the FAQ** - Contribute answers to common questions
- **Document tools** - Write about AI assistants we haven't covered

### Community Support

- **Answer questions** - Help others in discussions
- **Review pull requests** - Provide feedback on contributions
- **Report issues** - Let us know about problems or gaps

## Getting Started

### 1. Fork the Repository

```bash
# Fork via GitHub UI, then clone your fork
git clone https://github.com/YOUR-USERNAME/vibecoding.git
cd vibecoding
```

### 2. Set Up the Environment

```bash
# Create a virtual environment
python3 -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### 3. Run Locally

```bash
# Start the development server
mkdocs serve
```

Open http://localhost:8000 to see your changes live.

### 4. Make Your Changes

- Edit files in the `docs/` directory
- Add new pages by creating `.md` files
- Update `mkdocs.yml` to add new pages to navigation

### 5. Submit a Pull Request

```bash
# Create a branch for your changes
git checkout -b add-prompting-example

# Make your changes, then commit
git add .
git commit -m "docs: add example for debugging prompts"

# Push to your fork
git push origin add-prompting-example
```

Then open a Pull Request on GitHub.

## Writing Guidelines

### Style

- **Be concise** - Get to the point quickly
- **Use examples** - Show, don't just tell
- **Be inclusive** - Write for all skill levels
- **Stay practical** - Focus on actionable advice

### Formatting

Use MkDocs Material features for better readability:

```markdown
!!! tip "Pro Tip"

    Use admonitions to highlight important information.

=== "Python"

    ```python
    print("Use tabs for language-specific examples")
    ```

=== "JavaScript"

    ```javascript
    console.log("Like this!");
    ```
```

### Code Examples

- Include language identifiers in code blocks
- Make examples runnable when possible
- Use realistic, practical scenarios

## What We're Looking For

### High Priority

- [ ] More prompting examples and patterns
- [ ] Guides for specific programming languages
- [ ] Troubleshooting common issues
- [ ] Real-world case studies

### Always Welcome

- Typo fixes and clarity improvements
- Additional FAQ entries
- Tool comparisons and reviews
- Tips from your vibecoding experience

## Code of Conduct

All contributors must follow our [Code of Conduct](code-of-conduct.md). We're committed to maintaining a welcoming, inclusive community.

## Questions?

- Open a [Discussion](https://github.com/letsvibe/vibecoding/discussions) for questions
- Open an [Issue](https://github.com/letsvibe/vibecoding/issues) for bugs or suggestions
- Tag maintainers if you need help with your PR

Thank you for contributing to the vibecoding community!
