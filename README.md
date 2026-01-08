# Vibecoding

Open source knowledge base for the [letsvibe.org](https://letsvibe.org) community. Learn AI-assisted coding, prompting strategies, and collaborative development practices.

## Quick Start

### View the Documentation

Visit the live documentation at: **[https://letsvibe.org](https://letsvibe.org)** (or wherever deployed)

### Run Locally

```bash
# Clone the repository
git clone https://github.com/letsvibe/vibecoding.git
cd vibecoding

# Create and activate a virtual environment
python3 -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Start the development server
mkdocs serve
```

Open http://localhost:8000 to view the documentation.

### Build for Production

```bash
mkdocs build
```

The static site will be generated in the `site/` directory.

## Project Structure

```
vibecoding/
├── docs/                    # Documentation source files
│   ├── index.md            # Home page
│   ├── getting-started/    # Getting started guides
│   ├── guides/             # In-depth guides
│   ├── community/          # Community resources
│   └── faq.md             # Frequently asked questions
├── mkdocs.yml              # MkDocs configuration
├── requirements.txt        # Python dependencies
└── README.md              # This file
```

## Contributing

We welcome contributions from the community! See [Contributing Guide](docs/community/contributing.md) for details.

### Quick Contribution

1. Fork this repository
2. Make your changes in the `docs/` directory
3. Submit a pull request

## License

See [LICENSE](LICENSE) for details.

## Community

- [GitHub Discussions](https://github.com/letsvibe/vibecoding/discussions)
- [letsvibe.org](https://letsvibe.org)
