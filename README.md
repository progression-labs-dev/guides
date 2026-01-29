# Palindrom Guides

Operational playbooks and how-to guides for Palindrom.

Guides live in `guides/` as Markdown files with YAML frontmatter. The [internal portal](https://github.com/palindrom-ai/internal-portal) reads from this repo at build time.

## Frontmatter Schema

```yaml
---
id: incident-response
title: Incident Response Playbook
category: Operations
author: Michael Ross
lastUpdated: "2024-03-10"
summary: Step-by-step guide for handling production incidents
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
