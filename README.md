# Kile Business Systems — Microsoft 365 Security Baseline

This repository documents the Microsoft 365 and Microsoft Entra security baseline used by Kile Business Systems LLC. It serves as an internal operating reference and a sanitized portfolio example of Microsoft 365 security administration practices.

> **Security:** Never commit passwords, recovery codes, client secrets, private keys, Bitwarden exports, authentication tokens, or client-confidential information to this repository.

## Baseline scope

- Microsoft Entra Conditional Access
- Multi-factor authentication
- Legacy authentication blocking
- Privileged administrator protection
- Emergency-access administration
- Shared mailbox security
- Change control and validation

## Conditional Access policies

| ID | Purpose | Initial deployment state |
|---|---|---|
| CA001 | Require MFA for users | Report-only |
| CA002 | Block legacy authentication | Report-only |
| CA003 | Protect privileged administrators with stronger authentication | Report-only |

See [`docs/conditional-access/`](docs/conditional-access/) for policy documentation.

## Security principles

1. Apply least privilege.
2. Require strong authentication for interactive identities.
3. Keep emergency access independent from normal administrative access.
4. Do not use shared mailboxes as interactive user identities.
5. Validate Conditional Access in report-only mode before enforcement.
6. Enable policies incrementally and maintain a tested rollback path.
7. Store credentials and recovery material outside GitHub.
8. Document security changes as they are made.

## Repository structure

```text
.
├── README.md
├── CHANGELOG.md
└── docs/
    ├── identity/
    │   ├── account-model.md
    │   └── emergency-access.md
    ├── messaging/
    │   └── shared-mailboxes.md
    └── conditional-access/
        ├── README.md
        ├── CA001-require-mfa.md
        ├── CA002-block-legacy-auth.md
        └── CA003-protect-admins.md
```

## Deployment workflow

**Design → Report-only → Review sign-in logs → Test → Enable one policy → Monitor → Document**

The emergency-access account must be verified before enforcing changes that could affect administrator sign-in.

## Source of truth

This repository documents the intended baseline and operational decisions. Microsoft Entra remains the authoritative source for the live tenant configuration. Exact assignments, exclusions, conditions, and grant controls must be verified against the tenant after material changes.
