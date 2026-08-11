# Project 3 – Active Directory Structure

## Objective

Design and implement the initial Organizational Unit (OU) structure for the Apex Technologies Active Directory environment.

The structure separates user identities, computers, servers, security groups, service accounts, and business departments.

## Environment

- Domain: apextech.local
- Domain Controller: DC01
- Operating System: Windows Server 2022
- Active Directory Domain Services: Installed

## Organizational Structure

### User Departments

Created the following departmental OUs under `Apex-Users`:

- Executive
- Human Resources
- Finance
- Information Technology
- Sales
- Marketing
- Customer Support
- Operations

### Infrastructure OUs

Created:

- Apex-Computers
- Apex-Servers

### Identity Management OUs

Created:

- Apex-Groups
- Apex-Service-Accounts

## Design Considerations

The OU structure separates users and infrastructure objects so different administrative controls and Group Policies can be applied as the environment develops.

Departmental users are organized by business function, while computers, servers, groups, and service accounts are maintained separately.

## Security Considerations

Each custom OU was configured with protection against accidental deletion.

## Skills Demonstrated

- Active Directory Users and Computers
- Organizational Unit creation
- Active Directory structure design
- Identity organization
- Security administration
- Windows Server administration

## Outcome

The initial Active Directory structure for Apex Technologies was successfully created and is ready for user, group, computer, and Group Policy administration.
