# Lab 6 – Group Policy & Security Hardening

## Objective

Implement centralized security controls within the Apex Technologies Active Directory environment using Group Policy.

The lab demonstrates password security, account lockout protection, workstation security configuration, Group Policy scoping, and GPO troubleshooting.

## Environment

- Domain: apextech.local
- Domain Controller: DC01
- Operating System: Windows Server 2022
- Active Directory Domain Services: Installed
- Group Policy Management: Configured

## Domain Password Policy

Configured the domain password policy with:

- Minimum password length: 12 characters
- Password complexity: Enabled
- Password history: 10 passwords
- Maximum password age: 90 days
- Minimum password age: 1 day
- Reversible encryption: Disabled

## Account Lockout Policy

Configured:

- Lockout threshold: 5 invalid attempts
- Lockout duration: 15 minutes
- Lockout counter reset: 15 minutes

These settings provide protection against repeated authentication attempts and password-guessing attacks.

## Workstation Security GPO

Created:

`Apex-Workstation-Security`

The GPO was linked specifically to:

`Apex-Computers`

### Configured Controls

- Interactive logon security message
- Machine inactivity limit: 900 seconds
- Guest account: Disabled

## Group Policy Scope

The workstation security GPO was intentionally scoped to the `Apex-Computers` OU.

DC01 remains in the `Domain Controllers` OU and therefore does not receive the workstation-specific GPO.

This demonstrates the importance of correct OU placement and GPO scope when administering Active Directory.

## Troubleshooting

An initial `gpresult /r` check on DC01 did not show `Apex-Workstation-Security`.

The issue was investigated by reviewing the GPO link and scope.

The GPO was confirmed to be correctly linked and scoped to `Apex-Computers`.

The absence of the GPO from DC01's applied policies was expected because DC01 resides in the `Domain Controllers` OU rather than `Apex-Computers`.

## Security Concepts Demonstrated

- Group Policy
- Password policy
- Account lockout
- Workstation hardening
- Centralized security configuration
- OU-based policy targeting
- GPO scope
- Active Directory troubleshooting
- Least privilege and security baseline concepts

## Skills Demonstrated

- Group Policy Management
- Group Policy configuration
- Active Directory administration
- Windows Server security configuration
- Security policy troubleshooting
- GPO scope analysis
- Organizational Unit management

## Outcome

Apex Technologies now has a defined domain security baseline and a workstation-specific security policy that is correctly scoped to the `Apex-Computers` OU.

The environment is prepared for future domain-joined workstation testing and additional IAM/security controls.
