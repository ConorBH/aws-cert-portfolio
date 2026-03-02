# IAM (Identity and Access Management) — One-Pager

## What it is (plain English)
- AWS’s system for controlling **who/what can do what** in an AWS account.
- It’s how you define identities (users/roles) and permissions (policies).

## What it’s for
- Enforcing **least privilege** so people/services only have the access they need.
- Separating duties (admin vs read-only vs deployment roles).
- Reducing blast radius if credentials are compromised.

## Core concepts / components
- **Root user**: all-powerful account owner identity. Should be locked down and rarely used.
- **IAM User**: a person identity inside the account (ideally minimal use; prefer SSO).
- **IAM Role**: an identity **assumed** temporarily (best practice for services + humans).
- **Policies**: JSON permission documents (Allow/Deny) attached to users/roles/groups/resources.
- **Groups**: collections of users with shared permissions (legacy but still common).
- **MFA**: second factor for sign-in (especially for root / privileged identities).
- **STS (temporary creds)**: short-lived credentials issued when assuming roles.

## Security “gotchas” (what goes wrong)
- Root user used day-to-day or without MFA.
- Long-lived access keys created and never rotated.
- Wildcard permissions (`Action:"*"` / `Resource:"*"`) on human identities.
- Roles that can be assumed from anywhere without strong conditions.
- “Permission creep” (people keep getting access but never lose it).

## SOC / IR relevance (what you’d look for)
- Signs of compromised credentials:
  - Unusual **console login** activity (especially root)
  - Suspicious **AssumeRole** events (unexpected role assumption)
  - New access keys created unexpectedly
  - Policy changes that broaden access
- Typical investigation questions:
  - *Which identity did it? From where? What permissions changed? What actions followed?*

## Services / keywords to remember
- IAM, MFA, Roles, Policies, Least Privilege, STS, AssumeRole, Access Keys