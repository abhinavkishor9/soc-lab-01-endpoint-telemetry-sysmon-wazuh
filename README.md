# soc-lab-01-endpoint-telemetry-sysmon-wazuh

## 📌 Overview

This project demonstrates how to collect and investigate Windows endpoint telemetry using **Sysmon** and **Wazuh**.

The objective is to build practical SOC analyst skills by investigating normal Windows activity in a workflow similar to Microsoft Defender XDR.

Instead of relying on a commercial EDR platform, this lab uses:

- Windows Host
- Sysmon
- Wazuh Agent
- Wazuh Dashboard
- Windows Event Logs

---

# 🎯 Objectives

- Install and configure Sysmon
- Collect endpoint telemetry
- Forward Sysmon events to Wazuh
- Investigate process creation events
- Build an investigation timeline
- Map activities to MITRE ATT&CK

---

# 🏗️ Lab Architecture

```
Windows Host
│
├── Windows Defender Antivirus
├── Sysmon
├── Windows Event Logs
├── Wazuh Agent
│
▼
Wazuh Server
│
▼
Wazuh Dashboard
```

---

# 🛠️ Tools Used

- Wazuh
- Sysmon
- Windows PowerShell
- Windows Event Viewer
- Windows Defender Antivirus

---

# 📋 Lab Activities

- Verified Sysmon installation
- Generated endpoint telemetry
- Investigated process creation events
- Examined command-line activity
- Correlated Sysmon logs in Wazuh
- Reconstructed an event timeline

---

# 🔍 Example Commands Executed

```powershell
whoami
hostname
ipconfig /all
ping 8.8.8.8 -n 3
notepad
calc
cmd
```

---

# 🎯 MITRE ATT&CK Mapping

| Command | Technique | ATT&CK ID |
|----------|-----------|-----------|
| whoami | System Owner/User Discovery | T1033 |
| hostname | System Information Discovery | T1082 |
| ipconfig | System Network Configuration Discovery | T1016 |
| ping | Network Discovery | T1018 |
| cmd | Command and Scripting Interpreter | T1059 |

---

# 🔍 Key Investigation Findings

- Sysmon successfully recorded endpoint activity.
- Wazuh ingested Windows endpoint telemetry.
- Process creation events were correlated with executed commands.
- Timeline reconstruction identified parent-child process relationships.
- MITRE ATT&CK techniques were mapped for each activity.

---

# 🚀 Skills Demonstrated

- Endpoint Monitoring
- Windows Event Analysis
- Sysmon
- Wazuh
- Threat Hunting
- Process Investigation
- MITRE ATT&CK Mapping
- SOC Investigation Workflow

---

## 📄 License

This project is intended for cybersecurity education and defensive security training.
