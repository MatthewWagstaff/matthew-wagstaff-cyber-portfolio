# Project 6 — PowerShell Automation Script

## Objective
Develop a PowerShell script to automate log collection and identify potential indicators of compromise (IOCs), improving efficiency during investigations.

## Tools
PowerShell, Windows Event Logs

## Functionality
- Collects relevant Windows Event Logs (e.g. Security logs)  
- Searches logs for defined indicators of compromise (e.g. suspicious IPs, failed login patterns)  
- Filters and organises results for easier analysis  
- Exports findings to a structured output file  
- Generates an alert when suspicious activity is detected  

## Approach
- Defined key indicators to search for based on common attack behaviour  
- Built script to automate log collection and filtering  
- Applied basic logic to highlight suspicious patterns within logs  
- Designed output to be clear and usable for investigation or escalation  

## Outcome
Script successfully automated initial log review and IOC detection, reducing manual effort and improving speed of analysis. Demonstrates how automation can support SOC workflows and improve response time.

## Related Diagrams
- [Automation Flow](../Diagrams/Automation%20Flow.md)

