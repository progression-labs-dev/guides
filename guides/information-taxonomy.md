---
id: information-taxonomy
title: Information Taxonomy
category: Architecture
author: Sarah Chen
lastUpdated: "2025-01-29"
summary: How we classify and locate every piece of information in the company — by type, change frequency, and audience
---

## Information Taxonomy

Every piece of information is classified along two dimensions: **type** and **change frequency**.

### Dimension 1 — Type

| Type | Description | Example Question |
|------|-------------|-----------------|
| **Knowledge** | Reference information. Authored, curated, has an owner. | "Who owns the billing system?" |
| **State** | Current reality. System-fed, read-only. | "Is production up?" |
| **Process** | How work gets done. Workflows, forms, procedures. | "How do I book a holiday?" |

### Dimension 2 — Change Frequency

| Frequency | Characteristics | Tolerance for Staleness |
|-----------|----------------|------------------------|
| **Static** | Changes rarely. High accuracy. Curated and deliberate. | Low — wrong info causes real problems |
| **Dynamic** | Changes often. Can be messy, evolving, in-progress. | High — may be outdated, that's acceptable |

### Where Things Live

| System | What | Examples |
|--------|------|----------|
| Portal: PostgreSQL | Structured entities | People, projects, apps, contracts, secrets, decisions |
| Portal: Git + Markdown | Canonical prose | Values, guides, specs |
| Portal: Dashboards | Live state | Service health, spend, key expiry, alerts |
| Portal: Built-in workflows | Stable processes | Holiday, expenses, access requests |
| Notion | Everything dynamic | Working docs, evolving processes, research, records |

### Audience Tiers

- **Member** (all employees): People directory, values, guides, OKRs, vendor contacts
- **Developer** (engineers): + secrets, environments, service health, infrastructure, compliance
- **Admin** (principals, C-suite): + full cost/billing, contracts, all audit logs, system settings

### Graduation

Content moves from dynamic to static when it stabilises. The author decides. Triggers:

- Unchanged for 6+ months
- Decision accepted
- Spec finalised
- People keep asking where the doc is
