# Automation Flow

This diagram outlines the process used by the PowerShell automation script to collect logs and identify potential indicators of compromise.

**Flow:**

Collect Logs → Filter Data → Identify IOCs → Output Results → Alert

---

## Breakdown

- **Collect Logs**  
  Retrieves relevant Windows Event Logs for analysis.

- **Filter Data**  
  Filters logs to focus on relevant events such as authentication activity.

- **Identify IOCs**  
  Searches for indicators such as suspicious IPs, failed logins, or unusual patterns.

- **Output Results**  
  Exports findings into a structured format for review.

- **Alert**  
  Generates an alert if suspicious activity is detected.

---

This process demonstrates how automation can support SOC workflows by reducing manual effort and improving detection speed.
