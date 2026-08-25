# Lab 12 — Enterprise IAM Capstone Project

## Executive Summary

This capstone project demonstrates an end-to-end Identity and Access Management (IAM) implementation for a fictional organization, ApexTech.

The project combines the technical skills developed throughout Labs 1–11 into an enterprise-style IAM environment using on-premises Active Directory, Microsoft Entra ID, Azure RBAC, security groups, identity lifecycle management, and hybrid identity components.

The primary objective was to demonstrate how identities can be structured, provisioned, granted access based on job responsibilities, modified when roles change, and disabled when employees leave the organization.

---

# 1. Business Scenario

ApexTech is a fictional technology services organization with multiple departments and centralized identity management requirements.

The organization requires an IAM model that supports:

- Centralized identity management
- Role-based access control
- Least privilege
- Group-based access
- Identity lifecycle management
- Administrative account separation
- Hybrid identity
- Access governance
- Auditable identity changes

The capstone models these requirements using a combination of Active Directory and Microsoft Entra ID.

---

# 2. Environment

## On-Premises Environment

- Windows Server 2022
- Active Directory Domain Services
- Domain Controller: `DC01`
- Active Directory domain: `apextech.local`

## Cloud Environment

- Microsoft Entra ID
- Azure subscription
- Microsoft Entra Cloud Sync
- Microsoft Entra Provisioning Agent
- Azure Role-Based Access Control (RBAC)

---

# 3. IAM Architecture

The capstone architecture is based on the following identity flow:

```text
                    APEXTECH IAM
                         |
              +----------+----------+
              |                     |
       Active Directory       Microsoft Entra ID
        apextech.local               |
              |                      |
             DC01            Cloud Sync Agent
              |                      |
       Security Groups          Azure RBAC
              |
       +------+------+------+
       |      |      |      |
      HR   Finance   IT   Security
       |
     Users
       |
 Joiner → Mover → Leaver
