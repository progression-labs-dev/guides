---
id: secret-rotation
title: Secret Rotation Guide
category: Security
author: Tom Anderson
lastUpdated: "2024-03-01"
summary: How to rotate API keys and credentials
---

## Secret Rotation Guide

Process for safely rotating API keys, credentials, and other secrets.

### Steps

1. Generate new credential in provider dashboard
2. Update Vault with new value
3. Deploy services that use the credential
4. Verify services work with new credential
5. Revoke old credential
6. Update rotation log in Notion

### Rotation Schedule

| Secret Type | Rotation Frequency | Owner |
|-------------|-------------------|-------|
| API keys | Every 90 days | Service owner |
| Database passwords | Every 90 days | Infrastructure |
| OAuth client secrets | Every 180 days | Security |
| SSH keys | Every 365 days | Individual |
| Signing keys | Every 365 days | Security |

### Emergency Rotation

If a secret is compromised:

1. **Immediately** generate a new credential
2. Deploy with new credential to all environments
3. Revoke the compromised credential
4. Audit access logs for unauthorized usage
5. File a security incident report
