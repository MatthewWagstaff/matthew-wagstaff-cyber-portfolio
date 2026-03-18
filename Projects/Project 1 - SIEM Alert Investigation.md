# Project 1 — SIEM Alert Investigation

## Objective
Investigate a suspicious PowerShell alert using Wazuh & Sysmon.

## Tools
Wazuh, Sysmon, Event Viewer, MITRE ATT&CK

## Process
1. Reviewed Wazuh alert metadata  
2. Pulled Sysmon logs (Event ID 1, 4104)  
3. Identified Base64‑encoded PowerShell command  
4. Decoded payload  
5. Detected C2 communication attempt  
6. Mapped activity to MITRE T1059.001  
7. Documented findings  

## Key Findings
- Malicious PowerShell execution  
- Outbound connection to suspicious IP  
- Persistence attempt via registry  

## Related Diagrams
- [MITRE Mapping](../Diagrams/MITRE%20Mapping.md)
- [Attack Flow](../Diagrams/Attack%20Flow.md)
- [SIEM Flow](../Diagrams/SIEM%20Flow.md)
