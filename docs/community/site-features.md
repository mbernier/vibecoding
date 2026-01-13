---
description: Documentation site features including comments, RSS feeds, print/PDF export, and tools for contributors.
comments: true
---

# Site Features

This page documents the features available on the Vibecoding documentation site, including how to use them when contributing.

## For Readers

### Comments (Giscus)

Pages can have comments powered by [Giscus](https://giscus.app/), which uses GitHub Discussions as the backend.

- Comments appear at the bottom of enabled pages
- Sign in with your GitHub account to comment
- Discussions are stored in the [vibecoding repository](https://github.com/mbernier/vibecoding/discussions)

### RSS Feeds

Subscribe to updates via RSS:

| Feed | URL | Description |
|------|-----|-------------|
| New Content | [/feed.xml](/feed.xml) | New pages added to the site |
| Updated Content | [/feed-updated.xml](/feed-updated.xml) | Recently modified pages |
| JSON Feed | [/feed_json_created.json](/feed_json_created.json) | JSON format for new content |

### Print / PDF Export

Need an offline copy? Use the **Print / PDF** option in the navigation to:

- View all documentation on a single page
- Print to PDF using your browser (File > Print > Save as PDF)
- Save as standalone HTML

### LLM-Friendly Documentation

For AI assistants, we provide:

| File | URL | Description |
|------|-----|-------------|
| llms.txt | [/llms.txt](/llms.txt) | Index of all documentation |
| llms-full.txt | [/llms-full.txt](/llms-full.txt) | Complete documentation in one file |

These follow the [llmstxt.org](https://llmstxt.org/) specification.

## For Contributors

When writing documentation, you have access to several powerful features.

### Enabling Comments on Pages

Add `comments: true` to a page's front matter:

```yaml
---
description: Your SEO description here (50-160 characters)
comments: true
---

# Page Title

Your content here...
```

!!! tip "When to Enable Comments"
    Enable comments on pages where discussion adds value:

    - Guide pages (feedback, questions)
    - FAQ (follow-up questions)
    - Contributing guide (help requests)
    - Tool pages (tips from users)

### SEO Meta Descriptions

Every page should have a `description` in front matter for SEO:

```yaml
---
description: Brief description of the page content (50-160 characters recommended)
---
```

The site automatically generates meta tags from:

1. **Front matter description** (preferred)
2. **First paragraph** (fallback)

!!! warning "Description Length"
    Keep descriptions between 50-160 characters. The build will warn if descriptions are too short or too long.

### Embedding Tables from Files

Use the table-reader plugin to embed CSV, Excel, or JSON tables:

{% raw %}
```markdown
<!-- Embed a CSV file as a table -->
{{ read_csv('path/to/data.csv') }}

<!-- Embed an Excel file -->
{{ read_excel('path/to/data.xlsx') }}

<!-- Embed specific sheet from Excel -->
{{ read_excel('path/to/data.xlsx', sheet_name='Sheet2') }}
```
{% endraw %}

File paths are resolved relative to the `docs/` directory.

### Using Macros and Variables

The macros plugin allows variables and templates:

{% raw %}
```markdown
<!-- Show current date -->
Last updated: {{ now().strftime('%Y-%m-%d') }}

<!-- Access site configuration -->
Site name: {{ config.site_name }}
Site URL: {{ config.site_url }}
```
{% endraw %}

Available variables:

| Variable | Description |
|----------|-------------|
| `config` | MkDocs configuration |
| `environment` | Build environment info |
| `git` | Git repository info |
| `now()` | Current datetime |

### Page Contributors

The site automatically shows contributors at the bottom of each page, pulled from git history. No configuration needed - just commit your changes!

## Plugin Reference

| Plugin | Purpose | Documentation |
|--------|---------|---------------|
| **rss** | RSS/JSON feeds | [mkdocs-rss-plugin](https://guts.github.io/mkdocs-rss-plugin/) |
| **git-committers** | Show contributors | [mkdocs-git-committers-plugin-2](https://github.com/ojacques/mkdocs-git-committers-plugin-2) |
| **print-site** | PDF export | [mkdocs-print-site-plugin](https://timvink.github.io/mkdocs-print-site-plugin/) |
| **macros** | Variables/templates | [mkdocs-macros-plugin](https://mkdocs-macros-plugin.readthedocs.io/) |
| **table-reader** | Embed tables | [mkdocs-table-reader-plugin](https://timvink.github.io/mkdocs-table-reader-plugin/) |
| **meta-descriptions** | SEO meta tags | [mkdocs-meta-descriptions-plugin](https://github.com/prcr/mkdocs-meta-descriptions-plugin) |
| **llmstxt** | LLM-friendly docs | [mkdocs-llmstxt](https://github.com/pawamoy/mkdocs-llmstxt) |
| **glightbox** | Image lightbox | [mkdocs-glightbox](https://github.com/blueswen/mkdocs-glightbox) |
| **minify** | HTML/CSS/JS minification | [mkdocs-minify-plugin](https://github.com/byrnereese/mkdocs-minify-plugin) |

## Environment Variables

These control optional features during build:

| Variable | Default | Effect |
|----------|---------|--------|
| `ENABLE_SOCIAL_CARDS` | `false` | Generate social media preview images |
| `ENABLE_OPTIMIZE` | `false` | Compress images |
| `ENABLE_PRINT_SITE` | `true` | Include print/PDF page |
