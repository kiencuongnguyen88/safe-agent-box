# Safe Agent Box — Quick Start

Use this when you want an AI agent to help with a real project, repo, folder, database, API, or automation.

---

## 1. Choose the box

Start small.

```text
Project / Repo:
Workspace:
Goal:
Current B:
```

Example:

```text
Project / Repo: personal-notes-tool
Workspace: copied repo folder / test branch
Goal: improve markdown export
Current B: a simple export command that works without breaking existing notes
```

---

## 2. Choose permission level

Recommended starting levels:

```text
Level 1 — Read-only
Level 2 — Draft changes
```

Avoid jumping straight to production actions.

---

## 3. Define what the agent can touch

```text
Allowed paths:
Blocked paths:
Allowed commands:
Blocked commands:
```

Example:

```text
Allowed paths:
- src/exporter.py
- tests/test_exporter.py

Blocked paths:
- .env
- secrets/
- production.db
- deploy/

Allowed commands:
- pytest tests/test_exporter.py

Blocked commands:
- rm -rf
- git push
- deployment commands
- database migration commands
```

---

## 4. Define Human Gate triggers

```text
Human Gate triggers:
- deleting files
- changing database schema
- using secrets
- pushing code
- deploying
- sending messages
- calling paid APIs
```

---

## 5. Ask for an action plan first

Before execution, ask the agent:

```text
State your action plan.
List files and commands you intend to touch.
Identify risks.
Ask for approval if a Human Gate is triggered.
```

---

## 6. Require readback after execution

After execution, require:

```text
Files changed:
Commands run:
Tests/checks run:
Result:
Remaining issues:
Rollback path:
Next checkpoint:
```

---

## 7. Move in loops

```text
Define box
→ action plan
→ run inside box
→ readback
→ checkpoint
→ patch / rollback / raise permission
```

---

## Quick rule

```text
Hộp trước.
Chạy sau.
Readback rồi mới tin.
```
