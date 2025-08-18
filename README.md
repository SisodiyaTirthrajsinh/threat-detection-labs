# Threat Detection Labs 🔍

Collection of threat detection labs demonstrating real‑world attack patterns, log analysis, and detection logic using Splunk, Elastic Stack, and Sigma rules.

---

## 📂 Labs Included

### **Brute‑Force RDP Detection**
- Description: Simulates 10+ failed Windows RDP login attempts (EventID 4625, LogonType 10) followed by a successful login.
- Contents:
  - `detection.md`: Splunk SPL & Elastic KQL queries
  - `brute_force_rdp_sigma.yml`: Standardized Sigma rule
  - `sample-logs/windows_rdp_logs.csv`: Sample log events used for query testing

### **SharePoint ToolShell Zero‑Day Exploit Detection**
- Description: Based on the ToolShell exploit (CVE‑2025‑53770/53771); logs show spoofed POSTs to `ToolPane.aspx` followed by `spinstall0.aspx` shell deployment.
- Contents:
  - `detection.md`: Detection logic in SPL & KQL
  - `sharepoint_toolShell_sigma.yml`: Sigma rule for cross-platform detection
  - `sample-logs/sharepoint_logs.csv`: Sample IIS logs simulating attack


## 🧠 About Me

I’m a proactive Threat Detection Engineer with hands‑on experience in building use cases and detection content mapped to MITRE ATT&CK. My labs showcase a structured approach to identifying real-world behavior using log data and query languages. Ready to contribute to SOC teams and threat hunting operations.


Happy to collaborate or share more if needed. Your feedback or suggestions welcome!
