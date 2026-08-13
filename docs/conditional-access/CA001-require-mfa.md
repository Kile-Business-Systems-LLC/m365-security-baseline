# CA001 — Require MFA for Users

## Purpose

Require multi-factor authentication for interactive user access to Microsoft 365 and Microsoft Entra resources.

## Intended configuration

- **Users:** All users
- **Exclusions:** Emergency-access account
- **Target resources:** All resources
- **Conditions:** None initially
- **Grant:** Require multifactor authentication
- **Initial state:** Report-only

## Validation

Before enforcement:

1. Sign in with the normal daily-use account.
2. Open Microsoft Entra sign-in logs.
3. Inspect the Conditional Access result.
4. Confirm CA001 reports that MFA would be required.
5. Confirm the emergency-access account is excluded.
6. Confirm no unintended service identities are affected.

## Enforcement

After validation, enable CA001 before enabling more restrictive policies.

## Rollback

If legitimate users are unexpectedly blocked:
- Set CA001 back to Report-only or Off
- Review user targeting and exclusions
- Confirm authentication methods are registered
- Re-test before re-enabling
