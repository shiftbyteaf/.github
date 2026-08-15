# Contributing to ShiftByte repositories

This guide defines the organization-wide contribution baseline. Follow any repository-specific instructions when they are more specific or restrictive.

## Workflow

Normal work follows this sequence:

```text
Issue
→ latest main
→ short-lived task branch
→ implementation
→ local validation
→ push branch
→ pull request
→ review
→ CI validation where configured
→ merge into main
→ delete task branch
```

## Main branch

`main` is the permanent source-of-truth branch and should remain releasable. Routine development must not happen directly on `main`; completed work should return through a pull request.

Direct changes to `main` are reserved for exceptional repository-bootstrap or emergency administrative cases. Because the current GitHub Free plan cannot enforce every policy on private repositories, contributors are expected to follow these rules manually.

Do not use these as permanent branches:

```text
develop
development
test
testing
uat
staging
production
prod
```

Environments are represented by configuration, application flavors or profiles, CI/CD workflows, deployment targets, and release artifacts—not by permanent source branches.

## Branch naming

Use a short-lived branch with one of these forms:

```text
feature/<issue-number>-<description>
fix/<issue-number>-<description>
chore/<issue-number>-<description>
docs/<issue-number>-<description>
refactor/<issue-number>-<description>
test/<issue-number>-<description>
hotfix/<version>-<description>
release/<version>
```

Examples:

```text
feature/53-push-notifications
fix/61-login-timeout
chore/72-upgrade-dependencies
docs/80-release-runbook
refactor/91-auth-service
hotfix/1.0.1-login-failure
release/1.1.0
```

`release/*` is optional and should be used only when release stabilization must continue independently while new development proceeds on `main`.

Avoid personal or vague names such as `danish`, `zia`, `developer1`, `new`, `latest`, `final`, `work`, and `backend-work`.

## Issue-first development

Normal development starts from a GitHub Issue or another documented work item. It should explain:

- the problem or requirement;
- why it is needed;
- acceptance criteria;
- the affected component; and
- security, configuration, and release considerations where applicable.

Very small documentation or administrative corrections may skip a dedicated issue when reasonable.

## Commits

Use Conventional Commit-style messages that describe the actual change:

```text
feat: add push notification support
fix: correct API timeout handling
docs: document production release process
test: add authentication contract tests
chore: upgrade dependencies
refactor: simplify login coordinator
ci: add validation workflow
build: update Android build configuration
```

Scopes may be used, for example:

```text
feat(ios): add UAT bundle configuration
fix(auth): preserve normalized phone number
ci(mobile): validate release configuration
```

Do not use meaningless messages such as `update`, `changes`, `final`, `fix`, `new code`, or `work`.

## Pull requests

Normal changes require a pull request. Each pull request should explain:

- what changed and why;
- the related issue or work item;
- how the change was tested;
- security and configuration impact;
- API or contract impact where relevant;
- release or environment impact; and
- documentation impact.

Keep pull requests focused. Do not mix unrelated refactoring, formatting, and feature development in one pull request.

## Review

Authors should self-review before requesting review. Reviewers should inspect correctness, security, tests, maintainability, architecture, and unintended side effects. Address unresolved review comments before merge.

Approvals are expected procedurally even when the current GitHub plan cannot enforce them technically.

## Testing and validation

- Run repository-specific validation commands before opening or completing a pull request.
- Add or update tests for behavioral changes.
- Never delete, disable, weaken, or bypass tests merely to make a build pass.
- Document any validation that could not be executed and explain why.

## Documentation

Update documentation when changing architecture, configuration, environments, deployment, APIs or contracts, developer workflows, release behavior, or security-sensitive behavior.

## Security

Follow [SECURITY.md](SECURITY.md). Secrets must never be committed, and `.env` files containing secrets must not be tracked. Do not add private keys, signing material, service-account credentials, tokens, certificates containing private material, or production credentials to source control.

Treat accidentally exposed credentials as compromised and rotate or revoke them promptly.

## Dependencies

New dependencies require justification. Before adding one, consider:

- whether the existing stack already solves the problem;
- maintenance status and security history;
- license compatibility;
- size and runtime implications; and
- the repository's version policy.

## Definition of done

A task is not complete merely because the code compiles. It should normally have:

```text
implementation complete
tests complete
validation successful
documentation updated if needed
no secrets introduced
no unrelated changes
review feedback resolved
PR ready for merge
```
