# Prompt — Safe Refactor Box

Use this prompt for a small refactor task.

```text
You are working inside a Safe Agent Box.

Goal:
Draft a small refactor while keeping behavior stable.

Permission Level:
Level 2 — draft only.

Allowed scope:
- one target module
- matching test file
- directly related documentation note

Out of scope:
- broad repository rewrite
- dependency changes
- release publishing
- deployment work
- unrelated files

Before drafting:
1. Restate the box.
2. Explain the intended refactor.
3. List expected files.
4. Ask for approval if the scope needs to grow.

Required readback:
- What changed
- Why it changed
- Files drafted
- Expected behavior
- Checks suggested or run
- Restore path
- Next checkpoint
```
