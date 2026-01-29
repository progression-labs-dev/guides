---
id: incident-response
title: Incident Response Playbook
category: Operations
author: Michael Ross
lastUpdated: "2024-03-10"
summary: Step-by-step guide for handling production incidents
---

## Incident Response Playbook

A structured approach to detecting, responding to, and resolving production incidents.

### Steps

1. **Detect** — Alert fires in PagerDuty
2. **Triage** — Assess severity (SEV1–4)
3. **Respond** — Page on-call, open incident channel
4. **Mitigate** — Apply known fix or rollback
5. **Resolve** — Verify fix, update status page
6. **Review** — Post-mortem within 48 hours

### Severity Levels

| Level | Description | Response Time | Example |
|-------|-------------|---------------|---------|
| SEV1 | Full outage or data loss | 15 minutes | Production database down |
| SEV2 | Major feature broken | 30 minutes | Payments failing |
| SEV3 | Minor feature broken | 2 hours | Search returning stale results |
| SEV4 | Cosmetic / low impact | Next business day | Typo on marketing page |

### Post-Mortem Template

Every SEV1 and SEV2 incident requires a post-mortem within 48 hours:

- **Timeline** — What happened and when
- **Root cause** — Why it happened
- **Impact** — Users affected, duration, revenue impact
- **Action items** — Concrete follow-ups with owners and deadlines
