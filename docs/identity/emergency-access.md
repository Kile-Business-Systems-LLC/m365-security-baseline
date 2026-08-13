# Emergency-Access Standard

## Purpose

Maintain a reliable path into the Microsoft 365 tenant if normal administrator authentication or Conditional Access becomes unavailable.

## Requirements

- Maintain at least one dedicated emergency Global Administrator account
- Use a strong, unique credential stored in a secure password manager
- Do not use the account for routine administration
- Exclude the account from Conditional Access policies that could create tenant-wide lockout
- Avoid dependencies on the same authentication path used by normal administrators
- Review sign-in activity for the account
- Test access periodically
- Record tests in the change log or operational runbook

## Storage

Credentials and recovery information must never be committed to GitHub.

## Test procedure

1. Open a private browser session.
2. Sign in with the emergency-access account.
3. Confirm access to Microsoft Entra administration.
4. Confirm that Conditional Access exclusions behave as intended.
5. Sign out.
6. Review the sign-in event for unexpected risk or policy results.
7. Record the test date.

## Use criteria

The account should be used only for genuine administrative recovery, lockout prevention, or tenant emergency operations.
