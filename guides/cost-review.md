---
id: cost-review
title: Monthly Cost Review
category: Finance
author: Ben Zhang
lastUpdated: "2024-02-15"
summary: Process for reviewing and optimizing cloud spend
---

## Monthly Cost Review

A repeatable process for reviewing cloud spend and identifying optimisation opportunities.

### Steps

1. Pull cost reports from AWS Cost Explorer
2. Compare against budget in Google Sheets
3. Identify top 5 cost drivers
4. Review any anomalies > 10% month-over-month
5. Propose optimisations to Engineering
6. Update forecast for next quarter

### Review Template

| Metric | Current | Budget | Variance |
|--------|---------|--------|----------|
| AWS Total | — | — | — |
| GCP Total | — | — | — |
| SaaS Total | — | — | — |
| **Grand Total** | — | — | — |

### Common Optimisations

- **Right-size EC2 instances** — Check CPU/memory utilisation over 14 days
- **Spot instances** — Use for batch jobs and non-critical workloads
- **Reserved instances** — Commit to 1-year terms for stable workloads
- **Storage tiering** — Move infrequently accessed data to S3 Glacier
- **Query optimisation** — Review Snowflake warehouse auto-suspend settings
