# Project 2 — Incident Response Simulation

## Objective
Simulate a phishing → credential theft → lateral movement incident to understand how it would be identified, investigated, and contained.

## Tools
Outlook, Sysmon, Splunk, Azure AD logs

## Detection
- Suspicious email identified within Outlook  
- Indicators of phishing, including a credential harvesting link  
- Alert triggered following login from an unusual location  

## Analysis
1. Collected and reviewed phishing email evidence  
2. Identified credential harvesting URL within the email  
3. Analysed Azure AD logs to detect foreign login activity  
4. Reviewed login patterns and location to confirm anomalous access  
5. Investigated potential lateral movement across the environment  

## Findings
- Phishing email delivered with credential harvesting link  
- Foreign login detected using compromised credentials  
- Indicators of attempted lateral movement  

## Response
- Contained compromised account  
- Forced password reset and revoked active sessions  
- Recommended blocking malicious domain  
- Documented incident timeline for escalation  

## Outcome
Incident contained at the account level with no confirmed wider impact. Demonstrated how phishing can lead to credential compromise and potential lateral movement if not identified early.

## Related Diagrams
- [IR Timeline](../Diagrams/IR%20Timeline.md)
