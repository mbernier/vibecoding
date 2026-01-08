# Frequently Asked Questions

Common questions about vibecoding and this community resource.

## General Questions

### What is vibecoding?

Vibecoding is a development approach that embraces AI-assisted coding as a conversational, collaborative practice. Instead of writing code line-by-line, you describe what you want to build and iterate with AI to create solutions. See [What is Vibecoding?](getting-started/what-is-vibecoding.md) for more details.

### Is vibecoding just for beginners?

No! Developers at all levels benefit from vibecoding:

- **Beginners** - Learn patterns and best practices while building
- **Intermediate** - Accelerate development and learn new technologies
- **Senior** - Focus on architecture while delegating implementation details
- **All levels** - Reduce time on boilerplate and research

### Will AI replace developers?

No. AI coding assistants are tools that augment human developers, not replace them. You still need to:

- Understand the problem you're solving
- Make architectural decisions
- Review and validate generated code
- Consider security and performance
- Maintain and evolve the codebase

### Is it cheating to use AI for coding?

No more than using Stack Overflow, documentation, or autocomplete. The key is to:

- Understand the code you're using
- Review it thoroughly before shipping
- Continue learning the fundamentals
- Use AI to accelerate, not bypass, learning

## Using AI Assistants

### Which AI assistant should I use?

It depends on your needs:

- **For inline completions**: GitHub Copilot or Cursor
- **For complex reasoning**: Claude
- **For an AI-native editor**: Cursor
- **For quick questions**: ChatGPT

See [AI Coding Assistants](guides/ai-coding-assistants.md) for detailed comparisons.

### How do I get better results from AI?

1. Be specific about what you want
2. Provide relevant context
3. Show examples when possible
4. Iterate with follow-up prompts
5. Break large tasks into smaller pieces

See [Prompting Strategies](guides/prompting-strategies.md) for detailed guidance.

### Can I trust AI-generated code?

Treat it like code from an unfamiliar source - review it carefully. Always:

- Understand what the code does
- Test with various inputs
- Check for security vulnerabilities
- Verify it follows your project conventions

### What should I NOT share with AI assistants?

Never include in prompts:

- API keys and secrets
- Production credentials
- Customer data or PII
- Proprietary algorithms you want to protect

## This Documentation

### How do I contribute?

See our [Contributing Guide](community/contributing.md) for detailed instructions. In short:

1. Fork the repository
2. Make your changes
3. Submit a pull request

### Can I use this content elsewhere?

This project is open source - check the LICENSE file in the repository for specific terms.

### I found an error - how do I report it?

Options:

1. [Open an issue](https://github.com/letsvibe/vibecoding/issues) on GitHub
2. Submit a pull request with the fix
3. Start a [discussion](https://github.com/letsvibe/vibecoding/discussions)

### How do I run this documentation locally?

```bash
# Clone the repository
git clone https://github.com/letsvibe/vibecoding.git
cd vibecoding

# Set up Python environment
python3 -m venv .venv
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run locally
mkdocs serve
```

Then open http://localhost:8000 in your browser.

## Community

### How can I connect with other vibecoders?

- Join [GitHub Discussions](https://github.com/letsvibe/vibecoding/discussions)
- Follow updates at [letsvibe.org](https://letsvibe.org)
- Contribute to this documentation

### I have a question not covered here

Feel free to:

1. [Open a discussion](https://github.com/letsvibe/vibecoding/discussions) for general questions
2. [Open an issue](https://github.com/letsvibe/vibecoding/issues) for documentation improvements
3. Contribute a new FAQ entry via pull request

---

Don't see your question? [Ask in Discussions](https://github.com/letsvibe/vibecoding/discussions) and we may add it here!
