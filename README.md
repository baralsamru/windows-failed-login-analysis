# Windows Failed Login Analysis

## Project Overview
I analyzed Windows Security Event Logs to identify failed authentication attempts (Event ID 4625). This project simulates a basic SOC investigation task — reviewing login failures for signs of brute force attacks.

## Tools Used
- Windows Event Viewer
- Windows PowerShell (Get-WinEvent)
- MITRE ATT&CK Framework

## What I Did
1. Generated 10+ failed login attempts by intentionally locking my screen and entering wrong passwords
2. Used Event Viewer to filter for Event ID 4625 (failed logons)
3. Examined timestamps, targeted usernames, and failure reasons
4. Attempted to identify source IP addresses (local vs. network)
5. Documented findings in a structured report

## Key Findings
| Field | Value |
|-------|-------|
| Total failed logins analyzed | 5 events |
| Failure reason most common | Unknown username or bad password (0xC000006A) |
| Source of attempts | Local computer (no network IPs detected) |
| Threat assessment | Low — consistent with user error, not brute force |

## Screenshots
![Event Viewer showing failed login](screenshot1.png)
![PowerShell output](screenshot2.png)

## MITRE ATT&CK Mapping
- **T1110 (Brute Force)** — Multiple failed authentication attempts observed
- **T1078 (Valid Accounts)** — Failed logins indicate attacker would need valid credentials first

## What I Learned
- How to navigate Windows Event Viewer and filter for specific Event IDs
- The difference between successful (4624) and failed (4625) logons
- How to extract forensic data using PowerShell commands
- When failed logins indicate user error vs. suspicious activity

