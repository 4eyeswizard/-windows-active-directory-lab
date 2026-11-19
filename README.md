

# Windows Server & Active Directory Home Lab

### Simulated Enterprise IT Support Environment | Northbridge IT Ltd

## Project Overview

This project documents the deployment and administration of a simulated corporate IT environment using Windows Server 2025, Windows 11 Enterprise and Active Directory Domain Services (AD DS).

The objective is to develop practical IT support and systems administration skills through realistic helpdesk scenarios, including employee onboarding, account management, Group Policy, network troubleshooting and access control.

**Northbridge IT Ltd** is a fictional company created for this home lab. All employees, accounts and support incidents are simulated.

## Lab Environment

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Server OS | Windows Server 2025 Evaluation |
| Client OS | Windows 11 Enterprise Evaluation |
| Domain | `corp.example.test` |
| Domain Controller | DC01 — `192.168.56.10` |
| Workstation | PC01 — `192.168.56.20` |
| Network | VirtualBox Host-only Network |
| Server Roles | Active Directory Domain Services, DNS |

### Network Architecture

```text
                 Northbridge IT Ltd
                  corp.example.test
                         |
             VirtualBox Host-only Network
                  192.168.56.0/24
                         |
            +------------+------------+
            |                         |
          DC01                      PC01
     Windows Server 2025       Windows 11 Enterprise
       192.168.56.10              192.168.56.20
            |
     Active Directory
     DNS / Group Policy
```

The lab uses an isolated virtual network to simulate corporate infrastructure without exposing domain services directly to the home network.

## Implementation Milestones

- [x] Installed Windows Server 2025 Evaluation
- [x] Installed Windows 11 Enterprise Evaluation
- [x] Configured VirtualBox virtual machines
- [x] Created an isolated host-only network
- [x] Assigned static IP addresses
- [x] Troubleshot ICMP connectivity and firewall rules
- [x] Installed Active Directory Domain Services
- [x] Promoted DC01 to a domain controller
- [x] Configured DNS for the domain
- [x] Created departmental organisational units
- [x] Created initial employee and security-group objects
- [ ] Joined PC01 to the domain
- [ ] Configured Group Policy
- [ ] Configured shared-folder permissions
- [ ] Completed domain troubleshooting exercises

## Simulated IT Support Tickets

| Ticket | Scenario | Status |
|---|---|---|
| [INC-001](INC-001-Employee-Onboarding/README.md) | Active Directory Employee Onboarding | Completed |
| INC-002 | Windows 11 Domain Joining | Planned |
| INC-003 | Password Reset | Planned |
| INC-004 | Account Lockout | Planned |
| INC-005 | Department Access Changes | Planned |
| INC-006 | Employee Offboarding | Planned |
| INC-007 | Shared Folder Permissions | Planned |
| INC-008 | Group Policy Configuration | Planned |
| INC-009 | DNS Troubleshooting | Planned |
| INC-010 | Domain Login Troubleshooting | Planned |

Each completed ticket will include its objective, implementation steps, verification, troubleshooting findings and lessons learned.

## Skills and Technologies

**Windows Administration**
- Windows Server 2025
- Windows 11 Enterprise
- Active Directory Domain Services
- User and Group Management
- Organisational Units
- DNS Administration

**Networking and Troubleshooting**
- IPv4 Addressing and Subnetting
- VirtualBox Host-only Networking
- Windows Defender Firewall
- ICMP Connectivity Testing
- Network Configuration Diagnostics

**Administration Tools**
- Server Manager
- Active Directory Users and Computers
- PowerShell
- Windows Command Prompt

## Key Learning Experiences

### Network Connectivity Troubleshooting

During network configuration, PC01 was unable to ping DC01 despite both machines having addresses within the same subnet.

Investigating the issue led to identifying an inbound Windows Firewall restriction affecting ICMP echo requests.

After adjusting the relevant firewall rule, connectivity was successfully verified.

This exercise reinforced the importance of systematic troubleshooting and distinguishing firewall restrictions from underlying network connectivity problems.

### PowerShell and Active Directory Administration

Used PowerShell to retrieve Active Directory user information and investigate security-group membership.

Encountered a `CommandNotFoundException` when attempting to run an Active Directory cmdlet without the necessary module available, highlighting the importance of PowerShell modules and administrative tools.

## Project Goals

- Develop hands-on experience with common first-line and second-line IT support responsibilities.
- Build confidence in Windows Server and Active Directory administration.
- Practise troubleshooting using realistic simulated incidents.
- Understand the relationship between DNS, domain authentication and access management.
- Maintain a documented technical portfolio demonstrating continuous learning.

## Disclaimer

This project is conducted entirely within a personally owned, isolated virtual lab environment. All organisational information, employee identities and incidents are fictional.

The project is intended for educational purposes and professional IT skills development.
