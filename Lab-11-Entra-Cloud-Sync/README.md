# Lab 11 – Microsoft Entra Cloud Sync

## Objective

Configure Microsoft Entra Cloud Sync to establish connectivity between an on-premises Active Directory environment and Microsoft Entra ID.

## Environment

- Microsoft Entra ID
- Windows Server 2022
- Active Directory Domain Services
- Domain: apextech.local
- Domain Controller: DC01
- Microsoft Entra Provisioning Agent

## Tasks Completed

1. Verified the Hybrid Admin account in Microsoft Entra ID.
2. Assigned the Hybrid Identity Administrator role.
3. Downloaded the Microsoft Entra Provisioning Agent.
4. Installed the Microsoft Entra Provisioning Agent on the domain controller.
5. Connected the provisioning agent to Microsoft Entra ID.
6. Configured the Active Directory domain `apextech.local`.
7. Configured the provisioning service account using a group Managed Service Account (gMSA).
8. Confirmed the provisioning agent configuration.
9. Verified that the domain controller was registered as an active provisioning agent.

## Configuration

### Active Directory

- Domain: `apextech.local`
- Domain Controller: `DC01`
- Provisioning service account: `apextech.local\provAgentgMSA`

### Microsoft Entra ID

The provisioning agent was authenticated using the Hybrid Admin account and successfully connected to the Microsoft Entra tenant.

## Result

The Microsoft Entra provisioning agent was successfully installed and configured. The domain controller appears in the Microsoft Entra Cloud Sync Agents page with an **Active** status.

This demonstrates the foundational configuration required for identity synchronization between on-premises Active Directory and Microsoft Entra ID.

## Evidence

Screenshots included in this lab document the:

- Microsoft Entra provisioning agent configuration
- Active Directory domain configuration
- Completed provisioning agent configuration
- Registered and active provisioning agent

## IAM Skills Demonstrated

- Microsoft Entra ID administration
- Active Directory integration
- Identity provisioning
- Cloud synchronization
- Role-based access control (RBAC)
- Service account configuration
- Hybrid identity administration
