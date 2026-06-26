# Troubleshooting Notes

## Issue 1

### Problem

Sysmon installation failed.

### Cause

Configuration XML file was missing.

### Resolution

Downloaded a valid Sysmon configuration XML and reinstalled Sysmon.

---

## Issue 2

### Problem

Commands such as:

- whoami
- hostname
- ipconfig
- net

were not recognized.

### Cause

The Windows System PATH variable was missing default Windows directories.

### Resolution

Restored the default Windows PATH entries including:

```
C:\Windows
C:\Windows\System32
C:\Windows\System32\Wbem
C:\Windows\System32\WindowsPowerShell\v1.0\
C:\Windows\System32\OpenSSH\
```

---

## Issue 3

### Problem

Sysmon events were not immediately visible in Wazuh.

### Resolution

Verified:

- Sysmon service status
- Sysmon Operational Event Log
- Wazuh Agent configuration
- Wazuh Agent service
- Event forwarding configuration

---

## Verification Commands

```powershell
Get-Service Sysmon64

Get-WinEvent -LogName "Microsoft-Windows-Sysmon/Operational" -MaxEvents 5

Get-Service WazuhSvc
```

---

# Outcome

After resolving the issues:

- Sysmon generated endpoint telemetry successfully.
- Wazuh collected endpoint events.
- Endpoint investigations could be performed using Wazuh dashboards.
