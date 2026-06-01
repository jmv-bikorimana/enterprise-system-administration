# Active Directory User Management Procedures

## Purpose

This document provides standard procedures for managing user accounts in Microsoft Active Directory environments.

## Scope

The procedure applies to:

- User account creation
- User account modification
- Password management
- Group membership management
- Account disabling and removal

## User Creation Procedure

1. Verify user authorization request.
2. Open Active Directory Users and Computers.
3. Navigate to the appropriate Organizational Unit (OU).
4. Create a new user account.
5. Configure:
   - First Name
   - Last Name
   - Username
   - Display Name
6. Assign initial password.
7. Enable password change at next logon.
8. Add user to required security groups.
9. Verify account creation.

## Password Reset Procedure

1. Verify user identity.
2. Locate the user account.
3. Reset password.
4. Enable "User must change password at next logon".
5. Inform user securely.

## Group Membership Management

1. Review access request.
2. Verify approval.
3. Add or remove user from security groups.
4. Validate permissions.

## Account Disable Procedure

Accounts should be disabled when:

- Employee leaves organization
- Contract expires
- Security incident occurs
- Extended inactivity is detected

Steps:

1. Disable account.
2. Remove privileged access.
3. Document action.
4. Notify relevant stakeholders.

## Security Best Practices

- Apply least privilege principle.
- Review inactive accounts regularly.
- Enforce password policies.
- Monitor privileged accounts.
- Enable account auditing.

## Review

This procedure should be reviewed periodically to ensure compliance with organizational security requirements.
