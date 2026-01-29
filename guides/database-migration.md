---
id: database-migration
title: Database Migration Guide
category: Engineering
author: Alex Kumar
lastUpdated: "2024-01-20"
summary: Running schema migrations safely
---

## Database Migration Guide

How to write, test, and deploy database schema migrations without downtime.

### Steps

1. Write migration with `prisma migrate dev`
2. Test migration on staging
3. Schedule migration window for low-traffic period
4. Run `prisma migrate deploy` on production
5. Verify application works correctly
6. Monitor database metrics for 1 hour

### Migration Checklist

- [ ] Migration is backwards-compatible (old code can still run)
- [ ] No `DROP COLUMN` without a prior release removing usage
- [ ] Large table migrations use batched operations
- [ ] Staging migration tested with production-like data volume
- [ ] Rollback migration written and tested
- [ ] On-call engineer notified of migration window

### Safe Migration Patterns

| Pattern | Use When |
|---------|----------|
| Add column (nullable) | Adding a new optional field |
| Add column with default | Adding a new required field |
| Rename via alias | Renaming a column (two-step deploy) |
| Backfill then constrain | Adding NOT NULL to existing column |

### What to Avoid

- Never run `DROP TABLE` or `DROP COLUMN` in the same release that removes code usage
- Never add a `NOT NULL` column without a default to a table with existing rows
- Never run migrations during peak traffic hours
