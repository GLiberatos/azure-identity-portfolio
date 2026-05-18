# Entra Tenant Overview

## Purpose

This document captures the high-level tenant overview for the Microsoft Entra ID environment used in this portfolio lab.

The purpose is to document tenant context before making identity, access, security, or governance changes.

## Tenant Summary

| Item | Current State |
|---|---|
| Tenant Type | Microsoft 365 E5 Developer tenant |
| Primary Domain Type | Default `.onmicrosoft.com` developer tenant domain |
| License | Microsoft Entra ID P2 |
| Identity Model | Hybrid identity |
| Directory Sync | Enabled |
| Sync Source | On-premises Active Directory Domain Services |
| Sync Target | Microsoft Entra ID |
| Authentication Method | Password Hash Sync |
| Seamless Single Sign-On | Enabled |
| Federation | Disabled |
| Pass-through Authentication | Disabled |
| Total Users | 72 |
| Total Groups | 26 |
| Total Applications | 7 |
| Total Devices | 2 |
| Azure Infrastructure Tenant | Separate personal Azure subscription / tenant |
| Production Data Used | No |

## Tenant Role in Portfolio

This tenant is used for identity and Microsoft 365 administration labs.

It will support future projects involving:

- Microsoft Entra ID users and groups
- Hybrid identity
- Conditional Access
- MFA
- Privileged Identity Management
- Identity Governance
- Microsoft 365 administration
- Intune / endpoint management
- PowerShell and Microsoft Graph automation

## Identity Source Overview

This tenant includes identities synchronized from an on-premises Active Directory lab.

High-level identity flow:

```text
Active Directory Domain Services
→ Microsoft Entra Connect / sync agent
→ Microsoft Entra ID
→ Microsoft 365 E5 Developer tenant
```

## Tenant Boundary Notes

This tenant is separate from the Azure subscription used for Azure infrastructure labs.

| Environment                       | Purpose                                                                |
| --------------------------------- | ---------------------------------------------------------------------- |
| Microsoft 365 E5 Developer tenant | Entra ID, Microsoft 365, Intune, and identity testing                  |
| Personal Azure subscription       | Azure infrastructure, budgets, networking, VMs, monitoring, and policy |

## Baseline Observations

| Observation | Notes |
|---|---|
| Directory synchronization is enabled | Microsoft Entra Connect sync is enabled |
| Last sync was recent | Last sync showed less than 1 hour ago during review |
| Password Hash Sync is enabled | Password Hash Sync is being used for hybrid sign-in |
| Seamless SSO is enabled | Seamless single sign-on showed enabled for 1 domain |
| Federation is disabled | Federation showed disabled |
| Pass-through Authentication is disabled | Pass-through Authentication showed disabled |
| Synced users exist | Users show `On-premises sync enabled = Yes` |
| Cloud-only users exist | Cloud-only filter showed 3 users |
| Tenant uses default developer domain | Public screenshots should sanitize domain details |
| Lab is hybrid identity focused | On-prem AD is the source for synced identities |

## Screenshot Evidence

| Screenshot                             | Purpose                               |
| -------------------------------------- | ------------------------------------- |
| 01-tenant-overview-sanitized.png       | Shows tenant overview context         |
| 02-directory-sync-status-sanitized.png | Shows directory synchronization state |

## Security and Privacy Notes

Do not expose the following in public screenshots:

- Tenant ID
- Full tenant domain
- User principal names
- Personal email addresses
- Sync service account names
- Private identifiers

## Initial Findings

- The tenant is a Microsoft 365 E5 Developer tenant.
- The tenant uses the default `.onmicrosoft.com` developer domain.
- Microsoft Entra Connect sync is enabled.
- Password Hash Sync is enabled.
- Seamless Single Sign-On is enabled.
- Federation and Pass-through Authentication are disabled.
- The tenant is being used for hybrid identity and Microsoft 365 administration labs.

## Lessons Learned

To be completed after validation.