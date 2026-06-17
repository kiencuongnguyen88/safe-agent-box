# Example — Safe Refactor Box

Use this when an AI coding agent proposes a small refactor.

```text
Agent Box Name: Small Refactor Box

Project / Repo:
example-project

Goal:
Improve one module while keeping behavior stable.

Workspace:
Feature branch or copied workspace.

Permission Level:
Level 2 — Draft changes

Allowed paths:
- one target module
- matching test file
- related documentation note

Blocked paths:
- unrelated modules
- configuration files
- release files
- deployment files

Allowed commands:
- agreed test command for the target module

Commands not allowed:
- broad formatting of the whole repo
- dependency changes
- publishing commands
- deployment commands

Human Gate triggers:
- changing public behavior
- touching more files than listed
- adding a dependency
- changing configuration
- removing files

Readback required:
- reason for refactor
- files drafted
- behavior expected to stay the same
- checks suggested or run
- rollback path

Rollback plan:
Discard draft patch or revert the branch.
```

## Safe refactor rule

```text
No broad rewrite.
No hidden scope expansion.
Readback before trust.
```
