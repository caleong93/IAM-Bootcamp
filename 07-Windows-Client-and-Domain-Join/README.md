# Lab 7 – Windows Client & Domain Join

## Objective

Deploy a Windows client workstation and integrate it with the Apex Technologies Active Directory environment.

## Environment

- Domain: `apextech.local`
- Domain Controller: `DC01`
- Domain Controller IAM IP: `10.0.3.10`
- Workstation: `Apex-Workstation`
- Workstation IP: `10.0.3.4`
- IAM Network: `IAM-Lab-Network`
- Subnet: `10.0.3.0/24`

## Windows Client Deployment

Created and installed the `Apex-Workstation` Windows client VM.

The workstation was connected to the `IAM-Lab-Network` NAT Network.

## Network Configuration

The workstation received:

- IPv4 address: `10.0.3.4`
- Subnet mask: `255.255.255.0`
- Default gateway: `10.0.3.1`
- DNS server: `10.0.3.10`

DC01 provides DNS services for the Active Directory environment.

## Active Directory Connectivity

Verified connectivity between Apex-Workstation and DC01.

Verified that:

- `dc01.apextech.local` resolves to `10.0.3.10`
- Active Directory LDAP SRV records resolve correctly
- Kerberos service discovery is available
- `nltest /dsgetdc:apextech.local` successfully discovers DC01

## Domain Join

Joined:

`Apex-Workstation`

to:

`apextech.local`

The workstation successfully authenticated using the ApexTech domain administrator account.

## Domain Membership Verification

Verified that the workstation reports:

`APEXTECH`

as its domain and successfully authenticates using a domain account.

## Troubleshooting

During deployment, the workstation initially experienced connectivity and DNS resolution issues with DC01.

The issue was investigated through:

- IP configuration verification
- VirtualBox NAT Network verification
- ARP testing
- ICMP connectivity testing
- DNS resolution testing
- Active Directory SRV record testing
- Domain Controller discovery testing

The workstation and DC01 were ultimately configured to communicate successfully across `IAM-Lab-Network`.

## Skills Demonstrated

- Windows client deployment
- VirtualBox networking
- Active Directory domain integration
- DNS configuration
- LDAP service discovery
- Kerberos service discovery
- Domain Controller discovery
- Windows domain joining
- Active Directory troubleshooting
- Network troubleshooting
- IAM lab environment administration

## Outcome

Apex-Workstation was successfully integrated into the `apextech.local` Active Directory environment.

The workstation is now positioned for future IAM activities involving centralized identity management, Group Policy, authentication, authorization, and user lifecycle management.

## Snapshot

VirtualBox snapshot:

`07 - Windows Client and Domain Join`
