# Entra Group Inventory

## Purpose

This document captures the group inventory baseline for the Microsoft Entra ID tenant used in this portfolio lab.

The purpose is to understand the current group structure before implementing access controls, Conditional Access, Privileged Identity Management, Identity Governance, Microsoft 365 administration, or automation.

## Why Group Inventory Matters

Groups are commonly used to manage access, apply policies, assign licenses, organize users, and support collaboration.

A group inventory helps answer questions such as:

- How many groups exist?
- Which groups are security groups?
- Which groups are Microsoft 365 groups?
- Which groups are synced from Active Directory?
- Which groups are cloud-only?
- Are any groups role-assignable?
- Are department-based groups present?
- Are groups being used consistently?

## Group Inventory Summary

| Inventory Item | Count / Status | Notes |
|---|---|---|
| Total groups | 26 | Count shown in Microsoft Entra admin center |
| Security groups | 20 | Used for access control and policy targeting |
| Microsoft 365 groups | 5 | Used for Microsoft 365 collaboration workloads |
| Synced groups | 16 | Groups synchronized from on-premises Active Directory |
| Cloud-only groups | 10 | Groups created directly in Microsoft Entra ID |
| Dynamic groups | 1 | Rule-based group membership present |
| Role-assignable groups | To be reviewed | Requires additional review |
| Department-based groups | Present | Department-based group names observed |

## Group Type Definitions

| Group Type | Description | Common Use |
|---|---|---|
| Security group | Group used to assign access to resources | Access control, policy targeting, app assignment |
| Microsoft 365 group | Collaboration group tied to Microsoft 365 services | Teams, SharePoint, Outlook, Planner |
| Synced group | Group created in Active Directory and synchronized to Entra ID | Hybrid identity access structure |
| Cloud-only group | Group created directly in Microsoft Entra ID | Cloud-native access and administration |
| Dynamic group | Group with membership based on rules | Automated membership by user or device attributes |
| Role-assignable group | Group that can be assigned Microsoft Entra roles | Privileged access management |

## Group Review Process

The group inventory will be reviewed using the Microsoft Entra admin center.

Review areas include:

- All groups
- Group type
- Membership type
- Source
- Security enabled groups
- Microsoft 365 groups
- Synced groups
- Cloud-only groups
- Role-assignable groups, if present

## Source of Authority Notes

For synced groups, Active Directory should generally be treated as the source of authority.

Cloud-only groups are managed directly in Microsoft Entra ID.

| Task | Correct Management Location |
|---|---|
| Create synced security group | Active Directory |
| Modify synced group membership | Active Directory |
| Review synced group in cloud | Microsoft Entra admin center |
| Create cloud-only security group | Microsoft Entra admin center |
| Create Microsoft 365 group | Microsoft 365 admin center or Entra admin center |
| Review group usage | Microsoft Entra admin center / Microsoft 365 admin center |

## Screenshot Evidence

| Screenshot | Purpose |
|---|---|
| 06-groups-all-overview-sanitized.png | Shows group inventory overview |
| 07-groups-security-filter-sanitized.png | Shows security groups |
| 08-groups-m365-filter-sanitized.png | Shows Microsoft 365 groups |
| 09-groups-synced-filter-sanitized.png | Shows synced groups, if present |

## Screenshot Privacy Notes

Do not expose:

- Full tenant domain
- Group object IDs
- Sensitive group names
- Admin group membership details
- Private identifiers
- Any real production naming

## Initial Findings

- The tenant contains 26 total groups.
- Security groups are the most common group type, with 20 security groups observed.
- Microsoft 365 groups are present, with 5 groups observed.
- On-premises synchronized groups are present, with 16 groups observed.
- Cloud-only groups are present, with 10 groups observed.
- One dynamic group was observed.
- Department-based groups are present for lab scenarios.
- Further review is needed to confirm whether any role-assignable groups exist.

## Lessons Learned

- Group inventory helps identify how access and collaboration may be structured in the tenant.
- Security groups are commonly used for access control, app assignment, and policy targeting.
- Microsoft 365 groups support collaboration workloads such as SharePoint, Outlook, Teams, and Planner.
- Synced groups should generally be managed from Active Directory first.
- Cloud-only groups should be managed directly in Microsoft Entra ID.
- Dynamic groups can support automation by using rule-based membership.