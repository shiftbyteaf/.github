# AI-assisted development rules

These rules apply to AI coding agents and to contributors using AI-assisted development across ShiftByte repositories.

## Inspect first

Before changing code:

- inspect the relevant implementation;
- inspect nearby tests;
- inspect repository-specific documentation;
- understand the current architecture; and
- verify existing contracts instead of assuming them.

## Stay within scope

Work only on the requested issue or task. Avoid unrelated refactors, broad formatting changes, and unrelated renaming. Do not replace existing architecture without explicit approval.

## Do not invent contracts

Never invent API endpoints, request or response schemas, environment variables, database fields, permissions, configuration, or third-party behavior. Inspect authoritative source code or documentation when it is available. If required information is unavailable, state the uncertainty and request direction rather than presenting an assumption as fact.

## Security

Never:

- commit secrets;
- print sensitive credentials into logs;
- disable TLS verification or weaken certificate validation;
- bypass authentication or reduce authorization checks;
- weaken tests merely to make them pass; or
- replace a secure implementation with an insecure shortcut.

Follow [SECURITY.md](SECURITY.md) for reporting and handling sensitive material.

## Dependencies

Do not add dependencies without explaining why they are needed. Prefer existing project capabilities where reasonable, and evaluate maintenance, security, licensing, and runtime impact.

## Tests

Behavioral changes should have corresponding tests where practical. Do not remove a failing test unless it is demonstrably obsolete and the change is explicitly justified. Report validation that was not run and why.

## Documentation

Update documentation whenever behavior, architecture, configuration, APIs, environments, or release processes change.

## Git and release actions

Agents must not perform any of the following unless the user or an authorized project owner explicitly requests that action:

```text
commit
push
merge
tag
release
publish
deploy
upload builds
distribute applications
```

Permission to inspect or modify files does not imply permission to publish.

## Reporting completion

At completion, report:

- files created and modified;
- key behavior changed;
- tests and validation run, with results;
- anything not validated; and
- remaining risks or blockers.

## Repository-specific rules

A repository may contain its own `AGENTS.md`. Repository-specific instructions supplement this file and take precedence where they are more specific or restrictive.
