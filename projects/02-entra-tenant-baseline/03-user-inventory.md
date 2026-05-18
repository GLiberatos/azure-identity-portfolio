# Entra User Inventory

## Purpose

This document captures the user inventory baseline for the Microsoft Entra ID tenant used in this portfolio lab.

The purpose is to understand the current user population before implementing security controls, role assignments, Conditional Access, Identity Governance, or automation.

## Why User Inventory Matters

A user inventory helps answer important identity administration questions:

- How many users exist?
- Which users are cloud-only?
- Which users are synced from on-premises Active Directory?
- Are there guest users?
- Are there disabled users?
- Which accounts may be administrative or service-related?
- Which identities require special handling?

## User Inventory Summary

| Inventory Item | Count / Status | Notes |
|---|---|---|
| Total users | 72 | Count shown in Microsoft Entra admin center |
| Cloud-only users | 3 | Users with `On-premises sync enabled = No` |
| Synced users | 69 | Users with `On-premises sync enabled = Yes` |
| Guest users | 1 | One guest account observed in cloud-only filtered view |
| Disabled users | To be reviewed | Requires account enabled/disabled filter review |
| Administrative users | To be reviewed | Requires roles and administrators review |
| Test users by department | To be reviewed | Engineering, Finance, HR, IT, Operations, Sales |

## Identity Type Definitions

| Identity Type | Description | Management Location |
|---|---|---|
| Cloud-only user | User created directly in Microsoft Entra ID | Entra admin center |
| Synced user | User created in Active Directory and synchronized to Entra ID | Active Directory first |
| Guest user | External user invited into the tenant | Entra admin center / collaboration workflow |
| Administrative user | User assigned privileged administrative access | Entra roles and administrators |

## User Review Process

The user inventory was reviewed using the Microsoft Entra admin center.

Review areas included:

- All users
- User type
- On-premises sync enabled
- Cloud-only users
- Synced users
- Guest users
- Administrative accounts to be reviewed later
- Disabled users to be reviewed later

## Source of Authority Notes

Synced users should generally be managed from Active Directory first.

Cloud-only users should be managed directly from Microsoft Entra ID.

| Task | Correct Management Location |
|---|---|
| Create synced lab user | Active Directory |
| Modify synced user attributes | Active Directory |
| Disable synced user | Active Directory |
| Create cloud-only test user | Microsoft Entra admin center |
| Review synchronized user state | Microsoft Entra admin center |

## Screenshot Evidence

| Screenshot | Purpose |
|---|---|
| 03-users-all-overview-sanitized.png | Shows user inventory overview |
| 04-users-synced-filter-sanitized.png | Shows synced users |
| 05-users-cloud-only-filter-sanitized.png | Shows cloud-only users |

## Screenshot Privacy Notes

Do not expose:

- Full real names
- User principal names
- Email addresses
- Tenant domains
- Object IDs
- Sync service accounts
- Private identifiers

## Initial Findings

- The tenant contains 72 total users.
- Most users appear to be synchronized from on-premises Active Directory.
- The synced user filter showed 69 users.
- The cloud-only user filter showed 3 users.
- One guest account was observed during the cloud-only user review.
- Microsoft Entra Connect sync is enabled.
- Password Hash Sync is enabled.
- Synced users show `On-premises sync enabled = Yes`.
- Further review is needed for disabled users and administrative users.

## Lessons Learned

- A tenant baseline helps separate cloud-only identities from synced identities.
- Synced identities should generally be managed from Active Directory first.
- Cloud-only accounts should be reviewed separately because they are managed directly in Microsoft Entra ID.
- Guest accounts should be tracked because they represent external access into the tenant.
- User inventory is required before building Conditional Access, PIM, Identity Governance, or automation labs.