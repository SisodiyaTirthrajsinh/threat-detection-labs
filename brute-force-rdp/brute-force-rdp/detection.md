# Detection Logic – Brute Force RDP

## Behavior Overview

Attackers frequently perform brute-force login attempts on exposed RDP services using repeated guesses. Successful entry may lead to privilege misuse or malware deployment.:contentReference[oaicite:1]{index=1}

## MITRE ATT&CK Mapping

- **T1110 – Brute Force** (e.g. repeated login attempts):contentReference[oaicite:2]{index=2}  
- **T1021.001 – Remote Desktop Protocol** (use of RDP for access or lateral movement):contentReference[oaicite:3]{index=3}  

## Windows Event Log Fields Used

- **EventID 4625** – Failed Logon  
- **EventID 4624** – Successful Logon (to confirm compromise)  
- **LogonType = 10** – RemoteInteractive (RDP) attempts  

Watch for failed attempts followed by a success.:contentReference[oaicite:4]{index=4}

---

## Splunk SPL Detection Query

```spl
index=winlogbeat EventCode=4625 LogonType=10
| stats count by src_ip, user
| where count > 10
| join src_ip user [search index=winlogbeat EventCode=4624 LogonType=10]

Elastic KQL Detection Query
kql
Copy
Edit
event.code: 4625 AND winlog.event_data.LogonType: 10
| stats count by winlog.event_data.SourceIp, winlog.event_data.TargetUserName
| where count > 10
