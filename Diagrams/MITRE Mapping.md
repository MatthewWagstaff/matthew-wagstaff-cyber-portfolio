## MITRE ATT&CK Mapping

The observed behaviour was mapped against known MITRE ATT&CK techniques to better understand the nature of the activity and its potential impact.

- **T1059.001 – Command and Scripting Interpreter: PowerShell**  
  Identified use of an encoded PowerShell command, commonly used to execute obfuscated or malicious scripts.

- **T1105 – Ingress Tool Transfer (C2 Communication)**  
  Observed outbound connection to an external IP address, indicating possible command-and-control communication.

- **T1547 – Boot or Logon Autostart Execution (Persistence via Registry)**  
  Indicators of registry modification suggesting an attempt to maintain persistence on the system.

This mapping helped confirm that the activity followed a known attack pattern involving execution, communication, and persistence techniques.

