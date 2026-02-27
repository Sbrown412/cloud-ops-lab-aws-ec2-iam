# Runbook — AWS EC2 + IAM Lab

## Purpose
Provide a repeatable procedure to:
1) verify IAM least-privilege enforcement,
2) operate an EC2 instance safely,
3) validate remote access,
4) shut down cleanly to avoid accidental costs.

## Preconditions
- AWS account access via Admin group
- SSH key pair stored locally (not in repo)
- Screenshots redacted for public sharing

## Procedure

### A) IAM Verification (Least Privilege)
1. Confirm IAM groups exist (Admins, Sandbox Users).
2. Confirm restricted policy is attached to Sandbox Users.
3. Validate enforcement:
   - Attempt a restricted action as Sandbox user.
   - Confirm **AccessDenied** appears (expected).
4. Confirm Admin group retains required access for maintenance.

**Success criteria**
- Sandbox user cannot perform restricted actions.
- Admin user can manage resources as needed.

### B) EC2 Lifecycle: Start / Validate / Operate
1. Confirm EC2 instance is in expected state (running or stopped).
2. If starting:
   - Start instance and wait for status checks to pass.
3. Connect via SSH (key-based auth).
4. Run baseline health checks:
   - `uptime`
   - (optional) `df -h` (disk), `free -h` (memory)
5. Document any changes made during session.

**Success criteria**
- SSH connection successful.
- Baseline checks show healthy state (normal load, expected uptime).

### C) Shutdown / Cost Safety
1. End SSH session cleanly (`exit`).
2. Stop instance when lab is not actively in use.
3. Confirm no unexpected resources were created (volumes, IPs, paid add-ons).
4. Update `CHANGELOG.md` with any meaningful changes.

**Success criteria**
- Instance is stopped (or terminated if cleaning up).
- No orphaned/billable resources remain.

## Troubleshooting (Quick)
- SSH fails: confirm inbound SSH rule and your current public IP; confirm correct username/key.
- AccessDenied for admin tasks: confirm you are using the Admin group account, not sandbox user.