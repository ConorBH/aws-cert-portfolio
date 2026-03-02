# Lab 06: S3 Block Public Access prevents public bucket policy

## Goal
- Prove that account-level **Block Public Access** prevents saving a public bucket policy.

## Cost / safety notes
- Free-tier friendly
- Intentionally attempt a public policy to validate the control; do not leave a public policy in place.

## Steps
1) Created a test bucket `ccp-bpa-test-001`.
2) Opened bucket -> Permissions -> Bucket policy -> Edit.
3) Attempted to save a policy allowing `Principal: "*"` for `s3:GetObject` on `arn:aws:s3:::<bucket>/*`.
4) Observed S3 refusing the save due to Block Public Access settings.

## What I observed / learned
- S3 Block Public Access overrides attempts to grant public access via bucket policy/ACLs.
- The “failure” to save is the expected/desired outcome.

## Evidence
- `02-labs/evidence/s3-test-bucket-created.png`
- `02-labs/evidence/s3-bpa-policy-blocked.png` (banner showing conflict with Block Public Access)

## Cleanup
- Ensured the bucket policy was not saved.