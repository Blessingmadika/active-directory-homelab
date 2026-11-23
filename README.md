# active-directory-homelab

# TECHCORP SOLUTIONS
## Enterprise Active Directory Administration, Group Policy & PowerShell Automation Lab

**Project Type:** Windows Server Administration | Active Directory | Group Policy | PowerShell | IT Infrastructure

**Project Focus:** Enterprise IT Administration, Identity and Access Management, Security Policy Enforcement, and Infrastructure Automation.

---

## 1. Project Overview

TECHCORP SOLUTIONS is a simulated corporate IT environment developed to demonstrate practical skills in Windows Server administration, Active Directory management, Group Policy configuration, enterprise security, and PowerShell automation.

The project simulates the responsibilities of an IT Support Technician, Systems Administrator, and Junior Windows Server Administrator working within a business environment.

The objective is to design, configure, manage, secure, and maintain a centralized Windows domain infrastructure while implementing administrative procedures commonly used in enterprise IT environments.

Rather than focusing exclusively on theoretical concepts, this project emphasizes hands-on configuration, troubleshooting, testing, and documentation.

## 2. Project Objectives

The primary objectives of this project are to:

- Deploy and administer a centralized Active Directory environment.
- Create and manage domain users, organizational units, and security groups.
- Implement Group Policy Objects (GPOs) to enforce organizational policies.
- Configure enterprise desktop and user environment settings.
- Implement password policies and account security controls.
- Automate repetitive administrative tasks using Windows PowerShell.
- Perform Active Directory backup and recovery procedures.
- Troubleshoot authentication, Group Policy, and domain administration issues.

## 3. Simulated Business Environment

TECHCORP SOLUTIONS operates as a simulated organization with multiple departments requiring centralized user administration, access management, and security policy enforcement.

**Organizational structure:**

| Department | Purpose |
|---|---|
| Human Resources | Employee records and HR operations |
| Finance | Financial administration |
| Information Technology | IT infrastructure and technical support |
| Sales | Sales operations |
| Operations | General business operations |

The Active Directory environment will use organizational units (OUs) to separate departments, simplify administration, and support the application of department-specific Group Policies.

## 4. Project Architecture

The lab is designed around a Windows Server domain environment with domain-joined client workstations.

**Core infrastructure components:**

- Windows Server – Domain Controller
- Active Directory Domain Services (AD DS)
- Active Directory Users and Computers (ADUC)
- Group Policy Management Console (GPMC)
- Windows 10/11 – Domain-joined client workstation
- Windows PowerShell
- Microsoft Management Console (MMC)
- DNS and domain authentication services

**Architecture overview:**

```text
             TECHCORP SOLUTIONS
                     |
              Active Directory
                     |
               Domain Controller
                     |
          Organizational Units (OUs)
                     |
       +-------------+-------------+
       |             |             |
      HR          Finance          IT
       |             |             |
    Users         Users          Users
       |
  +----+--------+----------+
  |             |          |
 Sales       Operations   Security
                            Groups
                     |
                Group Policies
                     |
             Domain Workstations
                     |
             PowerShell Automation
```

## 5. Project Implementation

The implementation is divided into six phases, each focusing on a different area of enterprise Windows administration.

### Phase 1: Active Directory Fundamentals

**Focus:** Identity and Access Management (IAM).

This phase establishes the organizational structure and centralized user management environment.

**Technical implementation:**

- Explore and manage Active Directory Users and Computers (ADUC).
- Understand organizational units and containers.
- Create and organize departmental OUs.
- Create and manage domain user accounts.
- Search for Active Directory objects.
- Reset user passwords.
- Create security groups and manage group memberships.
- Disable and delete user accounts.
- Understand domain controller authentication considerations.

**Practical scenario:**

Establish the TECHCORP SOLUTIONS organizational structure by creating five departmental OUs and populating the environment with 10 fictional employee accounts.

Create security groups, assign appropriate memberships, and demonstrate common account administration procedures.

**Evidence & Screenshots:**

- [ ] Active Directory organizational structure.
- [ ] Departmental OUs and employee accounts.
- [ ] Security groups and group memberships.
- [ ] Password reset demonstration.
- [ ] Disabled user account.

---

