# Lab 03: S3 Block Public Access (account-level)

## Goal
- Enable **Block all public access** at the **account level** for Amazon S3.

## Cost / safety notes
- Free-tier friendly
- This is a preventative control
- This setting overrides bucket/object policies that attempt to grant public access.

## Steps
1) Opened Amazon S3 -> **Block Public Access settings for this account**.
2) Clicked **Edit**.
3) Enabled **Block all public access** (all related checkboxes on).
4) Saved changes and confirmed the setting is **On**.

## What I observed / learned
- Account-level Block Public Access is a strong “guard rail” that prevents accidental public exposure.

## Evidence
- `02-labs/evidence/s3-block-public-access-account.png`