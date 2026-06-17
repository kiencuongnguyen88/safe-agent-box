# Security Policy

Safe Agent Box is a public method kit. It does not run code by itself, store credentials, or provide a hosted service.

However, the method deals with AI agents that may interact with real repositories, files, commands, APIs, dependencies, and automation. Security-sensitive feedback is useful.

## Report a security concern

Open a private GitHub security advisory when possible if the concern includes:

- a workflow that may expose private credentials;
- a template that encourages unsafe command execution;
- a prompt that may leak private data;
- a dependency or command pattern that is risky;
- an example that could cause data loss;
- guidance that weakens Human Gate or readback.

If private advisory is unavailable, open a public issue with a minimal description and do not include sensitive details.

## Do not include

- credentials;
- private production logs;
- real customer data;
- operational secrets;
- details that enable harm.

## Security design principles

Safe Agent Box prefers:

```text
least permission first
read-only before write
sandbox before production
explicit Human Gate before impact
readback before trust
rollback path before action
```

## Supported versions

Current public candidate:

```text
v0.2.0 candidate
```

Earlier public seed:

```text
v0.1.0
```
