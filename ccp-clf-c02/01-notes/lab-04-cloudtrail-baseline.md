# Lab 04: CloudTrail baseline trail + log file validation

## Goal
- Create/enable an account trail to log management activity.
- Enable **log file validation** (integrity checking) for stronger auditability.

## Cost / safety notes
- Logs go to S3; keep scope simple:
  - Management events: ON (baseline)
  - Data events: OFF (avoid noise/cost for now)

## Steps
1) Opened CloudTrail -> created/confirmed a trail named `account-trail`.
2) Verified **Trail logging: Logging**.
3) Confirmed this is a **multi-region** trail.
4) Enabled **Log file validation** on the trail.
5) Verified management events are collected; data events are not configured.

## What I observed / learned
- CloudTrail provides the “who did what, when, from where” audit trail for AWS API activity.
- Log file validation improves integrity assurances for delivered log files.

## Evidence
- `02-labs/evidence/cloudtrail-validation-enabled.png` (logging + multi-region + validation enabled)
- `02-labs/evidence/cloudtrail-events-settings.png` (management events / data events status)
