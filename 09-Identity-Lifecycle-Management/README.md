# Lab 9 — Identity Lifecycle Management: Joiner, Mover, Leaver

## Objective

Demonstrate an end-to-end Identity and Access Management (IAM) lifecycle using Microsoft Active Directory:

- Joiner — provision a new identity and assign appropriate access
- Mover — modify an existing identity when the user's department changes
- Leaver — disable the identity and revoke access when the user leaves the organization

This lab demonstrates the principle that identity access should change with a user's employment status and job responsibilities.

---

## Environment

- Windows Server 2022
- Active Directory Domain Services (AD DS)
- Domain: `apextech.local`
- Domain Controller: `DC01`
- Active Directory Users and Computers (ADUC)
- PowerShell
- Organizational Units (OUs)
- Active Directory Security Groups

---

# IAM Lifecycle

## 1. Joiner — New Employee

A new employee is provisioned into Active Directory as part of the onboarding process.

The Joiner process demonstrates:

1. Creating the user identity.
2. Placing the user in the appropriate organizational unit.
3. Assigning the appropriate security group.
4. Configuring the user's department and job information.
5. Verifying that the account is enabled.

### IAM Principle

A new identity should receive only the access required for the user's assigned role.

---

# 2. Mover — Department Transfer

### Scenario

Taylor Johnson transfers from the **Sales department to the Marketing department**.

The user's identity remains the same, but their organizational placement and access must change to reflect their new responsibilities.

### Changes Performed

- Moved Taylor Johnson to:

  `Apex-Users/Marketing`

- Updated the user's organizational information:
  - Job Title: `Marketing Associate`
  - Department: `Marketing`

- Added Taylor Johnson to:

  `GG-Marketing-Users`

- Removed Taylor Johnson from:

  `GG-Sales-Users`

### Verification

The Sales security group no longer contains Taylor Johnson.

The Marketing security group contains Taylor Johnson.

### IAM Principle

A department transfer requires access to be reviewed and modified based on the user's new role.

Access associated with the previous role should be removed to prevent privilege accumulation.

---

# 3. Leaver — Employee Offboarding

### Scenario

Taylor Johnson leaves the organization.

The account is retained in Active Directory for administrative and audit purposes, but access to organizational resources must be revoked.

### Changes Performed

- Disabled Taylor Johnson's Active Directory account.
- Removed Taylor Johnson from:

  `GG-Marketing-Users`

- Retained:

  `Domain Users`

- The user account was not deleted.

### Verification

Taylor Johnson's account shows:

`Account is disabled`

The user's `Member Of` list no longer contains:

`GG-Marketing-Users`

---

# IAM Controls Demonstrated

## Identity Lifecycle Management

The lab demonstrates the three major identity lifecycle events:

| Lifecycle Event | IAM Action |
|---|---|
| Joiner | Create and provision identity |
| Mover | Modify identity and access |
| Leaver | Disable identity and revoke access |

## Least Privilege

Users receive access based on their current job responsibilities rather than retaining access from previous roles.

## Access Revocation

When an employee changes departments or leaves the organization, unnecessary access is removed.

## Account Disablement

Leaver accounts are disabled rather than immediately deleted, preserving the identity for administrative and audit purposes.

## Role-Based Access Control

Security groups are used to associate users with role or department-based access.

---

# Evidence

The following screenshots document the completed IAM lifecycle activities:

- `Lab9-Mover-Marketing-Group-Access.png`
- `Lab9-Leaver-Taylor-Johnson-Offboarding.png`

Screenshots will be stored in the `Screenshots` directory.

---

# Skills Demonstrated

- Active Directory identity lifecycle management
- User provisioning
- User attribute management
- Organizational Unit management
- Security group membership management
- Role-based access control (RBAC)
- Access revocation
- Account disablement
- Least privilege
- IAM Joiner/Mover/Leaver processes
- Identity governance concepts

---

# Lab Outcome

Successfully demonstrated an end-to-end IAM lifecycle in an on-premises Active Directory environment.

The lab shows how an IAM administrator can:

1. Provision a new identity.
2. Modify access when an employee changes roles.
3. Remove outdated access.
4. Disable an account during offboarding.
5. Preserve the identity for audit and administrative purposes.

This workflow provides the foundation for more advanced identity lifecycle automation and cloud identity management in later labs.
