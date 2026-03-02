# Lab 02: AWS Budget + email alerts

## Goal
- Create a small monthly **cost budget** and configure **email alerts** to prevent surprise spend during labs.

## Cost / safety notes
- Budgets are safe to create - alerts are not instantaneous.
- Keep limits small while learning.

## Steps
1) Opened Billing/Cost Management → **Budgets** → **Create budget**.
2) Created a **Monthly** budget with a fixed limit of **$5.00**.
3) Set scope to **All AWS services**.
4) Created **Actual cost** alerts at:
   - **80%** of budget (warning)
   - **100%** of budget (critical)
5) Verified the budget shows **Healthy/OK** and alerts are listed.

## What I observed / learned
- Alerts trigger when spend crosses thresholds - this acts as an early warning system for lab mistakes.
- Keeping a low budget limit is a practical safety rail while learning.

## Evidence
- `02-labs/evidence/budget-overview.png` (budget summary)
- `02-labs/evidence/budget-alerts.png` (80% + 100% alerts)
