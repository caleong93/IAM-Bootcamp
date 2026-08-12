# Project 5 – Security Groups & Access Control

## Objective

Implement role-based access control (RBAC) within the Apex Technologies Active Directory environment by using security groups to assign access to departmental resources.

The project demonstrates group-based authorization, NTFS permissions, least privilege, effective access verification, access removal, and access restoration.

## Environment

- Domain: apextech.local
- Domain Controller: DC01
- Operating System: Windows Server 2022
- Directory Service: Active Directory Domain Services

## Security Groups

### GG-IT-Users

Used to represent the IT department role.

Member:

- David Wilson (`dwilson`)

### GG-Finance-Users

Used to represent the Finance department role.

Member:

- Jennifer Davis (`jdavis`)

## Resources

Created departmental resources under:

`C:\ApexData`

Resources:

- `C:\ApexData\IT`
- `C:\ApexData\Finance`

## Access Control

### IT

`GG-IT-Users` was granted Modify permissions to:

`C:\ApexData\IT`

David Wilson receives access through his membership in `GG-IT-Users`.

### Finance

`GG-Finance-Users` was granted Modify permissions to:

`C:\ApexData\Finance`

Jennifer Davis receives access through her membership in `GG-Finance-Users`.

## IAM Principles Demonstrated

### Role-Based Access Control

Users receive access through security groups associated with their organizational role rather than through individual permissions.

### Least Privilege

IT users receive access to IT resources while Finance users receive access to Finance resources.

Users are not automatically granted access to resources outside their role.

### Group-Based Authorization

Permissions were assigned to security groups rather than directly to individual users.

### Access Verification

Windows Effective Access was used to evaluate the permissions available to specific identities.

### Access Removal

David Wilson was temporarily removed from `GG-IT-Users` to simulate a change in access requirements.

### Access Restoration

David was returned to `GG-IT-Users` after the access-removal test, restoring the appropriate IT role membership.

## Skills Demonstrated

- Active Directory Users and Computers
- Security group creation
- Global security groups
- Group membership management
- NTFS permissions
- Role-Based Access Control (RBAC)
- Least privilege
- Effective Access analysis
- Access provisioning
- Access removal
- Access restoration
- Windows Server administration

## Outcome

Apex Technologies now has a basic role-based access-control model in which departmental identities receive access to resources through security-group membership.

This establishes the foundation for future IAM projects involving Group Policy, automation, identity lifecycle management, and cloud identity.
