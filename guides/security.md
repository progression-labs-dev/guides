---
id: security
title: "Security"
category: Security
author: Chris Little
lastUpdated: "2026-02-25"
summary: "How we protect our most critical accounts"
---

# Security

Three accounts matter more than everything else: **Google**, **AWS**, and **GitHub**. If any one of them is compromised, the damage is catastrophic — stolen data, hijacked infrastructure, or supply-chain attacks on our code.

## Google Workspace

Google is the front door. It controls email, calendar, and SSO into most of our other tools.

- MFA is mandatory (hardware key preferred)
- SSO is the default path into third-party apps — don't create standalone passwords
- Review connected third-party apps quarterly and revoke anything unused

## AWS

AWS runs our production infrastructure. Unauthorized access means data exposure or service disruption.

- Console access goes through SSO with short-lived sessions
- IAM roles follow least privilege — request only what you need
- Root account credentials are locked away and used only for break-glass scenarios
- CloudTrail is always on; alerts fire on anomalous API calls

## GitHub

GitHub holds our source code and CI/CD pipelines. A compromised repo can ship malicious code to production.

- 2FA is required for every member of the org
- Branch protection is enforced on `main` — no direct pushes, all changes go through PR review
- Personal access tokens must be scoped and rotated regularly
- Dependabot and secret scanning are enabled on all repos
