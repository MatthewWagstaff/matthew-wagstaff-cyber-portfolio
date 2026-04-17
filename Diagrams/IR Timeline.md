## Incident Response Timeline

Timeline of key events identified during investigation and response.

- **00:00** – Phishing email reported and initial alert raised after user interaction  
- **00:05** – Email evidence collected, including sender details, headers, and embedded links  
- **00:10** – Credential harvesting URL identified and analysed, confirming it was designed to capture user credentials  
- **00:20** – Foreign login detected in Azure AD logs from an unusual location not consistent with normal user behaviour  
- **00:25** – Authentication logs reviewed to confirm successful login using compromised credentials  
- **00:30** – Investigated potential lateral movement by reviewing access patterns, system activity, and account behaviour  
- **00:35** – Compromised account contained by disabling access and revoking active sessions  
- **00:40** – Password reset enforced and additional security measures applied to prevent further access  
- **00:45** – Incident fully documented, including findings, timeline, and recommended actions for escalation  

This timeline reflects a structured response aligned with standard incident response practices, ensuring clear investigation, containment, and escalation.
