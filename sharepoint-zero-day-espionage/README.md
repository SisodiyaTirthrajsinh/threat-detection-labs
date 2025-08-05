# SharePoint ToolShell Zero‑Day Exploit Detection Lab

## Description
Based on CVE‑2025‑53770/53771 ("ToolShell") exploited in July 2025. Actors sent spoofed POST requests to **`ToolPane.aspx`**, then deployed **`spinstall0.aspx`** web shell to steal machine keys. Impacted government, enterprise & healthcare organizations.([turn0search2]],[turn0search3])

## MITRE ATT&CK Techniques
- **T1190** – Exploit public-facing application  
- **T1505.003** – Web shell deployment  
- **T1003 / T1078** – Credential theft / valid accounts  
- **T1059.003** – Command execution via w3wp.exe  
- **T1550** – Forged ASP.NET machine keys

## Tools & Logs
- **Logs:** IIS access entries containing method, uri_path, referer, src_ip, status  
- **Platforms:** Splunk, Elastic Stack 
