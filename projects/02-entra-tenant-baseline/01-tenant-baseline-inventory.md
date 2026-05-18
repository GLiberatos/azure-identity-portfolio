# Entra Tenant Baseline Inventory

## Purpose

This document captures the current baseline state of the Microsoft Entra ID tenant used for portfolio identity labs.

The purpose of this inventory is to document the environment before making changes to users, groups, roles, Conditional Access, PIM, Identity Governance, or automation.

## Environment Summary

| Item | Current State |
|---|---|
| Tenant Type | Microsoft 365 E5 Developer tenant |
| Primary Domain Type | Default `.onmicrosoft.com` developer tenant domain |
| On-Premises Directory | Active Directory Domain Services |
| On-Premises Platform | VMware Workstation lab VM |
| Domain Controller | Windows Server domain controller |
| Directory Sync | Enabled |
| Sync Target | Microsoft Entra ID |
| Authentication Method | Password Hash Sync |
| Identity Model | Hybrid identity lab |

## Hybrid Identity Design

This lab includes an on-premises Active Directory environment synchronized to Microsoft Entra ID.

High-level design:

```text
Active Directory Domain Services
→ Microsoft Entra Connect / sync agent
→ Microsoft Entra ID
→ Microsoft 365 E5 Developer tenant
```

## Identity Types

| Identity Type    | Created In                       | Managed From         | Notes                                                |
| ---------------- | -------------------------------- | -------------------- | ---------------------------------------------------- |
| Cloud-only users | Microsoft Entra ID               | Entra admin center   | Used for cloud-native identity testing               |
| Synced users     | Active Directory Domain Services | On-premises AD first | Synced to Entra ID through directory synchronization |

## Source of Authority Notes

For synced users, the on-premises Active Directory environment is the primary source for many identity attributes.

This means user changes should generally be made in Active Directory first and then synchronized to Microsoft Entra ID.

Examples of synced identity management tasks:

| Task                          | Primary Location             |
| ----------------------------- | ---------------------------- |
| Create synced lab user        | Active Directory             |
| Modify synced user department | Active Directory             |
| Disable synced user           | Active Directory             |
| Review synced user in cloud   | Microsoft Entra admin center |
| Create cloud-only test user   | Microsoft Entra admin center |

## Current OU Sync Scope

The current lab sync design uses a selected OU structure with departmental sub-OUs.

Current lab departments include:

- Engineering
- Finance
- HR
- IT
- Operations
- Sales

## User Inventory Review

To be completed during the tenant baseline review.

Planned review items:

- Total users
- Cloud-only users
- Synced users
- Guest users
- Disabled users
- Administrative users
- Test users by department

## Group Inventory Review

To be completed during the tenant baseline review.

Planned review items:

- Security groups
- Microsoft 365 groups
- Synced groups
- Cloud-only groups
- Department-based groups
- Role-assignable groups, if present

## Administrative Role Review

To be completed during the tenant baseline review.

Planned review items:

- Global Administrator accounts
- Privileged Role Administrator accounts
- User Administrator accounts
- Groups Administrator accounts
- Security Administrator accounts
- Authentication Administrator accounts
- Global Reader accounts

## Initial Security Notes

The following security principles will be used during this project:

- Avoid unnecessary Global Administrator use
- Document privileged roles
- Separate cloud-only and synced identities
- Avoid exposing tenant names, usernames, domains, or IDs in public screenshots
- Use test accounts only
- Avoid production data

## Screenshot Plan

Screenshots should be sanitized before being published.

Planned screenshots:

| Screenshot                               | Purpose                         |
| ---------------------------------------- | ------------------------------- |
| Tenant overview                          | Shows tenant baseline context   |
| Users list filtered for synced users     | Shows hybrid identity state     |
| Users list filtered for cloud-only users | Shows cloud-only identity state |
| Groups overview                          | Shows group baseline            |
| Roles and administrators overview        | Shows admin role baseline       |

Do not expose:

- Tenant ID
- Full tenant domain
- User principal names
- Personal email addresses
- Sync service account names
- Real names if not needed
- Private identifiers

## Framework Mapping

| Framework / Concept    | Related Control          | How This Project Supports It                                        |
| ---------------------- | ------------------------ | ------------------------------------------------------------------- |
| Zero Trust             | Verify explicitly        | Establishes identity baseline before access policies are configured |
| Least Privilege        | Role review              | Begins documenting privileged access assignments                    |
| Identity Governance    | User and group inventory | Establishes baseline for future access reviews                      |
| Operational Excellence | Documentation            | Creates repeatable identity documentation                           |
| Security               | Account visibility       | Identifies cloud-only and synced identity types                     |

## Lessons Learned

To be completed after validation.
