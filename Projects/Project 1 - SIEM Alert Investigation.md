# Project 1 — SIEM Alert Investigation

## Objective
Investigate a suspicious PowerShell execution alert identified within a Wazuh-monitored environment to determine potential malicious activity and risk.

## Tools
Wazuh, Sysmon, Event Viewer, MITRE ATT&CK

## Detection
- Alert generated in Wazuh indicating suspicious PowerShell activity  
- Initial triage identified encoded command execution  

## Analysis
1. Reviewed Wazuh alert metadata to understand trigger conditions  
2. Pulled Sysmon logs (Event ID 1 and 4104) to analyse process execution and script content  
3. Identified Base64-encoded PowerShell command within logs  
4. Decoded payload to determine intent  
5. Observed outbound network communication to an external IP address  
6. Assessed behaviour against known attack patterns  

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
- Documented findings for escalation and further investigation  

## Outcome
Activity assessed as likely malicious, demonstrating PowerShell-based execution and potential command-and-control behaviour. Escalation recommended for containment and remediation.

## Related Diagrams
- [MITRE Mapping](../Diagrams/MITRE%20Mapping.md)
- [Attack Flow](../Diagrams/Attack%20Flow.md)
- [SIEM Flow](../Diagrams/SIEM%20Flow.md)
