# Project 8 — Splunk Alert Investigation

## Objective

Investigate a suspicious authentication alert within Splunk to determine whether the activity is malicious, assess potential impact, and recommend appropriate response actions.

---

## Environment

- Splunk Enterprise 8.3  
- Simulated SOC lab environment  
- Windows authentication log data  

---

## Tools Used

- Splunk (SPL queries)  
- Log analysis and event correlation  
- MITRE ATT&CK framework  

---

## Detection

An alert was generated in Splunk indicating abnormal authentication activity.

Initial indicators showed:
- Multiple failed login attempts  
- Followed by a successful login  
- Activity occurring within a short timeframe  

This behaviour suggested a potential brute-force attempt.

---

## Investigation

I started by reviewing the alert details within Splunk to understand what triggered it.

Using SPL queries, I filtered authentication logs by:
- Target user account  
- Source IP address  
- Time range of the alert  

This allowed me to identify a pattern of repeated failed login attempts followed by a successful authentication.

Further analysis showed:
- The login attempts originated from an unfamiliar IP address  
- The successful login occurred immediately after multiple failures  
- The login took place outside of expected working hours  

I then correlated events to build a clear timeline of activity and confirm whether the behaviour aligned with normal user patterns.

## Example SPL Query

```spl
index=auth_logs user="target_user"
| stats count by src_ip, action

---

## MITRE ATT&CK Mapping

- T1110 — Brute Force  
- T1078 — Valid Accounts  

---

## Findings

- Behaviour consistent with a brute-force attack  
- Successful login suggests potential account compromise  
- Source IP considered suspicious based on activity pattern  
- Activity did not match expected user behaviour  

---

## Response

- Recommended immediate password reset and account review  
- Suggested monitoring or blocking of the source IP  
- Advised checking for further suspicious activity linked to the account  
- Escalated findings for further investigation  

---

## Outcome

The activity was assessed as likely malicious, demonstrating brute-force behaviour and potential unauthorised access.

This investigation highlights the importance of analysing authentication patterns, correlating events, and applying structured investigation techniques within a SIEM environment.

---

## Key Skills Demonstrated

- SIEM alert triage and investigation  
- SPL query usage for log analysis  
- Event correlation and timeline building  
- Threat identification and risk assessment  
- MITRE ATT&CK mapping  
- Clear documentation for escalation  
