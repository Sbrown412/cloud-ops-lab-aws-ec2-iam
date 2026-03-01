# AWS Cloud Ops Lab — EC2 + IAM Least Privilege + Operational Runbook

## Overview
This repository is a small AWS operations lab designed to demonstrate **safe cloud administration** and **professional documentation practices**. The infrastructure is intentionally simple; the focus is on operational discipline: access control, validation evidence, and repeatable runbooks.

## What this demonstrates
- IAM **group-based access control** with a restricted “sandbox” user group
- **Least-privilege** mindset using explicit denies to reduce risk and accidental billing exposure
- EC2 instance lifecycle control (run, validate, stop)
- SSH session validation and basic health checks
- Documentation-first workflow (README + runbook + decision notes)
- Version-controlled change history (Git)

## Repository structure
- `RUNBOOK.md` — operational procedures (start/validate/stop + troubleshooting)
- `docs/` — design decisions and redaction notes for public sharing
- `evidence/screenshots/` — ordered screenshots that validate configuration and enforcement

## Evidence (ordered)
1. IAM user groups (separation of duties)  
   `evidence/screenshots/01-iam-user-groups.png`
2. Sandbox policy attached (restricted permissions)  
   `evidence/screenshots/02-sandbox-policy.png`
3. Policy validation (AccessDenied confirms enforcement)  
   `evidence/screenshots/03-validation-access-denied.png`
4. Admin permissions (administrative control layer)  
   `evidence/screenshots/04-admin-permissions.png`
5. EC2 running state (deployment visible)  
   `evidence/screenshots/05-ec2-running.png`
6. EC2 lifecycle control (stop/shutdown)  
   `evidence/screenshots/06-ec2-stop-control.png`
7. SSH session validation (`uptime` + clean logout)  
   `evidence/screenshots/07-ssh-validation.png`

## Redaction & safety
Sensitive details are intentionally redacted for public sharing (account identifiers, public IPs, usernames). No secrets or key material are stored in this repository. See `docs/redaction-notes.md`.

## How to run this lab
Start here: **`RUNBOOK.md`**
