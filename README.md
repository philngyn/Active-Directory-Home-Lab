# Enterprise Active Directory Home Lab

## Project Overview

This project documents the deployment and administration of a virtualized Windows Active Directory environment designed to simulate common IT support and system administration responsibilities within a fictional organization, "HK Tech".

The lab was built using **Windows Server 2019** and **Windows 10** virtual machines hosted in **Oracle VirtualBox**.

The environment includes Active Directory Domain Services (AD DS), DNS, DHCP, Group Policy, PowerShell automation, security groups, domain-joined workstations, SMB file sharing, and role-based resource permissions.

The lab initially began as a foundational Active Directory environment and was later expanded into a more structured enterprise-style environment. This included creating departmental Organizational Units (OUs), provisioning users, implementing security groups, configuring domain workstations, deploying Group Policy security controls, creating departmental file shares, and testing authorized and unauthorized resource access.

### Project Goals

- Deploy a Windows Server 2019 Domain Controller
- Configure Active Directory Domain Services (AD DS)
- Configure DNS and DHCP services
- Design an enterprise-style Organizational Unit (OU) structure
- Create and manage Active Directory users and computers
- Automate bulk user provisioning using PowerShell
- Implement departmental security groups
- Join Windows 10 workstations to the domain
- Configure centralized workstation policies using Group Policy
- Implement workstation security controls
- Configure SMB departmental file sharing
- Implement group-based access permissions
- Test authorized and unauthorized access to network resources
- Practice network, DNS, Active Directory, Group Policy, and permissions troubleshooting
- ---

## Lab Environment & Architecture

The lab was built in Oracle VirtualBox to simulate a small corporate Windows domain environment. A Windows Server 2019 virtual machine serves as the Domain Controller and provides centralized identity and network services, while two Windows 10 virtual machines represent departmental employee workstations.

### Virtual Machines

| Virtual Machine | Operating System | Purpose |
|---|---|---|
| DC | Windows Server 2019 | Domain Controller hosting AD DS, DNS, DHCP, Group Policy, and File Services |
| HK-IT-001 | Windows 10 | Domain-joined workstation representing the IT department |
| HK-CS-001 | Windows 10 | Domain-joined workstation representing the Customer Support department |

### Network Configuration

The Domain Controller uses two virtual network adapters:

- **NAT Adapter:** Provides connectivity outside of the isolated lab network.
- **Internal Network Adapter:** Provides communication between the Domain Controller and domain workstations.

The internal Active Directory network uses the `172.16.0.0/24` subnet.

| Configuration | Value |
|---|---|
| Domain | `mydomain.com` |
| Domain Controller | `DC` |
| DC Internal IP Address | `172.16.0.1` |
| Internal Network | `172.16.0.0/24` |
| DHCP Address Pool | `172.16.0.100 - 172.16.0.200` |
| DNS Server | `172.16.0.1` |
| IT Workstation | `HK-IT-001` |
| Customer Support Workstation | `HK-CS-001` |
