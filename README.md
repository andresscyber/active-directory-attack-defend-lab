# Active Directory Attack & Defend Lab

## Overview

This project simulates an enterprise Active Directory environment and demonstrates how common attacker behavior can be detected using Wazuh, Sysmon, Windows Security Events, custom detection rules, and MITRE ATT&CK mapping.

The lab includes:

- Windows Server 2022 Domain Controller
- Windows 11 Domain-Joined Workstation
- Active Directory Domain Services
- Organizational Units and Security Groups
- Sysmon Endpoint Telemetry
- Wazuh SIEM Platform
- Custom Detection Rules
- MITRE ATT&CK Mapping
- Threat Hunting Investigations

---

## Technologies Used

- Active Directory Domain Services (AD DS)
- Windows Server 2022
- Windows 11 Enterprise
- Wazuh SIEM
- Sysmon
- VMware Workstation
- PowerShell
- Windows Event Viewer
- MITRE ATT&CK Framework

---

# 1. Lab Environment Setup

### Project Structure

![Project Structure](screenshots/01-lab-setup/01-project-folder-structure.png)

---

# 2. Domain Controller Deployment

### Windows Server Installation

![Server Install](screenshots/02-domain-controller/01-server2022-install-options.png)

### Server Installation Progress

![Install Progress](screenshots/02-domain-controller/02-server2022-install-progress.png)

### Server Desktop

![Desktop](screenshots/02-domain-controller/03-server2022-desktop.png)

### Domain Controller Renamed

![Rename Server](screenshots/02-domain-controller/04-server-renamed-ad-dc01.png)

### Static IP Configuration

![Static IP](screenshots/02-domain-controller/06-static-ip-configuration.png)

### Active Directory Installation

![AD DS](screenshots/02-domain-controller/08-add-ad-ds-role.png)

### Domain Promotion

![Promotion](screenshots/02-domain-controller/09-ad-ds-installed-promotion-required.png)

### New Forest Creation

![Forest](screenshots/02-domain-controller/10-new-forest-corp-local.png)

### Active Directory Users and Computers

![AD Users](screenshots/02-domain-controller/18-active-directory-users-computers.png)

### Organizational Units Created

![OU Creation](screenshots/02-domain-controller/19-organizational-units-created.png)

### Security Groups Created

![Security Groups](screenshots/02-domain-controller/20-security-groups-created.png)

### Domain Users Created

![Domain Users](screenshots/02-domain-controller/21-domain-users-created.png)

---

# 3. Windows 11 Domain Workstation

### DNS Configuration

![DNS](screenshots/03-domain-workstation/05-win11-dns-configured.png)

### Domain Join Success

![Domain Join](screenshots/03-domain-workstation/07-domain-join-success.png)

### Domain User Login

![Domain Login](screenshots/03-domain-workstation/09-domain-user-login.png)

### Domain Membership Verification

![Membership](screenshots/03-domain-workstation/10-domain-membership-verification.png)

---

# 4. Sysmon and Wazuh Deployment

### Sysmon Downloaded

![Sysmon Download](screenshots/04-sysmon-wazuh/02-sysmon-config-downloaded.png)

### Sysmon Installed

![Sysmon Installed](screenshots/04-sysmon-wazuh/03-sysmon-installed.png)

### Sysmon Configuration Verified

![Sysmon Verified](screenshots/04-sysmon-wazuh/04-sysmon-configuration-verified.png)

### Sysmon Operational Log

![Sysmon Log](screenshots/04-sysmon-wazuh/05-sysmon-operational-log.png)

### Wazuh Agent Service Running

![Wazuh Agent Service](screenshots/04-sysmon-wazuh/06-wazuh-agent-service-running.png)

### Wazuh Agent Registration

![Wazuh Agent](screenshots/04-sysmon-wazuh/07-win11-agent-active-in-wazuh.png)

### Sysmon Events Collected

![Sysmon Events](screenshots/04-sysmon-wazuh/08-sysmon-events-operational-log.png)

---

# 5. Attack Simulation

## Encoded PowerShell Execution

![PowerShell](screenshots/05-attack-simulation/01-encoded-powershell-execution.png)

### Detection

Custom Wazuh detection rule generated an alert for suspicious PowerShell activity.

---

## User Account Creation

![User Created](screenshots/05-attack-simulation/02-user-account-created.png)

### Detection

Custom Wazuh rule generated an alert when a new user account was created.

---

## Discovery Activity

![Recon](screenshots/05-attack-simulation/03-reconnaissance-commands.png)

### Detection

Wazuh detected account discovery activity and mapped the behavior to MITRE ATT&CK Discovery techniques.

---

## Failed Logon Attempts

![Failed Logons](screenshots/05-attack-simulation/04-failed-logon-attempts.png)

### Detection

Multiple failed authentication attempts generated Windows Security Event 4625 alerts.

---

## User Added to Administrators Group

![Admin Group](screenshots/05-attack-simulation/08-eviluser-added-to-admin-group.png)

### Detection

Custom Wazuh detection identified privilege escalation activity.

---

# 6. Threat Hunting Investigation

### Failed Logon Investigation

![Failed Logons Search](screenshots/07-threat-hunting/01-search-for-failed-logons.png)

### User Account Creation Investigation

![User Creation Hunt](screenshots/07-threat-hunting/02-investigating-eviluser-account.png)

### Privilege Escalation Investigation

![Admin Group Hunt](screenshots/07-threat-hunting/03-investigating-admin-group-changes.png)

### Discovery Activity Investigation

![Discovery Hunt](screenshots/07-threat-hunting/04-hunting-discovery-activity.png)

### PowerShell Investigation

![PowerShell Hunt](screenshots/07-threat-hunting/05-hunting-powershell-activity.png)

### Malware Drop Investigation

![Malware Hunt](screenshots/07-threat-hunting/06-hunting-malware-drop-alerts.png)

---

# 7. MITRE ATT&CK Mapping

### MITRE ATT&CK Overview

![MITRE Dashboard](screenshots/08-mitre-mapping/01-mitre-attack-overview.png)

### User Account Creation Mapping

![MITRE Mapping](screenshots/08-mitre-mapping/02-user-account-created-mitre-mapping.png)

### Techniques Demonstrated

| Activity | MITRE Technique |
|-----------|-----------|
| User Creation | T1136 |
| Account Discovery | T1087 |
| PowerShell Execution | T1059.001 |
| Privilege Escalation | T1098 |
| Failed Logons | Credential Access |
| Malware Drop | Defense Evasion |

---

# 8. Detection Engineering Outcomes

The lab successfully demonstrated:

- Active Directory deployment and administration
- Endpoint telemetry collection using Sysmon
- Centralized log collection with Wazuh
- Custom detection rule development
- Windows Security Event monitoring
- Threat hunting investigations
- MITRE ATT&CK mapping
- Detection engineering workflows

---

# 9. Final Dashboard

![Wazuh Dashboard](screenshots/09-final-dashboard/01-wazuh-overview-dashboard.png)

---

## Resume Highlights

- Built enterprise Active Directory lab using Windows Server 2022 and Windows 11.
- Deployed Sysmon and Wazuh for endpoint visibility and centralized log analysis.
- Developed custom Wazuh detection rules for user creation and privilege escalation.
- Performed threat hunting investigations using Windows Security Events and Sysmon telemetry.
- Mapped detections to MITRE ATT&CK techniques.
- Simulated attacker activity including reconnaissance, PowerShell execution, credential abuse, and privilege escalation.
