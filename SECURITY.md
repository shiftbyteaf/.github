# Security policy

## Reporting a vulnerability

Do not disclose suspected security vulnerabilities in public issues, pull requests, discussions, or other public channels.

Report vulnerabilities privately to an authorized ShiftByte project or repository owner, or through the repository's configured private security-reporting channel where one is available. Include enough detail to reproduce and assess the issue, but do not expose sensitive production or customer information unnecessarily.

## Sensitive material

Never commit or publish:

```text
passwords
API tokens
access tokens
refresh tokens
private keys
keystores
signing keys
service-account credentials
production .env files
database passwords
certificate private keys
cloud credentials
real customer data
OTP values
banking credentials
authentication secrets
```

Use the approved secret-management and configuration mechanisms for the repository.

## Accidental exposure

Removing a secret from the latest commit does not make it safe; it may remain in Git history, caches, logs, forks, or downloaded copies. If sensitive material is committed or exposed:

1. Stop using it.
2. Notify the appropriate project or security owner.
3. Rotate or revoke the credential.
4. Determine whether Git history remediation is required.
5. Review logs and assess the impact.
6. Document the incident through the appropriate private process.

## Security-sensitive changes

Changes involving the following areas require extra care and review:

```text
authentication
authorization
cryptography
TLS
certificate pinning
payments
financial transactions
ledger/accounting
secrets handling
production configuration
CI/CD credentials
signing
database migrations
external integrations
```

Document relevant threats, trust boundaries, validation performed, migration or rollback concerns, and any residual risk.

## Dependencies

Review dependency security advisories and reported vulnerabilities promptly. Assess applicability, exposure, available fixes, compatibility, and mitigation according to the affected repository's risk and release process. Do not defer a relevant advisory solely because an automated update is unavailable.
