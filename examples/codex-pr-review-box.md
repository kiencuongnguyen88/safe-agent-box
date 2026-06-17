# Example — Codex Pull Request Review Box

Use this example when asking a coding agent to review a pull request in a bounded way.

```text
Agent Box Name: Codex Pull Request Review Box

Project / Repo:
safe-agent-box

Goal:
Review one pull request and produce a concise maintainer readback.

Workspace:
Pull request diff and related files only.

Permission Level:
Level 1 — Read-only review

Allowed paths:
- files changed by the pull request
- directly referenced documentation or examples

Blocked paths:
- unrelated files
- private notes
- release publishing settings
- deployment settings

Allowed commands:
- none by default

Blocked commands:
- destructive commands
- publishing commands
- deployment commands
- broad repository rewrites

Human Gate triggers:
- requesting a major rewrite
- changing repository policy
- adding a dependency
- publishing release notes
- expanding review scope

Readback required:
- summary of the pull request
- files reviewed
- issues found
- suggested patch if needed
- checks not run
- next checkpoint

Rollback plan:
No source mutation. Close the review loop or discard the draft feedback.
```

## Expected readback

```text
Review summary:
Files reviewed:
Findings:
Suggested change:
Risk level:
Human Gate triggered:
Next checkpoint:
```
