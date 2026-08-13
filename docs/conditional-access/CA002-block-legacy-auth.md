# CA002 — Block Legacy Authentication

## Purpose

Prevent authentication methods and clients that cannot satisfy modern security controls such as MFA.

## Intended configuration

- **Users:** All users
- **Exclusions:** Emergency-access account
- **Target resources:** All resources
- **Conditions:** Legacy authentication client types
- **Grant:** Block access
- **Initial state:** Report-only

## Validation

Before enforcement:

1. Review sign-in logs for legacy authentication activity.
2. Identify whether any legitimate workflow still depends on legacy authentication.
3. Confirm modern Outlook and Microsoft 365 clients are not impacted.
4. Confirm the emergency-access account exclusion is present.
5. Remediate legacy dependencies before enabling the block.

## Enforcement

Enable only after the report-only period shows no required business dependency on legacy authentication.

## Rollback

If a legitimate business process fails:
- Disable the policy or return it to Report-only
- Identify the application or protocol
- Replace the legacy authentication dependency with modern authentication
- Re-enable after remediation
