# df-mod3-smd

## Secure Data Management (SDM)

## Managing Permissions

## PowerShell Scripting

## Time Log

# DF Module 3 – Secure Data Management (SDM)

## Secure Data Management (SDM)
**Goal:** Demonstrate CIA: confidentiality (EFS encryption), integrity (ACL capture & restricted writes), availability (organized backups & artifacts).
- Commands used:
  - `Get-Process`, `Get-Service`, `Get-ChildItem` → inventory → CSV/TXT
  - `Get-Content`, `Select-String` → content search
  - `Export-Csv` → structured data capture
  - `Get-WinEvent` → event logs (Application/System)
  - `cipher /E` → EFS encryption at rest
- Example artifacts:
  - `artifacts/processes.csv`, `artifacts/services.csv`
  - `artifacts/system_events.txt`, `artifacts/search_results.txt`
  - `3-Evidence` (source) and `3-Evidence-Encrypted` (encrypted copy)

## Managing Permissions
- Captured ACLs before/after changes:
  - `artifacts/3-Evidence-ACL.txt`
  - `artifacts/3-Evidence-Encrypted-ACL.txt`
  - `artifacts/3-Evidence-Encrypted-ACL-Restricted.txt`
- Rationale:
  - Preserve integrity of evidence by denying write to broad groups (e.g., Users).
  - Optional: set ReadOnly attribute for quick protection; ACLs are stronger.

## PowerShell Scripting
- Script: `scripts/backup-evidence.ps1`
  - Creates dated backup folder
  - Copies evidence
  - Applies deny-write ACL to prevent overwrites
- Why it’s useful:
  - Repeatable, auditable, minimizes human error, supports availability.
- Screenshot(s): running the script in VS Code terminal & result folders.

## Time Log
- 00:00–00:30 — Repo setup & cloning  
- 00:30–01:15 — Artifacts gathering  
- 01:15–02:00 — Encryption & ACLs  
- 02:00–02:45 — Script & testing  
- 02:45–03:00 — README & push
