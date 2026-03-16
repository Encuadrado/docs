# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Centralized Mintlify documentation site for Encuadrado, covering multiple repos. Pages are MDX files with YAML frontmatter. Site configuration lives in `docs.json`.

Each repo's docs live in their own subdirectory (e.g., `web/`). Navigation tabs in `docs.json` map to repos. When adding a new repo, create a new subdirectory and add corresponding tabs in `docs.json`.

## Common commands

```bash
# Install CLI (requires Node.js 19+)
npm i -g mint

# Local preview at http://localhost:3000
mint dev

# Check for broken links
mint broken-links

# Update CLI to latest version
npm mint update
```

## Structure

- `docs.json` — central config: navigation tabs/groups, theme colors, logo, footer
- `web/` — Encuadrado Web (Flask) repo docs
  - `introduction.mdx`, `quickstart.mdx` — getting started
  - `architecture/` — overview, modules, models, frontend
  - `guides/` — testing, style-guide, background-jobs, contributing
  - `deployment/` — docker, ci-cd, infrastructure
  - `api-reference/` — 13 endpoint docs by domain (Core, Payments, Clinical, Communication)

## Navigation

Navigation is defined in `docs.json` under `navigation.tabs`. Each repo gets its own tab(s):
- **Web** — Getting started, Architecture, Guides, Deployment
- **Web API** — Overview, Core, Payments, Clinical, Communication

Every new page must be added to the appropriate group in `docs.json` to appear in the site.

## Writing conventions

- MDX with YAML frontmatter (`title`, `description`) at top of every page
- Active voice, second person ("you")
- Sentence case for headings
- Bold for UI elements: Click **Settings**
- Inline code for file names, commands, paths, and code references
- Use Mintlify components (`<Card>`, `<Steps>`, `<Accordion>`, `<Tip>`, `<Info>`, `<Frame>`, `<Columns>`, `<CardGroup>`, etc.)

## Deployment

Pushing to the default branch auto-deploys via the Mintlify GitHub app.
