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

This behaviour is commonly associated with brute-force attempts against user accounts.

---

## Investigation

I began by reviewing the alert details within Splunk to confirm the trigger conditions and rule out any false positives.

Using SPL queries, I filtered authentication logs by:
- Target user account  
- Source IP address  
- Relevant time window  

This allowed me to identify a clear pattern of repeated failed login attempts followed by a successful authentication event.

Further analysis showed:
- Login attempts originated from an unfamiliar external IP address  
- The successful login occurred immediately after multiple failures  
- Activity took place outside of expected working hours  

I then correlated events across the timeframe to build a clear sequence of activity and assess whether the behaviour aligned with normal user patterns.

---

## Example SPL Query

```spl
index=auth_logs user="target_user"
| stats count by src_ip, action

```

This query was used to group authentication activity by source IP and action, helping identify a high volume of failed login attempts followed by a successful login from the same source.

---

## MITRE ATT&CK Mapping

- **T1110 — Brute Force**  
- **T1078 — Valid Accounts**

---

## Findings

- High number of failed login attempts from a single source IP  
- Successful login immediately after failures  
- Source IP not recognised as normal user activity  
- Login timing outside expected behaviour  

---

## Response

- Flagged as suspicious and high risk  
- Recommended password reset / account lock  
- Suggested blocking source IP  
- Advised further investigation for lateral movement  

---

## Outcome

Activity assessed as likely malicious, consistent with brute-force leading to account compromise.

---

## Skills Demonstrated

- SIEM alert investigation  
- SPL query usage  
- Log analysis and correlation  
- Threat identification  
- MITRE ATT&CK mapping  
- Incident documentation  

---

## Related Diagrams

- [MITRE Mapping](../Diagrams/MITRE%20Mapping.md)  
- [Attack Flow](../Diagrams/Attack%20Flow.md)  
- [SIEM Flow](../Diagrams/SIEM%20Flow.md)  
