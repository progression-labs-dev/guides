# Progression Labs Guides

Operational guides for Progression Labs.

Guides live in `guides/` as Markdown files with YAML frontmatter. The [internal portal](https://github.com/progression-labs/internal-portal) reads from this repo at build time.

## Guides

| Guide | Description |
|-------|-------------|
| [offboarding](guides/offboarding.md) | Checklist for revoking access when someone leaves the team |
| [onboarding](guides/onboarding.md) | New hire checklist — accounts, tooling, and getting up to speed |
| [security](guides/security.md) | Protecting our critical accounts (Google, AWS, GitHub) |
| [security-gcp](guides/security-gcp.md) | Security best practices for Google Cloud Platform |
| [security-training](guides/security-training.md) | AI-specific security training for all engineers |

## Frontmatter Schema

```yaml
---
id: onboarding
title: "New Hire Onboarding"
category: People
author: Chris Little
lastUpdated: "2026-02-25"
summary: "Checklist for getting new hires set up and productive"
---
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `id` | string | yes | Kebab-case unique identifier (matches filename) |
| `title` | string | yes | Human-readable title |
| `category` | string | yes | Grouping category |
| `author` | string | yes | Guide author |
| `lastUpdated` | string | yes | ISO date of last update |
| `summary` | string | yes | One-line description |
