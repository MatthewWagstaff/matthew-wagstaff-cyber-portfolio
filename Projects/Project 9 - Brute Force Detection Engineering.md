# Project 9 — Brute Force Detection Engineering

## Objective

Design and test a brute-force detection use case within a simulated SOC environment, using authentication patterns to identify suspicious behaviour and support structured investigation.

---

## Environment

- Splunk Enterprise 8.3  
- Simulated SOC lab environment  
- Windows authentication log data  

---

## Tools Used

- Splunk (SPL queries)  
- Authentication log analysis  
- Detection logic development  
- MITRE ATT&CK framework  

---

## Use Case

The goal of this project was to create a simple but effective detection for brute-force activity by identifying repeated failed login attempts followed by a successful authentication from the same source.

This type of behaviour can indicate an attacker attempting to gain access to a valid account through repeated password guessing.

---

## Detection Logic

The detection was based on the following conditions:

- Multiple failed authentication attempts from the same source IP  
- Activity occurring within a short period of time  
- A successful authentication following the failed attempts  
- Behaviour not consistent with expected user activity  

---

## Example SPL Query

```spl
index=auth_logs
| stats count(eval(action="failure")) as failed_count count(eval(action="success")) as success_count by user, src_ip
| where failed_count > 5 AND success_count > 0
```

---

## Investigation Process

Once the detection logic identified suspicious activity, I reviewed the results to assess whether the behaviour was likely malicious.

I looked at:

volume of failed login attempts
timing between events
whether a successful login followed the failures
source IP behaviour
whether the login occurred outside expected hours
whether the source appeared normal for the user

This helped determine whether the activity looked like normal user error or an attack pattern requiring escalation.

---

MITRE ATT&CK Mapping

T1110 — Brute Force
Repeated failed login attempts used to guess valid credentials
T1078 — Valid Accounts
Successful use of credentials after repeated authentication failures

---

Findings

Detection logic successfully identified suspicious authentication patterns
Repeated failed logins followed by success created a clear high-risk pattern
The activity demonstrated how a simple correlation rule can improve visibility of account compromise attempts

---

Response

Recommended account review and credential reset
Suggested monitoring or blocking of suspicious source IP addresses
Advised further review for any related login or lateral movement activity
Documented findings in an escalation-ready format

---

Outcome

This project demonstrated how brute-force behaviour can be identified through detection engineering rather than waiting for a generic alert alone.

It also showed the value of combining detection logic with analyst review, helping reduce false positives while improving visibility of suspicious authentication activity.

---

Skills Demonstrated
Detection use case development
SPL query writing and refinement
Authentication log analysis
Threat identification and investigation
MITRE ATT&CK mapping
Structured escalation thinking

--- ## Related Diagrams 

- [MITRE Mapping](../Diagrams/MITRE%20Mapping.md)
- [Attack Flow](../Diagrams/Attack%20Flow.md)
- [SIEM Flow](../Diagrams/SIEM%20Flow.md)
- [Brute Force Detection Flow](../Diagrams/Brute%20Force%20Detection%20Flow.md)


