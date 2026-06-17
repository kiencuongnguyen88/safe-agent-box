# Example — Database Read-Only Box

Use this when an AI agent needs to reason about a database-related task without changing the database.

```text
Agent Box Name: Database Read-Only Box

Project / Repo:
example-app

Goal:
Inspect database-related code and explain the current flow.

Workspace:
Repository files only. No live database connection.

Permission Level:
Level 1 — Read-only

Allowed paths:
- schema documentation
- query builder files
- test fixtures
- README or docs

Blocked paths:
- live database files
- environment files
- production settings
- migration execution paths

Allowed commands:
- none by default

Commands not allowed:
- migration commands
- data update commands
- production commands
- package or deployment commands

Human Gate triggers:
- asking for live data access
- changing schema
- changing data
- running a migration
- using environment-specific settings

Readback required:
- files inspected
- data model summary
- uncertainty list
- proposed next safe step

Rollback plan:
No data mutation. Close the read-only loop.
```

## Rule

```text
Read the design.
Do not touch live data.
Ask before raising permission.
```
