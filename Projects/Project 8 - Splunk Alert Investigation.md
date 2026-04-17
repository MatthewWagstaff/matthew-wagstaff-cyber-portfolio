# Project 8 — Splunk Alert Investigation

## Objective

Investigate suspicious authentication activity within Splunk to determine whether the behaviour is malicious, assess potential impact, and recommend appropriate response actions.

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

This pattern suggested a potential brute-force attack against a user account.

---

## Investigation

I began by reviewing the alert details within Splunk to understand what triggered the detection and confirm it was not a false positive.

Using SPL queries, I filtered authentication logs by:
- Target user account  
- Source IP address  
- Relevant timeframe  

This allowed me to identify a clear pattern of repeated failed login attempts followed by a successful authentication.

Further analysis identified:
- Login attempts originating from an unfamiliar external IP address  
- A successful login immediately after multiple failures  
- Activity occurring outside of expected working hours  

I then correlated related events to build a timeline of activity and assess whether the behaviour aligned with normal user patterns.

---

## Example SPL Query

```spl
index=auth_logs user="target_user"
| stats count by src_ip, action
```spl
---

MITRE ATT&CK Mapping
T1110 — Brute Force
Repeated failed authentication attempts used to guess valid credentials
T1078 — Valid Accounts
Successful login using compromised credentials
Findings
High volume of failed login attempts from a single source IP
Successful authentication following repeated failures
Login behaviour inconsistent with normal user activity
Indicators of potential account compromise
Response
Flagged the activity as suspicious and high risk
Recommended immediate account containment (reset credentials / disable account)
Suggested blocking the identified source IP address
Advised further review of account activity for potential lateral movement
Outcome

The activity was assessed as likely malicious, demonstrating characteristics of a brute-force attack leading to potential account compromise. Escalation was recommended for containment and further investigation.

Skills Demonstrated
SIEM alert triage and investigation
SPL query development and log analysis
Event correlation and timeline building
Threat identification and risk assessment
MITRE ATT&CK mapping
Clear documentation for escalation
Related Diagrams
MITRE Mapping
Attack Flow
SIEM Flow
