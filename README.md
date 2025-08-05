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

---

## 🧩 Structure of Each Lab

| Folder | Files Included |
|--------|----------------|
| `README.md` | Lab overview, context, MITRE mapping |
| `detection.md` | Splunk and KQL query logic |
| `*.yml` | Sigma rules (optional but professional) |
| `sample-logs/` | CSV logs illustrating attack behavior |

---

## 🧠 About Me

I’m a proactive Threat Detection Engineer with hands‑on experience in building use cases and detection content mapped to MITRE ATT&CK. My labs showcase a structured approach to identifying real-world behavior using log data and query languages. Ready to contribute to SOC teams and threat hunting operations.

---

## 📌 How to Use This Repo

1. Navigate into a lab folder (e.g. `brute-force-rdp/` or `sharepoint-zero-day-espionage/`).
2. Review the `README.md` inside that folder for context and MITRE mapping.
3. Open `detection.md` to see query logic in Splunk SPL and Elastic KQL.
4. (Optional) Load `*.yml` Sigma files into a rule engine to test portability.
5. Ingest sample logs into your SIEM and test detection queries.

---

## 🎯 Why It Matters

- Demonstrates knowledge of log analysis across platforms.
- Shows practical implementation of enterprise detection standards.
- Aligns with how modern threat detection teams operate using Sigma and MITRE frameworks.

---

Happy to collaborate or share more if needed. Your feedback or suggestions welcome!
