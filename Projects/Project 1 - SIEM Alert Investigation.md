# Project 1 — SIEM Alert Investigation

## Objective
Investigate a suspicious PowerShell execution alert identified within a Wazuh-monitored environment to determine potential malicious activity and risk.

## Tools
Wazuh, Sysmon, Event Viewer, MITRE ATT&CK

## Detection
- Alert generated in Wazuh indicating suspicious PowerShell activity  
- Initial triage identified encoded PowerShell command execution  

## Analysis
- Reviewed Wazuh alert details to understand what triggered the alert  
- Pulled Sysmon logs (Event ID 1 and 4104) to analyse process execution and script content  
- Identified Base64-encoded PowerShell command within logs  
- Decoded payload to determine intent  
- Observed outbound network communication to an external IP address  
- Assessed behaviour against known attack patterns  

## MITRE ATT&CK Mapping
- T1059.001 – Command and Scripting Interpreter: PowerShell  

## Findings
- Malicious PowerShell execution confirmed  
- Evidence of outbound communication to a suspicious IP (potential C2 activity)  
- Indicators of persistence via registry modification  

## Response
- Flagged activity as malicious and high-risk  
- Recommended isolation of affected host  
- Suggested blocking of identified IP address  
- Documented findings clearly for escalation and further investigation  

## Outcome
Activity assessed as likely malicious, demonstrating PowerShell-based execution and potential command-and-control behaviour. Escalation recommended for containment and remediation.

## Related Diagrams
- [MITRE Mapping](../Diagrams/MITRE%20Mapping.md)  
- [Attack Flow](../Diagrams/Attack%20Flow.md)  
- [SIEM Flow](../Diagrams/SIEM%20Flow.md)  




