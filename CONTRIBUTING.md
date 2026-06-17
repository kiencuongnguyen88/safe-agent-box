# Contributing to Safe Agent Box

Safe Agent Box is a public method kit for giving AI coding agents a clear operating box before they touch real files, repositories, commands, APIs, data, or automation.

Contributions are welcome when they improve clarity, safety, examples, templates, or maintainer workflows.

## Good contributions

Useful contributions include:

- clearer examples;
- safer default permission levels;
- new Safe Agent Box templates;
- pull request review workflows;
- issue triage workflows;
- release and readback workflows;
- security-aware agent workflows;
- corrections to unclear wording;
- real-world usage notes without private data.

## Public-safe rule

Do not include private credentials, private databases, personal data, production logs, confidential repository paths, or internal company details.

Use simulated examples when needed.

## Contribution workflow

1. Open an issue describing the use case.
2. Keep the scope small.
3. State the permission level the example assumes.
4. Add a readback section.
5. Add a rollback or stop condition when relevant.
6. Submit a pull request.

## Method quality checklist

A contribution should answer:

```text
What is the agent trying to do?
What is the allowed workspace?
What is blocked?
What permission level is assumed?
What Human Gate is required?
What readback is required?
How can the change be rolled back or stopped?
```

## Style

Keep language practical and specific. Avoid broad promises. Safe Agent Box is a method for bounded execution, not a guarantee that an agent is safe in every environment.
