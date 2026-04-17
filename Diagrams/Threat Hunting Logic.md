# Threat Hunting Logic

This diagram represents the structured approach taken during the threat hunting exercise, focusing on identifying potential persistence mechanisms.

**Flow:**

Hypothesis → Log Query → Detection → Investigation → MITRE Mapping → Remediation

**Breakdown:**

- **Hypothesis**  
  Assumed an attacker may attempt to maintain persistence using registry Run keys.

- **Log Query**  
  Queried Sysmon logs (Event ID 13) to identify registry modifications.

- **Detection**  
  Identified a suspicious registry entry linked to an unfamiliar executable.

- **Investigation**  
  Analysed the associated executable and its behaviour to determine legitimacy.

- **MITRE Mapping**  
  Mapped activity to T1547 (Boot or Logon Autostart Execution).

- **Remediation**  
  Recommended removal of the registry entry and further analysis of the executable.

  This approach ensures a structured and repeatable method for identifying suspicious activity during proactive threat hunting.