### Phase 2: Group Policy Administration

**Focus:** Centralized Configuration Management.

This phase focuses on implementing and managing Group Policy Objects to control user and computer configurations across the domain.

**Technical implementation:**

- Create and link Group Policy Objects (GPOs).
- Understand Group Policy processing and precedence.
- Configure and edit GPO settings.
- Troubleshoot policies using Resultant Set of Policy (RSOP.msc).
- Analyze applied policies using `gpresult /r`.
- Configure non-inheriting OUs for policy testing.
- Understand Group Policy inheritance and enforcement.

**Practical scenario:**

Implement department-specific policies within TECHCORP SOLUTIONS.

Examples include:

- HR: Restrict access to Control Panel.
- Finance: Apply a designated desktop configuration.
- IT: Configure access to required administrative tools.
- All Employees: Apply company-wide configuration policies.

Test policy inheritance and precedence, then use RSOP and GPResult to verify and troubleshoot policy application.

**Evidence & Screenshots:**

- [ ] Group Policy Management Console.
- [ ] Created and linked GPOs.
- [ ] Configured departmental policies.
- [ ] RSOP policy results.
- [ ] GPResult command output.
- [ ] Group Policy inheritance testing.

---

### Phase 3: Enterprise Policy Deployment

**Focus:** User Environment and Software Management.

This phase demonstrates how enterprise administrators centrally configure employee workstations and user environments.

**Technical implementation:**

- Deploy corporate desktop backgrounds through Group Policy.
- Configure interactive logon banners.
- Deploy software using Group Policy.
- Configure roaming user profiles.
- Automatically map network shared drives.
- Configure user environment settings.

**Practical scenario:**

Configure a standardized employee workstation environment for TECHCORP SOLUTIONS.

Implement a corporate desktop background, acceptable-use login banner, test software deployment, roaming profile configuration, and automatic network drive mapping.

**Evidence & Screenshots:**

- [ ] Corporate desktop background applied.
- [ ] Interactive logon banner.
- [ ] Software deployment verification.
- [ ] Roaming profile configuration.
- [ ] Automatically mapped network drive.

---

### Phase 4: Active Directory Security

**Focus:** Security Policy Enforcement and Account Protection.

This phase focuses on strengthening domain security through centralized password management, account protection, and workstation security configurations.

**Technical implementation:**

- Configure domain password policies.
- Implement account lockout policies.
- Deploy Fine-Grained Password Policies (PSOs).
- Configure Windows Firewall through Group Policy.
- Configure Windows Registry settings through GPOs.

**Practical scenario:**

Implement security policies for TECHCORP SOLUTIONS to improve account protection and enforce consistent workstation security configurations.

Examples include:

- Enforce password complexity requirements.
- Configure password expiration and account lockout thresholds.
- Apply stricter password requirements to privileged accounts using PSOs.
- Configure Windows Firewall rules through Group Policy.
- Apply selected registry-based restrictions.

**Evidence & Screenshots:**

- [ ] Domain password policy configuration.
- [ ] Account lockout policy.
- [ ] Fine-Grained Password Policy configuration.
- [ ] Windows Firewall Group Policy.
- [ ] Registry-based policy configuration.

---

### Phase 5: PowerShell & Administrative Automation

**Focus:** Windows Administration and Automation.

This phase demonstrates the use of Windows PowerShell to automate repetitive Active Directory administration tasks.

**Technical implementation:**

- Enable PowerShell script execution where appropriate.
- Understand PowerShell fundamentals.
- Retrieve and list Active Directory users.
- Create Active Directory user accounts using PowerShell.
- Import employee accounts from CSV files.
- Configure roaming profile paths using PowerShell.
- Identify disabled Active Directory accounts.
- Move disabled users into a designated Disabled Users OU.
- Handle duplicate usernames during account creation.

**Practical scenario:**

Develop PowerShell scripts to automate employee account administration within TECHCORP SOLUTIONS.

The automation process will support bulk account creation, user identification, OU organization, profile configuration, and disabled account management.

**Planned automation scripts:**

