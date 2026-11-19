INC-001 — Active Directory Employee Onboarding

Overview

This lab simulates a new employee onboarding request at Northbridge IT Ltd, a fictional organisation.

The objective was to provision a user account in Active Directory, organise departmental resources and configure appropriate security-group membership.

## Lab Environment

| Component | Configuration |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Server | Windows Server 2025 Evaluation |
| Client | Windows 11 Enterprise Evaluation |
| Domain | `corp.example.test` |
| Domain Controller | DC01 - `192.168.56.10` |
| Workstation | PC01 - `192.168.56.20` |
| Network | VirtualBox Host-only Network |


Service Desk Ticket

Ticket ID: INC-001
Category: User Account Management
Priority: Normal
Status: Resolved

Request: HR requires a new Active Directory account for Emma Carter, joining the HR department.

Implementation

1. Organisational Unit Structure

Created a departmental OU hierarchy to organise Active Directory objects.

corp.example.test
└── Northbridge
    ├── Employees
    │   ├── HR
    │   ├── IT
    │   └── Sales
    └── Workstations

Organisational units enable logical organisation of directory objects and provide a foundation for administrative delegation and Group Policy.

2. User Account Creation

Created a fictional employee account:

Display name: Emma Carter

Username: ecarter

Department OU: HR

Account status: Enabled

Initial password: Temporary password with change required at first logon

3. Security Group Configuration

Created the following Active Directory group:

GG_HR_Employees

Configuration:

Group scope: Global

Group type: Security

Added Emma Carter as a member.

This demonstrates group-based access management, enabling permissions to be assigned to groups rather than individual employees.

4. PowerShell Verification

Used PowerShell to inspect the account and group membership.

Get-ADUser -Identity ecarter -Properties MemberOf |
    Select-Object Name,SamAccountName,Enabled,MemberOf

Checked group membership using:

Get-ADGroupMember -Identity GG_HR_Employees

5. Troubleshooting and Lessons Learned

During the lab, I encountered a PowerShell CommandNotFoundException when attempting to use Get-ADUser on a machine without the Active Directory PowerShell module available.

I learned that:

PowerShell cmdlets can depend on additional modules.

Active Directory administration tools are not installed on every Windows workstation by default.

RSAT provides remote administrative capabilities for supported Windows clients.

PowerShell objects and pipelines allow administrators to retrieve specific account information.

Outcome

Completed the employee provisioning exercise and configured departmental security-group membership.

Skills Demonstrated

Active Directory Domain Services

Organisational Unit administration

User provisioning

Security group management

PowerShell fundamentals

Windows Server administration

IT support troubleshooting

Next Steps

INC-002: Join the Windows 11 Enterprise workstation to the corporate domain and test domain authentication.
