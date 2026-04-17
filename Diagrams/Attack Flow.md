# Attack Flow Diagram

This diagram shows the sequence of events identified during the investigation, from initial alert through to containment.

**Flow:**

Alert → PowerShell Execution → Decode Payload → Malicious Behaviour → Containment

---

## Breakdown

- **Alert**  
  Security alert triggered indicating suspicious PowerShell activity.

- **PowerShell Execution**  
  Detected execution of a PowerShell command within the system.

- **Decode Payload**  
  Identified and decoded Base64-encoded command to understand its purpose.

- **Malicious Behaviour**  
  Confirmed behaviour consistent with malicious activity, including potential command-and-control communication.

- **Containment**  
  Action taken to isolate the affected system and prevent further impact.

---

This flow demonstrates how an alert can be investigated step-by-step to identify malicious activity and apply appropriate containment.
