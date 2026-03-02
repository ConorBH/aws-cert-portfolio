# Lab 01: Root account MFA (AWS Console)

## Goal
- Enable MFA for the AWS **root user** (or confirm it is enabled).
- Capture evidence for baseline account security.

## Steps
1) Signed into the AWS Console as the **root user**.
2) Opened **Security credentials** from the account menu.
3) Under **Multi-factor authentication (MFA)**, assigned an MFA device.
4) Used an authenticator method to complete MFA enrolment.
5) Verified the MFA section shows **enabled**.

## What I observed / learned
- Root user has full control; MFA is a basic, high-impact control to reduce account takeover risk.
- AWS supports multiple MFA devices (useful for backup/recovery).

## Evidence
- `02-labs/evidence/root-mfa-enabled.png`
