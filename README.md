.# Windows Forensics Lab



\## Overview



This project demonstrates basic Windows forensic investigation using Splunk Enterprise and Sysmon telemetry.



The goal of this lab is to analyze endpoint activity, identify process execution, review parent-child process relationships, investigate network connections, examine file creation events, and build a simple forensic timeline.



\---



\## Environment



| Component | Details |

|----------|---------|

| SIEM | Splunk Enterprise 10.4 |

| Endpoint | Windows 11 |

| Telemetry | Sysmon |

| Log Source | Microsoft-Windows-Sysmon/Operational |

| Framework | MITRE ATT\&CK |



\---



\## Investigation Objectives



\- Analyze process execution activity

\- Review PowerShell and command shell usage

\- Investigate parent-child process relationships

\- Review network connections

\- Analyze file creation events

\- Build a basic forensic timeline



\---



\## 1. Process Analysis



\### Objective



Identify process execution activity on the Windows endpoint.



\### SPL Query



```spl

index=\* sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"

| search "powershell.exe"

