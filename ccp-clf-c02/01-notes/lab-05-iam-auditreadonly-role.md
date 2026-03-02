# Lab 05: IAM role "AuditReadOnly" (SecurityAudit policy)

## Goal
- Create a read-only role for security review / audit use-cases (no access keys).

## Cost / safety notes
- Free-tier friendly
- Do not create long-lived keys

## Steps
1) Opened IAM -> Roles-> **Create role**.
2) Selected **Trusted entity: AWS account** and chose **This account**.
3) Attached AWS managed policy **SecurityAudit**.
4) Named the role `AuditReadOnly`.
5) Left permissions boundary unset (not needed for this lab).
6) Verified the role exists and the policy is attached.

## What I observed / learned
- Roles are assumed (temporary credentials) rather than static user keys.
- SecurityAudit provides broad visibility for assessing security posture.

## Evidence
- `02-labs/evidence/iam-role-auditreadonly-securityaudit.png`
