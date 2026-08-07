# 02 - Windows Server Installation

## Objective

Build and configure a Windows Server 2022 virtual machine that will become the Domain Controller for the IAM lab.

---

## Environment

| Component | Value |
|-----------|-------|
| Host Computer | Intel Mac |
| Hypervisor | Oracle VirtualBox 7.2.2 |
| Operating System | Windows Server 2022 Standard (Desktop Experience) |
| Virtual Machine Name | DC01 |

---

## Status

🟢 Completed

---

# Active Directory Deployment

## Tasks Completed

- Installed Active Directory Domain Services (AD DS)
- Installed the DNS Server role
- Promoted DC01 to the first Domain Controller
- Created a new Active Directory forest
- Created the domain: apextech.local

## Skills Demonstrated

- Windows Server Administration
- Active Directory Installation
- Domain Controller Promotion
- DNS Configuration
- Virtual Machine Administration
- Infrastructure Deployment

## Troubleshooting

### DNS Resolution

During the initial Windows Server configuration, DNS name resolution failed after assigning a static IP address.

**Resolution:**
- Verified network connectivity using `ping`
- Determined the issue was DNS-related
- Updated DNS settings
- Verified connectivity before installing Active Directory

**Result:**
The server was successfully promoted to a Domain Controller.