| Script | Function |
|---|---|
| Get-ADUsers.ps1 | Retrieve Active Directory user accounts |
| New-ADUser.ps1 | Create individual domain users |
| Import-ADUsers.ps1 | Create users from a CSV file |
| Set-RoamingProfile.ps1 | Configure roaming profile paths |
| Move-DisabledUsers.ps1 | Move disabled users to a designated OU |
| Check-DuplicateUsers.ps1 | Identify potential duplicate usernames |

**Evidence & Screenshots:**

- [ ] PowerShell command execution.
- [ ] Active Directory user listing.
- [ ] Automated user creation.
- [ ] CSV employee import.
- [ ] Disabled account identification.
- [ ] Automated OU movement.
- [ ] Script execution results.

---

### Phase 6: Active Directory Backup & Disaster Recovery

**Focus:** Infrastructure Protection and Recovery.

This phase demonstrates the importance of protecting Active Directory infrastructure and preparing for potential system failures.

**Technical implementation:**

- Understand Active Directory System State backups.
- Configure and perform a System State backup.
- Understand Active Directory restoration procedures.
- Document the recovery process.
- Validate domain functionality following recovery.

**Practical scenario:**

Perform a System State backup of the TECHCORP SOLUTIONS Domain Controller and document the recovery procedure.

Where possible, simulate a recovery scenario using an isolated test environment or virtual machine snapshot.

**Evidence & Screenshots:**

- [ ] Backup configuration.
- [ ] Successful System State backup.
- [ ] Backup completion output.
- [ ] Documented restoration procedure.
- [ ] Post-recovery validation.

---

## 6. Technologies & Tools

| Technology | Application |
|---|---|
| Windows Server | Server administration |
| Active Directory Domain Services | Centralized identity management |
| Active Directory Users and Computers | User and group administration |
| Group Policy Management | Centralized policy enforcement |
| Windows PowerShell | Administrative automation |
| RSOP.msc | Group Policy troubleshooting |
| GPResult | Policy verification |
| Microsoft Management Console | Windows administration |
| Windows 10/11 | Domain-joined client testing |
| DNS | Domain name resolution |
| Windows Server Backup | Infrastructure backup |

## 7. Skills Demonstrated

Upon completing the project, the lab will demonstrate practical experience in:

**Windows Server Administration**
- Domain Controller administration.
- Active Directory management.
- Organizational Unit administration.
- Domain-joined workstation management.

**IT Support & User Administration**
- User account provisioning.
- Password resets and account troubleshooting.
- Group membership administration.
- User access management.

**Group Policy & Infrastructure Management**
- GPO creation and configuration.
- Policy inheritance and precedence.
- Centralized workstation configuration.
- Group Policy troubleshooting.

**Security Administration**
- Password and account lockout policies.
- Fine-Grained Password Policies.
- Firewall configuration.
- Registry-based policy enforcement.

**PowerShell & Automation**
- Active Directory PowerShell cmdlets.
- Bulk user provisioning.
- CSV-based account management.
- Administrative task automation.

**Backup & Recovery**
- Active Directory System State backups.
- Recovery planning.
- Infrastructure validation.

## 8. Project Documentation & Evidence

Screenshots, configuration evidence, PowerShell scripts, and implementation notes will be added to this repository as each phase is completed.

The repository will serve as a technical portfolio demonstrating the practical implementation of Windows Server and Active Directory administration concepts in a simulated enterprise environment.

## 9. Project Status

**Implementation roadmap:**

- [ ] Phase 1 – Active Directory Fundamentals
- [ ] Phase 2 – Group Policy Administration
- [ ] Phase 3 – Enterprise Policy Deployment
- [ ] Phase 4 – Active Directory Security
- [ ] Phase 5 – PowerShell & Administrative Automation
- [ ] Phase 6 – Backup & Disaster Recovery

*Project documentation and implementation evidence will be updated progressively as each phase is completed and tested.*

---

## 10. Author

**Project:** TECHCORP SOLUTIONS – Enterprise Active Directory Administration Lab

**Developed by:** Blessing Madika

**Area of Focus:** IT Support | Windows Server Administration | Active Directory | Networking | Systems Administration

**Purpose:** Practical technical development and demonstration of enterprise IT administration capabilities.

---

*This is an independently developed simulated enterprise lab. TECHCORP SOLUTIONS is a fictional organization created for educational and professional portfolio purposes.*
T
