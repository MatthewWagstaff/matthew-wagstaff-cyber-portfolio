# Brute Force Detection Flow

This diagram outlines the logic used to identify authentication patterns consistent with brute-force activity.

**Flow:**

Failed Logins → Threshold Met → Successful Login → Analyst Review → Escalation

---

## Breakdown

- **Failed Logins**  
  Multiple failed authentication attempts identified from the same source.

- **Threshold Met**  
  Detection logic checks whether failed login activity exceeds expected behaviour.

- **Successful Login**  
  A successful authentication after repeated failures increases suspicion of compromise.

- **Analyst Review**  
  Activity is reviewed for source IP, timing, user behaviour, and legitimacy.

- **Escalation**  
  If behaviour is confirmed as suspicious, the incident is documented and escalated.

---

This flow demonstrates how basic detection engineering can support faster identification of account compromise attempts.
