# Safe Agent Box Permission Levels

| Level | Name | Agent can do | Typical use |
|---|---|---|---|
| 0 | Think only | Analyze and propose. No file access. | Planning, risk review, prompt design. |
| 1 | Read-only | Read selected files/folders. No changes. | Repo review, bug diagnosis, source mapping. |
| 2 | Draft changes | Create patch, diff, or candidate files. No source mutation. | Proposed fix, candidate docs, migration draft. |
| 3 | Edit in sandbox | Edit copied workspace, branch, container, or test folder. | Local iteration, experiment, prototype. |
| 4 | Run checks | Run approved tests, lint, typecheck, or safe commands. | Verify changes inside scope. |
| 5 | Controlled execution | Run approved commands/API actions with logs and readback. | Limited automation, local DB copy, controlled scripts. |
| 6 | Production action | Touch production or real external systems only after explicit approval. | Deploy, real DB write, real user messages, paid API action. |

Recommended operating rail:

```text
Start low.
Read back.
Raise permission only when needed.
```
