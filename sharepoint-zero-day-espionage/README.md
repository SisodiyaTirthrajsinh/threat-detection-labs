# SharePoint ToolShell Zero‑Day Exploit Detection Lab

## Description
Simulates the ToolShell exploit (CVE‑2025‑53770/53771) seen in July 2025. Actors bypass authentication via spoofed POSTs to `ToolPane.aspx`, then deploy `spinstall0.aspx` web shell from same IP. Observed in Storm‑2603‑cluster activity.:contentReference[oaicite:16]{index=16}

## MITRE ATT&CK Techniques
- T1190 – Exploit Public‑Facing Application  
- T1505.003 – Web Shell  
- T1003 / T1078 – Credential Access / Valid Accounts  
- T1059.003 – Command Interpreter via w3wp.exe  
- T1550 – Credential Forgery via machine key extraction :contentReference[oaicite:17]{index=17}

## Tools & Logs
- Logs include: `timestamp, method, uri_path, referer, src_ip, status`  
- Detection platforms: Splunk & Elastic Stack
