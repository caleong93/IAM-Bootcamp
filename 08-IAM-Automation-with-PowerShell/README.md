# Lab 8 – IAM Automation with PowerShell

## Objective

Demonstrate practical Identity and Access Management automation using PowerShell and Active Directory.

The lab focuses on four core IAM administration tasks:

- User provisioning
- User modification
- Account disabling
- Identity reporting

## Environment

- Domain: `apextech.local`
- Domain Controller: `DC01`
- Active Directory Domain Services: Windows Server
- PowerShell ActiveDirectory module: `1.0.1.0`

## PowerShell Environment

Verified that the ActiveDirectory PowerShell module was available on DC01.

The domain was successfully queried using PowerShell with:

```powershell
Get-ADDomain
