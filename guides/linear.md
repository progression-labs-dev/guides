---
id: linear
title: "Linear"
category: Tools
author: Chris Little
lastUpdated: "2026-03-10"
summary: "How we use Linear to track and organise work"
---

# Linear

Linear is our trusted system for tracking committed work. If it's in Linear, we intend to do it. If it's someday/maybe, it belongs somewhere else.

## Philosophy

We follow a GTD-inspired approach:

- **Capture**: If a piece of work will take more than 5 minutes, it goes into Linear as an issue.
- **Organise**: Issues belong to projects. Large issues are broken into sub-issues.
- **Work**: Pull the next thing and do it. Update state as you go.
- **Review**: State is maintained continuously as work happens — no formal review cadence.

We do not run sprints. Linear is a kanban board that tells us where things are and what needs doing next.

## Hierarchy

```
Project
  └─ Issue (a deliverable or meaningful chunk of work)
       └─ Sub-issue (a next action — the thing you actually sit down and do)
```

### Projects

A project groups related work under a recognisable name. There are two types:

| Type | Definition | Example | Lifecycle |
|------|-----------|---------|-----------|
| **Goal project** | Has a finish line — a specific outcome you're working toward | ISO 27001 Certification | Completed when the goal is achieved |
| **Product project** | Long-lived — generates issues for as long as the product exists | Brief, Contractor Commerce | Stays open indefinitely |

**When to create a project:**

- It will have 3+ issues over its lifetime
- It has a name the team would recognise
- You can classify it as either a goal or a product

If it's just one piece of work with subtasks, it's an issue with sub-issues — not a project.

**Project hygiene:**

- Goal projects that have been open for a long time with no movement are stalled. Either add issues and work on them, or cancel the project.
- Product projects with no active issues should be moved to Backlog until work resumes.

### Issues

An issue is a meaningful chunk of work — a deliverable, a feature, a problem to solve. It should be concrete enough that you know when it's done.

**Good issue:**
> "Set up AWS Organization OUs (Platform, Internal, Clients)"

**Bad issue:**
> "Do infrastructure stuff"

**When an issue is too big:**

If you're tempted to put a task checklist in an issue description, those tasks should be sub-issues instead. A checklist in the description is invisible to the board — sub-issues have their own state, assignee, and visibility.

**Issue structure:**

Every issue should have:

- A clear title that describes the outcome
- Enough description to pick it up cold (context, what "done" looks like)
- Sub-issues for any work that has multiple steps

### Sub-issues

A sub-issue is a next action — the smallest unit of work you'd sit down and do. Sub-issues show up on the board with their own state, which makes progress visible.

```
Multi-cloud platform infra (issue)
  ├─ Set up AWS Organization OUs (sub-issue)
  ├─ Create shared-services account (sub-issue)
  ├─ Build GCP project vending automation (sub-issue)
  └─ ...
```

## States

### Project states

| State | Meaning |
|-------|---------|
| Backlog | Work we intend to do but haven't started planning |
| Planned | Scoped and ready to start when capacity opens up |
| In Progress | Actively being worked on — has issues in flight |
| Completed | Goal achieved or product retired |
| Cancelled | No longer relevant |

### Issue and sub-issue states

| State | Meaning |
|-------|---------|
| Backlog | Captured but not yet ready to work on |
| Todo | Ready to be picked up |
| In Progress | Currently in your focus list |
| Done | Completed |
| Cancelled | No longer relevant |

**"In Progress" means "in my current focus list"**, not "I am working on this right now." It is normal to have multiple issues in progress at once. You context-switch between them as needed.

## Labels

Use labels sparingly. They are most useful for cross-cutting concerns that span multiple projects:

- `repo:<name>` — links an issue to a specific repository (e.g., `repo:progression-labs-sdk`)

Do not use labels to replicate information that already exists in the project or state.

## What we don't use

| Feature | Status | Reason |
|---------|--------|--------|
| Cycles/Sprints | Disabled | We don't run sprints — work is pull-based |
| Initiatives | Not used | Not enough scale to need a level above projects |
| Estimates | Not used | We don't estimate work |
| Triage | Not used | Issues go straight into a project |

## Workflow

1. **Something comes up** that will take more than 5 minutes.
2. **Create an issue** in the relevant project. Write enough context that you (or someone else) could pick it up cold.
3. **Break it down** into sub-issues if it has multiple steps.
4. **Set state to Todo** if it's ready to be worked on, or **Backlog** if not yet.
5. **Move to In Progress** when you start focusing on it.
6. **Move to Done** when it's complete. Update sub-issues as you go.
7. **Cancel** anything that's no longer relevant — don't let dead issues linger.

## Team

We have one team: **PROG** (Progression Labs). All work lives here.
