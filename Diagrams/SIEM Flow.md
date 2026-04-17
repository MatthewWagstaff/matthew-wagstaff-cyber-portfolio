# SIEM Alert Flow

This diagram shows the process followed when investigating a SIEM alert, from initial detection through to analysis and classification.

**Flow:**

Wazuh Alert → Sysmon Logs → Analyst Review → Decode Payload → MITRE Mapping

---

## Breakdown

- **Wazuh Alert**  
  Alert generated indicating suspicious activity within the monitored environment.

- **Sysmon Logs**  
  Relevant Sysmon logs reviewed (e.g. Event ID 1, 4104) to understand process execution and behaviour.

- **Analyst Review**  
  Initial triage performed to determine if the alert represents genuine suspicious activity or a false positive.

- **Decode Payload**  
  Identified and decoded any encoded commands (e.g. Base64 PowerShell) to determine intent.

- **MITRE Mapping**  
  Mapped observed behaviour to MITRE ATT&CK techniques to classify the activity and understand its impact.

---

This flow demonstrates a structured approach to investigating SIEM alerts and identifying potential malicious activity.
