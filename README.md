# Safe Agent Box

Vietnamese name: **Hộp chạy an toàn cho AI Agent**

Status: `v0.2.0 / OSS maintainer kit candidate`

Safe Agent Box is a practical workflow for giving AI agents a clear operating box before they inspect, draft, edit, run, or report on real repositories and systems.

> Box first. Run second. Readback before trust.

---

## Why this exists

AI agents can help with repository work: reading files, reviewing pull requests, drafting patches, preparing documentation, and supporting maintainer workflows.

The key question is not only:

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

A Safe Agent Box defines:

- the goal;
- the workspace;
- the permission level;
- allowed paths;
- blocked paths;
- allowed commands;
- commands not allowed;
- Human Gate triggers;
- required readback;
- restore or stop plan;
- next checkpoint.

---

## Permission levels

| Level | Name | Agent can do |
|---|---|---|
| 0 | Think only | Analyze and propose. No file access. |
| 1 | Read-only | Read selected files/folders. No changes. |
| 2 | Draft changes | Create patch, diff, or candidate files. No source mutation. |
| 3 | Edit in sandbox | Edit copied workspace, branch, container, or test folder. |
| 4 | Run checks | Run approved tests, lint, typecheck, or safe commands. |
| 5 | Controlled execution | Run approved commands or API actions with logs and readback. |
| 6 | Production action | Touch production or real external systems only after explicit approval. |

Recommended default:

```text
Start at Level 1 or Level 2.
Raise permission only when the box is clear.
```

---

## Human Gate

A Human Gate is needed before high-impact actions.

Examples:

- removing files;
- changing persistent data;
- running broad repository commands;
- using paid or external services;
- using private credentials;
- pushing code;
- deploying;
- sending real messages;
- publishing public content;
- changing source of truth;
- adding unfamiliar packages;
- running downloaded scripts.

Gate shape:

```text
Action:
Scope:
Permission level:
Risk:
Restore path:
Readback:
Decision needed:
```

---

## Repository map

```text
README.md
→ main concept and method overview

docs/quick-start.md
→ first safe loop in 5–10 minutes

docs/codex-for-oss-trial.md
→ Codex-style maintainer trial workflow

docs/maintainer-workflow.md
→ issue, pull request, and release-note workflow boxes

examples/
→ practical Safe Agent Box examples

prompts/
→ copyable prompts for bounded agent work

templates/
→ reusable box and readback templates

.github/
→ issue and pull request templates
```

---

## Try it in 3 minutes

1. Open `templates/safe-agent-box-template.md`.
2. Fill in the goal, workspace, permission level, allowed paths, blocked paths, and readback requirement.
3. Give the prompt in `prompts/safe-agent-box-prompt.md` or `prompts/codex-pr-review-box.md` to your AI agent.
4. Start at Level 1 or Level 2.
5. Only raise permission after readback is clean.

---

## One-line summary

```text
Safe Agent Box is a practical method for giving AI agents clear scope, permission, checkpoint, readback, and Human Gate before real execution.
```
