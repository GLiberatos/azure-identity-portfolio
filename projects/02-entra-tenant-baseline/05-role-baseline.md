# Entra Role Baseline

## Purpose

This document captures the administrative role baseline for the Microsoft Entra ID tenant used in this portfolio lab.

The purpose is to understand privileged access before implementing Conditional Access, Privileged Identity Management, Identity Governance, security monitoring, or automation.

## Why Role Review Matters

Administrative roles control who can manage identity, security, applications, users, groups, and tenant settings.

A role baseline helps answer questions such as:

- Which accounts have privileged access?
- How many Global Administrators exist?
- Are privileged roles assigned only when needed?
- Are admin roles separated by responsibility?
- Are there accounts that should be reviewed before future security controls?
- Are role assignments aligned with least privilege?

## Role Baseline Summary

| Role | Count / Status | Notes |
|---|---|---|
| Global Administrator | 1 | Highest privilege tenant role; active direct assignment observed |
| Conditional Access Administrator | 1 | Privileged role used to manage Conditional Access policies |
| Security Administrator | 1 | Privileged role used to manage security-related settings |
| Privileged Authentication Administrator | 1 | Privileged role used to manage authentication methods for users |
| Attribute Assignment Administrator | 1 | Role assignment observed during review |
| Attribute Definition Administrator | 1 | Role assignment observed during review |
| Insights Administrator | 1 | Role assignment observed during review |
| Microsoft Entra Joined Device Local Administrator | 1 | Role assignment observed during review |
| Privileged Role Administrator | To be reviewed | Manages role assignments and PIM-related role tasks |
| User Administrator | To be reviewed | Manages users and some user settings |
| Groups Administrator | To be reviewed | Manages groups and group settings |
| Authentication Administrator | To be reviewed | Manages authentication methods for users |
| Global Reader | To be reviewed | Read-only visibility across many admin areas |
| Hybrid Identity Administrator | To be reviewed | Manages hybrid identity-related settings |

## Role Review Process

The role baseline will be reviewed using the Microsoft Entra admin center.

Review areas include:

- Roles and administrators
- Assigned role members
- Privileged roles
- Read-only roles
- Hybrid identity roles
- Administrative accounts
- Service or sync-related accounts, if visible

## Least Privilege Notes

Least privilege means assigning only the permissions required to perform a task.

For this lab, privileged roles should be reviewed carefully before future configuration work.

General principles:

- Avoid unnecessary Global Administrator use
- Prefer task-specific admin roles where possible
- Use read-only roles for review activities where possible
- Document privileged assignments
- Use PIM in a future project to reduce standing privilege
- Protect admin accounts with strong authentication controls

## Administrative Account Notes

Administrative accounts should be reviewed separately from standard user accounts.

Possible admin account types:

| Account Type | Purpose |
|---|---|
| Break-glass account | Emergency access account |
| Cloud admin account | Cloud-only administrative account |
| Synced admin account | Admin account synchronized from Active Directory |
| Service or sync account | Used by synchronization or service integrations |
| Test admin account | Used for lab role testing |

## Screenshot Evidence

| Screenshot | Purpose |
|---|---|
| 10-roles-admins-overview-sanitized.png | Shows selected administrative roles and assignment counts |
| 11-global-admin-role-sanitized.png | Shows Global Administrator active assignment count |

## Screenshot Privacy Notes

Do not expose:

- User principal names
- Tenant domain
- Tenant ID
- Object IDs
- Admin account names if sensitive
- Service account names
- Personal email addresses

## Initial Findings

- One active Global Administrator assignment was observed.
- The Global Administrator assignment appears to be direct and permanent.
- Several privileged administrative roles have assignments.
- Conditional Access Administrator, Security Administrator, and Privileged Authentication Administrator were observed with assignments.
- Additional role review is needed for User Administrator, Groups Administrator, Global Reader, Hybrid Identity Administrator, and Privileged Role Administrator.
- Future PIM work should review whether privileged roles can be changed from permanent active assignments to eligible assignments.

## Framework Mapping

| Framework / Concept | Related Control | How This Project Supports It |
|---|---|---|
| Least Privilege | Role review | Identifies privileged role assignments before changes |
| Zero Trust | Verify explicitly | Establishes privileged identity visibility |
| Identity Governance | Access review preparation | Creates baseline for future role reviews |
| Security | Privileged access visibility | Helps identify high-risk admin roles |
| Operational Excellence | Documentation | Creates repeatable role review documentation |

## Lessons Learned

- Administrative role review is required before implementing security controls or governance.
- Global Administrator is the highest privilege tenant role and should be limited.
- Permanent privileged assignments increase risk and should be reviewed.
- A role baseline helps prepare for future Privileged Identity Management work.
- Least privilege means assigning task-specific roles instead of relying on Global Administrator.