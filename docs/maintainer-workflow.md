# Maintainer Workflow

Safe Agent Box helps maintainers give AI coding agents a clear scope before repository work starts.

## Maintainer use cases

- Issue triage
- Pull request review
- Documentation cleanup
- Small patch drafting
- Release note preparation
- Example review

## Recommended workflow

```text
Scope first
Permission second
Action plan third
Human Gate before impact
Readback before trust
```

## Issue triage box

```text
Agent Box Name: Issue Triage Box
Goal: classify one issue and suggest next action
Permission Level: Level 1
Allowed paths: README, docs, examples related to the issue
Blocked paths: unrelated project files, private notes, release settings
Allowed commands: none by default
Human Gate triggers: changing labels, closing issues, requesting broad repo changes
Readback required: issue summary, likely category, missing information, proposed next step
```

## Pull request review box

```text
Agent Box Name: Pull Request Review Box
Goal: review a small change and report risk
Permission Level: Level 1 or Level 2
Allowed paths: files changed by the pull request
Blocked paths: unrelated files and maintainer-only materials
Allowed commands: agreed checks only
Human Gate triggers: requesting major rewrites, changing public API, publishing release notes
Readback required: reviewed files, findings, suggested patch, checks, next checkpoint
```

## Release note box

```text
Agent Box Name: Release Note Draft Box
Goal: draft notes from existing changes
Permission Level: Level 2
Allowed paths: CHANGELOG, release notes, docs
Blocked paths: credentials, deployment, package publishing settings
Human Gate triggers: publishing a release or changing the source of truth
Readback required: drafted notes, source files used, unknowns, final approval needed
```

## Stop rule

Stop and ask the maintainer when the agent needs broader scope, higher permission, release action, or any action outside the box.
