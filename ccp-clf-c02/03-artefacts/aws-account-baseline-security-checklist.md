# AWS Account Baseline Security Checklist (CCP-level)

**Status:** In progress (updated: 2026-03-02). Only checked items have been implemented.
This is a lightweight baseline I applied to a new AWS account to reduce common misconfiguration risk while learning AWS.

## 1) Root account protections
- [x] Root MFA enabled (root is high-impact; MFA reduces takeover risk)
- [ ] (Optional) Add a second MFA device as backup
- [ ] Root user used only for account-level tasks (day-to-day via roles)

**Evidence**
- `ccp-clf-c02/02-labs/evidence/root-mfa-enabled.png`

## 2) Billing safety rails
- [x] Monthly budget created ($5)
- [x] Alerts configured:
  - [x] Actual cost > 80%
  - [x] Actual cost > 100%
- [ ] (Optional) Forecasted cost alert at 100%

**Evidence**
- `ccp-clf-c02/02-labs/evidence/budget-overview.png`
- `ccp-clf-c02/02-labs/evidence/budget-alerts.png`

## 3) S3 exposure prevention
- [x] Account-level **Block Public Access** enabled (guard rail against accidental public buckets)
- [x] Validated the control by attempting (and failing) to save a public bucket policy

**Evidence**
- `ccp-clf-c02/02-labs/evidence/s3-block-public-access-account.png`
- `ccp-clf-c02/02-labs/evidence/s3-bpa-policy-blocked.png`

## 4) Logging baseline (audit trail)
- [x] CloudTrail enabled (management events)
- [x] Multi-region trail enabled
- [x] Log file validation enabled (integrity checking)
- [ ] Data events not enabled (kept off initially to reduce noise/cost)

**Evidence**
- `ccp-clf-c02/02-labs/evidence/cloudtrail-validation-enabled.png`
- `ccp-clf-c02/02-labs/evidence/cloudtrail-events-settings.png`

## 5) Read-only security review access (no long-lived keys)
- [x] Created an audit role (`AuditReadOnly`) with AWS managed `SecurityAudit` policy
- [ ] (Optional) Require MFA to assume the role via trust policy condition

**Evidence**
- `ccp-clf-c02/02-labs/evidence/iam-role-auditreadonly-securityaudit.png`

## Why this matters (in SOC/IR terms)
- **MFA + least privilege** reduces account takeover and privilege abuse.
- **Budgets** catch unexpected spend from misclicks or misconfigured services early.
- **S3 Block Public Access** prevents the most common “oops, public bucket” scenario.
- **CloudTrail** provides the core audit trail for investigations (“who did what, when, from where”).
- **Audit role** supports review/triage workflows without using root or distributing static credentials.

## Next steps (after CCP)
- Add CloudWatch Log Group integration for CloudTrail and basic alerting rules.
- Add IAM Access Analyzer checks and tighten trust policies.
- Start IaC (Terraform) for repeatable baselines (SAA phase).