# Human Gate Template

Use this when an agent action needs human approval.

```text
Action:

Why this action is needed:

Scope:

Permission Level:

Files / data / systems affected:

Commands / API calls involved:

Risk:

Rollback plan:

Readback after action:

Decision needed:
[approve / revise / stop / run in sandbox first]
```

## Typical Human Gate triggers

```text
- delete files
- write to database
- migrate schema
- run destructive command
- call paid API
- use token/key/secret
- push code
- deploy
- send real messages/emails
- publish public content
- change source of truth
- install unknown package
- run downloaded script
```
