# Lab 10 – Azure RBAC: Group-Based Access Control

## Objective

The objective of this lab was to demonstrate role-based access control (RBAC) in Microsoft Azure by assigning permissions to a security group rather than directly to an individual user.

This lab demonstrates how group-based authorization can be used to manage access efficiently and support the principle of least privilege.

---

## Environment

- Microsoft Azure
- Microsoft Entra ID
- Azure subscription
- Microsoft Entra security group
- Azure Role-Based Access Control (RBAC)

---

## Lab Scenario

A cloud IAM administrator needs to provide standard read-only access to a group of cloud users.

Instead of assigning permissions individually to each user, an Entra ID security group is created and assigned the appropriate Azure RBAC role.

The group used in this lab was:

**GG-Cloud-IAM-Users**

The group contains:

**Jordan Blake**

The Reader role was assigned to the group at the Azure subscription scope.

---

## Lab Tasks

### 1. Create the Cloud IAM Security Group

Created the following Microsoft Entra ID security group:

**GG-Cloud-IAM-Users**

Group description:

> Cloud IAM users requiring standard identity access

Configuration:

- Group type: Security
- Membership type: Assigned

---

### 2. Add a User to the Group

Added the following user as a member of the group:

**Jordan Blake**

This demonstrates how users can receive access through group membership rather than receiving individual role assignments.

---

### 3. Assign the Azure Reader Role

Navigated to:

**Azure Subscription → Access control (IAM) → Add role assignment**

Configured the role assignment as follows:

- Role: **Reader**
- Assign access to: **User, group, or service principal**
- Member: **GG-Cloud-IAM-Users**
- Scope: **Azure subscription**

The Reader role provides read-only access to Azure resources without granting permissions to modify or manage those resources.

---

### 4. Verify the Role Assignment

Verified the resulting Azure RBAC configuration under:

**Azure Subscription → Access control (IAM) → Role assignments**

The final configuration showed:

| Identity | Type | Role | Scope |
|---|---|---|---|
| Colette Aleong | User | Owner | Subscription |
| GG-Cloud-IAM-Users | Group | Reader | Subscription |

The Reader role was successfully assigned to the **GG-Cloud-IAM-Users** security group.

---

## IAM Concepts Demonstrated

### Role-Based Access Control (RBAC)

RBAC allows access to Azure resources to be controlled through roles containing defined permissions.

In this lab, the **Reader** role was assigned instead of a more privileged role.

### Group-Based Access Control

Permissions were assigned to a security group rather than directly to an individual user.

This allows administrators to manage access through group membership.

### Least Privilege

The Reader role was selected because the users only require the ability to view Azure resources.

Users do not receive unnecessary permissions to create, modify, or delete resources.

### Separation of Identity and Authorization

Microsoft Entra ID manages the identity and group membership, while Azure RBAC determines what that identity or group is authorized to access.

---

## Verification

The role assignment was successfully verified in the Azure subscription's **Access control (IAM)** section.

The final configuration confirmed that:

**GG-Cloud-IAM-Users → Reader → Azure Subscription**

---

## Evidence

Screenshots documenting the completed configuration are located in the `screenshots` directory.

### Screenshot 01 – Azure RBAC Reader Group Assignment

`01-azure-rbac-reader-group-assignment.png`

This screenshot verifies that the **GG-Cloud-IAM-Users** security group was assigned the **Reader** role at the subscription scope.

---

## Key Takeaways

- Azure RBAC controls authorization to Azure resources.
- Security groups can be used to manage access for multiple users.
- Assigning roles to groups reduces the need for individual role assignments.
- The Reader role provides read-only access.
- Group-based RBAC supports centralized access management and least privilege.
- IAM administrators should verify role assignments after configuration.

---

## Lab Status

**Completed**

Build → Verify → Screenshot → GitHub
