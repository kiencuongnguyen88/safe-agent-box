# Safe Agent Box

Vietnamese name: **Hộp chạy an toàn cho AI Agent**

Status: `v0.1.0 / public method seed`

Safe Agent Box is a practical workflow for giving AI agents a clear operating box before they touch real files, code, data, commands, APIs, or automation.

> Agent càng mạnh thì hộp chạy càng phải rõ.

---

## Why this exists

AI agents are no longer only generating text. They can read files, edit repositories, run terminal commands, call APIs, install packages, update databases, send messages, and trigger automations.

That means the main question is not only:

```text
Is the agent smart enough?
```

The better question is:

```text
What is the agent allowed to see, touch, run, change, and report back?
```

Safe Agent Box helps humans and teams define that operating box before execution.

---

## Core idea

```text
Box first.
Run second.
Readback before trust.
```

A Safe Agent Box defines:

- the goal;
- the workspace;
- the permission level;
- allowed paths;
- blocked paths;
- allowed commands;
- blocked commands;
- secrets policy;
- dependency policy;
- Human Gate triggers;
- required readback;
- rollback plan;
- next checkpoint.

---

## The loop

```text
Scope
→ Permission
→ Workspace
→ Action plan
→ Human Gate
→ Execution
→ Readback
→ Patch / rollback / checkpoint
```

Compact version:

```text
Hộp trước.
Chạy sau.
Readback rồi mới tin.
```

---

## Permission levels

| Level | Name | Agent can do |
|---|---|---|
| 0 | Think only | Analyze and propose. No file access. |
| 1 | Read-only | Read selected files/folders. No changes. |
| 2 | Draft changes | Create patch, diff, or candidate files. No source mutation. |
| 3 | Edit in sandbox | Edit copied workspace, branch, container, or test folder. |
| 4 | Run checks | Run approved tests, lint, typecheck, or safe commands. |
| 5 | Controlled execution | Run approved commands/API actions with logs and readback. |
| 6 | Production action | Touch production or real external systems only after explicit approval. |

Recommended default:

```text
Start at Level 1 or Level 2.
Raise permission only when the box is clear.
```

---

## Human Gate

A Human Gate is needed before the agent performs high-impact actions.

Examples:

- delete files;
- write to a database;
- migrate schema;
- run destructive commands;
- call paid APIs;
- use tokens or keys;
- push code;
- deploy;
- send real messages or emails;
- publish public content;
- change source of truth;
- install unknown packages;
- run downloaded scripts.

Gate shape:

```text
Action:
Scope:
Permission level:
Risk:
Rollback:
Readback:
Decision needed:
```

---

## Minimal template

Use this before giving an agent access to a real workspace:

```text
Agent Box Name:
Project / Repo:
Goal:
Current B:
Workspace:
Permission Level:
Allowed paths:
Blocked paths:
Allowed commands:
Blocked commands:
Secrets policy:
Dependency policy:
Human Gate triggers:
Readback required:
Rollback plan:
Next checkpoint:
```

---

## Relation to Progressive B Discovery

Safe Agent Box pairs well with Progressive B Discovery.

```text
Progressive B Discovery asks:
Where are we going, and how does B become clearer through runtime?

Safe Agent Box asks:
What can the agent safely do while helping us move toward B?
```

Together:

```text
Progressive B Discovery helps direction.
Safe Agent Box helps controlled execution.
```

---

## Repository map

```text
README.md
→ main concept and method overview

docs/quick-start.md
→ first safe loop in 5–10 minutes

prompts/safe-agent-box-prompt.md
→ copyable prompt for using an AI agent inside a safe box

templates/safe-agent-box-template.md
→ full box definition template

templates/human-gate-template.md
→ approval gate template

templates/readback-template.md
→ post-run report template

templates/permission-levels.md
→ permission level reference

examples/local-tooling-example.md
→ simple example for local tool-building
```

---

## Try it in 3 minutes

1. Open `templates/safe-agent-box-template.md`.
2. Fill in the goal, workspace, permission level, allowed paths, blocked paths, and readback requirement.
3. Give the prompt in `prompts/safe-agent-box-prompt.md` to your AI agent.
4. Start at Level 1 or Level 2.
5. Only raise permission after readback is clean.

---

## One-line summary

```text
Safe Agent Box is a practical method for giving AI agents clear scope, permission, checkpoint, readback, and Human Gate before real execution.
```
