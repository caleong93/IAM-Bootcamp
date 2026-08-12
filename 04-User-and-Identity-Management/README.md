# Project 4 – User & Identity Management

## Objective

Implement and manage user identities within the Apex Technologies Active Directory environment.

This project demonstrates identity provisioning, account lifecycle management, departmental organization, contractor management, privileged identity separation, and account deprovisioning.

## Environment

- Domain: apextech.local
- Domain Controller: DC01
- Operating System: Windows Server 2022
- Directory Service: Active Directory Domain Services

## Identities Created

### Sarah Johnson

- Department: Human Resources
- Username: sjohnson
- Identity Type: Standard Employee
- Lifecycle Activity: Department transfer to Operations

### David Wilson

- Department: Information Technology
- Username: dwilson
- Identity Type: Standard Employee

### Michael Brown

- Department: Operations
- Username: mbrown
- Identity Type: Contractor
- Lifecycle Control: Account expiration configured
- Offboarding Activity: Account disabled

### Privileged Identity

- Account: adm-dwilson
- Purpose: Separate administrative identity for IT administration
- Location: Privileged-Accounts OU
- Administrative privileges were not granted directly during this project.

## Identity Lifecycle Activities

### Joiner

Created new employee and contractor identities and provisioned them into the appropriate departmental OUs.

### Mover

Transferred Sarah Johnson from Human Resources to Operations to simulate a departmental change.

### Leaver

Disabled Michael Brown's account to simulate contractor offboarding.

## Privileged Identity Management

Created a dedicated `Privileged-Accounts` OU and a separate administrative identity for IT administration.

This demonstrates the principle of separating standard user activity from privileged administrative activity.

## Security Controls

- Standard employee accounts require a password change at first logon.
- Contractor account expiration was configured.
- Contractor account was disabled during offboarding.
- Privileged administrative identity was separated from the standard user identity.
- Custom OUs were protected from accidental deletion.

## Skills Demonstrated

- Active Directory Users and Computers
- User provisioning
- Identity lifecycle management
- Account modification
- Account disabling
- Contractor identity management
- Privileged identity separation
- Organizational Unit management
- Windows Server administration

## Outcome

Apex Technologies now has a functional identity population that can be used for future access-control, security-group, Group Policy, automation, and IAM lifecycle projects.
