# Project 3 — Threat Hunting Exercise

## Objective
Hunt for persistence mechanisms using Sysmon.

## Tools
Sysmon, Wazuh, MITRE ATT&CK

## Process
1. Formed hypothesis: attacker may use Run keys  
2. Queried Sysmon Event ID 13  
3. Identified suspicious registry entry  
4. Investigated associated executable  
5. Mapped to MITRE T1547  

## Related Diagrams
- [Threat Hunting Logic](../Diagrams/Threat%20Hunting%20Logic.md)

