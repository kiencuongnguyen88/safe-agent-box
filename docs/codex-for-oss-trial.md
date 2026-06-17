# Codex for OSS Trial Workflow

This document shows how Safe Agent Box can be used for a small open-source maintainer workflow with a coding agent.

## Purpose

Use a clear box before asking an AI coding agent to inspect an issue, review a pull request, draft a patch, or prepare release notes.

## Default permission

Start with:

```text
Level 1 — read selected files only
Level 2 — draft changes only
```

Do not begin with direct publishing, deployment, or production actions.

## Trial loop

```text
1. Define the issue or pull request.
2. Define allowed paths and blocked paths.
3. Ask the agent for an action plan.
4. Require the agent to state expected files and checks.
5. Approve only the next bounded step.
6. Require readback before accepting output.
```

## Maintainer box

```text
Agent Box Name: Codex OSS Maintainer Review Box
Project / Repo: safe-agent-box
Goal: review one issue or pull request inside a bounded workflow
Workspace: selected branch or draft patch
Permission Level: Level 1 or Level 2
Allowed paths: files related to the selected issue or pull request
Blocked paths: unrelated files, private files, release credentials, deployment settings
Allowed commands: documentation checks or agreed local checks
Blocked commands: destructive commands, publishing commands, deployment commands
Human Gate triggers: changing public source, adding new dependencies, publishing a release, broadening scope
Readback required: files reviewed, changes proposed, risk notes, checks run, next checkpoint
Rollback plan: discard draft patch or close the review loop
```

## Expected readback

```text
Route used:
Permission level:
Files inspected:
Files changed or drafted:
Commands run:
Checks performed:
Risks found:
Human Gate triggered:
Rollback path:
Next checkpoint:
```

## Boundary

Safe Agent Box is a workflow method. It does not replace repository permissions, branch protection, review policy, or runtime sandboxing.
