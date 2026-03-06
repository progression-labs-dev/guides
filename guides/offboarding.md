---
id: offboarding
title: "Offboarding"
category: People
author: Chris Little
lastUpdated: "2026-03-02"
summary: "Checklist for revoking access when someone leaves the team"
---

# Offboarding

When someone leaves, every hour of lingering access is a risk. This checklist should be completed within one business day of departure. The departing engineer's manager is responsible for driving it to completion.

## Access Revocation

- [ ] **Google Workspace** — Suspend the account (don't delete immediately — you may need email access for handoff). Transfer ownership of shared Drives and Docs.
- [ ] **GitHub** — Remove from the `progression-labs` org. Review and revoke any personal access tokens they created.
- [ ] **AWS** — Remove IAM user and/or SSO assignment. Check for any access keys that need deactivation.
- [ ] **GCP** — Remove IAM bindings across all projects. Revoke any service account keys they generated.
- [ ] **1Password** — Remove from all shared vaults. Revoke their account.
- [ ] **Vercel** — Remove from the team.
- [ ] **Clerk** — Remove admin access.
- [ ] **Slack** — Deactivate the account.
- [ ] **Linear** — Transfer open issues to another team member. Deactivate the account.

## Secret Rotation

If the departing engineer had direct access to any secrets (not just through a tool, but could read the raw values), rotate them:

- [ ] Review 1Password vault access — rotate any secrets in vaults they could access
- [ ] Review Secret Manager access — rotate any GCP secrets their account could read
- [ ] Review AWS Secrets Manager / Parameter Store — rotate anything they had access to
- [ ] Update any shared API keys or tokens they may have seen

## Claude and AI Tooling

- [ ] Remove their engineer layer from `claude-config` (if applicable)
- [ ] Revoke any Anthropic API keys issued to them
- [ ] Check for any MCP server configurations tied to their account

## Client-Specific Access

- [ ] Review client project access and revoke permissions on any client-owned systems
- [ ] Notify clients if contractually required when team members with access to their data depart

## Device

- [ ] Verify FileVault is enabled on their MacBook
- [ ] Remote wipe the device (or verify in-person wipe if returned)
- [ ] Remove the device from MDM

## Final Verification

- [ ] Run through the apps-and-API-keys inventory and confirm no access remains
- [ ] Document the offboarding completion date and who performed it
