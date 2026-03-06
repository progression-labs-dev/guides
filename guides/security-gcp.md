---
id: security-gcp
title: "GCP Security"
category: Security
author: Chris Little
lastUpdated: "2026-03-02"
summary: "Security best practices for Google Cloud Platform"
---

# GCP Security

GCP is our primary cloud provider. A misconfigured project or leaked service account key can expose client data, run up costs, or give an attacker a foothold into everything we run.

## IAM

Identity and Access Management is the most important layer. Get this wrong and nothing else matters.

- Follow least privilege — grant predefined roles at the narrowest scope possible (project > folder > org)
- Prefer Workload Identity Federation over service account keys; keys are static secrets that leak easily
- If a service account key is unavoidable, rotate it regularly and never commit it to a repo
- Use groups for role assignments instead of granting roles to individual accounts
- Audit IAM bindings quarterly — remove any permissions that are no longer needed
- Avoid `roles/owner` and `roles/editor` on production projects; use specific roles instead

## VPC and Firewalls

- Default VPC rules are too permissive — always define explicit firewall rules
- Deny all ingress by default; allow only what's required
- Use VPC Service Controls to create security perimeters around sensitive projects
- Enable VPC Flow Logs for network traffic visibility

## Secret Manager

- All secrets go in Secret Manager — never in environment variables, config files, or source code
- Grant `secretmanager.secretAccessor` only to the service accounts that need each secret
- Enable automatic rotation where the downstream service supports it
- Audit access logs to verify secrets aren't being read by unexpected principals

## Audit Logging

- Cloud Audit Logs (Admin Activity and Data Access) must be enabled on all production projects
- Export audit logs to a centralized logging sink that's write-once (separate project with restricted access)
- Set up alerts for high-risk events: IAM policy changes, service account key creation, firewall rule modifications
- Retain logs for at least 12 months

## GKE and Cloud Run

- GKE clusters use Workload Identity so pods never need service account keys
- Enable Binary Authorization to ensure only trusted container images run in production
- Run containers as non-root with read-only filesystems where possible
- Cloud Run services should have ingress restricted to internal traffic or load balancers — not `all`
- Keep node pools and base images up to date with auto-upgrade enabled

## Artifact Registry

- Use Artifact Registry (not Container Registry) for all container images and packages
- Restrict push access to CI/CD service accounts; developers get read-only
- Enable vulnerability scanning on all repositories
- Clean up untagged and old images on a schedule to reduce attack surface

## Billing and Budget Controls

- Set budget alerts at 50%, 80%, and 100% of expected monthly spend on every project
- Route billing alerts to a shared channel so the whole team sees them
- Use quotas to cap resource usage on non-production projects
- Review billing reports monthly — unexpected spikes often indicate misconfiguration or compromise
