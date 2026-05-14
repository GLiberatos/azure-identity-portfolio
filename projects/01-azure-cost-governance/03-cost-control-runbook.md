# Azure Cost Control Runbook

## Purpose

This runbook documents the cost control setup for my Azure portfolio lab subscription.

The goal is to reduce the risk of unexpected Azure spending while building hands-on infrastructure labs.

## Business Problem

Azure resources can create unexpected costs if budgets, alerts, and cleanup practices are not established early.

A cloud engineer should understand how to monitor spending before deploying billable infrastructure.

## Cost Control Strategy

This lab uses a monthly Azure credit subscription for learning and development.

To reduce cost risk, I configured a portfolio budget below the full monthly credit amount.

| Item | Value |
|---|---|
| Monthly Azure credit | $100 |
| Portfolio working budget | $50 |
| Budget reset period | Monthly |
| Budget scope | Personal Azure subscription |
| Budget name | budget-portfolio-lab-monthly-050 |

## Alert Thresholds

| Alert | Threshold | Purpose |
|---|---:|---|
| Alert 1 | 25% | Early usage awareness |
| Alert 2 | 50% | Midpoint review |
| Alert 3 | 75% | High usage warning |
| Alert 4 | 90% | Cleanup / stop-and-review point |

## Spending Limit Review

The subscription spending limit should not be removed if it is available.

The spending limit provides additional protection for credit-based subscriptions.

## Implementation Steps

1. Opened the Azure portal.
2. Selected the personal Azure subscription used for infrastructure labs.
3. Reviewed subscription cost management options.
4. Created a monthly Azure budget.
5. Set the budget amount to $50.
6. Configured actual cost alert thresholds.
7. Added an email recipient for budget alerts.
8. Captured sanitized screenshots for documentation.

## Validation

Validation confirmed:

- Budget exists in the Azure subscription
- Budget amount is set to $50
- Budget reset period is monthly
- Actual cost alert thresholds are configured at 25%, 50%, 75%, and 90%
- Alert recipient is configured
- Screenshots were sanitized before being added to GitHub

## Governance Notes

This budget does not replace good cleanup habits.

Before and after each Azure infrastructure lab, resources should be reviewed and deleted when no longer needed.

## Framework Mapping

| Framework / Concept | Related Control | How This Project Supports It |
|---|---|---|
| Azure Well-Architected Framework | Cost Optimization | Establishes budget visibility before deploying resources |
| Cloud Governance | Cost control | Defines spending boundaries and alerting |
| Operational Excellence | Monitoring | Creates alerts for cost events |
| Accountability | Ownership and review | Supports review of lab spending and cleanup |

## Lessons Learned

- Azure budgets provide cost visibility but should not be treated as a hard spending stop.
- Budget alerts help identify spending trends before the full monthly credit is consumed.
- A working budget below the full monthly credit provides a safety buffer.
- Screenshots should be sanitized before publishing to a public GitHub repository.