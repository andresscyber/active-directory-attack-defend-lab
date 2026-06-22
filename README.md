# Active Directory Attack & Defend Lab

## Overview

This project demonstrates the deployment of an Active Directory lab environment integrated with Sysmon and Wazuh for detection engineering, threat hunting, and security monitoring.

The lab simulates common attacker behavior including account creation, privilege escalation, reconnaissance activity, failed logons, PowerShell execution, and malware-related events. Security telemetry is collected through Sysmon and forwarded to Wazuh where detections are analyzed and mapped to MITRE ATT&CK techniques.

---

## Lab Objectives

- Build an Active Directory environment
- Deploy a Windows Server 2022 Domain Controller
- Join a Windows 11 workstation to the domain
- Install and configure Sysmon
- Install and configure the Wazuh agent
- Simulate attacker techniques
- Generate security events
- Perform threat hunting investigations
- Map detections to MITRE ATT&CK

---

## Technologies Used

- Windows Server 2022
- Windows 11
- Active Directory Domain Services
- Sysmon
- Wazuh
- PowerShell
- MITRE ATT&CK
- VMware Workstation

---

## Lab Architecture

Domain Controller (Windows Server 2022)
↓
Active Directory
↓
Windows 11 Workstation
↓
Sysmon
↓
Wazuh Agent
↓
Wazuh Manager

---

## Active Directory Deployment

### Domain Controller Setup

![Domain Controller](screenshots/02-domain-controller/21-domain-users-created.png)

### Domain Workstation Joined to Domain

![Workstation](screenshots/03-domain-workstation/10-domain-membership-verification.png)

---

## Sysmon and Wazuh Deployment

### Sysmon Installation

![Sysmon](screenshots/04-sysmon-wazuh/03-sysmon-installed.png)

### Wazuh Agent Registration

![Wazuh Agent](screenshots/04-sysmon-wazuh/08-win11-agent-active-in-wazuh.png)

---

## Attack Simulations

### Encoded PowerShell Execution

![PowerShell](screenshots/05-attack-simulation/01-encoded-powershell-execution.png)

### User Account Creation

![User Creation](screenshots/05-attack-simulation/02-user-account-created.png)

### Failed Logon Activity

![Failed Logon](screenshots/05-attack-simulation/04-failed-logon-attempts.png)

### Privilege Escalation

![Privilege Escalation](screenshots/05-attack-simulation/08-eviluser-added-to-admin-group.png)

---

## Detection Events

### User Account Creation Detection

![User Creation Detection](screenshots/06-detection-events/02-user-account-creation-detection.png)

### Failed Logon Detection

![Failed Logon Detection](screenshots/06-detection-events/04-failed-logon-detection.png)

### Malware Drop Detection

![Malware Detection](screenshots/06-detection-events/05-malware-drop-detection.png)

### Administrator Group Detection

![Admin Detection](screenshots/06-detection-events/06-user-added-to-administrators-group-detection.png)

---

## Threat Hunting

### Failed Logon Investigation

![Threat Hunting](screenshots/07-threat-hunting/01-search-for-failed-logons.png)

### User Account Investigation

![Threat Hunting](screenshots/07-threat-hunting/02-investigating-eviluser-account.png)

### Malware Alert Investigation

![Threat Hunting](screenshots/07-threat-hunting/06-hunting-malware-drop-alerts.png)

---

## MITRE ATT&CK Mapping

### ATT&CK Overview

![MITRE](screenshots/08-mitre-mapping/01-mitre-attack-overview.png)

### User Account Creation Mapping

![MITRE Mapping](screenshots/08-mitre-mapping/02-user-account-created-mitre-mapping.png)

Mapped Technique:

- T1136 – Create Account

---

## Wazuh Dashboard

![Dashboard](screenshots/09-final-dashboard/01-wazuh-overview-dashboard.png)

---

## Skills Demonstrated

- Active Directory Administration
- Windows Security Monitoring
- Detection Engineering
- Threat Hunting
- Security Event Analysis
- Sysmon Configuration
- Wazuh Administration
- MITRE ATT&CK Mapping
- Security Investigations
- Log Analysis

---

## Resume Highlights

- Built an Active Directory attack and defense lab using Windows Server 2022, Windows 11, Sysmon, and Wazuh.
- Developed custom detections for user creation and administrator group membership changes.
- Performed threat hunting investigations using Wazuh event telemetry and Sysmon logs.
- Mapped detections to MITRE ATT&CK techniques to improve detection coverage and analysis.