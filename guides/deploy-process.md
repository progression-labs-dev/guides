---
id: deploy-process
title: Deployment Process
category: Engineering
author: Alex Kumar
lastUpdated: "2024-03-05"
summary: How to deploy code to staging and production
---

## Deployment Process

Standard deployment workflow from merge to production.

### Steps

1. Merge PR to `main` branch
2. CI pipeline runs tests automatically
3. Staging deploy happens automatically
4. Verify on staging environment
5. Click **Promote to Production** in Vercel
6. Monitor Datadog dashboards for 15 minutes

### Pre-Deploy Checklist

- [ ] All CI checks passing
- [ ] PR approved by at least one reviewer
- [ ] Database migrations tested on staging
- [ ] Feature flags configured for gradual rollout
- [ ] Rollback plan documented

### Rollback Procedure

If issues are detected after production deploy:

1. Revert the merge commit on `main`
2. CI will automatically redeploy the previous version
3. If database migrations were involved, run the down migration
4. Notify the team in `#engineering` Slack channel
