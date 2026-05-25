# Example — Local Tooling Fix Inside a Safe Agent Box

## Rough goal

```text
I have a small local tool that exports notes to Markdown.
The export is messy.
I want AI to inspect and propose a cleaner export flow.
```

## Safe Agent Box

```text
Agent Box Name:
Markdown Export Cleanup Box

Project / Repo:
personal-notes-tool

Goal:
Improve markdown export formatting without changing database logic.

Current B:
A cleaner markdown export command that preserves existing notes.

Workspace:
Local copy of repo / feature branch

Permission Level:
Level 2 — Draft changes

Allowed paths:
- src/exporter.py
- tests/test_exporter.py
- docs/export-format.md

Blocked paths:
- .env
- secrets/
- production.db
- deploy/
- migrations/

Allowed commands:
- pytest tests/test_exporter.py

Blocked commands:
- rm -rf
- git push
- deployment commands
- migration commands

Secrets policy:
No secrets needed.

Dependency policy:
No new dependency unless Human approves.

Human Gate triggers:
- touching database
- changing migrations
- adding package
- deleting files
- pushing code

Readback required:
files changed, commands run, tests run, known debt, rollback path, next checkpoint

Rollback plan:
Use branch diff or discard candidate files.

Next checkpoint:
Decide whether to apply candidate patch or ask for simpler version.
```

## Agent action plan

```text
1. Read exporter and existing tests.
2. Identify formatting logic.
3. Draft a small change.
4. Add/adjust one test.
5. Run approved test if allowed.
6. Report exact changes and rollback path.
```

## Readback example

```text
Files changed:
- candidate_patch/exporter_patch.diff
- candidate_patch/test_exporter_patch.diff

Commands run:
- none, because permission level was Level 2 only

Result:
Candidate patch created, not applied.

Known debt:
No full export regression test yet.

Rollback:
Delete candidate_patch folder.

Next checkpoint:
Human reviews patch, then may raise permission to Level 3 or Level 4.
```
