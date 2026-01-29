---
id: security-review
title: Vendor Security Review
category: Security
author: Tom Anderson
lastUpdated: "2024-02-28"
summary: How to evaluate vendor security posture
---

## Vendor Security Review

Process for evaluating a third-party vendor's security posture before procurement.

### Steps

1. Request SOC 2 report or equivalent
2. Review data handling practices
3. Check SSO/SAML support
4. Assess data residency requirements
5. Document findings in vendor registry
6. Approve, request changes, or reject

### Evaluation Criteria

| Area | Requirement | Weight |
|------|-------------|--------|
| Compliance | SOC 2 Type II or ISO 27001 | High |
| Authentication | SSO/SAML support | High |
| Data residency | EU or configurable region | Medium |
| Encryption | At rest and in transit | High |
| Incident response | Documented process, SLA | Medium |
| Sub-processors | Disclosed list, notification of changes | Low |

### Decision Framework

- **Approve** — Meets all High requirements, most Medium
- **Conditional** — Missing one Medium requirement; vendor commits to timeline
- **Reject** — Missing any High requirement with no remediation plan

### Documentation

All vendor reviews must be recorded in the vendor registry with:

- Review date and reviewer
- Compliance certifications verified
- Data handling summary
- Decision and rationale
