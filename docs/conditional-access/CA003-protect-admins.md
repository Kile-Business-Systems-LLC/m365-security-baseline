# CA003 — Protect Privileged Administrators

## Purpose

Apply stronger authentication requirements to privileged Microsoft Entra and Microsoft 365 administrative roles.

## Intended configuration

- **Users:** Selected privileged directory roles
- **Exclusions:** Emergency-access account
- **Target resources:** All resources
- **Grant:** Require stronger authentication; phishing-resistant authentication is the preferred target state
- **Initial state:** Report-only

## Roles to consider

Target roles should be based on actual administrative need. Common examples include:

- Global Administrator
- Conditional Access Administrator
- Security Administrator
- Exchange Administrator
- SharePoint Administrator
- Authentication Administrator

Do not add roles mechanically; include only those relevant to the tenant's operating model.

## Validation

1. Confirm the dedicated administrative account is targeted.
2. Confirm the emergency-access account is excluded.
3. Test administrator sign-in.
4. Review Conditional Access results in Entra sign-in logs.
5. Verify the intended strong authentication method is registered and usable.
6. Confirm no administrative automation is unintentionally affected.

## Enforcement

Enable after administrator authentication is tested successfully.

## Rollback

If administrator access fails:
- Use the emergency-access account
- Return CA003 to Report-only or Off
- Correct targeting, authentication-strength requirements, or method registration
- Re-test before enforcing again
