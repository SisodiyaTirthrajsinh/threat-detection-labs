# Brute Force RDP Detection Lab

## Description

This lab demonstrates detection logic for identifying brute-force Remote Desktop Protocol (RDP) login attempts using Windows logs, Splunk SPL, and Elastic KQL.

RDP brute force remains a top threat: attackers often target exposed RDP endpoints with repeated login attempts using common or stolen credentials, aiming to gain unauthorized access.:contentReference[oaicite:1]{index=1}

## MITRE ATT&CK

- **T1110 – Brute Force**
- **T1078 – Valid Accounts (if successful login occurs after failures)**

## Tools & Data

- **Data Source:** Windows Security Logs (EventID 4625 & 4624), network logs
- **Platform:** Splunk, Elastic Stack (KQL)
- **Supporting tools:** Winlogbeat or Sysmon for log ingestion

## Events of Interest

- **EventID 4625:** Failed Logon (with LogonType 10 for RDP)
- **EventID 4624:** Successful Logon (for confirming breach)

## Detection Logic

### Splunk SPL

```splunk
index=winlogbeat EventCode=4625 LogonType=10
| stats count by src_ip, user
| where count > 10
