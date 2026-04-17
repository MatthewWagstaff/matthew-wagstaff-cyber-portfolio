# Project 3 — Threat Hunting Exercise

## Objective
Proactively hunt for potential persistence mechanisms within a monitored environment, focusing on identifying unauthorised registry modifications that could indicate attacker activity.

## Tools
Sysmon, Wazuh, MITRE ATT&CK

## Detection / Hypothesis
- Formed hypothesis that an attacker may attempt to maintain persistence using registry Run keys  
- Focus placed on identifying abnormal or unauthorised registry modifications  

## Analysis
1. Queried Sysmon logs (Event ID 13) to identify registry value changes  
2. Filtered results to highlight unusual or suspicious entries within Run key locations  
3. Identified registry entry linked to an unfamiliar executable  
4. Investigated associated executable path and behaviour  
5. Assessed whether activity aligned with legitimate system processes or potential persistence mechanism  

## MITRE ATT&CK Mapping
- T1547 – Boot or Logon Autostart Execution  

The identified activity was consistent with persistence techniques used to maintain access after initial compromise.

## Findings
- Suspicious registry Run key entry identified  
- Linked executable determined to be potentially unauthorised  
- Behaviour consistent with persistence mechanism  

## Response
- Flagged activity for further investigation  
- Recommended removal of unauthorised registry entry  
- Suggested deeper analysis of associated executable  
- Documented findings for escalation and validation  

## Outcome
Hunting activity successfully identified a potential persistence mechanism. Demonstrated how proactive log analysis can detect threats that may not yet have triggered alerts.

## Related Diagrams
- [Threat Hunting Logic](../Diagrams/Threat%20Hunting%20Logic.md)

