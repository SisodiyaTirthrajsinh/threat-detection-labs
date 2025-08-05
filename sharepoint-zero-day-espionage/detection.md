# Detection Logic – SharePoint ToolShell Exploit

## Behavior Overview
Chain: reconnaissance GET to ToolPane, spoofed POST, followed by web shell GET of spinstall0.aspx—all from same IP.

## Elastic KQL
```kql
method:"POST" uri_path:"/_layouts/15/ToolPane.aspx" referer:"/_layouts/SignOut.aspx"
| stats count by src_ip
| where count > 0
method:"GET" uri_path:"/_layouts/15/spinstall0.aspx" src_ip:<same-IP>

Splunk SPL
spl
Copy
Edit
index=sharepoint OR index=iis_access
method="POST" uri_path="/_layouts/15/ToolPane.aspx" referer="/_layouts/SignOut.aspx"
| stats count by src_ip
| where count > 0
| join type=inner src_ip [
  search index=sharepoint method="GET" uri_path="/_layouts/15/spinstall0.aspx"
]
